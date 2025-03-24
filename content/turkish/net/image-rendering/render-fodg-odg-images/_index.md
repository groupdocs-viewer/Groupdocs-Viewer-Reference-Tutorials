---
title: FODG ve ODG Görüntülerini Oluşturun
linktitle: FODG ve ODG Görüntülerini Oluşturun
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak FODG ve ODG görüntülerini HTML, JPG, PNG ve PDF'ye nasıl dönüştüreceğinizi öğrenin. Belge işlemenizi geliştirin.
weight: 15
url: /tr/net/image-rendering/render-fodg-odg-images/
---
## giriiş
Yazılım geliştirme dünyasında belge formatlarının verimli şekilde kullanılması çok önemlidir. GroupDocs.Viewer for .NET, .NET uygulamalarında FODG ve ODG görüntülerini işleme sürecini basitleştirmek için tasarlanmış güçlü bir araçtır. Bu eğitim, GroupDocs.Viewer for .NET'i kullanarak bu görüntüleri HTML, JPG, PNG ve PDF gibi çeşitli formatlara dönüştürmek için gereken adımlarda size yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Sisteminizde .NET Framework'ün kurulu olduğundan emin olun.
3. Temel C# bilgisi: C# programlama diline aşinalık faydalı olacaktır.

## Ad Alanlarını İçe Aktar
Uygulamaya başlamadan önce gerekli ad alanlarını içe aktarın:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Adım 1: Çıkış Dizinini Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"`oluşturulan görüntüleri kaydetmek istediğiniz dizin yoluyla.
## 2. Adım: HTML'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Bu adım, FODG görüntüsünü HTML formatına dönüştürür.
## 3. Adım: JPG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Burada FODG görüntüsü JPG formatına dönüştürülür.
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
## Adım 5: PDF'ye Dönüştür
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
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak FODG ve ODG görüntülerinin çeşitli formatlara nasıl dönüştürüleceğini araştırdık. Bu adımları izleyerek belge oluşturma yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET, .NET Framework'ün tüm sürümleriyle uyumlu mu?
GroupDocs.Viewer for .NET, en yenileri de dahil olmak üzere çok çeşitli .NET Framework sürümleriyle uyumludur.
### Belgeleri GroupDocs.Viewer for .NET ile eşzamansız olarak görüntüleyebilir miyim?
Evet, GroupDocs.Viewer for .NET, gelişmiş performans için eşzamansız işleme yetenekleri sağlar.
### GroupDocs.Viewer for .NET şifrelenmiş belgelerin görüntülenmesini destekliyor mu?
Evet, GroupDocs.Viewer for .NET, şifrelenmiş belgelerin uygun şifre çözme anahtarlarıyla görüntülenmesini destekler.
### Oluşturma çıktısını GroupDocs.Viewer for .NET ile özelleştirmek mümkün mü?
Kesinlikle GroupDocs.Viewer for .NET, işleme çıktısını gereksinimlerinize göre uyarlamak için çeşitli özelleştirme seçenekleri sunar.
### GroupDocs.Viewer for .NET'i kullanarak uzak depolama konumlarındaki belgeleri işleyebilir miyim?
Evet, GroupDocs.Viewer for .NET, belgelerin hem yerel hem de uzak depolama konumlarından görüntülenmesini destekler.