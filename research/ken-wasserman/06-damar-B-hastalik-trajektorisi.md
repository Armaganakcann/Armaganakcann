# 6. AŞAMA — Damar B: Hastalık Trajektorisi ve Semptom Öncesi Tahmin

**Tarih:** 8 Eylül 2026
**Kapsam:** Bu damarın bağımsız derinlemesine incelemesi. **Hâlâ proje fikri üretilmiyor.**
**Akış:** Ken'in bu damardaki gerçek konumu → mevcut durum → dünyadaki önemli çalışmalar → veri durumu → açık problemler → gerçek research gap

---

## 6.0 ÖNCE BİR DÜZELTME: Görüntüleme bulgusu rafine edilmeli

5. Aşama'da şunu yazmıştım:

> "Tıbbi görüntüleme kanalın %1'i (338 videoda 4)."

**Bu sayı hâlâ doğru** — video başlıkları üzerinden ölçüldü ve değişmedi. Ancak bu turda Ken'in LinkedIn arşivinde bulduğum iki gönderi, bu bulgunun **yorumunu** değiştiriyor:

| Ken'in gönderisi | Tarih | İçerik |
|---|---|---|
| *"Foundation model for cancer imaging biomarkers"* | 19 Mar 2024 | 11.467 radyografik lezyon üzerinde self-supervised (modifiye SimCLR) ön eğitim; anatomik bölge, malignite ve **prognoz** tahmini. Ken'in gönderiye eklediği kendi sorusu: **"How can imaging biomarkers predict the risk of developing a disease?"** |
| *"The Lethal Dogma: AI, Thymic Involution, and the Rejuvenation Imperative"* | (video: 3 ay önce) | Rutin BT taramalarından derin öğrenmeyle **timus sağlığı** ölçümü; korunmuş timus dokusu → belirgin biçimde düşük tüm-neden mortalite, kanser ve kardiyovasküler risk |

**Rafine edilmiş bulgu:** Ken tıbbi görüntülemeyle *tanı görevi* olarak ilgilenmiyor (bu gerçekten kanalın %1'i). Görüntülemeyle **risk/prognoz sensörü** olarak ilgileniyor — yani "bu görüntüde hastalık var mı?" değil, **"bu görüntü bana bu kişinin 10 yıl sonrasını ne kadar anlatıyor?"**

Bu ayrım, Damar B ile kullanıcının bilgisayarlı görü geçmişi arasındaki **tek doğal köprü** ve 6.5'te tekrar karşımıza çıkacak.

---

## 6.1 KEN'İN BU DAMARDAKİ DOĞRULANMIŞ KAYNAKLARI

Bu turda Ken'in LinkedIn arşivinden **yeni Kategori A kanıtları** çıktı. Damar B artık kanalın en iyi belgelenmiş damarı.

| Ken'in gönderisi / makalesi | Tarih | Kaynak çalışma | Kanıt |
|---|---|---|---|
| *Using Chreode AI to Map the Rate of Disease Onset Years Prior to Overt Symptoms* | 26 Haz 2026 | Optimal Transport tabanlı trajektori çıkarımı | 🟢 A |
| *Predicting Disease Via Cellular Aging AI* | 27 Haz 2026 | "Plazma proteomiği erken-uyarı fenotip sensörü olarak…" | 🟢 A |
| *Constructing the Personalized Virtual Patient, Health Trajectories, and Preventative Medicine* | 2026 | — | 🟢 A (Pulse makale başlığı) |
| *The Prescriptive Health Loop: Integrating Predictive AI with Targeted Physiology* | 30 Haz 2026 | — | 🟢 A |
| **Organ-spesifik proteomik yaşlanma saatleri** | 3 Ara 2025 | UK/Çin/ABD kohortları, 10 organ. Ken'in kendi vurgusu: *"Across all systems, accelerated organ aging predicted future disease **years before symptoms emerged**"* ve *"brain proteomic age emerged as one of the strongest predictors of mortality, cognitive decline, and neurodegenerative risk, outperforming traditional clinical biomarkers and even genetic risk scores"* | 🟢 A |
| **"Blood-based biomarkers of Alzheimer's disease and incident dementia in the community"** | 27 Mar 2025 | p-tau181, p-tau217, NfL, GFAP; 10 yıllık demans için AUC **%70,9–82,6**; **NPV >%90 ama PPV DÜŞÜK**; p-tau217+NfL/GFAP birleşimiyle PPV **%43**'e çıkıyor | 🟢 A |
| *"Robust and interpretable AI-guided marker for early dementia prediction in real-world clinical settings with 81.66% accuracy"* | 20 Tem 2024 | Cambridge; bilişsel testler + gri madde atrofisi; **UK ve Singapur hafıza kliniklerinde bağımsız çok-merkezli doğrulama** | 🟢 A |
| **"Foundation model for cancer imaging biomarkers"** | 19 Mar 2024 | 11.467 radyografik lezyon, SSL/SimCLR; malignite ve prognoz | 🟢 A |
| **Timus sağlığı / BT derin öğrenme** | 2026 | *Nature*, `10.1038/s41586-026-10242-y` | 🟢 A |
| *"Turning back time"* epigenetik saat derlemesi | 12 Ağu 2026 | 41 insan müdahale çalışması | 🟢 A |
| *Responsiveness of epigenetic aging biomarkers…* | (kullanıcıya gönderdi) | *Nature Medicine* 2026 | 🟢 A |
| *"Have you improved your #ML and #DNN/#AI to detect successful interventions yet?"* | 13 Haz 2023 | Horvath / Hannum DNAm saatleri | 🟢 A — **başlığın kendisi Ken'in asıl sorusunu ele veriyor: tahmin değil, MÜDAHALENİN İŞE YARADIĞINI TESPİT** |

### 🔥 Kritik gözlem

Ken'in bu damardaki iki gönderisi, alanın **en büyük iki açığını kendisi işaret ediyor**:

1. **Alzheimer biyobelirteç gönderisinde** vurguladığı şey yüksek AUC değil, **düşük PPV**. Yani: "bu test hastalığı dışlamakta iyi (NPV >%90), ama kimin gerçekten hastalanacağını söylemekte kötü."
2. **2023 tarihli makale başlığı** doğrudan şunu soruyor: *"AI'ını başarılı müdahaleleri tespit edecek şekilde geliştirdin mi?"* — yani tahminin kendisiyle değil, **tahminin bir eyleme dönüşüp dönüşmediğiyle** ilgileniyor.

Bu ikisi birlikte, Ken'in Damar B'ye Damar A'nın (güvenilirlik) gözlüğüyle baktığını gösteriyor. Aşağıdaki analiz bunun alanın gerçek açığıyla birebir örtüştüğünü gösterecek.

---

## 6.2 MEVCUT DURUM

Alan, **veri modalitesine göre dört katmana** ayrılmış durumda. Bunlar birbirinden büyük ölçüde habersiz çalışıyor — bu başlı başına bir bulgu.

```
KATMAN 1 — SAĞLIK KAYDI DİZİLERİ (EHR / kayıt sistemleri)
   Delphi-2M, APOLLO, BEHRT / Hi-BEHRT
   Ölçek: 10⁵–10⁷ hasta · Ufuk: 5–20 yıl · Girdi: ICD kodları, ilaçlar, olaylar
        ↓
KATMAN 2 — MOLEKÜLER SENSÖRLER (kanda ölçülen)
   Plazma proteomiği (UKB-PPP), epigenetik saatler, organ saatleri, p-tau217
   Ölçek: 10⁴–10⁵ · Ufuk: 5–17 yıl · Girdi: ~3.000 protein / DNAm / tek belirteç
        ↓
KATMAN 3 — HÜCRESEL/MEKANİSTİK DİNAMİK
   Chreode, Waddington-OT, hücresel yaşlanma modelleri
   Ölçek: 10⁶ hücre · Ufuk: gelişimsel/perturbasyon · Girdi: scRNA-seq
        ↓
KATMAN 4 — FIRSATÇI GÖRÜNTÜLEME (opportunistic imaging)
   Timus BT, kanser görüntüleme temel modeli
   Ölçek: 10⁴ · Ufuk: yıllar · Girdi: zaten çekilmiş rutin BT/MR
```

### Alanın olgunluk durumu — dürüst özet

| Boyut | Durum |
|---|---|
| **Ayrım gücü (discrimination)** | ✅ Büyük ölçüde çözülmüş. AUC 0,70–0,85 aralığı standart hale geldi |
| **Ölçek** | ✅ Çözülmüş. Milyonlarca hasta, binlerce protein, 1.000+ hastalık |
| **Dış doğrulama** | ⚠️ Nadir ve seçici. Yapıldığında performans düşüyor |
| **Kalibrasyon** | 🔴 **Sistematik olarak raporlanmıyor.** Sistematik derlemelerde modellerin yalnızca **~1/3'ü** kalibrasyon değerlendiriyor |
| **Nedensellik** | 🔴 Yok, ve yazarlar bunu açıkça söylüyor |
| **Klinik fayda (actionability)** | 🔴 **Neredeyse hiç gösterilmemiş** |
| **PPV / klinik kullanılabilirlik** | 🔴 Yüksek AUC'lerin altında düşük PPV gizleniyor |

**Tek cümlelik özet:** Alan "tahmin edebilir miyiz?" sorusunu büyük ölçüde çözdü; **"bu tahmine ne zaman ve ne kadar güvenebiliriz?"** ve **"bu tahmin bir şeyi değiştiriyor mu?"** sorularını neredeyse hiç ele almadı.

---

## 6.3 DÜNYADAKİ ÖNEMLİ ÇALIŞMALAR

### 🥇 Delphi-2M — bu damarın amiral gemisi

| | |
|---|---|
| **Başlık** | Learning the natural history of human disease with generative transformers |
| **Yazarlar** | Artem Shmatko, Alexander Wolfgang Jung, Kumar Gaurav, Søren Brunak, Laust Mortensen, Ewan Birney, Tom Fitzgerald, Moritz Gerstung |
| **Kurumlar** | EMBL, DKFZ, University of Copenhagen, Statistics Denmark, EMBL-EBI |
| **Yayın** | *Nature*, 17 Eylül 2025 · DOI `10.1038/s41586-025-09529-3` · PMID 40963019 · Ön baskı: medRxiv `10.1101/2024.06.07.24308553` |
| **Kod** | 🔓 **Açık: `github.com/gerstung-lab/Delphi`** |

**Ne yapıyor:** GPT-2 mimarisini üç noktada değiştiriyor — (1) ayrık pozisyon kodlaması yerine **sinüs/kosinüs tabanlı sürekli yaş kodlaması**, (2) bir sonraki token'a kadar geçen süreyi tahmin eden **üstel bekleme süresi başlığı**, (3) aynı anda kaydedilen token'ları da maskeleyen değiştirilmiş nedensel dikkat maskesi. Ayrıca ortalama 5 yılda 1 oranında **"olay yok" (padding) token'ı** ekleniyor.

**Veri:** 402.799 UK Biobank katılımcısı (eğitim), 100.639 (doğrulama), 471.057 (boylamsal test). **Dış test: 1,93 milyon Danimarkalı** — parametrelerde hiçbir değişiklik yapılmadan.

**Sözlük:** 1.258 durum (1.256 ICD-10 üst düzey tanı + ölüm + padding) + cinsiyet, BMI, sigara, alkol (girdi olarak, tahmin edilmiyor).

**Model boyutu:** 🔥 **Yalnızca 2,2 milyon parametre** (embedding 120, 12 katman, 12 head). UK Biobank ölçeğinde optimum bu civarda çıkmış.

**📄 Sonuçlar (makalede doğrudan belirtilen):**
- Yaşa göre stratifiye ortalama AUC ≈ **0,76** (iç doğrulama). Tanıların **%97'sinde AUC > 0,5.**
- **Ölüm için AUC 0,97** (her iki cinsiyette).
- 🔥 **Ufuk etkisi: AUC 10 yıl sonra 0,76 → 0,70'e düşüyor.**
- 🔥 **Dış test (Danimarka): ortalama AUC 0,67** (iç boylamsal test 0,69). Hastalıklar arası korelasyon Pearson r = 0,76 (%95 GA: 0,72–0,80).
- Kardiyovasküler hastalık ve demans için rutin klinik risk skorlarıyla benzer; ölüm için daha iyi; **diyabet için tek bir belirteçten (HbA1c) DAHA KÖTÜ.**
- Üretici mod: 60 yaşından itibaren 20 yıllık sentetik trajektoriler örnekleyebiliyor. İlk yıl tanı token'larının %17'si doğru; 20 yıl sonra %14'ün altına düşüyor (yaş+cinsiyet temel çizgisi: %12–13).
- 🔥 **Yalnızca sentetik veriyle eğitilen bir Delphi, gerçek doğrulama verisinde AUC 0,74 alıyor** — orijinalden sadece 3 puan düşük.
- SHAP analizi: pankreas kanseri riski önceki sindirim sistemi tanılarıyla **19 kat** artmış; ardından gelen pankreas kanseri tanısı mortalite oranını yaklaşık **10.000 kat** yükseltmiş.
- Kanserlerin mortalite üzerindeki etkisi birkaç yıllık yarı ömürle sönüyor; septisemininki keskin biçimde düşüyor.

**⚠️ Yazarların açıkça belirttiği sınırlamalar:**
1. **UK Biobank sağlıklı gönüllü yanlılığı.** Kohorta yalnızca 40–70 yaş arası, kayıt anında hayatta olan kişiler alınmış; kayıt öncesi ölümler tamamen eksik. Model, İngiltere ulusal istatistiklerine kıyasla mortaliteyi olduğundan düşük tahmin ediyor.
2. **Hastane kaydı eksikliği yanlılığı öğreniliyor.** Bir tanının hastane kayıtlarına ne kadar özel olduğuyla, ilk hastane token'ından sonraki oran değişimi arasında sistematik bir ilişki var — yani model **veri kaynağı örüntüsünü hastalık örüntüsü sanıyor.**
3. 🔥 **Nedensellik yok.** Ön baskıdan doğrudan alıntı: *"such temporal ordering does not imply the model is capable of identifying causal mechanisms in the sense of modifiable features."* Model olasılık ve eğilim veriyor; tıbbi kesinlik veya nedensel açıklama değil.
4. Yalnızca ICD-10 **üst düzey** kodları — şiddet, laboratuvar değerleri, ilaçlar, görüntüleme yok.

---

### Diğer temel çalışmalar

| Çalışma | Künye | Veri / Ölçek | Anahtar sonuç | Belirtilen sınırlama |
|---|---|---|---|---|
| **UKB-PPP seyrek proteomik imzalar** | *Nature Medicine*, Tem 2024, DOI `10.1038/s41591-024-03142-z` (Cambridge MRC Epidemiology Unit) | 41.931 kişi, Olink Explore 1536 + Expansion, **2.923 protein / 2.941 assay**, **218 hastalık**, 10 yıllık insidans | Sadece **5–20 protein** içeren seyrek modeller, temel klinik bilgiyi **67 hastalıkta** geçti (medyan ΔC-index 0,07; aralık 0,02–0,31). Klinik bilgi + 37 laboratuvar testi kombinasyonunu **52 hastalıkta** geçti (multipl miyelom, non-Hodgkin lenfoma, motor nöron hastalığı, pulmoner fibroz, dilate kardiyomiyopati) | 🔥 **Dış replikasyon 67 hastalığın yalnızca 6'sı için yapılabildi** (EPIC-Norfolk, N=295–1.116, olay sayısı 5–236). Geri kalan 61 hastalık için dış doğrulama YOK |
| **ProRS — proteomik risk skoru** | *Nature Communications*, Kas 2023, DOI `10.1038/s41467-023-43575-7` | 1.461 Olink proteini, **45 uç nokta** | Çoğu uç nokta için **en yüksek AUC 5 yıl içindeki olaylarda** — yani proteomik yakın-dönem riskte güçlü | Uzun ufukta performans düşüyor; ufka bağlı kalibrasyon raporlanmamış |
| **Organ-spesifik proteomik yaşlanma saatleri** | *Nature Aging* 2025, DOI `10.1038/s43587-025-01016-8` | UK Biobank n=**43.616**, Çin n=3.977, ABD n=800 | Çapraz kohort r = **0,98 / 0,93**. Hızlanmış organ yaşlanması, klinik ve genetik risk faktörlerinin ötesinde hastalık başlangıcı/ilerlemesi/mortalite öngörüyor; **beyin yaşlanması mortaliteyle en güçlü bağlantılı** | Gözlemsel; müdahale kanıtı yok |
| **Plazma proteomiğiyle beyin ve immün yaşlanma** | *Nature Medicine* 2025, DOI `10.1038/s41591-025-03798-1` | n=**44.498**, 11 organ, **17 yıllık takip** | Beyin ve immün sistem biyolojik yaşı sağlıklı ömür ve uzun yaşamın güçlü öngörücüsü; kalp yetmezliği, KOAH, tip 2 diyabet, Alzheimer başlangıcıyla ilişkili | Aynı |
| **APOLLO** | arXiv:2604.18570 (Nis 2026), Faisal Mahmood grubu | **7,2M hasta, 25 milyar kayıt, 33 yıl, 28 modalite** | **5 yıl öncesine kadar** yeni hastalık başlangıcı (95 görev), progresyon (78), tedavi yanıtı (59), advers olay (17) | Tek sağlık sistemi; genellenebilirlik açık |
| **Kan tabanlı Alzheimer biyobelirteçleri** | (Ken'in 27 Mar 2025 paylaşımı) | Toplum tabanlı kohort, 10 yıllık takip | p-tau181/p-tau217/NfL/GFAP için AUC **%70,9–82,6**; **NPV >%90** | 🔥 **PPV düşük.** Yazarların kendi sonucu: *"bu biyobelirteçler toplum ortamında yaklaşan demansı DIŞLAMAK için potansiyele sahip, ama tarama aracı olarak kullanılmak için başka belirteçlerle birleştirilmeleri gerekebilir."* Kombinasyonla PPV ancak **%43** |
| **Timus sağlığı — fırsatçı BT** | *Nature* 2026, DOI `10.1038/s41586-026-10242-y` | **NLST n=25.031** + **Framingham n=2.581**, asemptomatik yetişkinler | Rutin BT'den derin öğrenmeyle ölçülen iyi timus sağlığı: tüm-neden mortalitede **%50**, akciğer kanseri insidansında **%36**, kardiyovasküler mortalitede **%63–92** azalma. Yaş, cinsiyet ve sigaradan bağımsız | Gözlemsel; timus sağlığı değiştirilebilir mi, bu değişim riski değiştirir mi — gösterilmemiş |
| **Chreode** | arXiv:2605.28111 | 2,4M hücreli fare embriyonik atlası | Waddington ayrıştırmasıyla tek adımlı hücre durumu geçişi | Yetişkin insan dokusu değerlendirilmedi; **belirsizlik nicelemesi yok** |
| **Epic Sepsis Model (uyarıcı örnek)** | 2021 bağımsız değerlendirme | 38.455 hastane yatışı | 🔴 **2.552 sepsis hastasının %67'sini kaçırdı** | Ticari, yaygın kullanılan, dış doğrulaması yapılmamış bir modelin gerçek dünyada nasıl çöktüğünün kanonik örneği |

---

## 6.4 VERİ / DATASET DURUMU

Bu, damar B'nin en can sıkıcı tarafı ve dürüstçe konuşulması gerekiyor.

### Erişilebilirlik matrisi

| Veri kaynağı | Boylamsal? | Moleküler? | Erişim | Lisans öğrencisi için gerçekçi mi? |
|---|---|---|---|---|
| **UK Biobank** | ✅ 17+ yıl | ✅ Proteomik, DNAm, genomik | Kurumsal başvuru + ücret + etik onay | 🔴 Kurumsal destek olmadan **hayır** |
| **Danimarka ulusal kayıtları** | ✅ 40 yıl | ❌ | Danimarka kurumları | 🔴 Pratikte kapalı |
| **All of Us (NIH)** | ✅ | Kısmen | Researcher Workbench; kurumsal bağlılık + eğitim gerekli | 🟡 Kurum üzerinden mümkün |
| **MIMIC-IV** (PhysioNet) | ⚠️ **Sadece yoğun bakım — saatler/günler, yıllar değil** | ❌ | Ücretsiz; CITI eğitimi + DUA | 🟢 **Evet** — ama ufku B damarına uymuyor |
| **MIMIC-IV Demo** (AWS Open Data) | ⚠️ Aynı | ❌ | Tamamen açık, 100 hasta | 🟢 Evet (prototipleme için) |
| **ADNI** | ✅ Yıllar | ✅ MR, PET, BOS, kan biyobelirteçleri, bilişsel testler, genetik | Ücretsiz araştırmacı başvurusu | 🟢 **Evet — B damarı için en gerçekçi seçenek** |
| **NLST** (NCI/CDAS) | ✅ Yıllar | ❌ (ama BT var) | Ücretsiz başvuru | 🟢 **Evet — timus çalışmasının kullandığı veri** |
| **Framingham Heart Study** | ✅ On yıllar | Kısmen | BioLINCC başvurusu | 🟡 Mümkün |
| **Delphi kodu** | — | — | 🔓 GitHub'da açık | 🟢 Evet — **ama eğittiği veri kapalı** |

### 🔥 Veri probleminin çekirdeği

**Boylamsal + moleküler + erişilebilir: üçünden ikisini seçebilirsiniz.**

- Erişilebilir + boylamsal → ADNI, NLST (ama tek hastalık alanı, moleküler derinlik sınırlı)
- Boylamsal + moleküler → UK Biobank (ama erişilebilir değil)
- Erişilebilir + moleküler → GEO/TCGA (ama kesitsel, boylamsal değil)

### Az kullanılan bir çıkış: sentetik trajektoriler

Delphi-2M makalesinin en az konuşulan bulgusu şu: **yalnızca sentetik trajektorilerle eğitilen bir model, gerçek veride AUC 0,74 alıyor** (orijinal 0,77). Yazarlar bunu gizlilik argümanı olarak sunuyor, ama pratikte bu **veriye erişimi olmayan araştırmacılar için açık bir kapı** — ve bildiğim kadarıyla bu kapının üzerine metodoloji kurulmamış (bkz. 6.6, G5).

---

## 6.5 AÇIK PROBLEMLER (yazarların kendi belirttikleri)

Bunlar **benim çıkarımım değil** — her biri ilgili makalede veya sistematik derlemede açıkça yazıyor.

| # | Problem | Kanıt |
|---|---|---|
| **1** | **Ufuk uzadıkça performans düşüyor, ama düşüş standart olarak raporlanmıyor.** | Delphi: AUC 0,76 → 0,70 (10 yıl). ProRS: çoğu uç nokta için en iyi AUC **5 yıl içinde**. Ama hiçbiri "kalibrasyon hangi ufka kadar dayanıyor?" eğrisi vermiyor |
| **2** | **Kalibrasyon sistematik olarak ihmal ediliyor.** | Sistematik derlemeler: modellerin yalnızca **~1/3'ü** kalibrasyonu değerlendiriyor. ML tabanlı COVID prognoz modellerinde TRIPOD+AI uyumu **~%28** |
| **3** | **Dış doğrulama seyrek ve seçici.** | UKB-PPP: proteinin klinik modeli geçtiği 67 hastalığın **yalnızca 6'sı** dış kohortta test edilebildi |
| **4** | **Nedensellik yok — ve yazarlar bunu söylüyor.** | Delphi: *"temporal ordering does not imply the model is capable of identifying causal mechanisms in the sense of modifiable features"* |
| **5** | **Yüksek AUC düşük PPV'yi gizliyor.** | Alzheimer kan biyobelirteçleri: AUC %70,9–82,6 ve NPV >%90, ama PPV o kadar düşük ki yazarlar taramada kullanılamayacağını söylüyor; kombinasyonla ancak **%43** |
| **6** | **Rekabet eden riskler (competing risks) çoğunlukla ele alınmıyor.** | Rekabet eden olayı sansürleyen bir model, **o olayın hiç var olmadığı varsayımsal bir dünyanın riskini** tahmin ediyor. Etkisi kalibrasyon üzerinde ayrım gücünden daha büyük |
| **7** | **Ters nedensellik ile gerçek risk faktörü karıştırılıyor.** | UK Biobank Parkinson çalışması: düşük günlük adım sayısı Parkinson'un **öngörücüsü ama risk faktörü değil** — prodromal bir belirti. Aynı sorun "X yıl önce tahmin ediyoruz" iddialarının çoğunda var |
| **8** | **Eğitim verisinin yanlılığı öğreniliyor ve pekiştiriliyor.** | Delphi, UK Biobank'ın sağlıklı gönüllü yanlılığını ve hastane kaydı eksiklik örüntüsünü öğreniyor; yazarlar bunu açıkça gösteriyor |
| **9** | **Tahmin, sonucu iyileştirmiyor — bu gösterilmiş bir olgu.** | Büyük bir küme-randomize çalışmada hesaplanmış postoperatif bulantı/kusma riskinin hekimlere gösterilmesi **risk temelli yönetimi artırdı ama hasta sonucunu iyileştirmedi.** Genel çerçeve: *"Performance metrics for intervention-triggering prediction models do not reflect an expected reduction in outcomes from using the model"* (arXiv:2006.01752) ve *"On the Actionability of Outcome Prediction"* (arXiv:2309.04470) |
| **10** | **Gerçek dünyada çöküş kanıtlanmış.** | Epic Sepsis Model: 38.455 yatışta 2.552 sepsis hastasının **%67'sini kaçırdı** |

---

## 6.6 GERÇEK RESEARCH GAP

⚠️ **Bu bölüm tamamen benim analizimden çıkan çıkarımlardır.** Yukarıdaki 6.5 yazarların söyledikleridir; burası onların söylemedikleridir.

### G1 — "Güvenilir ufuk" diye standart bir kavram yok

Herkes **"X yıl önce tahmin ediyor"** diyor. Kimse **"hangi ufka kadar kalibrasyon ve PPV klinik olarak anlamlı kalıyor?"** diye bir eğri yayınlamıyor.

Elimizde olan: Delphi'nin AUC-ufuk eğrisi (0,76 → 0,70).
Elimizde olmayan: **kalibrasyon-ufuk eğrisi**, **PPV-ufuk eğrisi**, **net fayda (decision curve)-ufuk eğrisi.**

Bu boşluk büyük çünkü:
- AUC ufuk boyunca yavaş düşüyor (0,06 puan / 10 yıl) → "10 yıl öncesinden tahmin edebiliyoruz" izlenimi veriyor
- Ama PPV, olay oranı düştükçe (uzun ufuk = daha seyrek olay) **çok daha hızlı** çöküyor
- Yani AUC'ye bakarak "erken tahmin çalışıyor" demek, sistematik olarak yanıltıcı

**Bu boşluk ölçülebilir ve tek bir açık veri setinde gösterilebilir.**

### G2 — Ufka bağlı belirsizlik ve çekimserlik (abstention) yok

Damar A (güvenilirlik) ile Damar B (tahmin) burada kesişiyor ve **kesişim boş.**

Conformal prediction, OOD tespiti ve abstention literatürü var. Hastalık trajektorisi literatürü var. Ama:

> "Bu model 2 yıl için güvenilir bir aralık verebilir, 10 yıl için veremez — ve bunu kendisi söyleyebilir"

diyen bir sistem bulamadım. Chreode makalesi bunu kendisi itiraf ediyor: *"No uncertainty quantification yet… we do not currently calibrate or report posterior credible intervals."*

İlginç olan: **Ken'in kanalında "Weighted Conformal Prediction and PSI" videosu var** — yani o bu köprünün varlığını görmüş, ama ilaç tasarımı tarafında. Sağlık trajektorisi tarafında karşılığı yok.

### G3 — Prodromal tespit ile gerçek risk tahmini otomatik ayrılamıyor

Bir sinyal:
- **(a)** hastalığın zaten başlamış olmasının erken bir belirtisi mi (ters nedensellik / prodrom), yoksa
- **(b)** hastalıktan bağımsız, gerçek bir öncü risk faktörü mü?

Şu anda bu ayrım **elle, epidemiyolojik yorumla** yapılıyor (Parkinson–adım sayısı örneğinde olduğu gibi). 1.000+ hastalığı aynı anda tahmin eden Delphi gibi bir modelde bunu **her tanı için tek tek elle yapmak imkânsız.**

Yani: modelin ürettiği binlerce "erken sinyal"in hangilerinin prodromal artefakt olduğunu ayıklayacak sistematik bir yöntem yok. Delphi'nin SHAP analizi hangi geçmiş tanının riski artırdığını söylüyor ama **bunun mekanistik mi yoksa tanısal sıralama artefaktı mı olduğunu söylemiyor.**

### G4 — Fırsatçı görüntüleme çok az organ için denenmiş

Timus çalışması şunu kanıtladı: **zaten çekilmiş rutin bir BT**, çekilme nedeniyle tamamen ilgisiz bir konuda (tüm-neden mortalite, KVH, kanser) yıllar sonrasına dair güçlü bilgi taşıyor.

Ama bu yaklaşım şu ana kadar sayılı yapı için denenmiş. Rutin görüntülemede görünen ve yaşlanma/risk sinyali taşıyabilecek onlarca yapı var — ve her biri için soru aynı: **"bu yapının görünümü, hastanın 10 yıl sonrasını ne kadar öngörüyor?"**

🔥 **Bu, kullanıcının bilgisayarlı görü geçmişiyle Damar B arasındaki en doğrudan köprü** — ve Ken'in kendi sorusuyla birebir örtüşüyor: *"How can imaging biomarkers predict the risk of developing a disease?"*

Ama dikkat: fırsatçı görüntüleme çalışmaları **G1'in tuzağına** özellikle açık. Timus çalışmasında bile rapor edilen şey göreli risk azalması; ufka bağlı kalibrasyon veya PPV değil.

### G5 — Sentetik trajektori verisi bir metodoloji olarak kurulmamış

Delphi'nin sentetik verisiyle eğitilen model AUC 0,74 alıyor. Bu tek bir cümlelik bulgu, aslında şu soruyu açıyor:

> Kapalı bir kohorttan üretilmiş sentetik trajektoriler üzerinde geliştirilen yöntemler, gerçek veriye ne kadar transfer olur? Hangi tür bulgular transfer olur, hangileri olmaz?

Bu, veri erişimi olmayan araştırmacılar için ciddi bir kaldıraç olabilir — ama şu anda kimse bunun **sınırlarını haritalamamış.** Sentetik veride bulunan bir örüntünün gerçek olup olmadığını anlamanın standart bir yolu yok.

### G6 — Katmanlar birbirinden habersiz

6.2'deki dört katman büyük ölçüde ayrı literatürler:
- EHR dizisi modelleri moleküler veriyi kullanmıyor (Delphi yazarları bunu "gelecekteki değişiklikler için potansiyel" olarak not ediyor)
- Proteomik modeller hasta geçmişinin zamansal yapısını kullanmıyor
- Fırsatçı görüntüleme her ikisinden de habersiz
- Hücresel modeller (Chreode) insan hastalık trajektorisine hiç bağlanmamış — kendi yazarları yetişkin insan dokusunu değerlendirmediklerini söylüyor

APOLLO bu birleştirmeyi deniyor (28 modalite) ama **tek bir hastane sisteminde ve yeniden üretilemez ölçekte.**

---

## 6.7 ÖZET: Damar B'nin haritası

```
  ALANIN ÇÖZDÜĞÜ                      ALANIN ÇÖZMEDİĞİ
  ───────────────                     ─────────────────
  ✅ Ayrım gücü (AUC 0,70–0,85)       🔴 Kalibrasyon (%⅓ raporluyor)
  ✅ Ölçek (10⁷ hasta, 1.000+ hst.)   🔴 PPV (yüksek AUC'nin altında düşük)
  ✅ Çok-hastalık eşzamanlı tahmin    🔴 Nedensellik (yazarlar kabul ediyor)
  ✅ Moleküler sensörler (5–20 prot.) 🔴 Klinik fayda (RKÇ'de gösterilmedi)
  ✅ Fırsatçı görüntüleme kanıtı      🔴 Ufka bağlı güvenilirlik
                                       🔴 Prodrom vs. risk ayrımı
                                       🔴 Katmanlar arası entegrasyon

                            ↓
              GERÇEK BOŞLUK BURADA DURUYOR
                            ↓
   "Ne kadar erken tahmin edebiliriz?" sorusu çözüldü sayılır.
   "Ne kadar erken GÜVENİLİR tahmin edebiliriz?" sorusu hiç sorulmadı.
```

### Ken'in konumu ile alanın açığı örtüşüyor

Bu, bu aşamanın en önemli sonucu:

| Ken'in tekrar eden vurgusu | Alanın karşılık gelen açığı |
|---|---|
| Alzheimer gönderisinde **PPV'yi** vurgulaması | G1 — PPV-ufuk eğrisi yok |
| "Müdahaleyi tespit eden AI" sorusu (2023) | Açık problem #9 — tahmin sonucu iyileştirmiyor |
| Weighted conformal prediction ilgisi | G2 — ufka bağlı belirsizlik yok |
| Provenance / auditability takıntısı | Açık problem #8 — model veri yanlılığını öğreniyor |
| *"How can imaging biomarkers predict the risk of developing a disease?"* | G4 — fırsatçı görüntüleme az işlenmiş |

**Ken'in Damar A takıntısı ile Damar B ilgisi ayrı iki şey değil.** Aynı sorunun iki yarısı, ve alanın gerçek boşluğu tam olarak bu ikisinin kesişiminde.

---

## Hâlâ yapmadığımız şey

Bu belge **proje fikri içermiyor.** Sıradaki mantıklı adımlar:

- **A damarı** (Trustworthy / Auditable AI) için aynı derinlikte inceleme
- **C damarı** (Autonomous AI / Agents for Science) için aynı derinlikte inceleme
- Üç damar karşılaştırıldıktan **sonra** kullanıcının profiliyle kesişim analizi
- En son: proje/araştırma yönü seçimi
