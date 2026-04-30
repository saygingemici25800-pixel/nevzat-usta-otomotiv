# NUO Yayın Öncesi Durum Raporu

**Tarih:** 22 Nisan 2026
**Proje:** Nevzat Usta Otomotiv — Fethiye oto servis
**Canlı URL:** https://nevzatustaotomotiv.com

---

## ✅ Tamamlanan İşler (Sprint Listesi)

### Sprint 1 — Form Backend
- İletişim formu Formspree'ye bağlandı (`xzdykpqj`)
- Honeypot (`_gotcha`) spam koruması
- AJAX fetch submit + Türkçe success/error mesajları
- HTML5 + JS çift katmanlı validation (`checkValidity` + explicit check)

### Sprint 2 — SEO, Yasal & Favicon (tek commit `568eee1`)
- JSON-LD `AutoRepair` schema (adres, saatler, hizmet kataloğu, geo coord)
- Open Graph + Twitter Card — 9 sayfa (tür bazlı: website/article)
- Canonical URL'ler — 9 sayfa (Vercel domain)
- `sitemap.xml` — 9 URL (priority 1.0/0.9/0.7/0.3)
- `robots.txt` — `*.md` engelli, 9 SEO scraper bloklu, AI crawler'lar açık
- Favicon seti — SVG + ICO + 16/32/180 PNG
- KVKK aydınlatma metni (`kvkk.html`) — 9 bölüm, Formspree yurt dışı aktarım ibaresi
- Form KVKK checkbox (required)

### Sprint 3 — Polish & Integration
- Gerçek iletişim bilgileri (tel `0532 480 09 28`, wa.me, Instagram `@nevzatustaotomotivv`, Taşyaka Mh adres)
- Mobil hero layout düzeltmesi (üst siyah boşluk kaldırıldı)
- OG image (`og-image.jpg`, 1200×630) — 9 sayfada aktif
- Google Analytics 4 (`G-48R2D9T9N4`) — 8 sayfada aktif, `anonymize_ip`, `SameSite=Strict;Secure` cookie
- Search Console verification (`reXH_T6BYe9...`)
- GA4 `form_submit` conversion event (gtag guard'lı)
- Harita koordinat bazlı (36.615679, 29.1041687 — yaklaşık)
- JSON-LD `geo` GeoCoordinates eklendi

---

## 🟢 Canlı Durum

| Servis | Durum | Not |
|---|---|---|
| **Vercel deploy** | Aktif | `nevzat-usta-otomotiv.vercel.app`, her push sonrası otomatik |
| **GitHub** | `saygingemici25800-pixel/nevzat-usta-otomotiv` | main branch tekli geliştirme |
| **Formspree** | Aktif | endpoint `xzdykpqj`, e-posta `saygingemici25800@gmail.com` (geçici)|
| **Google Analytics 4** | Aktif | Property ID `G-48R2D9T9N4`, realtime çalışıyor |
| **Search Console** | Verified | Meta tag yöntemi, sitemap.xml submit edildi, 9 URL discovered |
| **Canlı asset health** | 18/18 × 200 OK | HTML + sitemap + robots + favicon + og-image + font |

---

## ⏳ Bekleyen Kritik İşler (Nevzat Usta Görüşmesi Sonrası)

### 1. Gerçek e-posta adresi
- Şu an: `nevzatolpakefatura@hotmail.com` (**placeholder, gerçekte kutusu yok**)
- Geçtiği yerler: `index.html` (JSON-LD + iletişim bölümü), `kvkk.html` (2 info-card) — toplam 5 nokta
- Güncelleme: `sed -i '' 's|nevzatolpakefatura@hotmail.com|GERÇEK@email.com|g' *.html`
- Formspree target e-posta'sını da aynı adrese değiştirmek gerek (panelden)

### 2. Nevzat Usta Gmail + Google Business Profile
- Nevzat Usta için Gmail hesabı oluştur (ya kendi telefonundan ya da atölyeden)
- Google Business Profile oluştur — **en önemli tek lokal SEO adımı**
- Kullanıcı kendini **manager** olarak ekleyecek
- GBP → fotoğraflar, çalışma saatleri, telefon, yorum yönetimi otomatikleşir

### 3. Custom Domain
- Önerilen: `nevzatustaotomotiv.com` (veya `.com.tr`)
- Vercel'e bağlamak: 2-3 DNS kaydı + 1 dakika
- **URL güncellemesi gereken yerler** (domain migration checklist):
  - 9 HTML canonical
  - 9 HTML OG/Twitter URL
  - `sitemap.xml` (9 URL)
  - `robots.txt` (sitemap reference)
  - `index.html` JSON-LD (`@id`, `url`, image URL)
  - `blog.html` JSON-LD (`url`)
- Tek komut: `sed -i '' 's|nevzat-usta-otomotiv.vercel.app|nevzatustaotomotiv.com|g' *.html *.xml *.txt`
- Sonrası: Search Console'da **yeni property aç** (domain değişikliği, "Change of Address" tool), GA4 Data Stream URL'sini güncelle, Formspree allowed domains güncelle

### 4. Galeri Fotoğrafları (12 placeholder)
- `index.html` galeri bölümü — 12 `.gallery-item` şu an placeholder span
- Gerekli: gerçek atölye/araba/usta fotoğrafları, tercihen 800×600+ JPEG, toplam < 2 MB

### 5. Hizmet Sayfası Fotoğrafları (18 placeholder)
- 3 hizmet sayfasında (motor, sanziman, ariza) × 6 `.photo-item` = 18 placeholder span
- Her hizmet için süreç fotoğrafları: söküm, onarım, test, teslim adımları

---

## 🟡 Nice-to-Have (Aciliyeti Yok)

- **Fiyat şeffaflığı** — "Motor yağı değişimi 1.500₺'den itibaren" tarzı başlangıç fiyatları
- **Randevu takvimi** — Calendly/Cal.com iframe ile müşteri tarih/saat seçsin
- **Review/yorum widget** — Google Business reviews embed (GBP aktif olduktan sonra)
- **Blog yazı sayısı artır** — şu an 3, SEO için aylık 1-2 yeni yazı hedeflenebilir
- **Gerçek Instagram feed** — `@nevzatustaotomotivv` son 6 post'u otomatik göster (instafeed.js vb.)

---

## 🔧 Teknik Notlar

### Formspree
- **Ücretsiz plan: 50 gönderim/ay**. Müşteri trafiği arttıkça sınır dolar → form sessizce düşer
- Gold plan $10/ay: 1000/ay + otomatik yanıt + webhook
- Panel'de notification e-posta değişimi yapmadan plan değiştirme sorun olmaz

### Vercel Free Tier
- 100 GB bandwidth/ay — statik site için aşılması zor
- Build dakikası sınırsız
- Özel domain **ücretsiz**, SSL Vercel tarafından otomatik (Let's Encrypt)

### KVKK / GDPR Uyumluluğu
- `anonymize_ip: true` GA4'te aktif
- `cookie_flags: SameSite=Strict;Secure` set edilmiş
- KVKK sayfasında çerez bildirimi (madde 7) ve Formspree yurt dışı aktarım açıklaması (madde 6) mevcut
- Form submit'te KVKK checkbox zorunlu — HTML5 required + JS çift katmanlı
- **Eksik:** Çerez onay banner'ı (cookie consent popup) yok. Türkiye'de opt-in zorunluluk yoktur ama AB kullanıcısı varsa gerekebilir. Şimdilik **işlevsel yeter**

### Font Stratejisi
- `Chillax-Variable.woff2` 8 HTML'e base64 gömülü (~85 KB/sayfa)
- `kvkk.html` external reference kullanıyor (~13 KB, cache'li)
- İlk yükleme hızı optimize edilmemiş — gelecekte tek bir external font'a geçilebilir

### Domain Migration Checklist (custom domain alındığında)
1. Domain al → DNS panelinde A/CNAME kayıtları
2. Vercel Dashboard → Project → Settings → Domains → Add
3. SSL otomatik aktif olur (~1 dk)
4. `sed -i ''` ile tüm HTML/XML/TXT dosyalarındaki eski URL'leri güncelle
5. Search Console'a yeni property ekle, verify et
6. Sitemap'i yeni property'de tekrar submit et
7. Eski property'de "Change of Address" tool'unu kullan
8. GA4 Data Stream URL'sini güncelle (Property → Data streams)
9. Formspree → Form settings → Allowed origins listesini güncelle
10. Instagram/WhatsApp/Google Business profilindeki site URL'sini güncelle
11. Eski `.vercel.app` → yeni domain için 301 redirect (Vercel otomatik ekleyebilir ya da `vercel.json`'a eklenir)

### Veri Akışı Özeti
```
Ziyaretçi → Vercel (statik HTML) → GA4 hit (G-48R2D9T9N4)
           ↓
  Form submit → Formspree (xzdykpqj) → saygingemici25800@gmail.com
           ↓
  GA4 form_submit event (engagement/contact_form)
```

---

## Son Commit Geçmişi

```
3152bb6 feat: switch maps embed + links to coordinate-based (36.615679, 29.1041687)
f8948a7 chore: polish + add GA4 form submission tracking
fd26bb3 feat: add Google Search Console verification meta tag
150a8c6 feat: activate Google Analytics 4 + KVKK cookie disclosure
8d65677 feat: prepare analytics + search console integration
f6db174 feat: update contact info to real business details
78f5808 feat: add OG image for social media link previews
2f78abf fix: mobile hero layout — remove empty top space on small screens
6c8a6d7 fix: enforce KVKK consent — block form submission when unchecked
568eee1 feat: sprint 2 - SEO, legal & favicon complete
3b3dddb feat: wire contact form to Formspree with AJAX + honeypot
93b42fe Initial deployment
```

---

## Sonraki Oturum İçin Giriş Noktası

Bu dosyayı okuyarak context'e gir. Hızlı durum:
- Site **yayında**, form **çalışıyor**, analytics **akıyor**.
- **En öncelikli 3 iş**: (1) gerçek e-posta, (2) Google Business Profile, (3) custom domain.
- Nevzat Usta ile yapılan görüşmeden sonra bunların hangisiyle başlanacağı belli olacak.
