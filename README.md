<div align="center">
  <h1>SDM</h1>
  <p><strong>Windows için modern indirme yöneticisi</strong></p>
  <p>İndirmelerini Atlas Pro ile düzenle, Odak Akışı ile takip et.</p>
  <p>Windows x64 · Chrome / Opera entegrasyonu · Açık / Koyu / Sistem</p>
  <p>
    <a href="https://github.com/EmreGUNDOGAN/SDM-Updates/releases/latest"><strong>En güncel sürümü indir →</strong></a>
    · <a href="https://github.com/EmreGUNDOGAN/SDM-Updates/releases">Sürüm geçmişi</a>
  </p>
</div>

## Resmî sürüm merkezi

Bu depo SDM’nin Windows kurulum dosyalarını, ayrıntılı sürüm açıklamalarını ve SHA-256 doğrulama dosyalarını sunar. **İndirme ve uygulama içinden güncelleme için GitHub hesabı veya token gerekmez.** Uygulamanın kaynak kodu ayrı, özel depoda tutulur.

Her yeni sürümün indirme sayfasında iki dosya bulunur:

| Dosya | Kullanımı |
|---|---|
| `SDM-Setup-<sürüm>.exe` | İlk kurulum ve güncelleme için Windows x64 paketi. |
| `SDM-Setup-<sürüm>.sha256` | Aynı setup dosyasının bütünlüğünü doğrulayan SHA-256 bilgisi. |

Tarayıcı eklentisi setup’a dahildir; yeni sürümler için ayrı eklenti ZIP’i indirmeniz gerekmez. Eski sürümlerin dosyaları sürüm geçmişinde korunur.

## 0.5.0: Atlas Pro ve Odak Akışı

**Atlas Pro**, durumları, kategorileri, kuyrukları ve ayrıntılı indirme tablosunu tek çalışma alanında toplar. **Odak Akışı**, ikon şeridi, indirme kartları ve pencere içinde açılan ayrıntı çekmecesiyle daha sade bir düzen sunar.

- Atlas / Odak tasarımı ile Açık / Koyu / Sistem renk modu ayrı seçilir.
- Tasarım ve renk seçimi Kaydet beklemeden önizlenir; iptal edildiğinde önceki görünüm geri gelir.
- Yeni kurulum Atlas + Açık ile başlar; eski görünüm tercihleri taşınır.
- Yeni indirme, tarayıcı yakalama, araçlar, ayrıntılar, HUD ve güncelleme pencereleri yenilendi.
- Medya araçlarında 128 / 192 / 256 / 320 kbps ses kalitesi seçimi bulunur.
- Türkçe / English sayı biçimi, kuyruklar ve indirme motorunun mevcut işlevleri korunur.

[0.5.0’ın ayrıntılı yenilikleri, geçiş adımları ve doğrulama bilgileri →](https://github.com/EmreGUNDOGAN/SDM-Updates/releases/tag/v0.5.0)

## Kurulum

1. [En güncel sürüm sayfasını](https://github.com/EmreGUNDOGAN/SDM-Updates/releases/latest) açın ve setup dosyasını indirin.
2. İsterseniz aynı sayfadaki SHA-256 dosyasıyla indirme bütünlüğünü kontrol edin.
3. Setup’ı çalıştırıp kurulum adımlarını izleyin.
4. Tarayıcı entegrasyonu için kurulumdaki Chrome/Opera seçeneğini işaretleyin ve açılan eklenti yönergelerini tamamlayın.

Python, FFmpeg, Deno veya 7-Zip’i ayrıca kurmanız gerekmez. İndirme zamanlamalarının çalışması için SDM açık olmalıdır.

## Mevcut SDM’yi güncelleme

**Ayarlar → Güncelleme** bölümündeki güncelleme kontrolünü kullanın. Yeni sürüm bulunduğunda setup indirilir, boyutu ve SHA-256 değeri doğrulanır; kurulum sizin onayınızla başlar.

Daha önce güncelleme deposuna erişim hatası aldıysanız kontrolü yeniden çalıştırın. Sürüm deposu artık herkese açıktır. GitHub tokenı girmeniz gerekmez. Alternatif olarak [son sürümün setup’ını](https://github.com/EmreGUNDOGAN/SDM-Updates/releases/latest) indirip kendiniz çalıştırabilirsiniz.

Tarayıcı eklentisini SDM’nin kurulum klasöründen yüklediyseniz kurulum sonrasında gerektiğinde tarayıcının eklenti sayfasındaki **Yeniden yükle** veya eklentideki **Eklentiyi yenile** seçeneğini kullanın; açık video sayfalarını da yenileyin.

## Bütünlüğü doğrulama

Setup ve SHA-256 dosyasını aynı klasöre indirin. PowerShell’de dosya adlarındaki `<sürüm>` alanını indirdiğiniz sürümle değiştirerek çalıştırın:

```powershell
$expected = (Get-Content -LiteralPath '.\SDM-Setup-<sürüm>.sha256').Split()[0]
$actual = (Get-FileHash -LiteralPath '.\SDM-Setup-<sürüm>.exe' -Algorithm SHA256).Hash
$actual -eq $expected
```

Sonucun `True` olması gerekir. SHA-256 kontrolü, indirdiğiniz dosyanın yayımlanan dosyayla aynı olduğunu doğrular. Setup dijital olarak imzalanmamıştır; Windows yayımlayıcı uyarısı gösterebilir.

## Doğrulama ve kullanım sınırları

Her sürümün notları, uygulanan testleri ve kapsamlarını açıklar. 0.5.0’da kaynak doğrulaması ve 97 regresyon testine ek olarak gerçek tarayıcı HTTP/SHA-256 kontrolleri, medya bölüm testleri ve derlenen paketin kaynakla karşılaştırılması yapıldı. Açılış, tray’den tam çıkış ve yeniden açılış ayrı test profillerinde sınandı.

İndirme hızı ve paralel bağlantı kazancı ağ ve sunucu koşullarına bağlıdır. DRM veya oturum gerektiren içerikler her durumda desteklenmeyebilir. İsteğe bağlı Kaspersky taraması için desteklenen uygulamanın kurulu olması gerekir; “tehdit bulunmadı” sonucu kesin güvenlik garantisi değildir.

Sorun bildirirken SDM sürümünü, yaptığınız işlemi ve görünen hata metnini paylaşın. Token, parola veya özel indirme bağlantılarını paylaşmayın.
