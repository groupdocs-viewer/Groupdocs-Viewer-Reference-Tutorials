---
"description": "GroupDocs.Viewer for .NET kullanarak CDR görüntülerini HTML, JPG, PNG ve PDF'ye nasıl dönüştüreceğinizi öğrenin. Bu eğitimle CorelDRAW dosyalarını kolayca dönüştürün."
"linktitle": "CDR Görüntülerini Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CDR Görüntülerini Oluştur"
"url": "/tr/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# CDR Görüntülerini Oluştur

## giriiş
Bu eğitimde, .NET için GroupDocs.Viewer kullanarak CDR (CorelDRAW) görüntülerini işleme sürecinde size rehberlik edeceğiz. CDR, öncelikle vektör grafik düzenleyicisi olan CorelDRAW ile ilişkilendirilen bir dosya biçimidir. GroupDocs.Viewer ile CDR dosyalarını HTML, JPG, PNG ve PDF gibi çeşitli biçimlere kolayca dönüştürebilirsiniz.

![.NET için GroupDocs.Viewer ile CDR Görüntülerini Oluşturun](/viewer/image-rendering/render-cdr-images.png)

## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i yüklediğinizden emin olun. Bunu şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/viewer/net/).
2. Belge Dizini: Oluşturulan görselleri kaydetmek istediğiniz dizini hazırlayın.
3. Temel C# Bilgisi: Kod örneklerini anlayabilmek için C# programlama diline aşina olmak gerekir.
## Ad Alanlarını İçe Aktar
Kod örneklerine dalmadan önce, gerekli ad alanlarını C# dosyanıza aktarın:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Şimdi her örneği birden fazla adıma bölelim:
## HTML'ye dönüştürme
1. Oluşturulan HTML dosyalarını kaydetmek istediğiniz çıktı dizinini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML dosyaları için dosya yolu biçimini belirtin:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. CDR dosyasını HTML'ye dönüştürmek için Viewer sınıfını kullanın:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## JPG'ye dönüştürme
1. JPG dosyaları için dosya yolu biçimini tanımlayın:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. CDR dosyasını JPG'ye dönüştürmek için Viewer sınıfını kullanın:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PNG'ye dönüştürme
1. PNG dosyaları için dosya yolu biçimini tanımlayın:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. CDR dosyasını PNG'ye dönüştürmek için Viewer sınıfını kullanın:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PDF'ye dönüştürme
1. PDF için dosya yolu biçimini tanımlayın:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. CDR dosyasını PDF'ye dönüştürmek için Viewer sınıfını kullanın:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. İsteğe bağlı olarak, ek parametreler geçirerek işleme seçeneklerini belirleyebilir veya belirli sayfaları işleyebilirsiniz. `viewer.View()` yöntem.
## Çözüm
GroupDocs.Viewer for .NET kullanarak CDR görüntülerini HTML, JPG, PNG ve PDF gibi çeşitli biçimlere dönüştürmek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, gereksinimlerinize göre CDR dosyalarını farklı biçimlere verimli bir şekilde dönüştürebilirsiniz.
## SSS
### GroupDocs.Viewer for .NET tüm CDR dosya sürümleriyle uyumlu mudur?
GroupDocs.Viewer for .NET, CorelDRAW'un farklı sürümleriyle oluşturulmuş CDR dosyalarının işlenmesini destekler.
### Oluşturulan dosyaların çıktısını özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET, görüntü kalitesini ayarlama, filigran ayarlama vb. gibi çıktıyı özelleştirmek için çeşitli seçenekler sunar.
### GroupDocs.Viewer for .NET herhangi bir harici bağımlılık gerektiriyor mu?
Hayır, GroupDocs.Viewer for .NET bağımsız bir kütüphanedir ve belgeleri oluşturmak için herhangi bir harici bağımlılığa ihtiyaç duymaz.
### GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için desteği nereden alabilirim?
GroupDocs.Viewer topluluk forumundan destek alabilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9).