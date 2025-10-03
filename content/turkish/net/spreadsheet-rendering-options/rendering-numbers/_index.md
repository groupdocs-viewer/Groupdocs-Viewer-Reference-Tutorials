---
"description": "Numbers dosyalarını kusursuz bir şekilde işlemede Groupdocs.Viewer for .NET'in gücünü keşfedin. HTML, JPG, PNG ve PDF'ye zahmetsizce dönüştürün."
"linktitle": "Sayıların Oluşturulması"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Sayıların Oluşturulması"
"url": "/tr/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# Sayıların Oluşturulması

## giriiş
Groupdocs.Viewer for .NET kullanarak Numbers dosyalarını işlemeye yönelik bu adım adım öğreticiye hoş geldiniz. İster deneyimli bir geliştirici olun ister yeni başlayan, bu kılavuz Numbers belgelerini çeşitli biçimlere dönüştürme sürecinde size yol gösterecektir. Groupdocs.Viewer for .NET, belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre etmenizi sağlayan güçlü bir araçtır.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- C# ve .NET geliştirme konusunda çalışma bilgisi.
- Groupdocs.Viewer for .NET kütüphanesi yüklendi. İndirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).
- Çıktı dosyalarının kaydedileceği belge dizin yolunuz.
## Ad Alanlarını İçe Aktar
C# projenizde Groupdocs.Viewer kitaplığını kullanmak için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıktı Dizinini Ayarlayın
İşleme başlamadan önce, dönüştürülen dosyaların kaydedileceği çıktı dizinini tanımlayın. "Belge Dizininiz"i gerçek yol ile değiştirin:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Çok Sayfalı HTML'ye Dönüştür
Numbers dosyasını çok sayfalı HTML'e dönüştürmek için aşağıdaki kodu kullanın:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 3: JPG'ye dönüştürün
Numbers dosyasını aşağıdaki kodla JPG formatına dönüştürün:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 4: PNG'ye dönüştürün
Aşağıdaki kodu kullanarak Numbers dosyasını PNG formatına dönüştürün:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 5: PDF'ye dönüştürün
Son olarak Numbers dosyasını aşağıdaki kodu kullanarak PDF formatına dönüştürün:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Tebrikler! Groupdocs.Viewer for .NET kullanarak Numbers dosyalarını çeşitli biçimlere başarıyla dönüştürdünüz.
## Çözüm
Bu eğitimde, .NET için Groupdocs.Viewer kullanarak Numbers dosyalarını işlemenin temellerini ele aldık. Bu güçlü kütüphane, .NET uygulamalarınızdaki belgeleri görüntülemek ve dönüştürmek için kusursuz bir entegrasyon sağlar.
## SSS
### Groupdocs.Viewer for .NET'i diğer belge türleriyle birlikte kullanabilir miyim?
Evet, Groupdocs.Viewer Word, Excel, PDF ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Test amaçlı geçici lisans mevcut mudur?
Evet, geçici bir lisans alabilirsiniz [Burada](https://purchase.groupdocs.com/temporary-license/) test için.
### Groupdocs.Viewer for .NET için desteği nerede bulabilirim?
Ziyaret edin [Groupdocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) yardım ve tartışmalar için.
### Groupdocs.Viewer for .NET'in tam sürümünü nasıl satın alabilirim?
Tam sürümü satın alabilirsiniz [Burada](https://purchase.groupdocs.com/buy).
### Ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü keşfedebilirsiniz [Burada](https://releases.groupdocs.com/).