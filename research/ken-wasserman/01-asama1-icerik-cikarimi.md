# 1. AŞAMA — İçeriklerin Çıkarılması

## 1.1 Kim olduğunun doğrulanması

🟢 **A — Doğrulandı** (LinkedIn profil ve gönderi arşivi üzerinden):

| Alan | Bilgi |
|---|---|
| Ad | Ken Wasserman, PhD |
| LinkedIn | `linkedin.com/in/ken-wasserman-3b1147216` |
| Ünvan | **Assistant Professor (Emekli / "Retired")**, Georgetown University School of Medicine |
| Görev süresi | Ağustos 2012 – Eylül 2023 (11 yıl 1 ay) |
| Konum | Leesburg, Virginia, ABD |
| Doktora | Georgetown University School of Medicine |
| Kendi yayın sayısı | ~20–30 akademik çalışma |
| Kendi araştırma alanları | İmmün hücre fonksiyonu ve etkileşimi, immünoterapi ve immün yanıtlar, hücre adezyon molekülleri, kemokin reseptörleri ve sinyalizasyon, kanserde anjiyogenez ve VEGF |
| En çok bilinen çalışması | *"Human endothelial cells express CCR2 and respond to MCP-1: direct role of MCP-1 in angiogenesis and tumor progression"* |
| Profilinde kullandığı etiketler | `#biochemistry #cellbiology #immunology #healthspan #lifespan #AI #ML #systemsanalysis #food #retired` |

⚠️ **Dikkat:** Arama sonuçlarında çok benzer içerikli ikinci bir profil de var (`ken-wasserman-09a14569`, "Assistant Professor at Georgetown University", 1979'da NIH'te lisans stajyeri olarak başlayan 40+ yıllık kariyer, Trevigen geçmişi, 2012'den beri Biyokimya ve Moleküler & Hücresel Biyoloji bölümünde). Tarihler ve kurum birebir örtüştüğü için **muhtemelen aynı kişinin ikinci profili**, ancak bunu kesin olarak doğrulayamadım. Üçüncü bir "Ken Wasserman" profili (Trevigen, Gaithersburg MD, Pittsburgh doktoralı) **farklı bir kişi olabilir** — birleştirmedim.

**Analitik önem:** Ken'in kendi akademik geçmişi **yapay zeka değil, immünoloji/hücre biyolojisi/biyokimya.** YouTube kanalındaki yapay zeka ağırlıklı içerik, kendi araştırma üretimi değil, **emeklilik sonrası bir bilim küratörlüğü faaliyeti.** Bu, kanalın karakterini anlamak için belirleyici.

---

## 1.2 KRİTİK BULGU: Videoların üretim formatı (birincil kanıt)

🟢 **A — Doğrulandı.** Ken'in LinkedIn gönderi arşivi, videoların nasıl üretildiğini birebir gösteriyor. **Her video, tek bir yayımlanmış makale üzerine kurulu ve şu şablonu izliyor:**

```
Perplexity: "…"   veya   NotebookLM: "…"
   ↓
[tek bir makalenin yapay zeka tarafından üretilmiş özeti]
   ↓
🔗 https://lnkd.in/<makale bağlantısı>
   ↓
watch: https://lnkd.in/<Ken'in YouTube videosu>
```

Yani Ken'in kullanıcıya söylediği:

> *"avail yourself of the provided links to the published papers that serve as source materials for my YouTube posts"*

cümlesi **tam anlamıyla doğru ve sistematik.** Her videonun altında gerçekten bir makale bağlantısı var — ama bu bağlantılar YouTube listesinde değil, **LinkedIn gönderilerinde.**

### Doğrulanmış gönderi → video eşleşmeleri

Aşağıdaki eşleşmelerde LinkedIn gönderi URL'i (slug), gönderi tarihi ve PDF'teki video tarihi birbirini tutuyor:

| LinkedIn gönderi tarihi | Gönderi/Pulse başlığı | Kaynak makale/araç | PDF'teki video |
|---|---|---|---|
| 2026-09-05 | PathFold: Predicting the entire protein… | PathFold (+PathScorer, Φ-değeri karşılaştırması) | "PathFold Protein Folding AI" (2 gün önce) |
| 2026-09-03 | `generating-medical-image-counterfactuals` | **arXiv:2609.02697** | "How Pixels and Counterfactuals Test Medical AI" (4 gün önce) |
| 2026-09-02 | `packora-systematic-design-for-generative` | Packora (kristal yapı tahmini) | "From Flat Chemical Drawing to Pill" (5 gün önce) |
| 2026-08-31 | `closed-loop-bayesian-molecular-inverse-design` | BoMolLLM | "BoMoLLM Molecular Design" (7 gün önce) |
| 2026-08-30 | `for-psi-neural-operators-are-essential` | Nöral operatörler | "Overcoming the Transformer Wall for PSI" (8 gün önce) |
| 2026-08-19 | `how-mega-cl-contributes-to-pharmaceutical` | MEGA-CL (ADMET) | "MEGA CL for ADMET Prediction" (2 hafta önce) |
| 2026-06-30 | The Prescriptive Health Loop… | — | "The Prescriptive Health Loop…" |
| 2026-06-27 | Predicting Disease Via Cellular Aging AI | Plazma proteomiği + hücresel yaşlanma | "Predicting Disease Via Cellular Aging AI" |
| 2026-06-26 | **Using Chreode AI to Map the Rate of Disease Onset Years Prior to Overt Symptoms** | Optimal Transport tabanlı yöntem | "Using AI to Map the Rate of Disease Onset Years Prior to Overt Symptoms" |
| 2026-06-26 | AI Doctors on Smartphones | **Google AMIE** | "AI Doctors on Smartphones" |
| 2026-06-24 | "Predicting Immune Biomarkers with MultiModal Mixture-of-Expert Pathology Foundation Models…" | (başlığın kendisi bir makale başlığı) | — |
| 2026-06-22 | Scaling Quantum Architectures Via Qumus AI Experimentalists | Qumus | "Scaling Quantum Architectures Via AI Qumus Experimentalists" |
| 2026-06-20 | Assembling a Co-Scientist that Runs on Your Laptop | **C3P** (Contrastive Promoter-Protein Pretraining) | "Assembling a Co-Scientist that Runs on Your Laptop" |
| 2026-06-20 | How Tiny AI is Mighty Enough to Model Gene Expression | **C3P** (aynı kaynak) | "How Tiny AI is Mighty Enough to Model Gene Expression" |
| 2026-06-18 | Why 99 percent of Healthcare AI is Built to Fail | (NotebookLM özeti; kaynak makale doğrulanamadı ⚫) | "Why 99 percent of Healthcare AI is Built to Fail" |
| 2026-06-18 | How to Employ Starling AI to Overcome Flawed Data | **Starling** (22,5 milyon PubMed makalesinden otonom veri seti kurma) | "How to Employ StarlingAI to Overcome Flawed Data" |
| 2026-06-16/18 | Binding Prediction in Dynamic Confirmation States | **AlloGen** ve **OmniInvent** | "Binding Prediction in Dynamic Confirmation States" |
| 2025-12-15 | Trio / FRAGPT + MCTS | arXiv, 10 Ara 2025 | — |
| 2025-09-24 | MedAgentBench hakkında | **MedAgentBench (NEJM AI)** | — |
| 2025-09-18 | ChemBOMAS | arXiv, 10 Eyl 2025 | — |

**Not:** İki farklı video ("Assembling a Co-Scientist…" ve "How Tiny AI is Mighty Enough…") **aynı kaynak makaleden (C3P)** üretilmiş. Aynı şekilde "Binding Prediction in Dynamic Confirmation States" başlığı iki kez, iki farklı araç (OmniInvent, AlloGen) için kullanılmış. Bu, kanaldaki bazı tekrarların açıklaması.

---

## 1.3 Ken'in kullanıcıya DOĞRUDAN gönderdiği içerikler

Bu, talebin 6. maddesinin ("Ken tarafından açıkça paylaşılmış, bağlantısı verilmiş veya referans gösterilmiş akademik makaleler") tek gerçek kaynağı. Hepsi DOCX'ten geliyor.

| # | Ken'in gönderdiği | Bağımsız doğrulama |
|---|---|---|
| 1 | "Welcome and food for thought" + bir AI videosu | ⚫ Hangi video olduğu belirtilmemiş |
| 2 | "Already installed in 300 hospitals" | ⚫ Hangi sistem/makale olduğu belirtilmemiş |
| 3 | **"Responsiveness of epigenetic aging biomarkers to longevity interventions"** | 🟢 **A** — *Nature Medicine* (2026), PubMed 42629466, DOI `10.1038/s41591-026-04562-9`. Ön baskı: bioRxiv `10.1101/2024.10.22.619522` |
| 4 | **Chreode AI** — hastalık başlangıcını belirtilerden yıllar önce haritalama | 🟢 **A** — Ken'in 26 Haz 2026 tarihli LinkedIn Pulse makalesi tam olarak bu: *"Using Chreode AI to Map the Rate of Disease Onset Years Prior to Overt Symptoms"*, Optimal Transport temelli. **Ayrı bir aday:** arXiv:2605.28111 *"Chreode: A Cell World Model"* — aynı isim, ama farklı odak (bkz. Aşama 2, dikkat notu) |
| 5 | **Pharmaceutical Superintelligence (PSI)** | 🟢 **A** — Ken'in kendi geliştirdiği çatı kavram; kanalda 72 video bu başlık altında |
| 6 | Retinal fundus görüntüleri / çoklu organ | 🟡 **B** — Ken'in kendi videolarında retina spesifik bir başlık yok; muhtemelen dış bir makale |
| 7 | Tıbbi görüntü counterfactual'ları | 🟢 **A** — Ken 3 Eyl 2026'da tam olarak bunu paylaştı (arXiv:2609.02697) |
| 8 | **"Adversarial prompt and fine-tuning attacks threaten medical large language models"** | 🟢 **A** — *Nature Communications* 16:9011 (2025), DOI `10.1038/s41467-025-64062-1`, PMID 41068092 |
| 9 | Video: **"What AI Can See in Medical Scans That Doctors Can't"** — konuk **Anant Madabhushi, PhD** | 🟢 **A** (video) / 🟡 **B** (bölüm tarihi) — "AI and Healthcare" podcast'i (sunucular: Dr. Sanjay Juneja, Dr. Doug Flora). **Madabhushi, Emory University ve Georgia Institute of Technology'de (Wallace H. Coulter Biyomedikal Mühendisliği) profesördür — Georgetown'da DEĞİL.** Bölüm açıklaması: rutin BT'lerdeki gizli sinyaller, retinal görüntüler, patoloji slaytları, tedavi yanıtı tahmini, tümör damarları ve çevre doku örüntüleri, açıklanabilirlik, klinik doğrulama, sağlıkta eşitlik |
| 10 | "apply to China" + Çin'in üst düzey teknoloji yayınlarındaki payını gösteren grafik | 🟡 **B** — Kullanıcının aktarımı; grafiğin kaynağı bilinmiyor |
| 11 | **Ken'in kendi proje önerisi:** düşük kaynaklı ortamda sağlık çalışanının kullandığı retinal tarayıcı + akıllı telefon uygulaması + AI'ın tespit ettiği hastalık durumunun *adversarial prompting* ile doğrulanması | 🟡 **B** — Kullanıcının aktarımı, ancak Ken'in 8. maddedeki makaleyi hemen ardından göndermesi bu öneriyi bağlamsal olarak destekliyor |
| 12 | **Talimat:** *"avail yourself of the provided links to the published papers that serve as source materials for my YouTube posts"* | 🟢 **A** — Ve 1.2'de gösterildiği gibi bu talimat sistematik olarak doğru |

### ⚠️ DOCX'te yer alan, doğrulayamadığım / hatalı olan iddialar

DOCX'teki ChatGPT çıktısında geçen ve **bu raporun kabul etmediği** noktalar:

- Anant Madabhushi'nin Georgetown ile ilişkilendirilmesi → **Yanlış.** Emory + Georgia Tech.
- "Georgetown AI CoLab", "Georgetown Research Opportunities Database", "AI Fellows", "Georgetown Global Health AI projeleri" → ⚫ Bu raporda doğrulanmadı, kullanılmadı.
- "Madabhushi Lab'da Eshan Momin adlı bir lisans öğrencisi var" → ⚫ Doğrulanmadı.
- Ken'in "Chreode AI" ile kastettiğinin arXiv:2605.28111 olduğu → 🟡 Kısmen; Ken'in kendi makalesi Optimal Transport'a odaklanıyor, arXiv:2605.28111 ise perturbasyon tahmini. **Aynı olmayabilirler.**
- APOLLO, GraphMERT, GenSeg, MedAgentBench'in "Ken'in videolarının kaynağı" olduğu → Bunların bir kısmını bağımsız olarak doğruladım (bkz. Aşama 2), ama DOCX'teki iddianın kendisi kanıt değildi.

---

## 1.4 338 videonun konu kümelerine göre dağılımı (başlıklardan)

Her video için "ana konu" ataması yalnızca başlıktan yapılabilir. Aşağıda kanalın tamamının nicel dağılımı verilmiştir (bir video birden fazla kümeye girebilir):

| Konu kümesi | Video sayısı | Oran |
|---|---:|---:|
| Pharmaceutical Superintelligence / prompt-to-drug / moleküler tasarım | 72 | 21% |
| Yaşlanma / longevity / rejuvenasyon | 86 | 25% |
| AI ajanları / co-scientist / otonom bilim | 36 | 11% |
| **Güvenilir / denetlenebilir / dayanıklı tıbbi AI** | **30** | **9%** |
| Genomik / epigenetik / varyantlar / omics | 34 | 10% |
| LLM / muhakeme / neurosymbolic / AGI | 34 | 10% |
| Metabolik sağlık / GLP-1 / obezite / diyabet / mikrobiyom | 30 | 9% |
| Kanser / immüno-onkoloji (NK, CAR-T, tümör) | 26 | 8% |
| Protein yapısı / katlanma / protein AI | 20 | 6% |
| Semptom öncesi tahmin / trajektori / sanal hasta | 20 | 6% |
| Kuantum hesaplama | 17 | 5% |
| Tiny AI / akıllı telefon / cihaz üstü / demokratikleşme | 18 | 5% |
| Alzheimer / beyin / nöro | 13 | 4% |
| **Tıbbi görüntüleme / radyoloji / patoloji (bilgisayarlı görü)** | **4** | **1%** |

### 🚨 Bu tablodaki en önemli tek bulgu

**Klasik tıbbi görüntüleme / bilgisayarlı görü, kanalın yalnızca ~%1'i (338 videoda 4).** Bunlar:

1. *How Pixels and Counterfactuals Test Medical AI*
2. *Neurosymbolic AI Radiology and Set Distance Rewards*
3. *Mapping Tumors with Spatial Omics and AI*
4. *Spatial Omics for Disease Pathology and Aging*

Ken'in ağırlık merkezi **moleküler/hesaplamalı ilaç tasarımı ve yaşlanma biyolojisi**; görüntüleme onun için merkezi bir konu değil. Kullanıcıya retinal görüntüleme fikrini vermesi bu genel dağılıma göre bir **istisna**, ana ilgi alanının yansıması değil — bu ayrım 5. Aşama'da önemli olacak.
