# 5. AŞAMA — Ken Wasserman'ın Araştırma Deseni

Her sonuç, dayandığı kanıtla birlikte verilmiştir. Kanıt yetersizse açıkça belirtilmiştir.

---

## Soru 1 — Hangi problemlere tekrar tekrar dönüyor?

### 1a. "Bir modelin çıktısına neden güvenelim?" — en istikrarlı damar

**Kanıt:**
- 🟢 Kanalda en az 30 video bu temada (%9), ve oran **yükseliyor** (%4 → %9).
- 🟢 Ken'in kullanıcıya *doğrudan gönderdiği* iki akademik makaleden **ikisi de** bu temada: adversarial LLM saldırıları (Nat Commun 2025) ve counterfactual görüntü denetimi (arXiv:2609.02697).
- 🟢 Kendi yorumu (18 Eki 2025, "The Illusion of Readiness" paylaşımında): *"Physicians that employ #AI need to stay alert: Will A.I. lead to de-skilling of physicians?"*
- 🟢 MedAgentBench paylaşımında (24 Eyl 2025) vurgusu performans değil **kırılganlık**: *"Modeller bilgi almada iyi. Eylem gerçekleştirmede kırılgan… Bugünün modelleri gerçek dünya iş akışları için yeterince güvenilir değil."*
- 🟢 Counterfactual paylaşımında (3 Eyl 2026) kendi ekliyor: *"Counterfactual'lar, ikna edici görseller yerine test edilebilir denetim vakaları yarattıklarında özellikle yararlı olur. Klinik olarak alakasız bir değişiklik tahmini çeviriyorsa ya da patolojiyi kaldırmak çevirmiyorsa, bu somut bir başarısızlıktır."*

**Sonuç:** Bu, Ken'in **tek bir konusu değil, tüm konularına uyguladığı bir filtre.** İlaç tasarımından (CRITIC, conformal prediction, IsoDDE veri sızıntısı), tıbbi görüntülemeye (counterfactual denetim), ajanlara (traceable reasoning) kadar her yerde aynı soruyu soruyor.

### 1b. "Snapshot değil, süreç" — hastalığı belirtilerden önce yakalamak

**Kanıt:**
- 🟢 En az 20 video başlığında açıkça "years before / decades before / prior to overt symptoms / trajectory / forecasting" geçiyor.
- 🟢 Ken kullanıcıya *doğrudan* "Chreode AI — disease onset years before overt symptoms" gönderdi ve buna kendi Pulse makalesini yazdı (26 Haz 2026), Optimal Transport üzerinden.
- 🟢 Aynı fikir farklı ölçeklerde tekrar ediyor: hücresel (Chreode, hücresel yaşlanma AI), organ (organ yaşlanma saatleri), hasta (APOLLO / sanal hasta), popülasyon.

**Sonuç:** Bu, kanalın **kavramsal omurgası.** Yaşlanma, hastalık tahmini ve nedensel tıp temaları hepsi buradan besleniyor.

### 1c. "Ölçek değil, mimari" — büyük LLM'lere metodolojik itiraz

**Kanıt:**
- 🟢 En az 12 video doğrudan "tiny beats giant" argümanını taşıyor.
- 🟢 GraphMERT paylaşımı: 80M parametreli model, LLM temel çizgisini FActScore'da %40 → %70'e çıkarıyor.
- 🟢 "Overcoming the Transformer Wall for PSI" ve "For PSI, neural operators are essential" gönderisi: *"Transformerlar doğal dil ve görüde devrim yaptı, ama fiziksel gerçeklikle karşılaştıklarında temel hesaplamalı ve matematiksel bariyerlerle karşılaşıyorlar."*
- 🟢 "A Hierarchical Neurosymbolic Multi-Agent System to Achieve AGI" (252 izlenme — kanalın en çok izlenen 6. videosu).

### 1d. "Provenance" — AI bunu nereden çıkardı?

**Kanıt:**
- 🟢 OptimusKG video etiketleri arasında birebir: *"agentic validation, gene transcript, data provenance"*.
- 🟢 GraphMERT'in seçilme gerekçesi tam olarak halüsinasyon + provenance.
- 🟢 DeepRare'de vurguladığı özellik "traceable reasoning".
- 🟢 "Medical AI Needs an Audit Trail and Adversarial Prompt Resistance" başlığı bunu birebir söylüyor.

---

## Soru 2 — En sık hangi tür akademik araştırmaları paylaşıyor?

🟢 **Doğrulanmış yayın türü profili:**

| Tür | Örnekler | Gözlem |
|---|---|---|
| **Yeni araç/model tanıtan ön baskılar (arXiv/bioRxiv)** | Chreode, GraphMERT, APOLLO, Packora, BoMolLLM, MEGA-CL, PathFold, AlloGen, Protenix, ChemBOMAS, Trio, counterfactual (2609.02697) | **Baskın tür.** Genellikle **yayınlandıktan günler sonra** paylaşıyor (örn. arXiv 2 Eyl → gönderi 3 Eyl → video 4 Eyl) |
| **Üst düzey dergi makaleleri** | *Nature* (AlphaGenome, DeepRare, AMIE), *Nature Medicine* (epigenetik saatler), *Nature Communications* (adversarial LLM, GenSeg), *Nature Biotechnology* (Folddisco, CellWhisperer), *Nature Genetics* (popEVE), *NEJM AI* (MedAgentBench), *Nature Aging* (organ saatleri) | Var ama arXiv'e göre azınlıkta |
| **Benchmark ve stres testi çalışmaları** | MedAgentBench, The Illusion of Readiness, HealthBench/VITA | Küçük ama Ken için orantısız önemli |
| Klinik çalışmalar / RKÇ | — | ⚫ **Neredeyse yok.** Kanalda tek bir randomize kontrollü çalışma paylaşımı tespit edemedim |
| Derleme/meta-analiz | Epigenetik saatler makalesi (51 çalışma harmonizasyonu) | Nadir |

🔥 **Kritik gözlem:** Ken **hakemli klinik kanıttan çok, hesaplamalı yenilik ön baskılarını** paylaşıyor. Bu, "güvenilirlik takıntısı"yla ilginç bir gerilim yaratıyor: metodolojik titizlik istiyor, ama beslendiği kaynakların çoğu henüz hakem sürecinden geçmemiş.

---

## Soru 3 — Hangi araştırmacılar, üniversiteler veya laboratuvarlar tekrar ediyor?

⚠️ **Bu, sorunun en zayıf kanıtlı kısmı.** Kanal listesinde hiç kurum/araştırmacı adı geçmiyor; aşağıdakiler doğrulanmış kaynak makalelerin künyelerinden geliyor ve **yalnızca ~25 video için** doğrulama var. Yani bu bir örneklem, tam sayım değil.

**Birden fazla kez ortaya çıkanlar:**

| Kurum / grup | Kaç kez | Kanıt |
|---|---|---|
| **Stanford** | ≥3 | MedAgentBench (Stanford ML Group — Jonathan H. Chen, James Zou, Andrew Ng), MIRAGE (Euan Ashley), CheXpert/AIMI ekosistemi |
| **Google / DeepMind** | ≥2 | AMIE + RxQA, AlphaGenome |
| **Princeton** | 1 | GraphMERT (Niraj K. Jha grubu) |
| **King's College London** | 1 (ama 2 makale zinciri) | Counterfactual (Chockler, Kelly) + altyapısı ReX |
| **Harvard / Broad** | 1 | popEVE (Debora Marks) |
| **NIH / NLM** | 1 | Adversarial LLM saldırıları (Zhiyong Lu) |
| **Emory + Georgia Tech** | 1 (ama kullanıcıya doğrudan gönderildi) | Anant Madabhushi |
| **ByteDance** | 1 | Protenix |
| **UNC Chapel Hill / UT Austin / UPenn** | 1 | Chreode |
| **CeMM (Avusturya)** | 1 | CellWhisperer |

**Adı geçen tek tek araştırmacılar:**
- 🟢 **Anant Madabhushi** — Ken bu kişinin yer aldığı bir podcast bölümünü kullanıcıya doğrudan gönderdi. Bu, kanaldaki hiçbir videoda geçmeyen, **kullanıcıya özel** bir yönlendirme.
- 🟢 **Alex Zhavoronkov** (Insilico Medicine) — Ken 9 Eyl 2025'te onun bir gönderisini yeniden paylaştı. PSI teması Insilico'nun "prompt-to-drug" vizyonuyla akraba.

⚫ **Sonuç: Tekrar eden tek bir laboratuvar veya araştırmacı yok.** Ken belirli bir grubu takip etmiyor; **konuyu takip ediyor.** Bu önemli bir negatif bulgu — "Ken'in çevresine girmek" diye bir strateji, bu kanıtla desteklenmiyor.

---

## Soru 4 — Hangi teknolojiler veya yöntemler sürekli tekrar ediyor?

🟢 **Doğrulanmış, tekrar eden yöntem repertuvarı:**

| Yöntem ailesi | Nerede tekrar ediyor |
|---|---|
| **Çok-ajanlı LLM sistemleri** | PSI mimarisi, DeepRare, MedAgentBench, Starling, ChemBOMAS, co-scientist videoları, "AI Agent Suites" serisi |
| **Bilgi grafiği + provenance** | OptimusKG, GraphMERT, iKraph, "34 million abstract haystack" |
| **Belirsizlik nicelemesi / conformal prediction** | "Weighted Conformal Prediction and PSI", "AI Validation Engine", BoMolLLM yorumu (*"weighted conformal prediction ile eşleştirmek, belirsiz veya dağılım-dışı adayların agresif biçimde ilerletilmesini önleyebilir"*) |
| **Nedensellik / counterfactual / müdahale** | "The Evolution of Causal Medicine", counterfactual görüntüleme, "Proteomic Root Causal Disease Susceptibility", Chreode'un Waddington ayrıştırması |
| **Kontrastif ön eğitim** | MEGA-CL (100M molekül), C3P, CellWhisperer |
| **Difüzyon / akış tabanlı üretim** | Packora (kristal yapı), PathFold (katlanma yolağı), MoPaDi karşılaştırması |
| **Küçük/uzman modeller** | GraphMERT (80M), Tiny AI serisi, "Gemma 4 4b and PSI" |
| **Geometrik derin öğrenme / eşdeğerlik (equivariance)** | "Equivariance Unlocks Molecular Modeling", "AI Designing Molecules with Physics and Symmetry", AlloGen'in SE(3)-değişmez skorlayıcısı |
| **Temel modeller (foundation models)** | APOLLO, Protenix, patoloji MoE modelleri |
| **Optimal Transport** | Chreode Pulse makalesi, "Mapping Cell Reprogramming with Optimal Transport Equations" |
| **Epigenetik saatler / DNAm biyobelirteçleri** | En az 10 video + kullanıcıya gönderdiği Nature Medicine makalesi |

⚫ **Kanalda belirgin şekilde YOK olanlar** (negatif bulgu, kullanıcı için önemli):
- Klasik denetimli tıbbi görüntü sınıflandırma / segmentasyon (U-Net, Dice skoru vb.) — 338 videoda ~0
- Federated learning
- Klinik uygulama/deployment çalışmaları, sağlık ekonomisi
- Randomize kontrollü çalışmalar

---

## Soru 5 — Paylaşımlarının altında ortak bir araştırma yaklaşımı var mı?

🟢 **Evet, ve bu yaklaşım birincil kanıtla gösterilebilir.**

### 5a. Üretim metodolojisi (doğrulanmış)

```
Yeni bir makale çıkar (çoğunlukla arXiv/bioRxiv, gün içinde)
        ↓
Ken makaleyi Perplexity veya NotebookLM'e verir
        ↓
Çıkan özeti LinkedIn'de yayınlar + 🔗 makale linki
        ↓
Aynı içerikten bir YouTube videosu üretir + "watch:" linki
        ↓
Videoyu, kendi çatı çerçevesi "PSI"a bir katkı olarak konumlandırır
```

Bu, **günde ~1,1 videoluk üretim hızını** ve son 3 aydaki video kısalmasını (4–9 dk) açıklıyor.

### 5b. Zihinsel model: **sistem mühendisliği, konu takibi değil**

Ken tekil makaleleri "ilginç haber" olarak sunmuyor. Her birini bir **mimarideki boşluğa** yerleştiriyor. Bunun en net kanıtı AlloGen makalesinde kendi yazdığı üç maddelik yapı:

> *"1. Otonom Tasarım için Modüler Rehberlik (Domain 3) … 2. CRITIC Zeminleme Çerçevesi için Yeni Bir Boyut … 3. 'Learning-by-Doing' Paradigması için Fiziksel Çeviri"*

Yani soru **"bu makale ne buldu?"** değil, **"bu makale benim inşa ettiğim sistemin hangi boşluğunu kapatıyor?"**

### 5c. Tekrar eden epistemik duruş: "verify-then-correct"

- CRITIC döngüsü ("verify-then-correct"), conformal prediction, counterfactual denetim, provenance'lı KG, adversarial dayanıklılık — hepsi aynı duruşun farklı teknik ifadeleri.
- Ken'in kendi cümlesiyle (counterfactual gönderisi): *"İşin zor kısmı, önerilen değişikliğin anatomik olarak makul olup olmadığına karar vermek — ki bu bir hekimin bakmasını gerektiriyor. Kendi testlerimizde iki inceleyicinin en çok anlaşamadığı yer burası, ve anlaşmazlık gürültü değil bilgilendirici çıkıyor."*

Bu cümle Ken hakkında iki şey söylüyor: (a) uzman-döngüde (expert-in-the-loop) yaklaşımı savunuyor, (b) **kendisi de bir şeyler test ediyor** ("in our own testing").

### 5d. Çelişki / gerilim (dürüst gözlem)

⚠️ Ken'in yaklaşımında içsel bir gerilim var ve bunu belirtmek dürüstlük gereği:

| Savunduğu | Uyguladığı |
|---|---|
| Metodolojik titizlik, external validation, hakemli kanıt | Ağırlıklı olarak **hakem sürecinden geçmemiş ön baskılar** paylaşıyor |
| AI halüsinasyonlarına ve LLM özetlerine güvensizlik | Videolarının içeriğini **Perplexity/NotebookLM özetlerinden** üretiyor |
| Derinlemesine doğrulama | Günde ~1 video hızında üretim |

Bu, onu değersizleştirmez — ama kanalın **bir literatür taraması değil, bir keşif akışı** olduğunu gösterir. Ken'in kullanıcıya *"videoları izleme, kaynak makalelere in"* demesi de tam olarak bunun farkında olduğunu gösteriyor.

---

## Soru 6 — Ken kullanıcıya neden retina/görüntüleme fikri verdi? (kritik uyumsuzluk)

Bu, analizin en önemli bulgularından biri ve dikkatle ele alınması gerekiyor.

**Olgu 1:** 🟢 Kanalda tıbbi görüntüleme/bilgisayarlı görü **338 videoda 4** (%1). Tekrar eden tema değil.
**Olgu 2:** 🟢 Ken kullanıcıya somut olarak "düşük kaynaklı ortamda retinal tarayıcı + akıllı telefon uygulaması + adversarial prompting ile doğrulama" önerdi.
**Olgu 3:** 🟢 Kullanıcı Ken'e kendini "deep learning ve computer vision ile sağlıkta AI projeleri yapan" biri olarak tanıttı.

**En makul yorum (🟡 çıkarım, kesin değil):**
Ken bu fikri **kendi araştırma gündeminden değil, kullanıcının beceri setinden türetmiş olabilir.** Kendi tarafından katkısı, ona ait olan üç şey: (a) düşük kaynaklı erişim/demokratikleşme teması, (b) adversarial doğrulama teması, (c) akıllı telefon üzerinde AI teması. Görüntüleme kısmı kullanıcıdan geliyor.

**Bunun pratik anlamı:** Ken'le konuşurken, retinal görüntüleme fikrinin kendisi değil, onun **etrafına sardığı iki tema** (adversarial doğrulama + düşük kaynaklı erişim) asıl ilgi çekecek kısımdır. Bu, kanıtla desteklenen bir çıkarım.

---

## Yeterli kanıtın OLMADIĞI konular (açık beyan)

Aşağıdaki sorular soruldu ama **kanıtla cevaplanamıyor:**

| Soru | Durum |
|---|---|
| Ken şu anda aktif bir araştırma projesi yürütüyor mu? | ⚫ **Yeterli kanıt yok.** LinkedIn'de "Retired" yazıyor; 2023'ten sonra yeni akademik yayını tespit edilmedi |
| Georgetown'da erişebileceği bir laboratuvar/merkez var mı? | ⚫ **Yeterli kanıt yok.** DOCX'teki "Georgetown AI CoLab" iddiası doğrulanmadı |
| Bir topluluğu, öğrenci grubu veya araştırma ağı var mı? | ⚫ **Yeterli kanıt yok** |
| Kullanıcıya bir işbirliği teklifi yaptı mı? | 🟢 **Hayır.** DOCX'teki tüm mesajlarında yönlendirme var, davet yok |
| "Apply to China" ile tam olarak ne kastetti? | ⚫ **Belirsiz.** Kullanıcı bunu kendisi sordu, cevabın tamamı DOCX'te yok |
| Kanalın "Podcast'ler" ve "Oynatma listeleri" sekmelerinde ne var? | ⚫ PDF'te yok |
| Videoların gerçek izleyici kitlesi kim? | ⚫ 405 abone, videolar tipik olarak 10–150 izlenme. **Kanal küçük.** Bu, Ken'in bunu bir yayın faaliyeti olarak değil, muhtemelen kendi düşünme/arşivleme aracı olarak kullandığına işaret edebilir (🟡 çıkarım) |

---

## Özet: Ken Wasserman Araştırma Haritası

```
                    KEN'İN ÇATI TEZİ
              "Pharmaceutical Superintelligence"
        (prompt'tan ilaca tam otonom bilimsel kaskad)
                          │
     ┌────────────────────┼────────────────────┐
     │                    │                    │
     ▼                    ▼                    ▼
 NE İNŞA EDİLİYOR    NASIL GÜVENİLİR      KİM ERİŞEBİLİR
                       KILINIR
     │                    │                    │
 • Çok-ajanlı        • Provenance / KG    • Tiny AI
   AI sistemleri     • Conformal pred.    • Akıllı telefon
 • Moleküler         • Counterfactual     • Düşük kaynaklı
   üretim/tasarım      denetim              ortamlar
 • Protein AI        • Adversarial        • Açık kaynak
 • Nöral operatörler   dayanıklılık       • "$20'ya COVID
 • Neurosymbolic     • External             nötralizörü"
                       validation
     │                    │                    │
     └────────────────────┼────────────────────┘
                          ▼
              UYGULANDIĞI BİYOLOJİK ALAN
                          │
     ┌────────────┬───────┴───────┬────────────┐
     ▼            ▼               ▼            ▼
 YAŞLANMA    SEMPTOM ÖNCESİ   İMMÜNO-      METABOLİK
 (%25)       TAHMİN (%6)      ONKOLOJİ     (%9, sönüyor)
             "snapshot değil,  (%8, Ken'in
              süreç"           kendi alanı)

  ── AYRIK ADA: Kuantum hesaplama (%5, sağlıkla zayıf bağ)
  ── NEREDEYSE YOK: Tıbbi görüntüleme / bilgisayarlı görü (%1)
```
