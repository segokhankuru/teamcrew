# Halı Saha Kadro Oluşturucu

Halı saha maçları için kadro listesi oluşturup sahada sürükle-bırak ile yerleşim yapmanıza yardımcı olan tek sayfalık bir web uygulamasıdır. Oyuncuları kadro havuzuna ekleyip takım seçimiyle sahaya yerleştirebilir, kılavuz (ızgara) çizgiler sayesinde düzgün hizalama yapabilir ve sonucu görsel olarak kaydedebilirsiniz.

## Özellikler

- **Kadro havuzu oluşturma:** Oyuncu adı girip listeye ekleyin, çiftleri engeller.
- **Pozisyon etiketi:** Her oyuncu için K/STP/BEK/OS/KN/FV pozisyon seçimi yapılır ve forma üstüne yazılır.
- **Takım yönetimi:** A/B takım adı, renk ve çizgili forma seçimi yapılabilir.
- **Sahada hizalama:** Sürüklerken ızgara kılavuzu açılır, bırakırken ızgaraya mıknatıslanır.
- **Saha stili:** Klasik, modern koyu ve taktik tahtası görünümleri.
- **Kaydetme:** Sahayı JPG olarak indir.
- **Mobil uyumluluk:** Ayarlar paneli mobilde aç/kapa yapılabilir.

## Nasıl Çalışır?

Uygulama tamamen **tek bir HTML dosyası** üzerinde çalışır (`index.html`). Temel akış:

1. **Oyuncu ekleme:** Sol panelde oyuncu adını yazıp **Ekle** ile listeye eklersiniz.
2. **Pozisyon seçimi:** Her oyuncu satırında GK/DF/OS/FV seçerek pozisyonu belirlersiniz.
3. **Takıma ekleme:** A ya da B butonuna basınca oyuncu sahaya çıkar.
4. **Sürükle-bırak:** Oyuncu token’larını sahada sürükleyip kılavuz çizgilere hizalarsınız.
5. **Kayıt:** **Görüntüyü Kaydet** ile sahayı JPG olarak indirirsiniz.

## Dosya Yapısı

- `index.html`
  - **CSS:** Saha, oyuncu token’ları ve layout stilleri.
  - **HTML:** Sol panel (ayarlar), saha alanı, footer, modallar.
  - **JavaScript:** Kadro yönetimi, sürükle-bırak, ızgara snap ve çıktı alma.
- `README.md`
  - Bu belge.

## Önemli Bileşenler (Koddan)

- **Kadro verisi:** `players` dizisi `localStorage` üzerinden saklanır (`players_v5`).
- **Pozisyon listesi:** `positions = ["K", "STP", "BEK", "OS", "KN", "FV"]`.
- **Sürükle-bırak:** `interact.js` ile `snapGrid` ve `restrictRect` kullanılır.
- **Kılavuz çizgiler:** Sürükleme başladığında `gridOverlay` görünür, bırakınca gizlenir.
- **Görsel kaydı:** `html2canvas` ile saha görseli üretilip JPG olarak indirilir.

## Kullanım

Yerel olarak çalıştırmak için herhangi bir web sunucusunda dosyayı açmanız yeterli.
Örnek:

```bash
# Python ile basit sunucu
python3 -m http.server
```

Tarayıcıda `http://localhost:8000` adresine gidin.

## Kısayollar

- Oyuncu adı alanında **Enter**: Oyuncu ekler.
- Sahadaki oyuncuya **çift tık**: Oyuncuyu sahadan siler.

## Notlar

- Veriler yalnızca tarayıcıda tutulur; sunucuya gönderilmez.
- Uygulama ücretsizdir ve sorumluluk kullanıcıya aittir.

---

**Yazar:** Gökhan Kuru

İletişim: se.gokhankuru@gmail.com
