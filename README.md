<div align="center">

![Nardugan](docs/afis.svg)

[![Canlı sayaç](https://img.shields.io/badge/Canlı_sayaç-ne_kadar_kaldı%3F-ffb347?style=for-the-badge)](https://enskygr234.github.io/nardugan/)
[![Lisans](https://img.shields.io/badge/lisans-MIT-e63946?style=for-the-badge)](LICENSE)

</div>

Yılın en uzun gecesine, kış gündönümüne canlı geri sayım. Gündönümü anını hazır bir tablodan okumaz, astronomik olarak hesaplar.

**[→ Sayacı aç](https://enskygr234.github.io/nardugan/)**

## Neler gösterir

- **Geri sayım** — bir sonraki kış gündönümüne gün, saat, dakika, saniye
- **Güneşin yolculuğu** — bir gündönümünden ötekine yolun yüzde kaçı geride kaldı
- **Bugünün gün uzunluğu** — seçtiğin şehirde gün kaç saat sürüyor, düne göre kaç dakika kısaldı ya da uzadı, en kısa günden ne kadar uzun
- **Nardugan günü** — gündönümünden sonraki ilk gün başlık "Bugün Nardugan!" olur

## Hesap ne kadar doğru?

`gundonumu.js`, Jean Meeus'un *Astronomical Algorithms* kitabındaki yöntemi kullanır. Bilinen gündönümü anlarıyla karşılaştırma:

| Yıl | Hesaplanan (UTC) | Bilinen (UTC) |
|---|---|---|
| 2020 | 21 Aralık 10:02 | 21 Aralık 10:02 |
| 2022 | 21 Aralık 21:48 | 21 Aralık 21:48 |
| 2023 | 22 Aralık 03:27 | 22 Aralık 03:27 |
| 2024 | 21 Aralık 09:20 | 21 Aralık 09:21 |
| 2025 | 21 Aralık 15:03 | 21 Aralık 15:03 |

Denediğim yıllarda fark bir dakikanın altında kaldı. Gün uzunluğu ise yaklaşık bir formülle hesaplanır; birkaç dakika sapabilir.

## Kendi projende kullan

`gundonumu.js` tek dosyadır, bağımlılığı yoktur; tarayıcıda da Node.js'te de çalışır.

```js
const Gundonumu = require('./gundonumu.js');

Gundonumu.kisGundonumu(2026);          // 2026 kış gündönümü anı (Date)
Gundonumu.sonrakiKisGundonumu();       // şu andan sonraki ilk kış gündönümü
Gundonumu.oncekiKisGundonumu();        // şu andan önceki son kış gündönümü
Gundonumu.gunUzunlugu(39.93);          // Ankara'nın enleminde bugünkü gün uzunluğu (saat)
Gundonumu.gunUzunlugu(69.65, tarih);   // kutup gecesinde 0, gece yarısı güneşinde 24 döner
```

Sayfadaki kar yağışı [kar.js](https://github.com/Enskygr234/kar-js) ile yapıldı.

## Lisans

[MIT](LICENSE) © Winterdeveloper
