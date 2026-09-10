# Tasarruf Koçu — Mevzuat Verisi

Bu depo **kaynak kod içermez**. Tek işi, [Tasarruf Koçu](https://github.com/TasarrufKocu/tasarruf-kocu) uygulamasının okuduğu `mevzuat.json` dosyasını herkese açık olarak barındırmaktır — asıl uygulama deposu gizlidir (private), ama mobil uygulamanın bu dosyaya internetten (kimlik doğrulama gerektirmeden) ulaşabilmesi gerekir.

`mevzuat.json`, TCMB ve BDDK'nın belirlediği ve zaman zaman değişen şu değerleri taşır:

- `tcmbAzamiFaizOrani` — TCMB'nin kredi kartı için yayınladığı kademeli azami akdi faiz oranları. **Otomatik güncellenir** (bkz. asıl depodaki `.github/workflows/mevzuat-guncelle.yml`, ayda bir TCMB'nin resmi sayfasını okur).
- `asgariOdemeOrani` — BDDK'nın kredi kartı asgari ödeme oranı kademeleri.
- `borcKapatmaKredisiAzamiVade` — BDDK'nın ihtiyaç kredisi azami vade sınırları.
- `faizVergiOrani` — KKDF + BSMV toplam vergi yükü.

Son üç değer BDDK'nın PDF biçimindeki, düzensiz aralıklarla yayınlanan "kurul kararları" ile değişir — güvenilir biçimde otomatik ayrıştırmak (parse etmek) riskli olduğu için bunlar **elle güncellenir** (asıl depodaki bakımcı, mevzuat değiştiğinde bu dosyayı düzenleyip buraya gönderir).

Bu dosyayı **doğrudan düzenlemeyin** — kaynak, asıl (gizli) depodaki `mevzuat.json`'dur; buraya sadece kopyalanır/yayınlanır.
