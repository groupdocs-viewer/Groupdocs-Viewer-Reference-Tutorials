---
title: Satır ve Sütun Başlıklarını Oluştur
linktitle: Satır ve Sütun Başlıklarını Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: .NET'te belge görüntülemeyi geliştirin! GroupDocs.Viewer for .NET'i kullanarak satır ve sütun başlıklarını oluşturmayı öğrenin. HTML, JPG, PNG ve PDF çıktılarını keşfedin.
weight: 18
url: /tr/net/spreadsheet-rendering-options/render-row-column-headings/
---
## giriiş
.NET uygulamalarında belge görüntüleme deneyiminizi geliştirmek mi istiyorsunuz? GroupDocs.Viewer for .NET ile elektronik tablo dosyalarınızdaki satır ve sütun başlıklarını sorunsuz bir şekilde oluşturabilirsiniz. Bu eğitimde size HTML, JPG, PNG ve PDF gibi farklı çıktı formatlarını kullanarak satır ve sütun başlıklarını oluşturma sürecinde rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- .NET kitaplığı için GroupDocs.Viewer yüklendi.
- Test amaçlı örnek bir XLSX dosyası.
- C# ve .NET geliştirme konusunda çalışma bilgisi.
## Ad Alanlarını İçe Aktar
C# kodunuzda GroupDocs.Viewer'ı kullanmak için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Çıkış Dizinini Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. HTML'ye dönüştürün
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. JPG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. PNG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. PDF'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## Çözüm
Tebrikler! GroupDocs.Viewer for .NET'i kullanarak e-tablonuzdan satır ve sütun başlıklarını başarıyla oluşturdunuz. Uygulamanızın ihtiyaçlarına uygun farklı çıktı formatlarını deneyin.
## Sıkça Sorulan Sorular
### S: İşlenen belgeler için çıktı dizinini özelleştirebilir miyim?
 C: Evet, istediğiniz çıktı dizinini, çıktının bulunduğu kodda ayarlayabilirsiniz.`outputDirectory` değişken tanımlanır.
### S: GroupDocs.Viewer diğer elektronik tablo formatlarıyla uyumlu mudur?
C: Evet, GroupDocs.Viewer, XLS, XLSX, CSV ve daha fazlası dahil olmak üzere çeşitli elektronik tablo formatlarını destekler.
### S: Oluşturma işlemi sırasında istisnaları nasıl ele alabilirim?
C: İstisnaları işlemek ve kullanıcıya uygun mesajları günlüğe kaydetmek veya görüntülemek için try-catch bloklarını uygulayabilirsiniz.
### S: GroupDocs.Viewer'ı uygulamamda kullanmak için herhangi bir lisans gereksinimi var mı?
C: Evet, geçerli bir lisansa ihtiyacınız var. Test amacıyla geçici bir lisans alabilir veya üretim için tam bir lisans satın alabilirsiniz.
### S: Ek desteği veya topluluk tartışmalarını nerede bulabilirim?
 C: Ziyaret edin[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) Destek ve tartışmalar için.