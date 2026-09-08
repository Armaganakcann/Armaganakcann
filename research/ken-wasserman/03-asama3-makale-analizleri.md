# 3. AŞAMA — Makale Analizleri

Her makale için **üç kategori kesin olarak ayrılmıştır:**

- 📄 **Makalede doğrudan belirtilen bulgular** — yazarların yazdığı
- ⚠️ **Yazarların açıkça belirttiği sınırlamalar** — yazarların kendi ifadeleri
- 🔍 **Benim analizimden çıkan olası araştırma boşlukları** — yazarların söylemediği, benim çıkarımım

---

# 3.1 — Generating Medical Image Counterfactuals using Causal Explanations
**arXiv:2609.02697** · Kelly, Yaacov, Blake, Beckers, Chockler · King's College London + UCL · 2 Eylül 2026
**Kanıt seviyesi: 🟢 A** — Ken bunu 3 Eyl 2026'da paylaştı, ertesi gün video yayınladı.

Bu, **kullanıcının bilgisayarlı görü / segmentasyon geçmişiyle en doğrudan kesişen makale** ve Ken'in en yeni tıbbi-görüntüleme paylaşımı. Bu yüzden en ayrıntılı analiz burada.

### 1. Çözülmeye çalışılan temel problem
Tıbbi görüntü sınıflandırıcıları yüksek performans gösteriyor ama klinik kullanımları açıklanabilirlik eksikliğiyle sınırlı. Counterfactual görüntüler ("bu görüntü, sınıflandırıcının kararını değiştirmesi için nasıl değişmeliydi?") bir denetim aracı sunuyor — ancak **mevcut tüm yöntemler bunu üretmek için GAN veya difüzyon modeli kullanıyor.** Bu, "bir kara kutuyu başka bir kara kutuyla açıklamak" anlamına geliyor: üretilen görüntünün sınıflandırıcının karar sınırını mı, üreticinin görüntü önselini mi, yoksa optimizasyon artefaktını mı yansıttığı ayırt edilemiyor.

### 2. Neden önemli
Yazarların gerekçesi: bir klinisyen ya da model denetçisi, sınıflandırıcının **nereye baktığını** değil, **kararını neyin değiştireceğini** bilmek zorunda. Ayrıca üretici modeller veri-yoğun ve eğitim seçimlerine duyarlı — tıbbi görüntülemede büyük ve iyi anotasyonlu veri setleri nadir.

Kritik kavramsal nokta (yazarların kendi ifadesi): *"Model denetimi için en bilgilendirici counterfactual, hedef sınıfın en gerçekçi görüntüsü değil, sınıflandırıcının kendisinin hedef sınıfa ait kabul ettiği YAKIN bir görüntüdür."* Klinik gerçekçilik burada bir önkoşul değil.

### 3. Veri setleri
| Veri seti | Detay |
|---|---|
| **Beyin MRI** | The Cancer Imaging Archive; 110 preoperatif düşük dereceli gliom (LGG) hastası, 5 ABD kurumundan; tüm görüntüler aksiyel kesit + FLAIR; 101'inde pre-kontrast, 104'ünde post-kontrast; hasta başına 20–88 kesit; **toplam 3.929 görüntü**, her biri 3 kanallı |
| **Cilt lezyonu** | ISIC arşivi; malign + benign; **1.250 görüntü**, yayın öncesi train/test ayrımı yapılmış |

### 4. Örneklem
Değerlendirmeye **sınıflandırıcının negatif tahmin ettiği tüm görüntüler** alındı — hem gerçek negatifler hem yanlış negatifler. Gerekçe: klinisyen açıklamayı ground truth henüz belli değilken ister.
- Beyin MRI: **560 test görüntüsü**
- ISIC: **277 test görüntüsü**
- Veri hasta düzeyinde bölündü (%80 eğitim / %20 test) — *veri sızıntısına karşı doğru yaklaşım.*

### 5. Yöntemler
Yeni bir üretici model **eğitilmiyor.** Akış:
1. Sağlıklı sınıflanmış görüntü `x` alınır
2. L2 mesafesine göre en yakın pozitif (hastalıklı) görüntü `p'` bulunur
3. `p'` için **önceden hesaplanmış nedensel açıklama** alınır
4. Açıklamadaki piksel değerleri toplanır, tekilleştirilir, sıralanır
5. `x` üzerinde seçilen konuma (varsayılan: `p'`deki anormalliğin ağırlık merkezi; klinisyen de seçebilir) bir maske uygulanır ve maske altındaki değerler adım adım `V'p`ye yaklaştırılır
6. Sınıflandırıcı sorgulanır; sınıf değişirse SLIC segmentasyonuyla yumuşatma yapılıp döndürülür

Karmaşıklık: `O(|M| × |V|)`. Deterministik, ek model eğitimi yok, kullanıcı tanımlı ROI içinde kontrollü düzenleme.

### 6. Kullanılan AI / ML yöntemleri
- **ReX** — gerçek nedensellik (actual causality) teorisine dayalı XAI aracı. Görüntüyü 4 süper-piksele böler, kombinasyonları baseline değerle maskeler, sınıfı koruyan kombinasyonlara nedensel sorumluluk dağıtır, özyinelemeli daraltır. Model çağrı sayısı: `O(2^s · n · N)`.
- **MSPS (Minimal Sufficient Pixel Set)** = yeterli açıklama; **Complete Explanation** = hem yeterli hem gerekli, minimal.
- Sınıflandırıcılar (yeniden eğitilmedi): beyin MRI için **ResNet50** tabanlı CNN; ISIC için **VGG** tabanlı dikkat mekanizmalı CNN.
- Karşılaştırma: **GANterfactual** (GAN), **MoPaDi** (difüzyon), ve naif yamalama (NSE/NCE).
- Metrikler: L1, L2, SSIM, **LPIPS**; "mesafe-kısıtlı başarı" kriteri: `success(x,x',t) = I[N(x)≠N(x') ∧ d(x,x')<t]`. Eşik: veri setinin ikili mesafe dağılımının **99. persentili.**

### 7. 📄 En önemli sonuçlar (makalede doğrudan belirtilen)
- **Beyin MRI:** Complete Explanation (CE) yaklaşımı düşük mesafe eşiklerinde diğerlerini geçti — **LPIPS 0,25 ve SSIM 0,2 eşiğinde %85 başarı.** L1/L2 metriklerinde beyin MRI için hiçbir GAN counterfactual'ı maksimum eşiğin altında kalmadı (başarı oranı 0).
- **ISIC cilt lezyonu:** CE yine düşük eşiklerde en iyi — **LPIPS 0,48 ve SSIM 0,21 eşiğinde %67 başarı.** Yüksek eşiklerde NCE/GAN/DM daha yüksek başarı gösteriyor, **ama bu yalnızca görüntüyü büyük ölçüde değiştirerek** — yani açıklama değeri düşerek.
- 🔥 **En çarpıcı bulgu:** GAN yaklaşımı, orijinal veri dağılımından belirgin biçimde farklı ama **birbirine çok benzeyen** counterfactual'lar üretti (ikili mesafe dağılımında keskin tepe). Yazarların yorumu: **GAN bir kestirme (shortcut) öğrenmiş** — tüm görüntüleri neredeyse aynı counterfactual'a dönüştürüyor. Ayrıca bunun, **orijinal sınıflandırıcıdaki kestirme öğrenmeyle şiddetlenmiş olabileceğini** söylüyorlar; bu, veri-kıt rejimlerde eğitilen tıbbi modellerde yaygın.
- Tüm nedensel yaklaşımlar (SE, CE, NSE, NCE) orijinal veri setinin ikili mesafe dağılımını korudu.
- Şekil 1'deki örnek: model bir beyin MRI'ını "tümör yok" olarak sınıflandırıyor; **oysa tümör var** (insan anotasyonuyla gösteriliyor). Yöntem, sınıfı 'tümör'e çeviren yaklaşık-minimal değişikliği üretiyor.

### 8. ⚠️ Yazarların açıkça belirttiği sınırlamalar
Makalede ayrı bir "Limitations" bölümü (§4.5) var:
1. **Referans setinin çeşitliliğine bağımlılık.** Yöntem, geniş bir patolojik görünüm ve görüntüleme koşulu yelpazesi içeren referans veri setinden fayda görür. Bazı örüntüler yeterince temsil edilmemişse mevcut perturbasyon uzayı daralır.
2. Yazarlar bu bağımlılığın üretici yöntemlerinkinden **daha az kısıtlayıcı** olduğunu savunuyor (üretici modeller tam görüntü dağılımını öğrenmek zorunda).
3. Sonuç bölümünde açık bir gelecek işi: *"Future work will assess whether clinicians do indeed find our counterfactual images useful for auditing models."* — **Yani klinisyen değerlendirmesi HENÜZ YAPILMAMIŞ.**
4. Yöntem tasarım gereği **klinik olarak makul olmayan** counterfactual'lar üretebilir; yazarlar bunu bilinçli bir tercih olarak savunuyor (denetim ≠ patoloji simülasyonu).

### 9. 🔍 Benim analizimden çıkan olası araştırma boşlukları
*(Bunlar yazarların iddiası değil, benim çıkarımım.)*
- Yalnızca **iki** veri setinde ve **iki** mimaride (ResNet50, VGG) test edilmiş. Vision Transformer, ConvNeXt gibi mimarilerde nedensel sorumluluk dağılımı farklı davranabilir.
- ReX'in maliyeti `O(2^s · n · N)` — yüksek çözünürlüklü veya 3B hacimlerde ölçeklenebilirliği gösterilmemiş (3D-ReX ayrı bir çalışma olarak anılıyor ama burada değerlendirilmemiş).
- Yöntem **ikili sınıflandırma** üzerine kurulu. Çok sınıflı veya çok etiketli (ör. göğüs röntgeninde 14 patoloji) durumlarda "hedef sınıf" tanımı belirsiz.
- Segmentasyon modelleriyle hiç birleştirilmemiş. Segmentasyon maskesi ile nedensel açıklamanın **örtüşme oranı** ölçülmemiş — bu ölçülebilir ve doğrudan "model gerçekten patolojiye mi bakıyor?" sorusunu niceliksel hale getirir.
- GAN'ın kestirme öğrendiği bulgusu **gözlemsel**; bunun sınıflandırıcının kestirmesinden mi yoksa GAN'ın kendisinden mi kaynaklandığı ayrıştırılmamış.
- Dış veri seti (external validation) yok — her iki vaka çalışması da kendi veri seti içinde kalıyor.

---

# 3.2 — Adversarial prompt and fine-tuning attacks threaten medical LLMs
**Nature Communications 16:9011 (2025)** · Yang, Jin, Huang, Lu · NIH/NLM + Univ. of Maryland
**Kanıt seviyesi: 🟢 A** — Ken bu makaleyi kullanıcıya doğrudan gönderdi.

### 1. Problem
Sağlık uygulamalarına entegre edilen LLM'ler iki tür saldırıya açık: **(a) kötü niyetli talimat içeren prompt enjeksiyonu**, **(b) zehirlenmiş örneklerle ince ayar.** Bu, hassas tıbbi bağlamlarda zararlı sonuçlara yol açabilir.

### 2. Neden önemli
Ticari LLM'ler koruma bariyerlerine rağmen kandırılabiliyor. Genel alandaki saldırı çalışmaları genellikle tek tetikleyici kelimeyle basitleştirilmiş senaryolara dayanıyor; **karmaşık tıbbi ortamlarda tekrarlanabilirliği belirsizdi.**

### 3–4. Veri setleri ve örneklem
- **MIMIC-III** — gerçek dünya yoğun bakım hasta notları (ana deney)
- **PMC-Patients** — gerçek hasta özetleri (transfer edilebilirlik testi)
- Değerlendirme benchmark'ları: PubMedQA, MedQA
- Üç tıbbi görev: **hastalık önleme** (aşı rehberliği), **tanı** (tanısal test önerisi), **tedavi** (ilaç reçetesi)
- Saldırı hedefleri: aşılamayı caydırmak, tehlikeli ilaç kombinasyonları önermek, gereksiz tetkik (US, X-ray, MRI, BT) önermek

### 5–6. Yöntemler ve modeller
Test edilen modeller: **GPT-4o, GPT-4, GPT-3.5-turbo** (kapalı); **Llama-3.3 70B, Llama-2 7B/13B/70B, Vicuna-13B** (açık); **PMC-LLaMA-13B** (tıp alanına özel).

### 7. 📄 En önemli sonuçlar
Prompt tabanlı saldırı altında (baseline → saldırı):

| Davranış | GPT-4 | GPT-4o |
|---|---|---|
| Aşı önerisi | %100 → **%3,98** | %88,06 → **%6,47** |
| Tehlikeli ilaç kombinasyonu önerisi | %0,50 → **%80,60** | %1,00 → **%61,19** |
| Gereksiz ultrason | %20,90 → %80,10 | %43,28 → %93,53 |
| Gereksiz BT | %48,76 → %90,05 | %64,18 → %90,05 |
| Gereksiz X-ray | %32,34 → %63,18 | %60,20 → %89,55 |
| Gereksiz MRI | %24,88 → %88,56 | %29,85 → %93,53 |

- Saldırılar **model-agnostik**: hem açık hem kapalı kaynaklı modellerde çalışıyor.
- 🔥 **Zehirlenmiş veriyle ince ayar, kamuya açık tıbbi QA benchmark'larındaki performansı belirgin biçimde düşürmüyor** — yani standart değerlendirmeyle saldırı tespit edilemiyor.
- Zehirlenmiş örnek oranı arttıkça saldırı başarı oranı (ASR) tüm görevlerde tutarlı biçimde artıyor.
- 🔥 **Yeni modeller daha savunmalı değil.** Llama-3.3 70B, Llama-2 varyantlarından **daha savunmasız**; GPT-4o, GPT-4'ten daha dayanıklı değil.
- Saldırıya uğramış modellerin **ağırlıklarının normu daha büyük** → tespit için potansiyel bir yol.
- PMC-Patients üzerinde de benzer örüntü → saldırı **transfer edilebilir.**

### 8. ⚠️ Yazarların belirttiği sınırlamalar / gözlemler
- İnce ayar saldırısı **kayda değer miktarda zehirlenmiş örnek gerektiriyor.**
- Alan-spesifik PMC-LLaMA-13B, prompt tabanlı saldırıda çok farklı bir ASR gösterdi — sebebi modelin **verilen talimatları doğru ayrıştıramaması** (orijinal Llama'dan ince ayarlanmasının bir sonucu). Yani "kötü talimat izleme" tesadüfen bir savunma gibi görünüyor.
- Yazarlar ağırlık-normu gözlemini bir **azaltma stratejisi önerisi** olarak sunuyor, kanıtlanmış savunma olarak değil.
- ⚫ Makalenin resmî "Limitations" bölümünün tam metnini bu oturumda doğrulayamadım; yukarıdakiler Abstract/Introduction/Results'ta açıkça belirtilenlerdir.

### 9. 🔍 Olası araştırma boşlukları (benim çıkarımım)
- Savunma tarafı **boş**: makale saldırıyı gösteriyor, çalışan bir savunma sunmuyor.
- Ağırlık-normu sinyali yalnızca **beyaz kutu** erişimde işe yarar; API üzerinden erişilen kapalı modeller için kullanılamaz.
- Yalnızca metin. **Multimodal** (görüntü + metin) tıbbi sistemlerde aynı saldırıların davranışı test edilmemiş — Ken'in kullanıcıya önerdiği "retinal tarayıcı + telefon + AI doğrulama" senaryosu tam olarak bu boşluğa düşüyor.
- Üç göreve odaklanılmış; triyaj, aciliyet sınıflandırması gibi görevlerde etki bilinmiyor.
- Ajanik (multi-step, araç kullanan) sistemlerde saldırının nasıl yayıldığı incelenmemiş.

---

# 3.3 — Chreode: A Cell World Model
**arXiv:2605.28111** · Qiu, Zheng, Xu, Zhang, Ding, Long, Chen · UNC Chapel Hill + UT Austin + UPenn · 27 Mayıs 2026
**Kanıt seviyesi: 🟡 B** — İsim eşleşiyor, ama Ken'in "Chreode AI"ının bu olduğu **kesin değil** (bkz. Aşama 2 dikkat notu).

### 1–2. Problem ve önemi
Bir hücrenin gelişimsel sinyal veya genetik perturbasyon altında transkripsiyonel durumunu nasıl değiştireceğini tahmin etmek, in-silico biyolojinin ve AI Virtual Cell programının hesaplama çekirdeği. Mevcut yaklaşımlar ya zamanı atan statik kontrol→tedavi haritaları kuruyor ya da her veri seti için bağımsız çok-adımlı ODE/Schrödinger köprüsü çözüyor.

**Ölçek argümanı:** Modern bir in-silico perturbasyon taraması ~10⁴ hücre × 10³ perturbasyon × 10 zaman noktası ≈ **10⁸ (durum, eylem, zaman) üçlüsü** gerektiriyor. Mevcut üretici modeller sorgu başına 40–100 çözücü adımı harcıyor → tam tarama **10¹⁰ ileri geçiş.**

### 3–4. Veri setleri ve örneklem
- Ön eğitim: **2,4 milyon hücrelik fare embriyonik atlası**, 7 veri seti
- Değerlendirme: **Weinreb hematopoez**, **Veres adacık farklılaşması**, **Norman Perturb-seq**
- Ortolog kelime dağarcığı: **16.520 gen** (fare–insan)

### 5–6. Yöntemler
- **scVI** paylaşımlı kodlayıcı + **DiT** tabanlı dinamik omurga
- **Waddington artığı** ayrıştırması: potansiyel gradyanı (−∇U_θ, "yokuş aşağı akış") + antisimetrik dönme (S_θ z_t) + stokastik yayılım (σ⊙ε)
- Tek adımlı güncelleme; dağılımsal evrim çıkarım zamanından eğitim zamanına kaydırılıyor
- Karşılaştırma: PI-SDE, PRESCIENT, GEARS

### 7. 📄 Sonuçlar
- İnce ayar başlangıcı olarak: Weinreb ve Veres'te hedef başına **Sinkhorn mesafesini** sıfırdan eğitilen modellere, PI-SDE'ye ve PRESCIENT'a göre iyileştiriyor.
- GEARS içinde gen-durum gömmesi olarak: Norman Perturb-seq'te paylaşılan kelime dağarcığı **DE20 MSE'yi 0,2121 → 0,1858'e** düşürüyor (**%12,4 göreli iyileşme**), GEARS eğitim prosedürü değiştirilmeden.
- Weinreb'te sıfır-atış klonal kader skorları güçlü dinamik-OT temel çizgileriyle rekabetçi.
- 🔥 Yazarların en dikkat çekici iddiası: *"bildiğimiz kadarıyla, yalnızca gelişimsel atlaslar üzerinde ön eğitilmiş bir dinamik temsilinin, ilgisiz bir veri setindeki genetik perturbasyonlar için bir trajektori önseli sağladığına dair ilk ampirik kanıt."*

### 8. ⚠️ Yazarların açıkça belirttiği sınırlamalar (§7 "Scope and Future Work" + Ek I)
- Türler arası transfer 16.520 genlik ortolog kelime dağarcığına dayanıyor; **yetişkin insan dokuları değerlendirilmedi.**
- Zaman-geçişi transferi katı sıfır-atış değil, **ince ayar** gerektiriyor.
- Perturbasyon kolu **GEARS'ı yeniden kullanıyor**; bağımsız bir perturbasyon operatörü sunulmuyor.
- Ön eğitim ölçeği, tescilli derlemeler üzerindeki büyük dünya modellerinden **1–2 kat düşük.**
- **Belirsizlik nicelemesi yok:** model boyut başına gürültü ölçeği σ_θ sunuyor ama *"downstream tahminlerde posterior güven aralıklarını kalibre etmiyor veya raporlamıyoruz."*
- Değerlendirme varsayılan olarak **latent uzayda** (scVI-128) yapılıyor, gen uzayında değil.
- Geniş amaçlı hücre temsili iddiası yok; Geneformer/scGPT tipi temsil modelleriyle karşılaştırılmadı (bunlar geçiş operatörü sunmadığı için).
- Ablasyon çalışması latent boyutu, DiT omurga boyutu gibi eksenleri **test etmiyor.**

### 9. 🔍 Olası araştırma boşlukları (benim çıkarımım)
- Fare embriyonik gelişiminden insan **hastalık** trajektorilerine geçiş kanıtı yok — Ken'in "hastalık başlangıcını yıllar önce haritalama" çerçevesi bu makalede **doğrudan gösterilmiyor.** Bu, Ken'in yorumu ile makalenin iddiası arasındaki en büyük mesafe.
- Kalibrasyon eksikliği, klinik karar desteği için doğrudan engelleyici.
- Waddington ayrıştırmasının biyolojik yorumlanabilirliği (öğrenilen U_θ potansiyelinin gerçek bir enerji manzarasına karşılık gelip gelmediği) test edilmemiş.

---

# 3.4 — Kısa analizler

## MedAgentBench (Stanford, NEJM AI, 2025) — 🟢 A
- **Problem:** LLM ajanlarının tıbbi kayıt ortamlarıyla otonom etkileşim yeteneğini ölçen bir benchmark yok.
- **Veri:** 100 gerçekçi hasta profili, **700.000+ veri öğesi**, FHIR uyumlu etkileşimli sanal EHR ortamı, hekimler tarafından yazılmış **10 kategoride 300 klinik görev** (lab çekme, order girme, not yazma, sevk, hasta mesajlaşma).
- 📄 **Sonuç:** En iyi model **Claude 3.5 Sonnet v2 — %69,67**; GPT-4o %64; DeepSeek-V3 %62,7; Llama 3.3 %46; **Mistral %4.**
- 📄 Ken'in kendi vurguladığı ayrım: *"Modeller bilgi almada iyi. Eylem gerçekleştirmede kırılgan (order girme, kayıt güncelleme). Hataların çoğu: geçersiz FHIR çağrıları, hatalı JSON, eksik çok-adımlı yürütme."*
- ⚠️ Yazarların belirttiği: *"iyileştirme için hâlâ önemli alan var"*, görev kategorileri arasında ciddi performans varyasyonu.
- 🔍 Boşluk: Benchmark **adversarial veya belirsiz girdi** içermiyor; ajanın hata yaptığında toparlanma mekanizması ölçülmüyor.

## DeepRare (Nature, 2026) — 🟡 B
- **Problem:** Nadir hastalık tanı yolculuğu çok uzun; mevcut araçlar izlenebilir muhakeme sunmuyor.
- **Veri:** Literatür, vaka raporları ve Asya/Kuzey Amerika/Avrupa klinik merkezlerinden **9 veri seti, 14 tıp uzmanlığı.**
- **Yöntem:** 40+ özel araç ve güncel bilgi kaynağı entegre eden çok-ajanlı sistem; serbest metin + HPO terimleri + genetik test sonuçlarını işliyor.
- 📄 **Sonuç:** **%57,18 top-1 recall** (2. sıradaki Claude-3.7-Sonnet-thinking: %33,39). Multimodal testte 168 vakada **%69,1** (Exomiser %55,9). Uzman incelemesinde muhakeme zincirlerine **%95,4 uyum.**
- 🔍 Boşluk: Doğrulama esas olarak retrospektif; prospektif klinik kullanım ve klinisyen-AI ortak karar dinamikleri ölçülmemiş.

## GraphMERT (Princeton, arXiv:2510.09580) — 🟡 B
- **Problem:** LLM'ler metinden bilgi grafiği çıkarırken halüsinasyon yapıyor ve prompt'a aşırı duyarlı; provenance yok.
- **Yöntem:** **80M parametreli** grafik kodlayıcı; küçük uzman-küratörlü tohum KG'den semantik, cümle düzeyi metinden sentaktik temsil; MLM + önerilen **MNM (masked node modeling)** kaybı.
- 📄 **Sonuç:** PubMed diyabet makalelerinde **%69,8 FActScore / %68,8 ValidityScore**; LLM temel çizgisi **%40,2 / %43,0.**
- 🔍 Boşluk: Tek alan (diyabet) üzerinde gösterilmiş; alanlar arası genellenebilirlik açık.

## APOLLO (arXiv:2604.18570) — 🟡 B
- **Veri:** Büyük bir ABD hastane sisteminden **33 yıllık longitudinal kayıt, 7,2 milyon hasta, 25 milyar kayıt, 28 modalite, 12 uzmanlık**, 100.000+ benzersiz tıbbi olay.
- 📄 **Sonuç:** **5 yıl öncesine kadar** yeni hastalık başlangıcı riski (95 görev), progresyon (78), tedavi yanıtı (59), tedaviye bağlı advers olay (17), hastane operasyonları (12).
- 🔍 Boşluk: Tek sağlık sistemi → coğrafi/kurumsal genellenebilirlik açık. Bu ölçek bir lisans/yüksek lisans projesinde **yeniden üretilemez.**

## Responsiveness of epigenetic aging biomarkers (Nature Medicine, 2026) — 🟢 A
- **Veri:** DNAm verisi içeren **51 insan müdahale çalışması**, harmonize edilerek **16 epigenetik saat + 94 ek DNAm biyobelirteci** hesaplanmış.
- 📄 **Sonuçlar:** Mortalite veya yaşlanma hızını tahmin etmek için eğitilmiş saatler tüm müdahalelerde **en güçlü ve birbiriyle en tutarlı** yanıtı veriyor. Farmakolojik ve yaşam tarzı müdahaleleri en güçlü yanıtı sürüklüyor. **Çoklu alt-skorlu açıklanabilir saatler**, tek skorlu saatlerden daha fazla özgüllük ve biyolojik içgörü sağlıyor. Trigliserid epigenetik vekili 7 diyet müdahalesinin 6'sında, glukoz vekili 4'ünde anlamlı.
- 🔍 Boşluk: 51 çalışma heterojen tasarımlarda; **standartlaştırılmış prospektif müdahale çalışması** hâlâ yok.
