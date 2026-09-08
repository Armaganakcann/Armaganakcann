# 7. AŞAMA — Damar A: Trustworthy / Auditable AI
### Rafine edilmiş araştırma sorusu
> **Trustworthiness yöntemleri, uzun vadeli hastalık tahmini ve disease-trajectory modellerinin güvenilirlik problemlerini gerçekten çözebiliyor mu?**

**Tarih:** 8 Eylül 2026 · **Hâlâ proje fikri üretilmiyor.**
Bu belge A'yı genel bir konu olarak değil, **Damar B'nin açtığı boşlukla kesişimde** inceler ve sonunda "A ile B aynı problemin iki yarısı mı?" hipotezini üç olası sonuca açık şekilde test eder.

---

## 7.0 ÖNCE İKİ DÜZELTME

### Düzeltme 1 — Ken'in conformal prediction ilgisi hakkındaki ifadem fazla güçlüydü

6. Aşama'da şöyle yazmıştım:

> "Ken'in kanalında 'Weighted Conformal Prediction and PSI' videosu var — yani o bu köprünün varlığını görmüş."

Kanıtı daraltınca durum şu:

| Kanıt | Ne söylüyor |
|---|---|
| 🟢 Kanalda **"Weighted Conformal Prediction and Pharmaceutical Superintelligence"** başlıklı bir video var (11 gün önce, 107 izlenme) | Ken bu yönteme **bir video ayıracak kadar** ilgi duyuyor — bu gerçek |
| ⚠️ BoMolLLM gönderisindeki cümle Ken'in kendi cümlesi **değil**, Perplexity özetinin bir cümlesi: *"Pairing it with uncertainty methods such as weighted conformal prediction **could** prevent uncertain or out-of-distribution candidates from being advanced too aggressively"* | Bu bir **öneri**, uygulanmış bir yöntem değil |
| ⚠️ Her iki durumda da bağlam **ilaç tasarımı** — sağlık trajektorisi değil | Köprü Ken'in kafasında **kurulmuş değil**; iki ucu ayrı ayrı elinde |

**Doğru ifade:** Ken konformal belirsizliğe ilgi duyuyor ve bunu PSI (ilaç) tarafına yerleştiriyor. Aynı yöntemi hastalık tahmini tarafına taşıdığına dair kanıt yok. Bu, hipotez testi için önemli bir nüans.

### Düzeltme 2 — Bir başlık beni yanılttı, kontrol ettim

Arama sonuçlarında **"Risk Horizons: Structured Hypothesis Spaces for Longitudinal Clinical Prediction"** başlıklı bir makale çıktı ve isim tam olarak G1'i (güvenilir ufuk) kapatıyormuş gibi duruyordu. Kontrol ettim: bu, arXiv:2602.12828'in (Zhan Qu, Michael Färber) **v2 yeniden adlandırılmış hâli**; v1'deki adı GRAIL. İçeriği **next-visit** tahmini (MIMIC-IV + eICU), hiperbolik gömme ve LLM yeniden sıralama üzerine. **Uzun ufuk kalibrasyonuyla ilgisi yok.** G1 kapanmadı.

Bunu ayrıca not ediyorum çünkü bu damarda **başlığı boşluğu kapatıyormuş gibi duran ama kapatmayan** çalışmalar yaygın — kaynak doğrulamanın neden gerekli olduğunun somut örneği.

---

## 7.1 KEN'İN A DAMARINDAKİ DOĞRULANMIŞ KAYNAKLARI

| Ken'in gönderisi | Tarih | Kaynak | Ken'in kendi vurgusu |
|---|---|---|---|
| **Adversarial prompt and fine-tuning attacks threaten medical LLMs** | kullanıcıya doğrudan gönderdi | *Nat Commun* 16:9011 | — |
| **Generating Medical Image Counterfactuals using Causal Explanations** | 3 Eyl 2026 | arXiv:2609.02697 | *"Counterfactual'lar, ikna edici görseller yerine **test edilebilir denetim vakaları** yarattıklarında yararlı olur."* |
| **The Illusion of Readiness** (multimodal tıbbi benchmark stres testi) | 18 Eki 2025 | arXiv:2509.18234 | *"Physicians that employ #AI need to stay alert: **Will A.I. lead to de-skilling of physicians?**"* |
| **MedAgentBench** | 24 Eyl 2025 | *NEJM AI* | *"Modeller bilgi almada iyi. **Eylem gerçekleştirmede kırılgan.** Bugünün modelleri gerçek dünya iş akışları için yeterince güvenilir değil."* |
| **SciencePedia / Inverse Knowledge Search over Verifiable Reasoning** | 13 Kas 2025 | arXiv, 30 Eki 2025 | Gönderi başlığı doğrudan: **"How can you determine which statements in scientific papers are true?"** — çapraz-model doğrulamayla üretilmiş, provenance taşıyan bilgi tabanı |
| **Why 99 percent of Healthcare AI is Built to Fail** | 18 Haz 2026 | (Ken'in kendi Pulse makalesi) | *"Why Almost All Medical ML Models are Methodologically Fragile"* |
| **How to Employ Starling AI to Overcome Flawed Data** | 18 Haz 2026 | Starling | Kötü veri problemini otonom veri seti inşasıyla çözme |
| **Kan tabanlı Alzheimer biyobelirteçleri** | 27 Mar 2025 | — | **Düşük PPV** vurgusu (bkz. 6. Aşama) |
| **Weighted Conformal Prediction and PSI** | ~2 hafta önce (video) | — | ⚠️ İlaç bağlamında (bkz. Düzeltme 1) |

**Desen:** Ken'in A damarındaki her kaynağı aynı iskelete oturuyor — *doğrulanabilirlik (verifiability), izlenebilirlik (traceability), kırılganlık (brittleness), denetlenebilirlik (auditability)*. Bu, 5. Aşama'daki "filtre" tespitini bağımsız olarak doğruluyor.

---

## 7.2 A1 — KALİBRASYON: model "%80 risk" dediğinde gerçekten %80 mi?

### Alanın cevabı: yöntem var, uygulama yok

**📄 Doğrulanmış olgular:**

| Bulgu | Kaynak |
|---|---|
| Kalibrasyon, klinik ortamın dinamik doğası nedeniyle **zamanla bozuluyor** (calibration drift) | Sistematik derleme literatürü |
| Bozulma tek tip değil — **dört ayrı biçimi** var: ani geçiş, kısa sürede hızlı geçiş, uzun sürede kademeli geçiş, ve mevsimsel/tekrarlayan geçiş | Calibration drift tespit literatürü |
| **Temporal recalibration** yöntemi var: prediktör etkileri tüm veriyle tahmin edilir, sonra **taban risk yalnızca en güncel veri alt kümesiyle** yeniden tahmin edilir; rekabet eden risk ortamları için de uyarlanmış | PMC10946485 |
| Bozulmayı tespit ve düzeltme yöntemleri derlendi (izleme, drift tespiti, kök-neden analizi, yeniden eğitim, test-zamanı adaptasyonu) | *Keeping Medical AI Healthy and Trustworthy*, arXiv:2506.17442 → **IEEE TBME 2026**, PMID 41370148 |
| Ufka göre ayrıştırılmış kalibrasyon **raporlanabiliyor** — IPCW-düzeltmeli ampirik olay oranlarıyla, ufuk-bazlı ağırlıklı mutlak boşluk olarak | Bazı 2026 çalışmaları |

**🔴 Ama:**

| Sorun | Rakam |
|---|---|
| Modellerin **yalnızca ~1/3'ü** kalibrasyonu değerlendiriyor | Sistematik derlemeler |
| ML tabanlı COVID prognoz modellerinde **TRIPOD+AI uyumu ~%28** — geleneksel regresyon modellerinin orijinal TRIPOD uyumundan **daha düşük** | TRIPOD+AI derlemesi |
| Yaygın desen: *"Yazarlar ayrım metriklerini raporlayıp duruyor; kalibrasyon görünmüyor; örneklem büyüklüğü gerekçelendirilmiyor; eksik veri tek cümleyle geçiştiriliyor; model okuyucunun test edebileceği hiçbir yere konulmuyor."* | Aynı derleme |

### 🔥 Kritik ampirik kanıt — kalibrasyonun dış kohortta çöküşü

**Eniolade (arXiv:2605.21566), "Calibration, Uncertainty Communication, and Deployment Readiness in CKD Risk Prediction"** — bu çalışma tam olarak bizim sorumuzu deneysel olarak test ediyor:

- **Kurulum:** 5 sınıflandırıcı (lojistik regresyon, random forest, XGBoost, Platt ölçeklemeli SVM, Gaussian naive Bayes), UCI CKD veri setinde eğitildi (400 hasta, %62,5 CKD). Dış stres testi: **MIMIC-IV demo** kohortu (97 hasta, %23,7 CKD) — yani prevalans kayması + öznitelik eksikliği altında.
- **İç sonuçlar:** Beş modelin **hepsi AUROC 1,00**. İzotonik kalibrasyon sonrası **ECE 0,000–0,022**.
- 🚨 **Dış sonuçlar:** AUROC **0,48–0,58**'e düştü. ECE **0,68–0,76**'ya fırladı. Konformal kapsama **0,80–0,98'den 0,21–0,25'e çöktü** (hedef: 0,90).
- **Sekiz kriterli konuşlandırma hazırlık kontrol listesinde hiçbir model geçemedi** — skorlar 16 üzerinden 2–4.

Yazarların sonucu: *"Near-perfect internal performance did not survive distributional shift."*

**Bu tek çalışma A ve B damarlarını aynı anda vuruyor:** hem kalibrasyonun (A1) hem konformal kapsamanın (A3) dış geçerlilik altında (A4) çöktüğünü gösteriyor.

---

## 7.3 A2 — PPV VE TABAN ORANI (base rate) PROBLEMİ

### Alanın cevabı: 2026'da yeni yeni ele alınıyor

**📄 Doğrulanmış:**

**Hoessly, "Why decision curves go above or below treat-all and treat-none: a PPV- and calibration-based guide for clinical prediction models"** — arXiv:2603.26184 (stat.AP), 27 Mart 2026.

Ne yapıyor:
- Net fayda (net benefit) yorumunu iki tamamlayıcı biçimde yeniden ifade ediyor
- Treat-none / treat-all karşılaştırmalarını **eşik-özgül gözlenen risk** üzerinden ifade ediyor → karar eğrisi performansını **klinik olarak anlamlı alt gruplardaki kalibrasyona** bağlıyor
- Net faydanın **PPV ile ilişkisini** gösteriyor
- 🔥 **PPV eğrilerini, karar eğrilerinin pratik tamamlayıcısı olarak öneriyor**

Net fayda formülü: `NB = duyarlılık × prevalans − (1 − özgüllük) × (1 − prevalans) × w`, burada `w` eşik olasılığındaki odds. **Prevalans formülün içinde** — yani taban oranı düştükçe net fayda mekanik olarak eriyor.

### 🔴 Ama: ufuk boyutu hâlâ yok

Hoessly'nin katkısı **eşik (threshold)** ekseninde. Bizim B damarından çıkardığımız problem ise **ufuk (horizon)** ekseninde:

```
Hoessly 2026 kapsıyor:          Kapsamıyor:
  PPV ↔ eşik                      PPV ↔ ufuk
  kalibrasyon ↔ eşik              kalibrasyon ↔ ufuk
  net fayda ↔ eşik                net fayda ↔ ufuk
```

Uzun ufukta prevalans **sabit değil** — ufuk uzadıkça kümülatif olay oranı artar ama **yıllık** olay oranı ve dolayısıyla belirli bir zaman penceresindeki tahminin PPV'si düşer. Bu iki etkinin bileşkesi hiçbir yerde eğri olarak verilmemiş.

**Hatırlatma (6. Aşama'dan):** Ken'in Alzheimer biyobelirteç gönderisinde vurguladığı tam olarak buydu — AUC %70,9–82,6, NPV >%90, **ama PPV düşük**, kombinasyonla ancak %43.

---

## 7.4 A3 — BELİRSİZLİK VE ÇEKİMSERLİK: model "bilmiyorum" diyebiliyor mu?

### Bu, A damarının en gelişmiş alt alanı — ve en çarpıcı boşluğun bulunduğu yer

**📄 Yöntem tarafı olgun ve B'ye teorik olarak tam uyuyor:**

| Yöntem | Künye | B ile ilişkisi |
|---|---|---|
| **Weighted conformal prediction** | Tibshirani, Barber, Candès, Ramdas — *Conformal Prediction Under Covariate Shift*, NeurIPS 2019 | Eğitim ve test kovaryat dağılımları farklıyken, olabilirlik oranıyla ağırlıklandırarak dağılımdan bağımsız tahmin aralıkları üretiyor |
| 🔥 **Conformalized Survival Analysis** | **Candès, Lei, Ren — *JRSS-B* 85(1):24–45 (2023)**, arXiv:2103.09763 | **Tam olarak B'nin ortamı.** Herhangi bir sağkalım tahmin algoritmasının etrafına sarılıp, kovaryata bağlı **kalibre edilmiş alt tahmin sınırları** üretiyor. Tip I sağdan sansürlemede, sansürleme tamamen dışsalsa **sonlu örneklemde garanti**; koşullu bağımsız sansürlemede **çift-sağlam (doubly robust)**: sansürleme mekanizması VEYA koşullu sağkalım fonksiyonu iyi tahmin edilirse marjinal kapsama yaklaşık garantili. **Erken sansürlenen bireyleri atıp, oluşan kovaryat kaymasını weighted CP ile düzelterek** çalışıyor. 🔥 **UK Biobank COVID verisinde gösterilmiş.** |
| Uyarlanabilir kesim noktalı versiyon | *Conformalized survival analysis with adaptive cutoffs* | Sansürleme eşiği kovaryata bağlı ve veriye uyarlamalı seçiliyor |
| İki taraflı versiyon | arXiv:2410.24136 | — |
| Geçmişe duyarlı versiyon | *History-Aware Conformal Prediction Sets for Censored Time-to-Event Outcomes*, arXiv:2605.06581 (May 2026) | Boylamsal geçmişi kullanıyor |
| **Selective prediction / deferral** | *Conformal selective prediction with cost aware deferral for safe clinical triage under distribution shift*, **Sci Rep 2026**, DOI `10.1038/s41598-026-40637-w` | Kalibre olasılıksal modelleme + konformal tahmin + maliyet-farkında erteleme. Zamansal olarak ayrılmış test bölmelerinde **erken sepsis** tahmininde, seçici erteleme tutulan vakalardaki hatayı **dağılım-içinde %49,6, dağılım-dışında %46,7** azaltmış |

### 🚨 Ve işte kritik boşluk

**Bu yöntemlerin uygulandığı görevlerin hepsi kısa ufuklu:**

| Uygulama | Ufuk |
|---|---|
| Erken sepsis tahmini | **saatler** |
| Klinik triyaj | **saatler–günler** |
| Yatış süresi (LOS) tahmini | **günler** |
| 30 günlük yeniden yatış | **günler–haftalar** |
| Next-visit tahmini (Risk Horizons/GRAIL) | **bir sonraki ziyaret** |
| Görüntü sınıflandırma (cilt lezyonu, histopatoloji, dermatoloji) | **anlık** |

**Delphi-2M, APOLLO veya organ saatleri gibi çok-yıllık çok-hastalık modellerine konformal tahmin, seçici çekimserlik veya kapsama garantisi uygulanmış bir çalışma bulamadım.** ⚫

Delphi-2M'in kendisinde:
- ✅ 5 yıllık yaş dilimlerinde kalibrasyon analizi **var**
- ❌ Konformal kapsama garantisi **yok**
- ❌ Çekimserlik / "bilmiyorum" mekanizması **yok**
- ❌ Ufka göre PPV veya net fayda eğrisi **yok**
- ❌ Bireysel tahmin için güven aralığı **yok**

Chreode makalesi bunu kendisi itiraf ediyor: *"No uncertainty quantification yet… we do not currently calibrate or report posterior credible intervals on downstream predictions."*

### ⚠️ Ayrıca: konformal tahminin kendisi de sanıldığı kadar sağlam değil

İki bağımsız eleştiri var ve ikisi de B'nin ortamında özellikle geçerli:

**1. Küçük kalibrasyon seti problemi.** Kladny, Schölkopf, Koch, Baumgartner, Muehlebach — *A Critical Perspective on Finite Sample Conformal Prediction Theory in Medical Applications*, arXiv:2512.14727 (Max Planck Intelligent Systems, Tübingen AI Center, ELLIS Tübingen, Bern Üniversitesi, Lucerne).

Argümanları: CP'nin sıkça alıntılanan avantajı, garantinin **herhangi bir büyüklükteki** kalibrasyon örneklemi için geçerli olması. Yazarlar bunu sorguluyor: *"garantiler herhangi bir büyüklükte geçerli olsa da, bu garantilerin **pratik faydası** kalibrasyon setinin büyüklüğüne yüksek oranda bağlı."* Tıpta veri kıt olduğu için bu doğrudan geçerli.

🔥 **Bu eleştiri B'de en sert ısırıyor:** uzun ufuk + nadir hastalık = hastalık başına **etkili kalibrasyon seti çok küçük**. Delphi-2M 1.256 tanı tahmin ediyor; bunların büyük kısmı için 10 yıllık pencerede yeterli olay yok.

**2. Ampirik çöküş.** Yukarıdaki CKD çalışması: konformal kapsama dağılım kayması altında 0,90 hedefine karşı **0,21–0,25'e** düştü. Yani garanti, tam da ihtiyaç duyulan yerde tutmuyor.

**3. Ölçek problemi.** Campagner ve ark.'nın (Eniolade'nin aktardığı üzere) sağlıkta ML çalışmalarını incelemesi: **%4'ten azı belirsizlik nicelemesini açıkça ele alıyor.**

---

## 7.5 A4 — DOĞRULAMA: başka hastanede, başka ülkede, 5 yıl sonra da çalışıyor mu?

**📄 Doğrulanmış olgular:**

| Bulgu | Rakam / kaynak |
|---|---|
| Onkoloji tahmin modeli çalışmalarında **287 uygun çalışmanın yalnızca %31'i** dış doğrulama içeriyor | Sistematik derleme, PMID 42580368 |
| Bu doğrulamaların **%88'i** aynı çalışma içinde yeni geliştirilen modeller üzerinde yapılmış — yani bağımsız değil | Aynı |
| **%36'sı** zamansal veya coğrafi split-sample yaklaşımı kullanmış | Aynı |
| Dış doğrulama sıklıkla **amacı açıkça belirtilmeden** raporlanıyor; *"transportability'yi değerlendirmek üzere tasarlanmış bir çalışma değil, prosedürel bir adım gibi"* ele alınıyor | Aynı |
| Coğrafi dış doğrulama, iç doğrulamadan **daha yüksek genellenebilirlik** kanıtı sağlıyor ve klinik uygulamadan önce zorunlu | Geographic/temporal validity literatürü |

**Delphi-2M bu tabloda iyi bir örnek:** parametrelerde hiçbir değişiklik yapmadan 1,93 milyon Danimarkalıya uygulanmış — **ve AUC 0,69'dan 0,67'ye düşmüş.** Bu, alanın standardının çok üstünde bir dürüstlük. Ama tek bir dış kohort ve tek bir ülke.

**UKB-PPP proteomik çalışması ise tersi:** proteinin klinik modeli geçtiği **67 hastalığın yalnızca 6'sı** dış kohortta (EPIC-Norfolk, N=295–1.116) test edilebilmiş. Kalan 61 hastalık için dış doğrulama **yok.**

**Regülasyon tarafı:** FUTURE-AI konsensüs kılavuzu (*BMJ*, 5 Şubat 2025, PMID 39961614) — 50 ülkeden 117 disiplinlerarası uzman, iki yıllık süreç. **Altı ilke:** Fairness, Universality, **Traceability**, Usability, **Robustness**, Explainability. **30 en iyi uygulama**, tasarımdan izlemeye kadar tüm yaşam döngüsünü kapsıyor ve **kalibre belirsizlik çıktılarını traceability gereksinimi olarak açıkça talep ediyor.**

---

## 7.6 A5 — DENETLENEBİLİRLİK ve PROVENANCE (açıklanabilirlikten farkı)

Kullanıcının uyarısı yerinde: bu ikisi karıştırılmamalı. Literatür de ayırıyor:

| Kavram | Ne soruyor | Odak |
|---|---|---|
| **Explainability / interpretability** | "Model bu çıktıyı **nasıl** üretti?" | Algoritmanın **iç mantığı** |
| **Auditability / transparency** | "Bu karar **hangi veriye, hangi model sürümüne, hangi kaynağa** dayanıyor ve geriye doğru izlenebilir mi?" | **Sistemik hesap verebilirlik** |

**📄 Doğrulanmış:**
- Bir **AI Fairness Provenance Record**, veri soy kütüğünü (data lineage), model sürüm geçmişini, karar-başına denetim izlerini ve yanlılık metriklerini yakalıyor
- Bu yaklaşım ABD **FDA**'nın ML-etkin tıbbi cihazlar için şeffaflık kılavuzuna ve **ONC HTI-1** algoritmik şeffaflık zorunluluğuna uyumu destekliyor
- Şeffaflık çok boyutlu: açıklanabilirlik **bir** ölçüt; diğerleri veri seti ve algoritma dokümantasyonu, yetenek ve sınırlamaların açık iletişimi
- Kaynak: *Auditing fairness in clinical AI systems using provenance-based simulation*, PMID 42038538; *From Black Box to Audit Trail*

**Ken'in konumu tam burada:** SciencePedia gönderisinin başlığı — *"How can you determine which statements in scientific papers are true?"* — bir açıklanabilirlik sorusu değil, bir **doğrulanabilirlik/provenance** sorusu. OptimusKG video etiketlerindeki *"agentic validation, data provenance"* aynı yerde. DeepRare'de vurguladığı *"traceable reasoning"* de öyle.

### 🔴 Ama B tarafında provenance neredeyse hiç yok

Bir hastalık trajektorisi modeli "8 yıl içinde risk yüksek" dediğinde:
- Delphi-2M **SHAP** veriyor → hangi geçmiş tanının riski ne kadar artırdığı (explainability ✅)
- Ama **provenance yok**: bu SHAP değerinin ne kadarı gerçek biyoloji, ne kadarı UK Biobank'ın hastane kaydı eksiklik örüntüsü? Makale bu yanlılığın **var olduğunu gösteriyor** ama tahmin başına ayrıştırmıyor.

Bu, A5'in B'ye uygulanmadığı somut nokta.

---

## 7.7 🔬 HİPOTEZ TESTİ: A ve B aynı problemin iki yarısı mı?

Üç olası sonuca da açık kalarak kanıtı tarttım.

### Sonuç 1 lehine kanıt — "A ve B gerçekten birleşiyor"

| Kanıt | Güç |
|---|---|
| **Conformalized Survival Analysis** tam olarak B'nin ortamında (sansürlü zaman-olay) A'nın yöntemini (weighted CP) kullanıyor ve **UK Biobank'ta gösterilmiş** | 🔥🔥🔥 Çok güçlü — bu literal bir köprü |
| **SurvivEHR** (npj Digital Medicine 2026, DOI `10.1038/s41746-026-02709-z`): 23 milyon hasta, 7,6 milyar kodlanmış olay, UK birinci basamak; **rekabet eden risk + zaman-sonraki-olay ön eğitim hedefi**, açıkça *"calibrated risk stratification"* ve *"longer-horizon risk prediction"* iddiasıyla | 🔥🔥🔥 Çok güçlü — 6. Aşama'daki "rekabet eden riskler ele alınmıyor" boşluğunu kısmen kapatıyor |
| Temporal recalibration yöntemleri **rekabet eden risk ortamları için** uyarlanmış | 🔥🔥 Güçlü |
| Hoessly 2026 net faydayı PPV ve kalibrasyona bağlıyor | 🔥🔥 Güçlü |
| FUTURE-AI **kalibre belirsizliği zorunlu** kılıyor | 🔥 Orta |
| CKD çalışması A1+A3+A4'ün aynı anda çöktüğünü gösteriyor → problem gerçekten **tek** | 🔥🔥 Güçlü |

### Sonuç 3 lehine kanıt — "bağlantıyı fazla yorumladık"

| Kanıt | Güç |
|---|---|
| Ken'in kendisi bu köprüyü kurmamış — conformal ilgisi **ilaç** tarafında (Düzeltme 1) | 🔥🔥 Ciddi bir uyarı |
| A literatürünün büyük kısmı görüntü sınıflandırma ve LLM güvenliği üzerine; B ile hiç temas etmiyor | 🔥 Orta |
| "Trustworthy AI" çok geniş bir şemsiye — her şeyle kesiştiği söylenebilir, bu onu anlamsızlaştırır | 🔥 Orta |

### ⚖️ VERDİKT: **Sonuç 2 — kısmen birleşiyor, ve birleşmediği yer tam olarak tarif edilebilir**

Bu, kanıtın desteklediği en dürüst ifade. Ama "kısmen" belirsiz bir kelime; şöyle keskinleştiriyorum:

> **A'nın yöntemleri B'nin problemini çözmek için VAR ve teorik olarak uygun. Ama yanlış ufukta test edilmişler.**

Somut olarak:

```
A'NIN YÖNTEM OLGUNLUĞU              A'NIN UYGULAMA UFKU
─────────────────────────           ────────────────────
Weighted CP (2019)          ✅      Görüntü sınıflandırma    anlık
Conformalized survival (2023)✅     Sepsis                   saatler
Adaptive cutoffs            ✅      Triyaj                   saatler-günler
History-aware CP (2026)     ✅      LOS                      günler
Selective deferral (2026)   ✅      30-gün yeniden yatış     haftalar
Temporal recalibration      ✅      Next-visit               1 ziyaret
Competing risks (SurvivEHR) ✅
                                    ❌ ────────────────────────────
                                    ÇOK-YILLIK ÇOK-HASTALIK
                                    (Delphi-2M, APOLLO, organ saatleri)
                                    → hiçbiri uygulanmamış
```

### Neden bu boşluk var? Üç yapısal neden (benim çıkarımım 🔍)

**1. Değişilebilirlik (exchangeability) varsayımı B'de üç kez birden ihlal ediliyor.**
Konformal tahmin değişilebilirlik varsayar. B'nin ortamı bunu eşzamanlı olarak üç şekilde bozar:
- **(a) Sansürleme kaynaklı kayma** → Conformalized Survival Analysis bunu çözüyor ✅
- **(b) Ufuk boyunca zamansal sürüklenme** → Temporal recalibration bunu çözüyor ✅
- **(c) Kohort/coğrafi kayma** → Weighted CP kısmen çözüyor ⚠️
- **(a)+(b)+(c) aynı anda** → ⚫ **Çözen yok**

**2. Nadir olay + uzun ufuk = küçük etkili kalibrasyon seti.**
Kladny ve ark.'nın eleştirisi tam burada ısırıyor. 1.256 hastalık × 10 yıllık pencere → çoğu hastalık için kalibrasyon seti pratikte çok küçük. CP'nin sonlu-örneklem garantisi teknik olarak geçerli kalır ama **pratik olarak boş** hale gelir.

**3. Değerlendirme kültürleri ayrı.**
A literatürü **kapsama (coverage)** diliyle konuşuyor. B literatürü **AUC/C-index** diliyle. İkisinin ortak bir metriği yok. Bu yüzden bir Delphi-2M makalesi "kapsama garantisi vermiyorum" demiyor — o dili hiç konuşmuyor.

---

## 7.8 KESİŞİM ANALİZİ — rafine edilmiş boşluklar

6. Aşama'daki G1–G6'yı A damarının kanıtıyla güncelliyorum. **Bazıları küçüldü, bazıları büyüdü, biri kapandı.**

| # | 6. Aşama'daki hâli | A damarından sonraki durum |
|---|---|---|
| **G1** | "Güvenilir ufuk" diye standart bir kavram yok | 🟡 **Küçüldü ama duruyor.** Hoessly 2026 PPV↔eşik bağını kurdu; ufuk-bazlı kalibrasyon raporlama yöntemi de var. Ama **PPV/net fayda × ufuk** eğrisi hâlâ hiçbir uzun-vadeli sağlık modelinde yayınlanmamış |
| **G2** | Ufka bağlı belirsizlik ve çekimserlik yok | 🔴 **BÜYÜDÜ ve keskinleşti.** Yöntemler tam olarak var (conformalized survival analysis, selective deferral) ama **çok-yıllık modellere hiç uygulanmamış** — ve iki bağımsız eleştiri (Kladny; CKD ampirik çöküşü) uygulandığında sorun çıkacağını gösteriyor. **Bu artık en net boşluk.** |
| **G3** | Prodrom vs. gerçek risk faktörü otomatik ayrılamıyor | 🔴 **Değişmedi.** A damarında bu soruya değinen bir yöntem bulamadım. Nedensel XAI (counterfactual, ReX) model davranışını açıklıyor, **biyolojiyi değil** — Kelly ve ark. bunu açıkça söylüyor |
| **G4** | Fırsatçı görüntüleme az organ için denenmiş | 🟡 **Değişmedi**, ama A damarı bir uyarı ekliyor: timus çalışması göreli risk azalması raporluyor; kalibrasyon, PPV veya kapsama **yok** |
| **G5** | Sentetik trajektori metodolojisi kurulmamış | 🟡 **Değişmedi.** Delphi'nin sentetik verisi AUC 0,74 veriyor; ama sentetik veride bulunan bir örüntünün gerçek olup olmadığını **doğrulama** metodolojisi yok |
| **G6** | Katmanlar birbirinden habersiz | 🟢 **Kısmen kapandı.** SurvivEHR (rekabet eden risk + uzun ufuk + 23M hasta) ve APOLLO (28 modalite) entegrasyon deniyor. Ama ikisi de kapalı verilerde |
| **G7 (YENİ)** | — | 🔴 **Üçlü kayma altında kapsama garantisi.** Sansürleme + zamansal sürüklenme + kohort kayması aynı anda olduğunda hiçbir yöntem garanti vermiyor. Bu, 7.7'deki analizden çıkan yeni boşluk |
| **G8 (YENİ)** | — | 🔴 **A ve B'nin ortak metriği yok.** Kapsama (A) ile ayrım gücü (B) aynı raporda yan yana getirilmiyor. CKD çalışması bunu yapan **tek** örnek — ve tek yaptığında çarpıcı bir sonuç çıktı |

---

## 7.9 ÖZET

```
        DAMAR B                              DAMAR A
  Hastalık trajektorisi              Trustworthy / Auditable AI
        │                                       │
        ▼                                       ▼
  "Ne kadar erken?"  ✅ çözüldü        Kalibrasyon      ✅ yöntem var
  "Ne kadar güvenilir?" ❌             Konformal UQ     ✅ yöntem var
        │                              Seçici çekimserlik ✅ yöntem var
        │                              Temporal recal.  ✅ yöntem var
        │                              Provenance       ✅ yöntem var
        │                                       │
        └───────────────┬───────────────────────┘
                        ▼
              KESİŞİM: neredeyse boş
                        │
    Yöntemler saatler–haftalar ufkunda test edilmiş.
    Çok-yıllık çok-hastalık modellerinde uygulanmamış.
                        │
                        ▼
     Uygulandığında ne olacağına dair TEK ampirik ipucu:
     CKD çalışması — konformal kapsama 0,90 hedefine karşı
     dış kohortta 0,21–0,25'e çöktü.
```

### Bu aşamanın tek cümlelik sonucu

> **A ve B aynı problemin iki yarısı — ama literatür bunu henüz böyle görmüyor, ve Ken de görmüyor.** Ken iki ucu ayrı ayrı tutuyor: güvenilirliği tıbbi AI'da, konformal belirsizliği ilaç tasarımında. Köprü teorik olarak kurulu (conformalized survival analysis), pratikte kurulmamış.

---

## Bu belge hâlâ proje fikri içermiyor

Sıradaki adım, kullanıcının planına göre: **A + B'yi birlikte tartışmak.** C damarına (Autonomous AI / Agents) henüz geçilmiyor.

Tartışmaya taşınması gereken üç soru:
1. G2 ve G7 gerçekten yapılabilir bir araştırma sorusu mu, yoksa büyük veri erişimi mi gerektiriyor? *(CKD çalışması UCI + MIMIC-IV demo ile yapıldı — yani erişilebilir veriyle bu tür bir sonuç mümkün.)*
2. G8 (ortak metrik) bir metodoloji katkısı olarak tek başına yeterli mi?
3. G4 (fırsatçı görüntüleme) kullanıcının CV geçmişine en yakın boşluk — ama A damarı orada da kalibrasyon/PPV eksikliği olduğunu gösterdi. İkisi birleştirilebilir mi?
