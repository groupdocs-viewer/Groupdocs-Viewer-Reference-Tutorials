---
"description": "GroupDocs.Viewer for .NET kullanarak PDF'de metin seçimini nasıl devre dışı bırakacağınızı öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin."
"linktitle": "PDF'de Metin Seçimini Devre Dışı Bırak"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF'de Metin Seçimini Devre Dışı Bırak"
"url": "/tr/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# PDF'de Metin Seçimini Devre Dışı Bırak

## giriiş
.NET için GroupDocs.Viewer, geliştiricilerin .NET uygulamalarına zahmetsizce belge görüntüleme yeteneklerini entegre etmelerine olanak tanıyan güçlü bir belge oluşturma API'sidir. GroupDocs.Viewer tarafından sağlanan temel işlevlerden biri, PDF belgelerinde metin seçimini devre dışı bırakma yeteneğidir. Bu özellik, kullanıcıların hassas belgelerden metin kopyalamasını engellemeniz gereken senaryolarda özellikle yararlıdır ve belge güvenliğini ve bütünlüğünü sağlar.

![GroupDocs.Viewer .NET ile PDF'de Metin Seçimini Devre Dışı Bırakma](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Ön koşullar
GroupDocs.Viewer for .NET kullanarak PDF'de metin seçimini devre dışı bırakmaya ilişkin adım adım kılavuza dalmadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:
1. GroupDocs.Viewer for .NET'in Kurulumu: GroupDocs.Viewer for .NET'i indirip kurduğunuzdan emin olun. [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).
2. Belge Dizini: Belgelerinizin saklanacağı bir dizin hazırlayın. PDF belgesini işlemek için bu dizini kod parçacığında belirtmeniz gerekecektir.

## Ad Alanlarını İçe Aktar
Öncelikle, .NET için GroupDocs.Viewer tarafından sağlanan işlevlere erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi, .NET için GroupDocs.Viewer'ı kullanarak bir PDF belgesinde metin seçimini devre dışı bırakma sürecini birden fazla adıma bölelim:
## Adım 1: Çıktı Dizinini Belirleyin
```csharp
string outputDirectory = "Your Document Directory";
```
Bu adımda, değiştirin `"Your Document Directory"` PDF belgenizin bulunduğu dizin yolunu belirtin.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bu adım, işlenen HTML sayfalarının dosya yollarının biçimini tanımlar. PDF belgesinin her sayfası, sıralı sayfa numarasına sahip bir HTML dosyasına dönüştürülecektir.
## Adım 3: Metin Seçimi Devre Dışı Bırakılmış PDF Belgesini Oluşturun
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Yer değiştirmek `"Path to Your PDF Document"` PDF dosyanızın gerçek yoluyla. Bu kod parçacığı bir `Viewer` nesne, kaynakları yerleştirmek için HTML görünüm seçeneklerini yapılandırır ve metin seçimini ayarlayarak devre dışı bırakır `RenderTextAsImage` mülk `true`.
## Adım 4: Başarı Mesajını Göster
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
PDF belgesi işlendikten sonra bu adım, işlenen HTML sayfalarının saklandığı dizinle birlikte bir başarı mesajı görüntüler.

## Çözüm
Bu eğitimde, .NET için GroupDocs.Viewer kullanarak PDF belgelerinde metin seçimini nasıl devre dışı bırakacağımızı öğrendik. Adım adım kılavuzu izleyerek, bu özelliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, belge güvenliğini sağlayabilir ve kullanıcı deneyimini geliştirebilirsiniz.
## SSS
### Oluşturulan HTML sayfaları için çıktı dizinini özelleştirebilir miyim?
Evet, oluşturulan HTML sayfalarının saklanmasını istediğiniz herhangi bir dizin yolunu belirtebilirsiniz.
### GroupDocs.Viewer for .NET, .NET framework'ün farklı sürümleriyle uyumlu mudur?
Evet, GroupDocs.Viewer for .NET, .NET Core ve .NET Framework dahil olmak üzere .NET framework'ün çeşitli sürümleriyle uyumludur.
### Metin seçimini devre dışı bırakmak PDF belgesinin diğer işlevlerini etkiler mi?
Hayır, metin seçimini devre dışı bırakmak yalnızca kullanıcıların belgeden metin seçmesini ve kopyalamasını engeller. Diğer işlevler bozulmadan kalır.
### Belgeyi oluşturduktan sonra metin seçimini tekrar etkinleştirebilir miyim?
Evet, metin seçimini yalnızca şunu ayarlayarak etkinleştirebilirsiniz: `RenderTextAsImage` mülk `false` HTML görünüm seçeneklerinde.
### GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz: [web sitesi](https://releases.groupdocs.com/).