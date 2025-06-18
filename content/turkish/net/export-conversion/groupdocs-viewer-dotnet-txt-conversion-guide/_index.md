---
"date": "2025-04-25"
"description": "Bu kapsamlı kılavuzla GroupDocs.Viewer for .NET kullanarak TXT dosyalarını HTML, JPG, PNG ve PDF gibi birden fazla formata nasıl dönüştüreceğinizi öğrenin."
"title": "GroupDocs.Viewer .NET&#58;i Kullanarak TXT'yi HTML, JPG, PNG, PDF'ye Dönüştürme Tam Bir Kılavuz"
"url": "/tr/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# GroupDocs.Viewer .NET ile TXT'yi Çoklu Biçimlere Dönüştürün

## giriiş

Metin belgelerini HTML, JPG, PNG veya PDF gibi çeşitli biçimlere zahmetsizce dönüştürmek mi istiyorsunuz? Belge dönüşümlerini yönetmek, özellikle birden fazla sayfa veya belirli biçim gereksinimleriyle uğraşırken zorlu olabilir. **.NET için GroupDocs.Viewer** TXT dosyalarının çeşitli çıktı biçimlerine dönüştürülme sürecini basitleştirerek verilerinizin erişilebilir ve görsel olarak çekici olmasını sağlar.

![TXT'yi .NET için GroupDocs.Viewer ile HTML, JPG, PNG, PDF'ye dönüştürün](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

Bu kılavuzda, TXT belgelerini çok sayfalı HTML, tek sayfalı HTML, JPG, PNG ve PDF'ye dönüştürmek için GroupDocs.Viewer for .NET'in nasıl kullanılacağını inceleyeceğiz. Sonunda şunlarda ustalaşacaksınız:
- GroupDocs.Viewer ile C# kullanarak TXT dosyalarını dönüştürme
- İhtiyaçlarınıza uygun farklı render seçeneklerinin uygulanması
- Dönüşümler sırasında performansı optimize etme

Belge dönüştürme zorluklarınızı çözmek için harekete geçelim.

## Ön koşullar

Başlamadan önce aşağıdakilerin hazır olduğundan emin olun:
- **Geliştirme Ortamı**: Visual Studio 2019 veya üzeri.
- **.NET Çerçevesi**: Sürüm 4.6.1 veya üzeri.
- **.NET Kütüphanesi için GroupDocs.Viewer**:
  - NuGet Paket Yöneticisi Konsolu Üzerinden: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - .NET CLI kullanımı: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Kolay takip edebilmek için C# programlama ve .NET'te temel dosya işlemlerine aşina olmanız önerilir.

## .NET için GroupDocs.Viewer Kurulumu

### Kurulum

Başlamak için şunu yükleyin: **GrupDokümanları.Görüntüleyici** Tercih ettiğiniz paket yöneticisini kullanarak kütüphaneyi çalıştırın:

#### NuGet Paket Yöneticisi Konsolu
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET Komut Satırı Arayüzü
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Lisanslama

Bir ile başlayabilirsiniz **ücretsiz deneme** veya bir tane elde edin **geçici lisans** .NET için GroupDocs.Viewer'ın tüm yeteneklerini değerlendirme sınırlamaları olmadan keşfetmek için:
- Ücretsiz Deneme: [Buradan indirin](https://releases.groupdocs.com/viewer/net/)
- Geçici Lisans: [Burada talep edin](https://purchase.groupdocs.com/temporary-license/)

Devam eden kullanım için doğrudan şu adresten bir lisans satın almayı düşünün: [GrupDokümanları](https://purchase.groupdocs.com/buy).

### Temel Başlatma

Projenizde GroupDocs.Viewer'ı kurmak için:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Viewer nesnesini TXT dosya yoluyla başlatın.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Oluşturduğunuz kodu buraya yazacaksınız.
}
```

## Uygulama Kılavuzu

Şimdi her bir özelliği inceleyelim ve bunları nasıl uygulayabileceğinizi görelim.

### TXT Belgesini Çok Sayfalı HTML'ye Dönüştür

#### Genel bakış
Bu özellik, bir TXT belgesinin çok sayfalı HTML biçimine dönüştürülmesini gösterir. Metin dosyasının her sayfası, gömülü kaynaklara sahip ayrı bir HTML dosyası olarak işlenir.

#### Adım 1: Görüntüleyiciyi Ayarlayın

Bir tane oluştur `Viewer` kaynak TXT dosyanız için nesne:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Görüntüleyiciyi örnek bir metin dosyasıyla başlatın.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2. adıma geçin...
```

#### Adım 2: HTML Görünüm Seçeneklerini Yapılandırın

Kurmak `HtmlViewOptions` her sayfayı ayrı ayrı işlemek için:

```csharp
// Çok sayfalı görüntüleme için HTML görünüm seçeneklerini ayarlayın.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Belgeyi çok sayfalı HTML olarak işleyin.
viewer.View(options);
}
```

**Açıklama**: : `ForEmbeddedResources()` Bu yöntem, görseller ve stiller gibi kaynakların doğrudan HTML dosyasına gömülmesini sağlayarak kolay paylaşımı kolaylaştırır.

### TXT Belgesini Tek Sayfa HTML'ye Dönüştür

#### Genel bakış
TXT belgesini tek bir HTML sayfasına dönüştürün. Bu, tek bir sürekli web sayfası olarak görüntülenmesi gereken belgeler için idealdir.

#### Adım 1: Görüntüleyiciyi Ayarlayın

Başlat `Viewer` nesne:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Farklı bir metin dosyası için yeni bir Görüntüleyici örneği başlatın.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // 2. adıma geçin...
```

#### Adım 2: Tek Sayfa HTML Seçeneklerini Yapılandırın

Yapılandır `HtmlViewOptions` tek sayfa ayarı etkinleştirildiğinde:

```csharp
// Tek bir HTML sayfasında görüntüleme için seçenekleri ayarlayın.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Tek bir HTML sayfası olarak işleyin.
viewer.View(options);
}
```

**Açıklama**: : `RenderToSinglePage` özelliği, tüm içeriğin tek bir sayfada oluşturulmasını sağlar.

### TXT Belgesini JPG'ye Dönüştür

#### Genel bakış
Bu özellik, bir metin belgesini görsel sunumlar veya arşivleme amaçları için kullanışlı olan JPEG görüntüsüne dönüştürmenize olanak tanır.

#### Adım 1: Görüntüleyiciyi Ayarlayın

Hazırla `Viewer` nesne:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Görüntüleyiciyi bir örnek dosyayla başlatın.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2. adıma geçin...
```

#### Adım 2: JPG Görünüm Seçeneklerini Yapılandırın

Kurmak `JpgViewOptions` görüntü oluşturma için:

```csharp
// JPG resmi olarak işleme seçeneklerini ayarlayın.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Belgeyi JPEG dosyası olarak işleyin.
viewer.View(options);
}
```

**Açıklama**: : `JpgViewOptions` sınıf, belgenizin her sayfasının JPEG formatında nasıl işleneceğini ve kaydedileceğini belirtir.

### TXT Belgesini PNG'ye Dönüştür

#### Genel bakış
Bir metin belgesini PNG formatına dönüştürerek, şeffaflık desteğiyle yüksek kaliteli görüntü çıktısı sunun.

#### Adım 1: Görüntüleyiciyi Ayarlayın

Başlat `Viewer` nesne:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// TXT dosyanız için bir görüntüleyici örneği oluşturun.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2. adıma geçin...
```

#### Adım 2: PNG Görünüm Seçeneklerini Yapılandırın

Kurmak `PngViewOptions`:

```csharp
// PNG resmi olarak işlemek için görünüm seçeneklerini ayarlayın.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Belgeyi PNG formatında işleyin.
viewer.View(options);
}
```

**Açıklama**: : `PngViewOptions` class, her sayfanın şeffaflıkla işlenmesine olanak tanır ve bu sayede katmanlı grafikler için uygun hale gelir.

### TXT Belgesini PDF'ye Dönüştür

#### Genel bakış
Bu özellik, metin belgelerini herkesin erişebileceği bir PDF formatına dönüştürmek için mükemmeldir.

#### Adım 1: Görüntüleyiciyi Ayarlayın

Hazırla `Viewer` nesne:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Örnek metin dosyanız için bir görüntüleyici örneği başlatın.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2. adıma geçin...
```

#### Adım 2: PDF Görünüm Seçeneklerini Yapılandırın

Kurmak `PdfViewOptions`:

```csharp
// PDF belgesi olarak işlemek için görünüm seçeneklerini ayarlayın.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Belgeyi PDF dosyasına dönüştürün.
viewer.View(options);
}
```

**Açıklama**: : `PdfViewOptions` sınıf, TXT dosyalarınızı PDF belgelerine nasıl dönüştüreceğinizi ve kaydedeceğinizi belirtir.

## Çözüm

GroupDocs.Viewer for .NET ile metin belgelerini çeşitli biçimlere dönüştürmek kolaydır. Bu kılavuz, TXT dosyalarını C# kullanarak çok sayfalı HTML, tek sayfalı HTML, JPG, PNG ve PDF'ye dönüştürmeyi ele almıştır. Belge erişilebilirliğini veya uyumluluğunu geliştirmek istiyorsanız, bu yöntemler sağlam çözümler sunar.

Daha fazla yardım veya daha gelişmiş özellikler için şuraya bakın: [resmi GroupDocs.Viewer belgeleri](https://docs.groupdocs.com/viewer/net/). Keyifli kodlamalar!