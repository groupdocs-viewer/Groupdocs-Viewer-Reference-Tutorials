---
title: CDR Görüntülerini Oluştur
linktitle: CDR Görüntülerini Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak CDR görüntülerini HTML, JPG, PNG ve PDF'ye nasıl dönüştüreceğinizi öğrenin. Bu eğitimle CorelDRAW dosyalarını kolayca dönüştürün.
weight: 12
url: /tr/net/image-rendering/render-cdr-images/
---
## giriiş
Bu eğitimde, GroupDocs.Viewer for .NET'i kullanarak CDR (CorelDRAW) görüntülerini oluşturma sürecinde size rehberlik edeceğiz. CDR, öncelikle bir vektör grafik düzenleyicisi olan CorelDRAW ile ilişkili bir dosya formatıdır. GroupDocs.Viewer ile CDR dosyalarını HTML, JPG, PNG ve PDF gibi çeşitli formatlara kolayca dönüştürebilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
2. Belge Dizini: Oluşturulan görüntüleri kaydetmek istediğiniz dizini hazırlayın.
3. Temel C# Bilgisi: Kod örneklerini anlamak için C# programlama diline aşinalık gereklidir.
## Ad Alanlarını İçe Aktar
Kod örneklerine dalmadan önce gerekli ad alanlarını C# dosyanıza aktarın:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Şimdi her örneği birden fazla adıma ayıralım:
## HTML'ye dönüştürme
1. İşlenen HTML dosyalarını kaydetmek istediğiniz çıktı dizinini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML dosyaları için dosya yolu formatını belirtin:
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
## JPG'ye dönüştürülüyor
1. JPG dosyaları için dosya yolu formatını tanımlayın:
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
1. PNG dosyaları için dosya yolu formatını tanımlayın:
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
1. PDF için dosya yolu formatını tanımlayın:
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
3.  İsteğe bağlı olarak, oluşturma seçeneklerini belirtebilir veya ek parametreler ileterek belirli sayfaları oluşturabilirsiniz.`viewer.View()` yöntem.
## Çözüm
GroupDocs.Viewer for .NET'i kullanarak CDR görüntülerini HTML, JPG, PNG ve PDF gibi çeşitli formatlara dönüştürmek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek CDR dosyalarını gereksinimlerinize göre verimli bir şekilde farklı formatlara dönüştürebilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET, CDR dosyalarının tüm sürümleriyle uyumlu mu?
GroupDocs.Viewer for .NET, CorelDRAW'ın farklı sürümleri tarafından oluşturulan CDR dosyalarının oluşturulmasını destekler.
### İşlenen dosyaların çıktısını özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET çıktıyı özelleştirmek için görüntü kalitesini ayarlama, filigran ayarlama vb. gibi çeşitli seçenekler sunar.
### GroupDocs.Viewer for .NET herhangi bir dış bağımlılık gerektiriyor mu?
Hayır, GroupDocs.Viewer for .NET bağımsız bir kitaplıktır ve belgelerin işlenmesi için herhangi bir dış bağımlılık gerektirmez.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.groupdocs.com/).
### .NET için GroupDocs.Viewer desteğini nereden alabilirim?
 GroupDocs.Viewer topluluk forumundan destek alabilirsiniz[Burada](https://forum.groupdocs.com/c/viewer/9).