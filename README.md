<div align="center">
  <h1>SDM</h1>
  <p><strong>Windows için modern indirme yöneticisi</strong></p>
  <p>İndirmelerini planla. Hızını takip et. Dosyalarını tek yerden yönet.</p>
  <p>Windows 10 / 11 · Chrome ve Opera · Açık ve koyu tema</p>
  <p><a href="https://github.com/EmreGUNDOGAN/SDM-Updates/releases/latest"><strong>Son sürümü indir →</strong></a></p>
</div>

## Sürüm merkezi

Bu depo SDM'nin resmi kurulum dosyalarını, sürüm notlarını ve güncelleme doğrulama bilgilerini sunar. Uygulamanın kaynak kodları ayrı özel depoda tutulur.

| Dosya | Kullanımı |
|---|---|
| **SDM-Setup-0.4.0.exe** | Windows kurulum ve güncelleme paketi. |
| **SDM-Extension-0.4.0.zip** | Chrome/Opera eklentisinin ayrı paketi. |
| **SDM-Setup-0.4.0.sha256** | Kurulum dosyasının bütünlük kontrolü. |
| **latest.json** | Sürüm numarası, indirme adresi, boyut ve SHA-256 bilgileri. |

## Neler sunar?

- Uygun sunucularda paralel indirme; duraklatma ve kaldığı yerden devam.
- Tarayıcıda **Şimdi indir / Kuyruğa ekle / İptal et** seçimi; video kalitesi ve MP3.
- Ayrı kuyruklar, öncelik ve takvimle tekrarlayan indirme saatleri.
- Canlı hız grafiği, küçük masaüstü paneli ve tek tıkla interneti rahatlatma.
- Altyazı, kesme/dönüştürme, isteğe bağlı arşiv çıkarma ve klasör düzenleme.
- Tamamlandı penceresinde kullanıcı isteğiyle Kaspersky taraması.
- Site istisnaları, ayar yedekleme ve token gerektirmeyen GitHub güncellemesi.

## İlk kurulum

1. [Son sürüm sayfasından](https://github.com/EmreGUNDOGAN/SDM-Updates/releases/latest) setup dosyasını indirip çalıştır.
2. Chrome veya Opera kullanıyorsan ilgili eklenti seçeneğini seç.
3. Tarayıcıda geliştirici modunu açıp `%LOCALAPPDATA%\Programs\SDM\extension` klasörünü bir kez **Paketlenmemiş yükle** ile yükle.

Python, FFmpeg, Deno veya 7-Zip'i ayrıca kurman gerekmez. Zamanlama için SDM açık olmalıdır.

## Güncelleme

SDM'de **Ayarlar → Güncelleme → Güncellemeleri kontrol et** yolunu kullan. GitHub tokenı gerekmez. Setup indirilip SHA-256 ile doğrulanır; kurulum onayınla başlar.

0.3.1 eklentisinden geçerken tarayıcıda bir defa **Yeniden yükle** kullan. Sonraki sürümlerde eklentide **Eklentiyi yenile** düğmesi bulunur. Eklentinin SDM kurulum klasöründen yüklenmiş olması gerekir; açık video sayfalarını yenile.

## Doğrulama ve sınırlar

Kurulum dosyaları GitHub Actions Windows runner üzerinde üretilir. Ayrıntılar ve test bilgileri her sürümün notlarında bulunur. Setup dijital olarak imzalanmamıştır.

Paralel indirme her sunucuda hız artışı sağlamaz. DRM/oturum gerektiren kaynaklar desteklenmeyebilir. Kaspersky taraması için desteklenen uygulama bilgisayarda kurulu olmalıdır; “tehdit bulunmadı” kesin güvenlik garantisi değildir.

