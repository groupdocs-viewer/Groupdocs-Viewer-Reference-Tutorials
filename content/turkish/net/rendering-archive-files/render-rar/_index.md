---
"description": "GroupDocs.Viewer for .NET kullanarak RAR arşivlerini HTML, JPG, PNG veya PDF formatlarına nasıl dönüştüreceğinizi öğrenin. RAR arşivlerinin içeriklerini kolayca görüntüleyin ve paylaşın."
"linktitle": "RAR Arşivlerini Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "RAR Arşivlerini Oluştur"
"url": "/tr/net/rendering-archive-files/render-rar/"
"weight": 13
---

# RAR Arşivlerini Oluştur

## giriiş
RAR arşivleri, birden fazla dosya ve klasörü tek bir kapsayıcıya sıkıştırmak ve depolamak için popüler bir biçimdir. RAR arşivlerini HTML, JPG, PNG veya PDF gibi çeşitli biçimlere dönüştürmek, bu arşivlerin içeriklerini görüntülemek veya paylaşmak için önemli olabilir. Bu eğitimde, .NET için GroupDocs.Viewer kullanarak RAR arşivlerinin nasıl oluşturulacağını inceleyeceğiz.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. .NET için GroupDocs.Viewer: .NET için GroupDocs.Viewer kitaplığını yükleyin [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).
2. Örnek RAR Arşivi: İşleme için hazır bir örnek RAR arşivi bulundurun.

## Ad Alanlarını İçe Aktar
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: HTML'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 3: JPG'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 4: PNG'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 5: PDF'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Çözüm
RAR arşivlerini çeşitli biçimlere dönüştürmek GroupDocs.Viewer for .NET ile basit hale getirildi. Bu eğitimde özetlenen adımları izleyerek, RAR arşivlerini HTML, JPG, PNG veya PDF biçimlerine zahmetsizce dönüştürebilir, içeriklerinin kolayca görüntülenmesini ve paylaşılmasını sağlayabilirsiniz.
## SSS
### GroupDocs.Viewer for .NET şifrelenmiş RAR arşivlerini işleyebilir mi?
Evet, GroupDocs.Viewer for .NET, oluşturma işlemi sırasında gerekli parolaların sağlanması koşuluyla şifrelenmiş RAR arşivlerinin oluşturulmasını destekler.
### İşlenen belgelerin çıktı görünümünü özelleştirmek mümkün müdür?
Kesinlikle! GroupDocs.Viewer for .NET, kullanıcıların kendi öğreticilerine göre işlenmiş belgelerin görünümünü özelleştirmelerine olanak tanıyan kapsamlı özelleştirme seçenekleri sunar.
### GroupDocs.Viewer for .NET, RAR haricindeki diğer arşiv formatlarını da destekliyor mu?
Evet, GroupDocs.Viewer for .NET, ZIP, TAR, 7z ve daha fazlası dahil olmak üzere çeşitli arşiv formatlarının işlenmesini destekler.
### GroupDocs.Viewer for .NET'i web uygulamama entegre edebilir miyim?
Elbette! GroupDocs.Viewer for .NET, hem masaüstü hem de web uygulamalarına entegrasyona uygun API'ler sağlar.
### GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümünden yararlanabilirsiniz. [web sitesi](https://releases.groupdocs.com/).