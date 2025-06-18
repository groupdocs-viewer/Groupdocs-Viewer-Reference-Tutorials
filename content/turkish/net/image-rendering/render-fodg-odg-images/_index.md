---
"description": "GroupDocs.Viewer for .NET kullanarak FODG ve ODG görüntülerini HTML, JPG, PNG ve PDF'ye nasıl dönüştüreceğinizi öğrenin. Belge işleme becerilerinizi geliştirin."
"linktitle": "FODG ve ODG Görüntülerini Oluşturun"
"second_title": "GroupDocs.Viewer .NET API"
"title": "FODG ve ODG Görüntülerini Oluşturun"
"url": "/tr/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# FODG ve ODG Görüntülerini Oluşturun

## giriiş
Yazılım geliştirme dünyasında, belge biçimlerinin etkili bir şekilde işlenmesi çok önemlidir. GroupDocs.Viewer for .NET, .NET uygulamaları içinde FODG ve ODG görüntülerini işleme sürecini basitleştirmek için tasarlanmış güçlü bir araçtır. Bu eğitim, GroupDocs.Viewer for .NET kullanarak bu görüntüleri HTML, JPG, PNG ve PDF gibi çeşitli biçimlere işlemek için gereken adımlarda size yol gösterecektir.

![.NET için GroupDocs.Viewer ile FODG ve ODG Görüntülerini Oluşturun](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirin ve yükleyin: [Burada](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Sisteminizde .NET Framework'ün yüklü olduğundan emin olun.
3. Temel C# bilgisi: C# programlama diline aşinalık faydalı olacaktır.

## Ad Alanlarını İçe Aktar
Uygulamaya başlamadan önce gerekli ad alanlarını içe aktarın:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Adım 1: Çıktı Dizinini Ayarla
```csharp
string outputDirectory = "Your Document Directory";
```
Yer değiştirmek `"Your Document Directory"` işlenmiş görselleri kaydetmek istediğiniz dizin yolunu yazın.
## Adım 2: HTML'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Bu adım FODG görüntüsünü HTML formatına dönüştürür.
## Adım 3: JPG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Burada FODG görüntüsü JPG formatına dönüştürülüyor.
## Adım 4: PNG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Bu adım FODG görüntüsünü PNG formatına dönüştürür.
## Adım 5: PDF'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Son olarak FODG görüntüsü PDF formatına dönüştürülür.

## Çözüm
Bu eğitimde, GroupDocs.Viewer for .NET kullanarak FODG ve ODG görüntülerinin çeşitli biçimlere nasıl işleneceğini inceledik. Bu adımları izleyerek, belge işleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS
### GroupDocs.Viewer for .NET, .NET Framework'ün tüm sürümleriyle uyumlu mudur?
GroupDocs.Viewer for .NET, en son sürümler de dahil olmak üzere çok çeşitli .NET Framework sürümleriyle uyumludur.
### GroupDocs.Viewer for .NET ile belgeleri eşzamansız olarak görüntüleyebilir miyim?
Evet, GroupDocs.Viewer for .NET, gelişmiş performans için eşzamansız işleme yetenekleri sağlar.
### GroupDocs.Viewer for .NET şifrelenmiş belgelerin işlenmesini destekliyor mu?
Evet, GroupDocs.Viewer for .NET, şifrelenmiş belgelerin uygun şifre çözme anahtarlarıyla işlenmesini destekler.
### GroupDocs.Viewer for .NET ile render çıktısını özelleştirmek mümkün müdür?
Kesinlikle, GroupDocs.Viewer for .NET, gereksinimlerinize göre çıktı oluşturmayı özelleştirmek için çeşitli özelleştirme seçenekleri sunar.
### GroupDocs.Viewer for .NET kullanarak uzak depolama konumlarındaki belgeleri görüntüleyebilir miyim?
Evet, GroupDocs.Viewer for .NET, belgelerin hem yerel hem de uzak depolama konumlarından işlenmesini destekler.