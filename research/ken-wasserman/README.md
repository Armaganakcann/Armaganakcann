# Ken Wasserman — Sistematik Araştırma Analizi

**Tarih:** 8 Eylül 2026
**Girdi:** `5_KEN_WASSERMAN__YouTube.pdf` (49 sayfa, kanal listesi) + `Chat_20260908.docx` (50 mesajlık ChatGPT sohbeti)
**Durum:** 1–5. aşamalar tamamlandı. **Proje fikri üretilmedi** (talep gereği).

## Dosyalar

| Dosya | İçerik |
|---|---|
| [`00-metodoloji-ve-kanit-durumu.md`](00-metodoloji-ve-kanit-durumu.md) | Kaynakların gerçekte ne içerdiği, kanıt seviyesi etiketleri (🟢A / 🟡B / 🔴C / ⚫), analizin bilinen sınırları |
| [`01-asama1-icerik-cikarimi.md`](01-asama1-icerik-cikarimi.md) | Ken'in kimliğinin doğrulanması, **videoların üretim formatının çözülmesi**, Ken'in kullanıcıya doğrudan gönderdikleri, 338 videonun konu dağılımı |
| [`02-asama2-kaynak-makaleler.md`](02-asama2-kaynak-makaleler.md) | A/B/C kategorilerinde kaynak makaleler, künyeler, DOI'ler |
| [`03-asama3-makale-analizleri.md`](03-asama3-makale-analizleri.md) | 8 makalenin 9 soruluk analizi; **bulgu / yazarın sınırlaması / benim çıkarımım** kesin ayrımıyla |
| [`04-asama4-tekrar-eden-temalar.md`](04-asama4-tekrar-eden-temalar.md) | Nicel frekans analiziyle tekrar eden temalar tablosu + zamansal kayma |
| [`05-asama5-arastirma-deseni.md`](05-asama5-arastirma-deseni.md) | Araştırma deseni, yöntem repertuvarı, epistemik duruş, kanıt yetersizliği beyanları, harita |
| [`06-damar-B-hastalik-trajektorisi.md`](06-damar-B-hastalik-trajektorisi.md) | **Damar B derin inceleme:** hastalık trajektorisi ve semptom öncesi tahmin — mevcut durum, dünyadaki çalışmalar, veri erişilebilirliği, açık problemler, gerçek research gap'ler |
| [`07-damar-A-guvenilir-denetlenebilir-ai.md`](07-damar-A-guvenilir-denetlenebilir-ai.md) | **Damar A derin inceleme:** trustworthy/auditable AI — kalibrasyon, PPV/taban oranı, belirsizlik ve çekimserlik, doğrulama, denetlenebilirlik; ve **A↔B hipotezinin testi** |
| [`08-G2-G7-falsifikasyon.md`](08-G2-G7-falsifikasyon.md) | **G2/G7'yi öldürme denemesi:** dört iddia düşman gözüyle test edildi — ikisi öldü, biri büyük ölçüde öldü, biri daraltılmış hâlde ayakta |
| [`veri/videolar.tsv`](veri/videolar.tsv) | PDF'ten ayrıştırılmış 338 video (başlık, izlenme, göreli tarih) |

## En kritik 5 bulgu

1. **Videoların üretim formatı çözüldü.** Her video, tek bir yayımlanmış makale üzerine kurulu. Ken makaleyi Perplexity/NotebookLM'e verip özetini LinkedIn'de makale linkiyle birlikte yayınlıyor, sonra aynı içerikten video üretiyor. **Aradığımız "kaynak makale linkleri" YouTube'da değil, Ken'in LinkedIn gönderilerinde.** 20'den fazla gönderi→video eşleşmesi birincil kanıtla doğrulandı.

2. **Ken emekli bir immünolog.** Georgetown University School of Medicine'da 2012–2023 Assistant Professor. Kendi alanı immünoterapi/hücre adezyonu/anjiyogenez. Kanal, kendi araştırma üretimi değil, **emeklilik sonrası bilim küratörlüğü.**

3. **Tıbbi görüntüleme/bilgisayarlı görü kanalın yalnızca %1'i (338'de 4 video).** Ken'in kullanıcıya retinal görüntüleme fikri vermesi, kendi gündeminin değil, muhtemelen kullanıcının beceri setinin yansıması. Onun kendi katkısı fikrin **etrafındaki** iki tema: adversarial doğrulama + düşük kaynaklı erişim. *(6. Aşama'da rafine edildi: Ken görüntülemeyle tanı görevi olarak değil, **risk/prognoz sensörü** olarak ilgileniyor — bkz. `06-…md` §6.0.)*

4. **En istikrarlı tema "modele neden güvenelim?"** Sayıca %9 ama Ken'in kullanıcıya doğrudan gönderdiği iki akademik makalenin **ikisi de** bu temada. Bir konu değil, tüm konularına uyguladığı bir filtre.

5. **338 videonun ~%7'si için kaynak doğrulanabildi.** Geri kalanı için "kaynak makale şudur" demek spekülasyon olur — raporda böyle bir iddia yapılmadı.

## Doğrulanmış temel kaynaklar (Kategori A — Ken açıkça paylaştı)

- Kelly, Yaacov, Blake, Beckers, Chockler — *Generating Medical Image Counterfactuals using Causal Explanations* — arXiv:2609.02697 (King's College London + UCL, 2 Eyl 2026)
- Yang, Jin, Huang, Lu — *Adversarial prompt and fine-tuning attacks threaten medical large language models* — *Nat Commun* 16:9011, DOI 10.1038/s41467-025-64062-1 (NIH/NLM + UMD)
- *Responsiveness of epigenetic aging biomarkers to longevity interventions in humans* — *Nature Medicine* 2026, DOI 10.1038/s41591-026-04562-9
- Jiang, Black, Chen, Zou, Geng, Park, Ng ve ark. — *MedAgentBench* — *NEJM AI*, DOI 10.1056/AIdbp2500144 (Stanford)
- *The Illusion of Readiness: Stress Testing Large Frontier Models on Multimodal Medical Benchmarks* — arXiv:2509.18234
- *Towards conversational AI for disease management* (Google AMIE) — *Nature* 2026, DOI 10.1038/s41586-026-10764-5
- Anant Madabhushi (Emory + Georgia Tech) — "AI and Healthcare" podcast bölümü *"What AI Can See in Medical Scans That Doctors Can't"*

## Damar derinlemesine incelemeleri (6. Aşama)

Araştırma haritası çıkarıldıktan sonra, haritadaki güçlü damarlar tek tek inceleniyor. **Hâlâ proje fikri üretilmiyor.**

| Damar | Durum | Dosya |
|---|---|---|
| **B — Hastalık trajektorisi / semptom öncesi tahmin** | ✅ Tamamlandı | `06-damar-B-hastalik-trajektorisi.md` |
| **A — Trustworthy / Auditable AI** (B ile kesişimde) | ✅ Tamamlandı | `07-damar-A-guvenilir-denetlenebilir-ai.md` |
| **G2/G7 falsifikasyon turu** | ✅ Tamamlandı | `08-G2-G7-falsifikasyon.md` |
| **Veri gerçekliği haritası** | ⏸️ **Şu an buradayız** | — |
| **C — Autonomous AI / Agents for Science** | ⏳ Sonra | — |

### Damar B'nin tek cümlelik sonucu

> "Ne kadar erken tahmin edebiliriz?" sorusu büyük ölçüde çözüldü. **"Ne kadar erken GÜVENİLİR tahmin edebiliriz?"** sorusu hiç sorulmadı.

### Damar A'nın tek cümlelik sonucu (hipotez testi)

> **Sonuç 2 — kısmen birleşiyor.** A'nın yöntemleri B'nin problemini çözmek için var ve teorik olarak uygun (conformalized survival analysis bunun literal kanıtı), **ama yanlış ufukta test edilmişler**: sepsis saatleri, triyaj günleri, 30 günlük yeniden yatış. Çok-yıllık çok-hastalık modellerine hiç uygulanmamışlar. Ken de bu köprüyü kurmamış — güvenilirliği tıbbi AI'da, konformal belirsizliği ilaç tasarımında tutuyor.

### Falsifikasyon turunun sonucu

Boşluk hayatta — **ama %70 küçüldü.** Ölen kısım: "yeni kavram / yeni çerçeve" iddiası (ufka bağlı değerlendirme meteoroloji, ekoloji, salgın tahmini ve landmarking'de yerleşik; "forecast horizon limit" kavramının formal tanımı ekolojide zaten var). Yaşayan kısım:

> Ufka bağlı değerlendirme yerleşik bir pratiktir, ancak uzun vadeli **bireysel** klinik risk tahminine **karar-ilgili güvenilirlik metrikleriyle birlikte** (kalibrasyon + kapsama + PPV + net fayda) taşınmamıştır — ve taşındığında ne olacağına dair mevcut iki ampirik ipucu birbiriyle çelişmektedir.

## Sonraki adım

Zincir:
`İÇERİKLERİ TOPLA ✅ → KAYNAK MAKALELERİ DOĞRULA ✅ → MAKALELERİ ANALİZ ET ✅ → TEKRAR EDEN TEMALARI BUL ✅ → ARAŞTIRMA HARİTASINI ÇIKAR ✅ → DAMAR B ✅ → DAMAR A ✅ → BOŞLUĞU ÖLDÜRMEYE ÇALIŞ ✅ → veri gerçekliği ⏸️ → C damarı ⏳ → proje seçimi ⏳`

Hâlâ seçilmedi: hastalık ❌ · veri seti ❌ · model ❌ · mimari ❌
