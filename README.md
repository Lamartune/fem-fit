# F🖤 Fitness — Kişisel Fitness PWA

Feminen ve güçlü vücut inşası için skolyoz uyumlu, tamamen mobil uyumlu bir PWA (Progressive Web App). iPhone'da Safari üzerinden ana ekrana eklenerek gerçek bir uygulama gibi çalışır — tam ekran, kendi ikonu, ve internet olmadan (offline) açılabilir.

## 📁 İçindekiler

| Dosya | Görev |
|-------|-------|
| `index.html` | Uygulamanın tamamı (program, ölçüm takibi, rehber, zamanlayıcı) |
| `manifest.json` | Uygulama tanımı (isim, ikon, renk, tam ekran ayarı) |
| `service-worker.js` | Offline çalışma — dosyaları önbelleğe alır |
| `apple-touch-icon.png` | iPhone ana ekran ikonu (180×180) |
| `icon-192.png` / `icon-512.png` | PWA ikonları |
| `icon-512-maskable.png` | Android uyarlanabilir ikon |
| `favicon.png` | Tarayıcı sekme ikonu |

## 🚀 GitHub Pages ile Yayına Alma

1. GitHub'da yeni bir repo oluştur (örn. `fatih-system`).
2. Bu klasördeki **tüm dosyaları** repoya yükle (dosyalar kök dizinde olmalı, alt klasörde değil).
3. Repo sayfasında **Settings → Pages** bölümüne git.
4. **Source** kısmında `Deploy from a branch` seç, branch olarak `main` ve klasör olarak `/ (root)` seç, **Save**.
5. Birkaç dakika sonra adresin hazır olur:
   `https://KULLANICI-ADIN.github.io/fatih-system/`

> ⚠️ **Önemli:** PWA'lar yalnızca **HTTPS** üzerinden çalışır. GitHub Pages otomatik HTTPS verir, o yüzden sorun olmaz. Dosyayı bilgisayarda çift tıklayıp `file://` ile açarsan service worker çalışmaz — bu normaldir.

## 📱 iPhone'a Kurulum (Ana Ekrana Ekle)

1. **Safari** ile yukarıdaki GitHub Pages adresini aç (Chrome değil, Safari olmalı).
2. Alttaki **Paylaş** butonuna dokun (yukarı ok işareti 􀈂).
3. Listeyi aşağı kaydır, **Ana Ekrana Ekle**'ye dokun.
4. İsmi onayla (F🖤) ve **Ekle**'ye dokun.
5. Ana ekranda ikon belirir. Ona dokununca uygulama **tam ekran** açılır — Safari çubukları görünmez.

Bir kez açtıktan sonra internet olmasa bile açılır (offline çalışır).

## 🔄 Güncelleme Yapınca

Programı değiştirip yeni dosyaları GitHub'a yüklediğinde, uygulamanın güncellemeyi çekmesi için `service-worker.js` içindeki sürüm numarasını artır:

```js
const CACHE = 'femfit-v1';  // → 'femfit-v2' yap
```

Sonra uygulamayı bir-iki kez kapat/aç; yeni sürüm yüklenir.

---

*Tek dosyalık, taşınabilir, bağımlılıksız. Tüm veriler telefonda (localStorage) saklanır — hiçbir yere gönderilmez.*
