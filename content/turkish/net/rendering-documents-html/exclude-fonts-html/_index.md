---
"description": "GroupDocs.Viewer for .NET kullanarak işlenmiş HTML'den yazı tiplerini nasıl hariç tutacağınızı öğrenin. Sorunsuz belge görüntüleme için bu adım adım kılavuzu izleyin."
"linktitle": "Yazı Tiplerini İşlenen HTML'den Hariç Tut"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Yazı Tiplerini İşlenen HTML'den Hariç Tut"
"url": "/tr/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# Yazı Tiplerini İşlenen HTML'den Hariç Tut

## giriiş
.NET için GroupDocs.Viewer, geliştiricilerin .NET uygulamalarında harici bağımlılıklara ihtiyaç duymadan 50'den fazla belge biçimini görüntülemelerine olanak tanıyan güçlü bir belge oluşturma kütüphanesidir. Bu eğitimde, GroupDocs.Viewer'ın belirli bir özelliğine odaklanacağız: Yazı tiplerini işlenmiş HTML çıktısından hariç tutma. 
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. C# ve .NET geliştirme konusunda temel anlayış.
2. GroupDocs.Viewer for .NET yüklü. Buradan indirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).
3. C# geliştirmek için Visual Studio veya herhangi bir IDE.

## Ad Alanlarını İçe Aktar
C# kodunuzda gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıktı Dizinini Tanımlayın
Oluşturulan HTML dosyalarının kaydedilmesini istediğiniz dizini ayarlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
İşlenen belgenin ayrı sayfalarının dosya yollarının biçimini belirtin.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: Görüntüleyici Nesnesini Başlatın
Görüntülemek istediğiniz belgeyi içeren Viewer nesnesini örnekleştirin.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Kodunuz buraya gelecek
}
```
## Adım 4: HTML Görünüm Seçeneklerini Ayarlayın
Gömülü kaynakların biçimi ve hariç tutulacak yazı tipleri dahil olmak üzere HTML oluşturma seçeneklerini tanımlayın.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Adım 5: Belgeyi Oluşturun
Belgeyi işlemek için HTML görünüm seçeneklerini Viewer nesnesine geçirin.
```csharp
viewer.View(options);
```
## Adım 6: Çıktı Oluşturulan Belge Konumu
Kullanıcıya, oluşturulan HTML dosyalarının kaydedildiği yer hakkında bilgi verin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu eğitimde, .NET için GroupDocs.Viewer'ı kullanarak işlenmiş HTML çıktısından yazı tiplerini nasıl hariç tutacağımızı öğrendik. Yukarıda özetlenen adımları izleyerek, işleme sürecini özel gereksinimlerinizi karşılayacak şekilde özelleştirebilir ve uygulamalarınızda belgelerin en iyi şekilde görüntülenmesini sağlayabilirsiniz.
## SSS
### Oluşturulan HTML'den birden fazla yazı tipini hariç tutabilir miyim?
Evet, birden fazla yazı tipi adı ekleyebilirsiniz `FontsToExclude` HTML görünüm seçeneklerinde liste.
### GroupDocs.Viewer tüm .NET framework'leriyle uyumlu mudur?
Evet, GroupDocs.Viewer .NET Framework 4.6.1 ve üzeri sürümleri destekler.
### Uzak depolama konumlarındaki belgeleri işleyebilir miyim?
Evet, GroupDocs.Viewer yerel depolama alanlarının yanı sıra uzak depolama konumlarından ve akışlarından da belgelerin işlenmesini destekler.
### GroupDocs.Viewer HTML çıktısı için duyarlı tasarımı destekliyor mu?
Evet, HTML görünüm seçeneklerini buna göre ayarlayarak duyarlı görüntülemeyi etkinleştirebilirsiniz.
### GroupDocs.Viewer için teknik destek mevcut mu?
Evet, yardım alabilir ve tartışmalara katılabilirsiniz. [GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9).