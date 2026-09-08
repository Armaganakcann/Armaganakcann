# Ken Wasserman Araştırma Analizi — Metodoloji ve Kanıt Durumu

**Tarih:** 8 Eylül 2026
**Kapsam:** Verilen iki belgeye (YouTube kanal listesi PDF'i + ChatGPT sohbet kaydı DOCX'i) dayalı sistematik analiz + bağımsız web/akademik kaynak doğrulaması.
**Not:** Bu aşamada proje fikri üretilmemiştir. Talep edildiği gibi yalnızca 1–5. aşamalar yürütülmüştür.

---

## 1. Elimizdeki kaynaklar ve bu kaynakların GERÇEKTE ne içerdiği

### Kaynak A — `5_KEN_WASSERMAN__YouTube.pdf` (49 sayfa)

Bu bir YouTube kanal *listeleme* sayfasının çıktısı. İçerdiği alanlar:

| Alan | Var mı? |
|---|---|
| Video başlığı | ✅ Var (bazıları "…" ile kesik) |
| Video süresi | ✅ Var |
| İzlenme sayısı | ✅ Var |
| Göreli yükleme tarihi ("2 ay önce") | ✅ Var |
| **Video açıklaması** | ❌ **YOK** |
| **Makale bağlantısı / kaynak linki** | ❌ **YOK** |
| **Transkript** | ❌ **YOK** |
| **Ekran görüntüsü / görsel içerik** | ❌ **YOK** |

**Kritik sonuç:** Kullanıcı talebindeki 1. Aşama'nın 4., 5. ve 6. maddeleri (bahsedilen araştırmacılar, kurumlar, Ken tarafından açıkça paylaşılmış makaleler) **bu PDF'ten çıkarılamaz.** PDF'te tek bir araştırmacı adı, kurum adı veya makale bağlantısı geçmiyor. Bu bilgiler için PDF dışı, bağımsız kaynaklara gidildi ve her biri ayrıca etiketlendi.

Ayrıştırma sonucu: **338 video girdisi**. Kanal başlığı 339 video olduğunu belirtiyor. Listede en az 6 çift kayıt var (ör. "The Evolution of Causal Medicine" ×2, "Impacts of AI on Peer Review" ×2, "Binding Prediction in Dynamic Confirmation States" ×2, "SFRP2 Antibody Reprograms TNBC Immune Attack" ×2) — bunlar muhtemelen aynı içeriğin yeniden yüklenmiş versiyonları.

Zaman aralığı: en eski girdi ~10 ay önce (Kasım 2025), en yenisi 4 saat önce (8 Eylül 2026). Yani **~10 ayda ~339 video ≈ günde ortalama 1,1 video.**

### Kaynak B — `Chat_20260908.docx` (50 mesaj)

Bu **Ken Wasserman'ın içeriği değil.** Bu, kullanıcı ile ChatGPT arasındaki Türkçe bir sohbetin dışa aktarımı. Analiz açısından iki farklı değerde bilgi içeriyor:

| İçerik türü | Kanıt değeri |
|---|---|
| Kullanıcının Ken'den aldığı LinkedIn mesajlarını aktarması | 🟡 **İkinci el ama birincil kaynağa yakın** — kullanıcı kendi konuşmasını aktarıyor, ancak ekran görüntüleri bu dışa aktarımda görünmüyor ("The output of this plugin was redacted") |
| Ken'in kullanıcıya doğrudan yazdığı cümlelerin alıntıları | 🟡 Aynı şekilde ikinci el |
| ChatGPT'nin Ken hakkındaki yorumları, iddiaları ve "citeturn0search…" referansları | 🔴 **Doğrulanmamış** — kaynak bağlantıları dışa aktarımda kaybolmuş, ChatGPT'nin kendisi de sohbet içinde iki kez geri adım atıyor ("bazı makaleleri Ken'in videolarının kesin kaynakları gibi ifade etmek için yeterli doğrulama yoktu") |
| ChatGPT'nin proje fikirleri | ⚪ Bu analizin kapsamı dışında (talep gereği) |

**Bu ayrımı analiz boyunca koruyorum.** DOCX'teki ChatGPT iddialarını, kendi bağımsız doğrulamamı yapmadan hiçbir yerde olgu olarak kullanmadım.

---

## 2. Kanıt seviyesi etiketleri

Bu raporda her iddia aşağıdaki etiketlerden biriyle işaretlenmiştir:

| Etiket | Anlamı |
|---|---|
| 🟢 **A — Doğrudan kanıt** | Ken'in kendi yayınladığı bir gönderi/makale ile makale arasındaki bağ birincil kaynaktan doğrulandı (LinkedIn gönderi URL'i, gönderi başlığı, tarih eşleşmesi), VEYA Ken'in kullanıcıya gönderdiği makale adı bağımsız olarak doğrulandı |
| 🟡 **B — Güçlü eşleşme** | Video başlığı/konusu bir yayınla güçlü şekilde örtüşüyor ve tarihler tutarlı, ancak Ken'in tam olarak o yayına link verdiğini birebir doğrulayamadım |
| 🔴 **C — Yalnızca konu benzerliği** | Aynı alanda yayın; Ken'in kaynağı olduğuna dair kanıt yok. Bu rapor bunları "Ken'in kaynağı" olarak SUNMAZ |
| ⚫ **Kanıt yok** | Yeterli kanıt bulunamadı; açıkça öyle belirtildi |

---

## 3. Kullanılan doğrulama yöntemi

1. PDF'ten 338 video başlığı programatik olarak ayrıştırıldı ve temizlendi (`videos_clean.tsv`).
2. DOCX'ten Ken'in gönderdiği somut içerikler (makale adları, video adları, kendi cümleleri) ayıklandı.
3. Ken'in gerçek LinkedIn hesabı ve gönderi arşivi bağımsız olarak arandı ve bulundu → **bu, kaynak makale zincirini doğrulamanın anahtarı oldu.**
4. Her aday makale için: arXiv/PubMed/Nature/bioRxiv üzerinden başlık, yazar, kurum, DOI, tarih doğrulandı.
5. Başlıklar üzerinde nicel tema frekans analizi yapıldı (5. Aşama için objektif kanıt).

---

## 4. Analizin bilinen sınırları

- Videoların **hiçbirini izlemedim**; transkript veya açıklama metnine erişimim yok. Video içeriğine dair tüm çıkarımlar başlık + Ken'in aynı başlıklı LinkedIn gönderisinden geliyor.
- LinkedIn içeriğine giriş yapmadan erişilebildiği kadarıyla ulaşıldı; bazı gönderilerin tam metni ve `lnkd.in` kısa linklerinin hedefleri açılamadı.
- Kullanıcı–Ken LinkedIn yazışmasının ekran görüntüleri DOCX dışa aktarımında silinmiş. Ken'in mesajları yalnızca kullanıcının/ChatGPT'nin aktardığı kadarıyla biliniyor.
- Kanalın "Oynatma listeleri", "Podcast'ler" ve "Gönderiler" sekmeleri PDF'te yok.
