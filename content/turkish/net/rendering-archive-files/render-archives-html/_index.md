---
"description": "GroupDocs.Viewer for .NET kullanarak arşivleri HTML sayfalarına nasıl dönüştüreceğinizi öğrenin. Belge görüntüleme yeteneklerini .NET uygulamalarınıza zahmetsizce entegre edin."
"linktitle": "Arşivleri Tek veya Çoklu HTML Sayfalarına Dönüştürün"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Arşivleri Tek veya Çoklu HTML Sayfalarına Dönüştürün"
"url": "/tr/net/rendering-archive-files/render-archives-html/"
"weight": 12
---

# Arşivleri Tek veya Çoklu HTML Sayfalarına Dönüştürün

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin .NET uygulamalarına belge görüntüleme yeteneklerini zahmetsizce entegre etmelerine olanak tanıyan güçlü bir belge oluşturma kütüphanesidir. Arşivleri tek veya birden fazla HTML sayfasına oluşturmanız gerekip gerekmediğine bakılmaksızın, bu eğitim sizi adım adım süreç boyunca yönlendirecektir.
## Ön koşullar
Bu eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: Projenizde kütüphanenin yüklü olduğundan emin olun. Buradan indirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için çalışan bir geliştirme ortamı kurun.
3. Belge Dizini: Belgelerinizin saklanacağı bir dizin hazırlayın.
4. C# Temel Anlayışı: C# programlama dilinin temellerini öğrenin.

## Ad Alanlarını İçe Aktar
C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

.NET için GroupDocs.Viewer'ı kullanarak arşivleri tek veya birden fazla HTML sayfasına dönüştürmek için şu adımları izleyin:
## Adım 1: Çıktı Dizinini Ayarla
Oluşturulan HTML sayfalarının kaydedilmesini istediğiniz dizini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Dosya Yolu Biçimini Tanımlayın
HTML sayfaları için dosya yolu biçimini belirtin. Tek sayfalık işleme için:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Çok sayfalı görüntüleme için:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Adım 3: Tek Sayfa HTML'ye Dönüştür
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Adım 4: Birden Fazla Sayfa HTML'sine Dönüştür
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Sayfa başına öğeleri ayarla
    viewer.View(options);
}
```
## Adım 5: Çıktıyı Kontrol Edin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET kullanarak arşivleri HTML sayfalarına dönüştürmek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS
### Arşivlerin dışında başka belge formatlarını da işleyebilir miyim?
Evet, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX ve daha fazlası dahil olmak üzere çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer hem masaüstü hem de web uygulamaları için uygun mudur?
Kesinlikle, GroupDocs.Viewer hem masaüstü hem de web uygulamalarında sorunsuz bir şekilde kullanılabilir.
### GroupDocs.Viewer görüntüleyici arayüzü için özelleştirme seçenekleri sunuyor mu?
Evet, görüntüleyici arayüzünü ihtiyaçlarınıza göre özelleştirebilirsiniz.
### GroupDocs.Viewer ile belgeleri eşzamansız olarak görüntüleyebilir miyim?
Evet, GroupDocs.Viewer gelişmiş performans için asenkron işleme yetenekleri sağlar.
### GroupDocs.Viewer belge açıklamalarını destekliyor mu?
Evet, GroupDocs.Viewer kullanıcıların belge açıklamalarını etkin bir şekilde görüntülemesine ve yönetmesine olanak tanır.