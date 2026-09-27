# Esin Begüm Kaya — Portfolyo

Statik HTML/CSS/JS; derleme gerekmez. `index.html` dosyasını açman yeterli.

## Yayınlama (GitHub Pages)
1. Bu klasörün içeriğini bir repoya yükle (`index.html` kök dizinde olmalı).
2. Settings → Pages → Branch: `main`, klasör: `/ (root)`.

## Yapı
- **Ana sayfa:** portfolyo girişi, yavaşça kayan proje önizlemeleri, tüm projeler listesi, hakkımda, deneyim, ödüller ve sertifikalar, yetkinlikler, iletişim.
- **Proje sunumları:** her proje tıklanınca kendi kısa sunumuyla açılır. Son slaytta "Sonraki proje" düğmesi çıkar.

## Gezinme
- Proje içinde: ← → ↑ ↓, Space, PageUp/PageDown ile ilerle; Home / End ilk / son slayt; Esc ana sayfaya döner.
- L: dili değiştirir.
- Paylaşılabilir adresler: `#p/recall` (projenin ilk slaydı), `#p/recall/2` (ikinci slayt), `#hakkimda`, `#iletisim`.

## Yeni proje eklemek
1. `index.html` içinde `<div id="decks">` altına yeni bir blok ekle:
   `<div class="project" id="p-yeniproje" data-project="yeniproje" hidden> ... slaytlar ... </div>`
   Her slayt: `<section class="slide w-..." id="s-yeniproje" data-title="..." data-title-en="...">`.
   Mevcut projelerden birini kopyalayıp düzenlemek en kolayı.
2. Script içindeki `PROJECTS` listesine bir kayıt ekle: `id`, `world` (renk dünyası), `title`, `cat`, `sum`
   ve `preview` (`{type:'img', src:'assets/...webp'}` ya da `{type:'phones', srcs:[...]}`).
3. Kayan önizleme şeridi, proje listesi, sayaç ve "Sonraki proje" düğmesi otomatik güncellenir.
   Şeridin hızı proje sayısına göre ayarlanır (proje başına 12 saniye).
4. Yeni bir renk dünyası istersen CSS'teki `.w-recall` gibi bir sınıf tanımla (koyu mod karşılığıyla birlikte).

## Dil desteği (TR / EN)
- Sağ üstteki TR/EN düğmesi ya da L tuşu dili değiştirir; seçim tarayıcıda hatırlanır.
- Belirli bir dille paylaşmak için: `index.html?lang=en` veya `?lang=tr`.
- İlk ziyarette tarayıcı dili Türkçe ise Türkçe, değilse İngilizce açılır.
- Sabit metinler: Türkçe metin elementin içinde, İngilizcesi `data-en="..."` özelliğinde.
  Görsel açıklamaları için `data-en-alt`, erişilebilirlik etiketleri için `data-en-aria-label`.
- Slayt adları: `data-title` / `data-title-en`, bölüm adları: `data-chapter` / `data-chapter-en`.
- Galeri, Recall hattı ve şemalardaki metinler JS içinde `L('türkçe','english')` biçiminde.

## İçerik güncelleme
- Görseller `assets/` klasöründe, WebP formatında.
- Galeri verileri `index.html` içindeki `const G = {...}` nesnesinde.
- Recall hattı `PIPE`, sistem şemaları `renderDiagram(...)` çağrılarında.
- Yeni slayt: `<section class="slide w-..." data-chapter="..." data-title="...">` ekle; sayaç, çubuk ve genel bakış otomatik güncellenir.
- Renk dünyaları: w-paper, w-recall, w-hotel, w-skin, w-systems, w-herobot, w-mirror.

## Gizlilik
Recall profil ve bilgi tabanı ekranları bulanıklaştırılmış sürümlerdir. Telefon numarası bilinçli olarak eklenmedi.
