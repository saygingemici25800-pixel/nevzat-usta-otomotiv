# CLAUDE.md — Nevzat Usta Otomotiv (NUO) Web Projesi

## Proje Özeti

Fethiye merkezli oto servis işletmesi "Nevzat Usta Otomotiv" için tam kapsamlı, tek sayfalık ana site + alt sayfalardan oluşan dark theme web sitesi. Vanilla HTML/CSS/JS ile yapılmış, framework kullanılmamış. Hedef: gerçek bir işletmenin dijital varlığını profesyonel düzeyde oluşturmak.

## Dosya Yapısı

```
/
├── nevzat-usta-hero2.html    # Ana sayfa (production — base64 gömülü foto + font)
├── nevzat-usta-hero.html     # Ana sayfa (dev — harici referanslar)
├── Chillax-Variable.woff2    # Custom font dosyası
├── nevzat-full.jpg           # Nevzat Usta fotoğrafı (grayscale, 1400x1050)
│
├── motor-revizyonu.html      # Hizmet: Motor revizyonu detay sayfası
├── sanziman.html             # Hizmet: Şanzıman tamiri detay sayfası
├── ariza-teshisi.html        # Hizmet: Arıza teşhisi detay sayfası
│
├── blog.html                 # Blog listeleme sayfası
├── blog-motor-yagi.html      # Blog yazısı: Motor yağı değişimi
├── blog-sanziman-bakim.html  # Blog yazısı: Şanzıman bakımı
├── blog-yolda-kalmamak.html  # Blog yazısı: Yolda kalmamak için önlemler
│
├── graph.html                # Graphify: İnteraktif bilgi grafiği
├── graph.json                # Graphify: GraphRAG uyumlu JSON
├── GRAPH_REPORT.md           # Graphify: Topluluk analiz raporu
│
├── CLAUDE.md                 # Bu dosya — proje rehberi
├── README.md                 # Proje açıklaması ve kurulum
├── DESIGN_SYSTEM.md          # Tasarım sistemi dokümantasyonu
└── ROADMAP.md                # Geliştirme yol haritası
```

## Teknoloji

- **Frontend**: Vanilla HTML5, CSS3, JavaScript (ES5 uyumlu)
- **Font**: Chillax Variable (woff2, base64 gömülü)
- **Backend**: Yok (statik site)
- **Framework**: Yok — saf HTML/CSS/JS
- **Build tool**: Yok — dosyalar doğrudan serve edilebilir

## Ana Sayfa Bölüm Sırası

1. **Splash** — Işın animasyonu + N-U-O harf çizimi (~0.5s)
2. **Header** — Sticky, blur backdrop, NUO particle logo, Acil Yardım particle butonu
3. **Hero** — Başlık, açıklama, international support kartı, 3 CTA butonu
4. **Usta** (Photo Reveal) — Scroll ile zoom-out fotoğraf geçişi
5. **Hizmetlerimiz** — 3 hizmet kartı (glowing border efekti)
6. **Galeri** — 12 fotoğraf masonry grid
7. **Neden Biz** — Bento grid (stat, feature, testimonial, SOS banner, typewriter)
8. **Yorumlar** — 3D perspektif marquee (16 testimonial kartı)
9. **SSS** — Accordion (7 soru) + dişli animasyonu + SOR BANA particle butonu
10. **Blog** — 3 blog kartı önizleme
11. **İletişim** — Google Maps + çalışma saatleri + iletişim formu (gradient border glow)
12. **Floating Bar** — Sabit alt bar (Telefon, WhatsApp, Instagram)

## Navigasyon (Header)

Usta → Hizmetlerimiz → Galeri → Neden Biz → SSS → Blog → İletişim

## Tasarım Sistemi

### Renkler
```css
--bg: #0B0B0B          /* Ana arka plan */
--bg2: #141414         /* İkincil arka plan */
--card: #1A1A1A        /* Kart arka planı */
--red: #E53935         /* Birincil aksiyon rengi */
--red-d: #C62828       /* Hover kırmızı */
--gold: #F5B400        /* İkincil vurgu */
--blue: #2979FF        /* Üçüncül vurgu */
--w: #fff              /* Beyaz metin */
--sub: #B8B8B8         /* Alt metin */
--mute: #777           /* Pasif metin */
--border: rgba(255,255,255,0.07)
```

### Tipografi — Chillax Variable (4 Ağırlık)
```
Bold (700)    → h1, h2, h3, logo, CTA butonları, hero başlık
Medium (500)  → Nav, h4 kart başlıkları, tag'ler, form başlıkları
Regular (400) → Paragraflar, açıklamalar, FAQ cevapları, liste öğeleri
Light (300)   → Tarihler, meta, form etiketleri, footer, ipuçları
```

### Spacing
- 8px grid sistemi
- Border radius: 12px (küçük), 16px (kart), 60px (pill/buton)

## Animasyonlar

| Animasyon | Konum | Teknik |
|-----------|-------|--------|
| Splash beam | Açılış | CSS keyframes, SVG stroke |
| NUO logo particle | Header | Canvas, mouse interaction |
| Acil Yardım particle | Header | Canvas, mouse interaction |
| SOR BANA particle | SSS | Canvas, mouse interaction |
| Glowing border | Hizmet kartları | CSS conic-gradient, mouse tracking JS |
| Photo zoom-out | Usta bölümü | requestAnimationFrame, scroll position |
| 3D marquee | Yorumlar | CSS keyframes, perspective transform |
| Gear rotation | SSS arka plan | CSS keyframes, opacity %4 |
| Typewriter | Neden Biz | JS setTimeout döngüsü |
| Gradient border glow | İletişim kartları | CSS gradient, hover transition |
| Scroll reveal | Tüm bölümler | IntersectionObserver |

## SEO

- Her sayfada `<title>`, `<meta description>`, `<link canonical>`
- Blog sayfalarında Open Graph + JSON-LD (BlogPosting schema)
- Blog listesinde Blog schema
- Semantic HTML: `<main>`, `<article>`, `<nav>`, `<section>`, `<header>`, `<footer>`

## Erişilebilirlik (a11y)

- Skip to content linki (tüm sayfalar)
- `focus-visible` outline (kırmızı, 2px)
- `prefers-reduced-motion` — tüm animasyonlar devre dışı
- `@media(hover:none)` — dokunmatik cihaz fallback'leri
- ARIA labels — tüm icon-only butonlar ve bölümler
- `touch-action: manipulation` — 300ms tap delay kaldırılmış
- Form label'ları `for` attribute ile bağlı
- Print styles
- `color-scheme: dark` meta

## İletişim Bilgileri (Placeholder)

```
Telefon: 0532 480 09 28
E-posta: nevzatolpakefatura@hotmail.com
Adres: Taşyaka Sanayi, Fethiye, Turkey
Instagram: @nevzatusta
WhatsApp: +90 532 480 09 28
```

## Geliştirme Notları

### Dev vs Production
- `nevzat-usta-hero.html` → geliştirme (harici img referansı)
- `nevzat-usta-hero2.html` → production (base64 foto + font gömülü)
- Alt sayfalar kendi base64 fontlarını taşıyor

### Dikkat Edilecekler
- Font dosyası tüm HTML'lere base64 olarak gömülü (~74KB per page)
- Fotoğraf ana sayfada base64 (~260KB)
- Google Maps iframe placeholder (gerçek koordinat gerekli)
- Form backend bağlantısı yok (sadece frontend feedback)
- Telefon/WhatsApp/Instagram linkleri placeholder

## Mevcut Skill'ler

### UI/UX Pro Max
Konum: `/ui-ux-pro-max-skill-main/`
Kullanım: `python3 src/ui-ux-pro-max/scripts/search.py "<query>" --design-system`
İçerik: 50+ stil, 161 renk paleti, 57 font eşleştirmesi, 99 UX kuralı

### Graphify
Konum: `/graphify-4/`
Kullanım: Bilgi grafiği oluşturma
Çıktı: `graph.html`, `graph.json`, `GRAPH_REPORT.md`

## Komutlar

```bash
# Yerel sunucu başlatma
cd /path/to/project
python3 -m http.server 8000

# Tarayıcıda açma
open http://localhost:8000/nevzat-usta-hero2.html

# UX audit çalıştırma
cd ui-ux-pro-max-skill-main
python3 src/ui-ux-pro-max/scripts/search.py "auto service dark" --design-system

# Graphify bilgi grafiği
# (graphify-4 klasöründen)
python3 -c "from graphify.detect import detect; ..."
```
