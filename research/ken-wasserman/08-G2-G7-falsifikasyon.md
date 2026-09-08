# 8. AŞAMA — G2/G7'yi Öldürme Denemesi (Falsifikasyon Turu)

**Görev:** Boşluğu savunmak değil, **öldürmeye çalışmak.** Dört soru soruldu, dördü de düşman gözüyle araştırıldı.
**Sonuç önizlemesi:** 🔴 **İki iddia öldü. Bir iddia büyük ölçüde öldü. Bir iddia daraltılmış hâlde ayakta kaldı.**

---

## 8.0 SKOR TABLOSU

| # | İddia | Sonuç |
|---|---|---|
| **1** | "Ufka göre metrik raporlamak yeni bir fikir" | 🔴 **ÖLDÜ** |
| **2** | "Tahmin ufku limiti diye yerleşik bir kavram yok" | 🔴 **ÖLDÜ** |
| **3** | "Konformal tahmin zamansal + popülasyon kayması altında test edilmemiş" | 🟠 **BÜYÜK ÖLÇÜDE ÖLDÜ** |
| **4** | "Tam güvenilirlik yığını (ayrım + kalibrasyon + kapsama + PPV + net fayda) uzun ufuklu **bireysel** klinik risk tahmininde birlikte raporlanmıyor" | 🟢 **AYAKTA** (ama daraltılmış) |

---

## 8.1 SORU 1 — "Horizon-dependent uncertainty" literatürde nasıl ele alınmış?

### 🔴 İDDİA ÖLDÜ. Üç ayrı literatür bunu zaten rutin olarak yapıyor.

#### Öldüren kanıt 1 — Salgın tahmini toplulukları

**COVID-19 Forecast Hub** değerlendirme raporları, tahminleri **ufka göre ayrıştırarak** şunları raporluyor:
- **Weighted Interval Score (WIS)** — *"absolute error'un bir genellemesi; tahmin dağılımı ile gözlenen veri arasındaki mesafeyi, hem **kalibrasyonu** hem **keskinliği** yansıtacak şekilde ölçüyor"*
- **Tahmin aralığı kapsaması (PI coverage)** — %50 ve %95 seviyelerinde, **ufka göre** (1–4 hafta ileri)
- Skorlar son 10 hafta ve 52 haftalık geçmiş için ayrı toplanıyor → **zaman içindeki performans değişimi izlenebiliyor**

Yani "ufka göre kapsama + kalibrasyon raporla" fikri **zaten standart pratik.**
Kaynak: `covid19forecasthub.org/eval-reports`; *Evaluating epidemic forecasts in an interval format*, PLOS Comput Biol (WIS'in tanımı).

#### Öldüren kanıt 2 — Sağkalım analizinde landmarking / dynamic prediction

**van Houwelingen (2007) landmark modelleme** çerçevesi ve ardılları, birden çok ufukta rutin olarak şunları raporluyor:
- **Zamana bağlı AUC (tdAUC)** — tahmin zamanındaki ayrım gücü
- **Zamana bağlı Brier skoru** — IPCW ile sansür için ağırlıklandırılmış ortalama kare hata; Kaplan-Meier'e göre yüzde azalma olarak da veriliyor

Yani "birden çok ufukta ayrım + kalibrasyon raporla" da **yerleşik pratik.**
Kaynak: *Dynamic Prediction by Landmarking in Event History Analysis*; JRSS-A 184(1):3; *Estimation of incident dynamic AUC in practice*, CSDA.

#### 🚨 Öldüren kanıt 3 — Ve bu, klinik risk tahmininde birebir yapılmış

**Simon, Mandair, Albakri, Fohner, Simon, Lange, Biggs, Mukamal, Psaty, Rosenberg — "The Impact of Time Horizon on Classification Accuracy: Application of Machine Learning to Prediction of Incident Coronary Heart Disease"**, *JMIR Cardio*, 9 Ağustos 2022, PMC9669890. (University of Colorado, University of Washington, Beth Israel Deaconess; NIA/NHLBI/NINDS fonlu.)

Yaptıkları tam olarak G2'nin deney tasarımı:
- Kardiyovasküler sağlık çalışmasından **5.201 katılımcı** (analize giren 4.190), tek klinik ziyaretten **61 değişken**
- **500–10.000 gün** arasında değişen ufuklarda gerçekleşen miyokard enfarktüsünü tahmin etmek üzere eğitilmiş modeller (random forest, L1 regresyon, gradient boosted trees, SVM, k-NN), **ufuklar üzerinde döngü kurularak**
- 10.000 günlük takipte **813 olay**
- Framingham cinsiyete özgü Cox modeliyle karşılaştırma

📄 Bulguları: ML modelleri **orta ufuklarda en tahmin edici** (1.500–2.500 gün). En iyi model L1 (Lasso) lojistik regresyon, **1.500 günde AUROC 0,71**. En etkili değişkenler ufka göre değişiyor.

**Yani "ufuk uzadıkça klinik risk modelinin performansı nasıl değişiyor?" sorusu 2022'de sorulmuş ve cevaplanmış.** Bu, G2'nin orijinal hâlini öldürüyor.

#### ⚠️ Ama bu makale neyi yapmamış? (S1'in tohumu burada)

| Metrik | Simon ve ark. 2022 |
|---|---|
| AUROC ufka göre | ✅ |
| Kalibrasyon ufka göre | ❌ |
| Konformal kapsama ufka göre | ❌ |
| PPV ufka göre | ❌ |
| Net fayda ufka göre | ❌ |
| Dış doğrulama | ❌ (tek kohort, %20 held-out) |

---

## 8.2 SORU 2 — "Reliable prediction horizon" kavramı zaten var mı?

### 🔴 İDDİA ÖLDÜ. Kavram var, adı da var — sadece başka alanlarda.

| Kavram | Alan | Tanım | Kaynak |
|---|---|---|---|
| **Ecological forecast horizon / forecast limit** | Ekoloji | *"Forecast limit, tahmin kalitesinin bir referans modelden daha iyi olmadığı — ya da varsa önceden tanımlanmış bir standardın altına düştüğü — an olarak tanımlanır."* | Petchey ve ark., *The Ecological Forecast Horizon, and examples of its uses and determinants*; Wesselkamp ve ark., *Methods in Ecology and Evolution* 2025, DOI `10.1111/2041-210X.70049` — potansiyel, mutlak ve göreli sistem öngörülebilirliği |
| **Predictability limit / horizon of predictability** | Meteoroloji, kaotik sistemler | Kararsız bir sistemde hafifçe farklı başlangıç durumlarına sahip yörüngelerin sonlu öngörülebilirliği. **Hava için ~iki hafta.** Hataların üstel birikimi nedeniyle kırılamaz bir sınır | Lorenz geleneği; ScienceDaily 2019 özeti |
| **Forecastability profile** | Zaman serisi / bilgi teorisi | Gelecekteki gözlem ile mevcut bilgi kümesi arasındaki **karşılıklı bilgi**; logaritmik kayıp altında herhangi bir tahmincinin ulaşabileceği maksimum beklenen log-kayıp azalmasına eşit. **Ufka özgü tavan.** Ayrıca "exploitability ratio" ile sınırlı bilgiden kaynaklanan kayıp ile kusurlu modellemeden kaynaklanan kaybı ayırıyor | Peter M. Catt, *Forecastability Profiles: Horizon-Specific Limits to Prediction Before Model Selection*, Research Square rs-9882043, 1 Haz 2026 (**ön baskı, hakem sürecinde**); ayrıca *Forecastability as an Information-Theoretic Limit on Prediction*, arXiv:2603.27074 |
| **Temporal horizons / performance-learnability trade-off** | ML forecasting | — | arXiv:2506.03889 |
| **Prediction horizon (h)** | Klinik ML | Sepsis başlangıcından ne kadar önce tahmin yapılmaya çalışıldığı; çok-ufuklu tahmin ICU'da erken uyarı ile yanlış alarm arasında denge kurmak için kullanılıyor | Yerleşik kullanım |

**Sonuç:** "Reliable prediction horizon"u yeni bir kavram olarak ilan edersek **tekerleği yeniden icat etmiş oluruz.** Kullanıcının uyarısı yerindeydi.

### ⚠️ Ama burada ince ama gerçek bir fark var (S2)

Yerleşik tanımların hepsi **beceri (skill)** kriteri kullanıyor:

> *forecast limit = tahmin kalitesinin bir referans modelden daha iyi olmadığı an*

Bu, "model hâlâ bir şey biliyor mu?" sorusudur. Klinik karar için gereken kriter **farklı**:

| Kriter türü | Soru | Yerleşik mi? |
|---|---|---|
| **Beceri (skill)** | Model temel çizgiden iyi mi? | ✅ Ekoloji, meteoroloji, salgın tahmini |
| **Bilgi tavanı** | Bu ufukta ne kadar bilgi mevcut? | ✅ Forecastability profiles |
| **Güvenilirlik** | Modelin **olasılık çıktısına** güvenebilir miyim? (kalibrasyon) | ❌ Ufka göre klinik risk tahmininde yok |
| **Klinik fayda** | Bu ufukta **karar eşiğinde** PPV/net fayda anlamlı mı? | ❌ Yok |

Bir model temel çizgiden iyi olabilir (beceri kriteri geçer) ama **kalibrasyonu bozuk ve PPV'si karar eşiğinin altında** olabilir. Ekolojinin forecast limit'i bunu yakalamaz.

Bu ayrım gerçek ve S2'nin temeli. Ama "yeni kavram" değil, **mevcut kavramın farklı bir kritere göre uyarlanması.**

---

## 8.3 SORU 3 — Konformal tahmin, zamansal + popülasyon kayması + uzun ufuk üçlüsü altında test edilmiş mi?

### 🟠 BÜYÜK ÖLÇÜDE ÖLDÜ — ilk iki bileşen test edilmiş.

**Öldüren kanıt:** *Conformal selective prediction with cost aware deferral for safe clinical triage under distribution shift*, **Scientific Reports 2026**, DOI `10.1038/s41598-026-40637-w`, PMID 41721063.

Bu makale beklediğimden çok daha fazlasını yapıyor:
- **Zamansal olarak ayrılmış** geliştirme ve değerlendirme kohortları kullanıyor
- Hem **dağılım-içi** hem **dağılım-dışı** test bölmelerinde ölçüyor
- 📄 *"Temporal separation between development and evaluation cohorts introduces **measurable but controlled** degradation in calibration and cost."*
- 📄 *"Coverage stays close to the nominal 90% target in-distribution and **degrades only slightly** out-of-distribution, with the **weighted method most robust**."*
- 📄 **Weighted conformal prediction**, kalibrasyon skorlarını hedef kovaryat dağılımına doğru yeniden ağırlıklandırarak bu etkiyi hafifletiyor
- Seçici erteleme tutulan vakalarda hatayı %80 kapsamada **ID'de %49,6, OOD'de %46,7** azaltıyor

Ayrıca ilgili yeni yöntemler: *Drift-Aware Spectral Conformal Prediction for Non-Exchangeable Streaming Data* (arXiv:2606.15953), *KMM-CP: Practical Conformal Prediction under Covariate Shift via Selective Kernel Mean Matching* (arXiv:2603.26415), *Conformal Prediction Intervals with Temporal Dependence*.

### 🚨 AMA: İki şey hâlâ ayakta

**(a) Ufuk.** Bu çalışma **erken sepsis** üzerinde — ufuk **saatler**. Çok-yıllık ufukta aynı sonucun çıkacağının garantisi yok.

**(b) Üçüncü kayma boyutu: sansürleme.** Uzun ufuk = ağır sansürleme. Sepsiste bu problem yok. Conformalized Survival Analysis (Candès, Lei, Ren) sansürlemeyi çözüyor ama zamansal sürüklenme veya kohort kayması altında test edilmemiş.

```
        SANSÜRLEME    ZAMANSAL SÜRÜKLENME    KOHORT KAYMASI
Conformalized
Survival (2023)    ✅              ❌                  ❌
Sci Rep sepsis
(2026)             ❌              ✅                  ✅
Bir arada          ⚫              ⚫                  ⚫
```

### 🔥 Ve şu çelişki gerçek bir açık soru

| Çalışma | Ortam | Kapsama sonucu |
|---|---|---|
| Sci Rep 2026 (sepsis) | Zamansal + OOD kayma, saatler | *"degrades only slightly"*, weighted CP en sağlam |
| Eniolade CKD (arXiv:2605.21566) | Prevalans kayması + öznitelik eksikliği | **0,80–0,98 → 0,21–0,25** (hedef 0,90) — **çöküş** |

İki çalışma **taban tabana zıt** sonuç veriyor. Bu, üzerine araştırma kurulabilecek bir gerilim.

### ⚠️ Ama CKD çalışmasını fazla ciddiye almamak için bir uyarı

Kendi kanıtıma karşı dürüst olmam gerek: CKD çalışmasında **beş modelin hepsi iç testte AUROC 1,00** alıyor. Bu, veri setinin **önemsiz derecede ayrılabilir** olduğunun klasik işareti (UCI CKD, n=400). Dış küme MIMIC-IV **demo** (n=97). Yani gözlenen çöküş, kısmen "oyuncak veri setinden gerçek veriye geçiş" artefaktı olabilir — gerçek bir kayma etkisi değil.

**Bu, kullanıcının kendi uyarısının doğruluğunu kanıtlıyor:** dataset shift ile horizon effect'i ayırmazsak yanlış sonuç çıkarırız. CKD çalışması bu ayrımı yapmıyor.

---

## 8.4 SORU 4 — Tam metrik yığını, uzun ufuklu bireysel klinik risk tahmininde birlikte raporlanıyor mu?

### 🟢 BU İDDİA AYAKTA — ve öldürmeye çalıştıkça daha net hâle geldi.

Her literatür yığının **bir parçasını** ufka göre veriyor, ama hiçbiri tamamını vermiyor:

| Literatür | Ayrım | Kalibrasyon | Kapsama | PPV | Net fayda | Ufuk ekseni | Birey düzeyi |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Salgın tahmin hub'ları | ✅ | ✅ (WIS) | ✅ | ❌ | ❌ | ✅ 1–4 hafta | ❌ **popülasyon** |
| Landmarking / dynamic prediction | ✅ tdAUC | ✅ Brier | ❌ | ❌ | ❌ | ✅ | ✅ |
| Simon ve ark. 2022 (MI) | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ 500–10.000 gün | ✅ |
| Sci Rep 2026 (sepsis) | ✅ | ✅ | ✅ | ❌ | ✅ (maliyet) | ❌ tek ufuk | ✅ |
| Hoessly 2026 | — | ✅ | ❌ | ✅ | ✅ | ❌ **eşik ekseni** | ✅ |
| Eniolade CKD 2026 | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ tek ufuk | ✅ |
| Delphi-2M | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ (yalnız AUC) | ✅ |
| **Aranan** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ **yıllar** | ✅ |

**Bulunamayan:** Çok-yıllık, bireysel düzeyde bir klinik risk modelinde bu beş metriğin **aynı ufuk ekseni üzerinde** birlikte raporlandığı bir çalışma. ⚫

Hoessly 2026'nın konumu özellikle öğretici: PPV ↔ kalibrasyon ↔ net fayda bağını **kuruyor**, ama ekseni **eşik**. Ufka taşınmamış.

---

## 8.5 REVİZE EDİLMİŞ PROBLEM İFADESİ

Kullanıcının 6.1 aşamasında koyduğu aday problem ifadesi:

> ~~"Uzun vadeli hastalık tahmin modellerinde, tahmin ufku uzadıkça güvenilirlik ve belirsizliğin nasıl değiştiğine ilişkin **standart ve sağlam bir değerlendirme çerçevesinin olmaması**."~~

**Bu ifade artık savunulamaz.** Ufka bağlı değerlendirme çerçeveleri var (WIS+coverage, tdAUC+Brier, forecast limit, forecastability profile). Falsifikasyondan sağ çıkan hâli:

> **Ufka bağlı değerlendirme, tahmin bilimlerinde (meteoroloji, ekoloji, salgın tahmini) ve sağkalım analizinde (landmarking) yerleşik bir pratiktir. Ancak bu pratik, uzun vadeli *bireysel* klinik risk tahminine, *karar-ilgili güvenilirlik metrikleriyle birlikte* (kalibrasyon + kapsama + PPV + net fayda) taşınmamıştır. Taşındığında ne olacağına dair mevcut iki ipucu birbiriyle çelişmektedir.**

Farkı görmek önemli:
- ❌ "Kimse ufka bakmıyor" → yanlış
- ❌ "Ufuk limiti kavramı yok" → yanlış
- ✅ "Yerleşik bir pratik, ihtiyaç duyulduğu yere **karar kriteriyle birlikte** taşınmamış" → şu ana kadar doğrulanamayan tek iddia

### Bu daha zayıf mı? Evet. Daha kötü mü? Hayır.

Aslında bu **daha iyi bir araştırma konumu**, çünkü:
- Sıfırdan kavram icat etmiyor → hakem "bu neden gerekli?" diye sorduğunda cevap var
- Yerleşik yöntemlere (WIS, tdAUC, IPCW-Brier, weighted CP, decision curve) **yaslanıyor** → metodolojik temel hazır
- İki çelişen ampirik sonuç (sepsis vs CKD) → **cevaplanabilir somut bir soru**
- Simon ve ark. 2022 bir **şablon** sunuyor: aynı kohortta ufuklar üzerinde döngü. Onlar yalnız AUROC yaptı; eksik dört metrik ekleme yeri belli

---

## 8.6 KULLANICININ DENEY TASARIMI DEĞERLENDİRMESİ

Kullanıcının önerdiği dört deneyle kaymaları izole etme fikri **doğru ve literatürle uyumlu.** Güncel durum:

| Deney | Kullanıcının tanımı | Literatürdeki durum |
|---|---|---|
| **1** | Aynı kohort, farklı ufuklar → **ufuk etkisi** | 🟠 **Simon ve ark. 2022 bunu yaptı** — ama yalnız AUROC ile. Kalibrasyon/kapsama/PPV/net fayda ile tekrarı yapılmamış |
| **2** | Farklı zaman dilimi, aynı popülasyon → **zamansal sürüklenme** | 🟠 Sci Rep 2026 sepsis bunu yaptı (saatler ufkunda). Uzun ufukta yok |
| **3** | Farklı kohort/hastane → **kohort kayması** | 🟢 Yaygın (Delphi-2M Danimarka, UKB-PPP EPIC-Norfolk) — ama kapsama metriğiyle değil |
| **4** | Hepsi birlikte → **üçlü kayma** | ⚫ **Yok.** Ve sansürleme dördüncü boyut olarak eklenmeli |

🔥 **Yani en yüksek katma değer Deney 1'in metrik olarak genişletilmesinde ve Deney 4'te.** Deney 3 tek başına yeni değil.

---

## 8.7 VERDİKT

### Boşluk hayatta mı? **Evet — ama %70 küçüldü.**

**Ölen kısım:** "Yeni bir kavram / yeni bir çerçeve" iddiası. Bu bir yeniden-icat olurdu.

**Yaşayan kısım:** Yerleşik ufuk-bazlı değerlendirme pratiğinin, uzun vadeli bireysel klinik risk tahminine karar-ilgili güvenilirlik metrikleriyle taşınmamış olması — ve taşındığında ne olacağına dair çelişkili iki ipucu.

### Devam etmeye değer mi?

Kanıta dayalı görüşüm: **evet**, üç nedenle:

1. **Somut ve cevaplanabilir.** "Ufka göre kalibrasyon/kapsama/PPV nasıl bozuluyor?" ölçülebilir bir sorudur; felsefi değil.
2. **Şablonu var.** Simon ve ark. 2022 deney iskeletini vermiş; eksik olan metrik katmanı.
3. **Ampirik gerilim var.** Sepsis çalışması "kapsama sadece biraz bozulur" diyor, CKD çalışması "çöker" diyor. Bu boşluğu doldurmak gerçek bir katkı.

### Ama iki ciddi risk

| Risk | Neden |
|---|---|
| **⚠️ Ufuk etkisi ile kayma etkisinin karışması** | Kullanıcının kendi uyardığı tuzak. CKD çalışması tam olarak buna düşmüş görünüyor (AUROC 1,00 → oyuncak veri seti şüphesi). Deney tasarımı bunu izole etmezse sonuç yorumlanamaz |
| **⚠️ Uzun ufuk + nadir olay = küçük etkili kalibrasyon seti** | Kladny ve ark.'nın eleştirisi. 10 yıllık ufukta konformal kalibrasyon seti pratikte çok küçülebilir. Bu, çalışmanın **bulgusu** olabilir — ama bunu bilerek tasarlamak gerekir |

---

## Bu belge hâlâ proje fikri içermiyor

Sıradaki adım (kullanıcının 6.2 planı): **veri gerçekliği haritası.** Eğer boşluk buraya kadar geldiyse, şimdi "biz bunu gerçekten yapabilir miyiz?" sorusu.

Hâlâ seçilmedi: hastalık ❌ · veri seti ❌ · model ❌ · mimari ❌
