# Game Studio Project

Dört kişilik okul projesi için Unity başlangıç reposu.

| Ayar | Değer |
| --- | --- |
| Unity Editor | **6000.3.27f2 — Unity 6.3 LTS** |
| Proje modu | 3D |
| Render pipeline | Built-in |
| Başlangıç sahnesi | `Assets/Scenes/Main.unity` |
| Sürüm kontrolü | Git / GitHub |

Bu repo kamera ve ışık içeren bir başlangıç sahnesi, Unity proje ayarları
ve Git yapılandırması içerir. Oyun mekanikleri geliştirme sırasında eklenecektir.
Paket manifestinde yalnızca Unity Editor ile gelen yerleşik modüller bulunur.

## İlk kurulum

1. [Unity Hub](https://unity.com/download) üzerinden **6000.3.27f2** sürümünü kur.
   Sürümü Hub listesinde göremiyorsan
   [resmî sürüm sayfasındaki](https://unity.com/releases/editor/whats-new/6000.3.27f2)
   kurulum bağlantısını kullan.
2. GitHub Desktop'ta **File → Clone repository → URL** seçerek
   `https://github.com/Buwaee/game-studio-project..git` adresini klonla.
3. **Local path** alanındaki son klasör adını `game-studio-project` olarak yaz.
   GitHub'daki repo adının sonunda nokta var; Windows'taki yerel klasör adının
   sonunda nokta bulunmasın.
4. Unity Hub'ın **Projects** bölümünde mevcut projeyi diskten ekleme seçeneğini
   kullan ve klonladığın ana klasörü seç. Seçtiğin klasörün içinde
   `Assets`, `Packages` ve `ProjectSettings` bulunmalı.
5. Projeyi **6000.3.27f2** ile aç. İlk içe aktarma işleminin tamamlanmasını bekle.
6. Project penceresinden `Assets/Scenes/Main.unity` sahnesini çift tıklayarak aç.
   Başlangıç sahnesinde **Main Camera** ve **Directional Light** bulunur.
   Sahne build listesine de eklenmiştir.

Terminal kullananlar için:

```bash
git clone https://github.com/Buwaee/game-studio-project..git game-studio-project
```

### İlk açılışta oluşan dosyalar

Unity, ilk açılışta eksik varsayılan proje ayarlarını ve
`Packages/packages-lock.json` dosyasını oluşturabilir. İlk açan ekip üyesi
sahneyi kaydetsin, `ProjectSettings` değişikliklerini ve paket kilit dosyasını
kontrol edip commit/push yapsın. Diğer üyeler projeyi açmadan önce bu değişiklikleri çeksin.

`Library`, `Temp`, `Logs` ve `UserSettings` gibi yerel dosyalar
`.gitignore` tarafından hariç tutulur.

Ders için başka bir Unity sürümü zorunluysa ekip önce o sürümde anlaşmalı.
Sürüm değişikliğini bir kişi yapıp Unity'nin ürettiği dosyaları paylaşmalı;
`ProjectVersion.txt` içindeki sürüm numarasını tek başına değiştirmek
projeyi başka bir sürüme dönüştürmez.

## Dört kişi nasıl çalışacağız?

- Herkes kendi GitHub hesabını kullanır ve bu repo için collaborator davetini kabul eder.
- Çalışmaya başlamadan önce GitHub Desktop'ta **Fetch origin / Pull origin** ile
  en güncel değişiklikleri al.
- Her görev için `feature/player-movement`, `feature/main-menu` gibi ayrı
  bir branch aç.
- Değişikliği açıklayan bir mesajla commit yap ve **Push origin / Publish branch**
  ile gönder.
- GitHub'da Pull Request aç. Ekipten biri değişiklikleri kontrol ettikten sonra
  `main` dalına birleştirin. Bu önerilen çalışma düzenidir; zorunlu branch
  koruması bu kurulumda etkinleştirilmemiştir.
- Aynı sahne veya prefab üzerinde eş zamanlı çalışmadan önce görev paylaşımı yap.
- Dosya ve klasörleri mümkün olduğunca Unity'nin Project penceresinde taşı
  veya yeniden adlandır; böylece ilgili `.meta` dosyaları da birlikte taşınır.

## Git'e hangi dosyalar eklenir?

| Dosya / klasör | Git'e eklenir mi? |
| --- | --- |
| `Assets/` ve assetlerin `.meta` dosyaları | Evet |
| `Packages/` ve `packages-lock.json` | Evet |
| `ProjectSettings/` | Evet |
| `.gitignore`, `.gitattributes`, `README.md` | Evet |
| `Library/`, `Temp/`, `Obj/`, `Logs/`, `UserSettings/` | Hayır |
| `Build/`, `Builds/` ve IDE'nin otomatik ürettiği dosyalar | Hayır |

`.meta` dosyalarını silmeyin veya topluca hariç tutmayın; Unity asset referanslarını
bu dosyalardaki GUID'ler ile takip eder.

## Ortak proje ayarları

- **Asset Serialization:** Force Text
- **Version Control:** Visible Meta Files
- **Yeni C# dosyalarının kök namespace'i:** GameStudio
- Metin dosyalarının satır sonları `.gitattributes` ile düzenlenir.
- Büyük modeller, sesler veya videolar eklemeden önce boyutlarını kontrol edin.
  Git LFS gerekecekse dosyaları ilk commit etmeden önce ekip olarak yapılandırın.

## Kurulum doğrulaması

Projenin JSON/YAML dosyaları, sahne içi referansları, asset GUID eşleşmeleri,
build sahnesi kaydı ve Git ignore kuralları statik olarak kontrol edilmiştir.
Bu başlangıç projesi hazırlanırken Unity Editor kullanılarak açılış, Play Mode
veya build testi yapılmamıştır. İlk yerel açılışta Console'u kontrol edin.

## Başvuru kaynakları

- [Unity 6000.3.27f2 sürüm sayfası](https://unity.com/releases/editor/whats-new/6000.3.27f2)
- [Unity proje klasörleri](https://docs.unity.com/en-us/engine/6000.0/manual/get-started/project-configuration/default-directories)
- [Unity sürüm kontrolü](https://docs.unity3d.com/6000.3/Documentation/Manual/Versioncontrolintegration.html)
- [GitHub Unity .gitignore şablonu](https://github.com/github/gitignore/blob/main/Unity.gitignore)
- [GitHub Flow](https://docs.github.com/en/get-started/using-github/github-flow)
