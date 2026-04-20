# NUO Design System

## Renkler

### Birincil
| Token | Hex | Kullanım |
|-------|-----|----------|
| `--bg` | `#0B0B0B` | Ana arka plan |
| `--bg2` | `#141414` | İkincil arka plan (alternatif bölümler) |
| `--card` | `#1A1A1A` | Kart arka planı |
| `--card-h` | `#1F1F1F` | Kart hover |

### Vurgu
| Token | Hex | Kullanım |
|-------|-----|----------|
| `--red` | `#E53935` | Birincil CTA, acil, SOS |
| `--red-d` | `#C62828` | Hover kırmızı |
| `--gold` | `#F5B400` | İkincil vurgu, featured |
| `--blue` | `#2979FF` | Üçüncül, international |

### Metin
| Token | Hex | Kullanım |
|-------|-----|----------|
| `--w` | `#FFFFFF` | Başlıklar, birincil metin |
| `--sub` | `#B8B8B8` | Alt metin, açıklamalar |
| `--mute` | `#777777` | Pasif, meta, ipucu |

### Border
| Token | Değer | Kullanım |
|-------|-------|----------|
| `--border` | `rgba(255,255,255,0.07)` | Varsayılan kenar |
| `--border-h` | `rgba(255,255,255,0.12)` | Hover kenar |

## Tipografi

**Font:** Chillax Variable (woff2)
**Fallback:** system-ui, sans-serif

| Ağırlık | CSS | Kullanım |
|---------|-----|----------|
| Light (300) | `font-weight: 300` | Tarih, meta, label, footer, caption |
| Regular (400) | `font-weight: 400` | Paragraf, açıklama, FAQ cevap, body |
| Medium (500) | `font-weight: 500` | Nav link, h4, tag, kart başlığı |
| Bold (700) | `font-weight: 700` | h1-h3, logo, CTA, hero başlık |

### Boyutlar
- Hero h1: `clamp(2.2rem, 5vw, 3.6rem)`
- Section h2: `clamp(1.5rem, 3.5vw, 2.4rem)`
- Body: `.88rem - .95rem`
- Small: `.72rem - .82rem`
- Micro: `.64rem - .68rem`

## Spacing

8px grid sistemi.

| Token | Değer |
|-------|-------|
| Bölüm padding | `112px 0` (desktop), `80px 0` (mobil) |
| Kart padding | `28px - 32px` |
| Grid gap | `12px - 16px` |
| Element gap | `8px - 12px` |

## Border Radius

| Token | Değer | Kullanım |
|-------|-------|----------|
| `--r` | `12px` | Küçük elementler |
| `--rl` | `16px` | Kartlar, bölümler |
| `--rr` | `60px` | Butonlar, pill şekiller |

## Gölgeler

```css
--shadow-s: 0 1px 2px rgba(0,0,0,.3), 0 4px 12px rgba(0,0,0,.15);
--shadow-m: 0 2px 4px rgba(0,0,0,.3), 0 8px 24px rgba(0,0,0,.2);
--shadow-l: 0 4px 8px rgba(0,0,0,.3), 0 16px 48px rgba(0,0,0,.25);
```

## Animasyon Kuralları

- Geçiş süresi: `150ms - 300ms` (UI micro-interaction)
- Easing: `ease`, `ease-out` (giriş), `ease-in` (çıkış)
- Hover transform: `translateY(-2px)` ile `translateY(-6px)` arası
- Active: `scale(0.97)` geri basma efekti
- `prefers-reduced-motion` her zaman desteklenmeli

## Buton Stilleri

### Primary (Beyaz)
```css
background: #fff; color: #0B0B0B;
padding: 16px 32px; border-radius: 60px;
font-weight: 700;
```

### Danger (Kırmızı)
```css
background: #E53935; color: #fff;
box-shadow: 0 4px 20px rgba(229,57,53,0.3);
```

### Outline
```css
border: 1.5px solid rgba(255,255,255,0.12);
background: transparent; color: #fff;
```

## Responsive Breakpoints

| Breakpoint | Hedef |
|------------|-------|
| `< 640px` | Mobil |
| `640px - 767px` | Büyük mobil |
| `768px - 899px` | Tablet |
| `900px - 1023px` | Küçük desktop |
| `1024px+` | Desktop |
| `1200px+` | Geniş desktop |

## Erişilebilirlik

- Kontrast: minimum 4.5:1 (normal metin)
- Focus: `outline: 2px solid #E53935; outline-offset: 3px`
- Touch target: minimum 44px
- Reduced motion: tüm animasyonlar devre dışı
- Skip link: her sayfada
- ARIA: tüm interaktif elementlerde
