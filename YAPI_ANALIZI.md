# Editorial Şablonu — Jeoloji.org Yapı Analizi

Şablon 3 ana bölümden oluşuyor: Sol Sidebar, Sağ Ana İçerik, İç Sayfa (generic.html).

---

## 1. SOL SIDEBAR

Sidebar tüm sayfalarda sabit kalıyor, mobilde hamburger menüye dönüşüyor.

### 1a. Arama Kutusu (`#search`)
**Şu an:** Boş form
**Jeoloji.org için:** Google Custom Search (CSE) entegre edilecek
→ Anahtar kelime: "fay hattı", "deprem", "mineral" gibi aramaları site içinde yakalar
→ CSE ayrıca AdSense reklamı da gösterebiliyor (ekstra gelir)

### 1b. Navigasyon Menüsü (`#menu`)
**Şu an:** Örnek linkler
**Jeoloji.org için:**
```
Ana Sayfa
Depremler
  ├── Canlı Deprem Haritası       → /deprem/          (deprem-harita reposu)
  ├── Son Depremler Listesi       → /depremler/
  └── Büyük Depremler Arşivi     → /depremler/arsiv/
Makaleler
  ├── Jeoloji                     → /makaleler/jeoloji/
  ├── Mineraloji & Kayaçlar       → /makaleler/mineraller/
  ├── Volkanoloji                 → /makaleler/volkanlar/
  ├── Jeomorfoloji                → /makaleler/jeomorfoloji/
  └── Paleontoloji                → /makaleler/paleontoloji/
Araçlar
  ├── İnteraktif Harita           → /harita/           (mevcut map.js)
  └── Zemin Sınıfı Sorgula       → /zemin/            (mevcut zemin_sinifi.html)
Kaynaklar                         → /kaynaklar/
Hakkında                          → /hakkinda/
```

### 1c. Mini-Posts Bölümü (sidebar'da 3 küçük kart)
**Şu an:** Statik görsel + yazı
**Jeoloji.org için:** "Son Depremler" widget
→ JavaScript ile AFAD/USGS'den son 3 depremi çekip burada göster
→ Her kart: Büyüklük rozeti + konum + "x dk önce"
→ "Tümünü gör →" butonu deprem haritasına bağlanır
→ Bu bölüm sayfa yenilemeden otomatik güncellenir (5 dk interval)

### 1d. İletişim Bölümü
**Şu an:** Telefon, adres, mail
**Jeoloji.org için:** Affiliate/sponsor kutusuna dönüştür
→ Örnek: "Önerilen Ürünler" başlığıyla 2-3 affiliate link
  - Estwing Jeoloji Çekici (Amazon TR affiliate)
  - Büyüteç Seti
  - "Türkiye Jeolojisi" kitabı (Kitapyurdu affiliate)

### 1e. AdSense Yeri #1 — Sidebar Sabit Reklam
→ İletişim bölümünün hemen altına 300x250 reklam kutusu eklenecek
→ Sidebar scroll edilse de bu alan görünür kalır

---

## 2. MAIN — ANA İÇERİK ALANI

### 2a. Header (`#header`)
**Şu an:** Logo + sosyal medya ikonları
**Jeoloji.org için:**
→ Logo: "Jeoloji**.**org" (mevcut sitedeki gibi)
→ Sosyal ikonlar: Twitter/X, Instagram, YouTube (jeoloji içerikleri)
→ AdSense Yeri #2: Header'ın hemen altına 728x90 leaderboard reklam

### 2b. Banner (Hero Bölümü)
**Şu an:** Büyük başlık + paragraf + görsel + buton
**Jeoloji.org için:**
→ Sol: "Türkiye'nin Yer Bilimleri Portalı" başlığı
→ Alt yazı: "Canlı deprem takibi, jeoloji makaleleri, interaktif haritalar"
→ Buton: "Canlı Deprem Haritasını Aç →" (deprem-harita reposuna link)
→ Sağdaki görsel: Türkiye'nin fay hatları haritası veya dramatik kayaç fotoğrafı

### 2c. Features Grid (2×2 İkon Kartları)
**Şu an:** 4 ikon + başlık + açıklama
**Jeoloji.org için:** Sitenin 4 ana özelliği
```
🌍 Canlı Deprem Takibi     →  /deprem/
   "AFAD + USGS verisiyle anlık deprem haritası"

📚 Makale Kütüphanesi      →  /makaleler/
   "Jeoloji, mineraloji, volkanoloji ve daha fazlası"

🗺️ İnteraktif Harita       →  /harita/
   "Türkiye jeoloji katmanlarını keşfet"

📊 Zemin Analizi           →  /zemin/
   "İlçe bazında zemin sınıfı ve deprem riski"
```
→ Her ikon tıklanabilir, ilgili sayfaya gidiyor

### 2d. Posts Grid (6 Makale Kartı)
**Şu an:** 6 kart, her birinde görsel + başlık + özet + "More" butonu
**Jeoloji.org için:** Son 6 makale
→ Her kart: Kapak görseli + kategori etiketi + başlık + 2 satır özet + "Devamını Oku"
→ Konu önerileri (başlangıç içeriği):
  1. Türkiye'nin Aktif Fay Hatları — Bilmeniz Gerekenler
  2. Kayaç Türleri: Magmatik, Metamorfik, Tortul Nasıl Ayırt Edilir?
  3. Mineral Koleksiyonculuğuna Başlamak İçin Rehber
  4. 1999 Marmara Depremi: Jeolojik İnceleme
  5. Türkiye'de Volkanik Yapılar: Erciyes, Nemrut, Süphan
  6. Zemin Sınıflandırması ve Bina Güvenliği

→ **AdSense Yeri #3:** 3. ve 4. kart arasına tam genişlik reklam şeridi
→ 6 kartın altına "Tüm Makaleler →" butonu

---

## 3. İÇ SAYFA (generic.html → makale şablonu)

Her makale bu şablonu kullanacak.

### Yapı:
```
[Büyük Kapak Görseli]           ← span.image.main
[Makale Başlığı]
[Kategori + Tarih + Yazar]
[AdSense #4 — İçerik Başı]     ← 728x90 veya responsive
[Makale İçeriği — paragraflar, görseller, tablolar]
[AdSense #5 — İçerik Ortası]   ← 336x280 içerik içi reklam
[Devamı...]
[İlgili Ürünler — Affiliate]   ← makale konusuna göre 2-3 ürün linki
[İlgili Makaleler]              ← 3 kart grid
[AdSense #6 — Makale Sonu]     ← 728x90
```

### Sidebar'da makale sayfasında:
→ Arama kutusu (aynı)
→ Menü (aynı)
→ Mini-posts → "Bu Kategorideki Diğer Makaleler" (statik)
→ Sidebar reklam (aynı)

---

## 4. GELİR MODELİ HARİTASI

### AdSense Konumları (toplam 6 nokta):
| # | Konum | Format | Sayfa |
|---|-------|--------|-------|
| 1 | Sidebar sabit | 300×250 | Tüm sayfalar |
| 2 | Header altı | 728×90 | Tüm sayfalar |
| 3 | Posts grid ortası | Responsive | Ana sayfa |
| 4 | Makale içerik başı | Responsive | Makaleler |
| 5 | Makale içerik ortası | 336×280 | Makaleler |
| 6 | Makale sonu | 728×90 | Makaleler |

### Affiliate Konumları:
| Yer | İçerik | Platform |
|----|---------|----------|
| Sidebar "İletişim" yerine | Jeoloji ekipmanları | Amazon TR |
| Makale sonları | Konuyla ilgili kitap/ekipman | Amazon TR / Kitapyurdu |
| Features grid altı | GIS/Jeoloji kursları | Udemy affiliate |

---

## 5. DOSYA YAPISI PLANI

```
jeoloji-site/
├── index.html              ← Ana sayfa (Editorial index)
├── generic.html            ← Makale şablonu
├── elements.html           ← Referans (silinmeyecek)
├── deprem.html             ← Deprem haritası sayfası (iframe veya doğrudan)
├── harita.html             ← İnteraktif harita sayfası
├── zemin.html              ← Zemin sınıfı sayfası
├── makaleler/
│   ├── index.html          ← Makale listesi
│   ├── fay-hatlari.html    ← Örnek makale
│   └── ...
├── assets/                 ← Editorial CSS/JS (değiştirilmeyecek)
├── images/                 ← Jeoloji görselleri
└── YAPI_ANALIZI.md         ← Bu dosya
```

---

## 6. ÖNCELİK SIRASI

1. `index.html` → Türkçeleştir + içerikleri yerleştir
2. Sidebar menüsünü kur
3. Sidebar'a "Son Depremler" widget ekle (deprem-harita reposundan JS)
4. 2-3 başlangıç makalesi yaz → `generic.html` şablonuyla
5. AdSense başvurusu (min. 10-15 makale olunca)
6. Affiliate linkleri ekle
7. Google Search Console + Sitemap
