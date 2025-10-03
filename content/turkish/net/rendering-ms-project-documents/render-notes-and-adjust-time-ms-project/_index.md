---
"description": "GroupDocs.Viewer for .NET ile MS Project belgelerinin işlenmesinde uzmanlaşın. Notları işleyin, zaman birimlerini ayarlayın ve çeşitli çıktı biçimlerini zahmetsizce keşfedin."
"linktitle": "Render Notları ve Zaman Birimlerini Ayarlama (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Render Notları ve Zaman Birimlerini Ayarlama (MS Project)"
"url": "/tr/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Render Notları ve Zaman Birimlerini Ayarlama (MS Project)

## giriiş
.NET için GroupDocs.Viewer, geliştiricilerin .NET uygulamaları içinde çeşitli belge biçimlerini görüntülemelerine ve düzenlemelerine olanak tanıyan güçlü bir belge oluşturma API'sidir. Bu eğitimde, özellikle MS Project belgeleri için notları oluşturmaya ve zaman birimlerini ayarlamaya odaklanacağız.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET kitaplığını indirip kurduğunuzdan emin olun. Bunu şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET desteğiyle tercih ettiğiniz geliştirme ortamını kurun.
3. MS Project Dokümanı: Test için hazır bir örnek MS Project dokümanınız olsun.
## Ad Alanlarını İçe Aktar
Öncelikle MS Project belgelerini oluşturmaya başlamak için gerekli ad alanlarını içe aktaralım:
## Adım 1: Ad Alanlarını İçe Aktar
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Artık gerekli ad alanlarını içe aktardığımıza göre, kapsamlı bir anlayış için her örneği birden fazla adıma bölelim.
## MS Project Belgesini HTML'ye Dönüştürme
Bir MS Project belgesini notlar eklenmiş şekilde HTML formatına dönüştürmek için şu adımları izleyin:
### Adım 2: Çıktı Dizinini ve Dosya Biçimini Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Adım 3: Görüntüleyici Nesnesini Başlatın ve Seçenekleri Ayarlayın
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Adım 4: Belgeyi HTML'ye Dönüştür
```csharp
viewer.View(options);
```
## MS Project Belgesini Görüntü Formatlarına Dönüştürme
MS Project belgelerini JPG ve PNG gibi resim formatlarına da dönüştürebilirsiniz. İşte nasıl:
### Adım 5: JPG için Çıktı Dizini ve Dosya Biçimini Ayarlayın
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Adım 6: Görüntüleyici Nesnesini Başlatın ve JPG Seçeneklerini Ayarlayın
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Adım 7: Belgeyi JPG'ye Dönüştür
```csharp
viewer.View(options);
```
PNG ve diğer resim formatlarına dönüştürmek için benzer adımları tekrarlayın.
## MS Project Belgesini PDF'ye Dönüştürme
Bir MS Project belgesini PDF formatına dönüştürmek için aşağıdaki adımları izleyin:
### Adım 8: PDF için Çıktı Dizini ve Dosya Biçimini Ayarlayın
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Adım 9: Görüntüleyici Nesnesini Başlatın ve PDF Seçeneklerini Ayarlayın
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Adım 10: Belgeyi PDF'ye Dönüştürün
```csharp
viewer.View(options);
```

## Çözüm
Tebrikler! GroupDocs.Viewer for .NET kullanarak MS Project belgelerini nasıl işleyeceğiniz ve zaman birimlerini nasıl ayarlayacağınız konusunda başarılı bir şekilde bilgi edindiniz. Belge görüntüleme yeteneklerini geliştirmek için bu bilgiyi projelerinize dahil edin.
## SSS
### MS Project belgelerini HTML, resim ve PDF dışındaki formatlara dönüştürebilir miyim?
Evet, GroupDocs.Viewer for .NET DOCX, XLSX, PPTX gibi çeşitli formatlara dönüştürmeyi destekler.
### GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten alabilirsiniz: [Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için geçici lisanslamayı nasıl alabilirim?
Ziyaret etmek [bu bağlantı](https://purchase.groupdocs.com/temporary-license/) geçici lisans almak.
### GroupDocs.Viewer for .NET için dokümanları nerede bulabilirim?
Belgelere bakın [Burada](https://tutorials.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET ile ilgili destek almak veya soru sormak için nereye başvurabilirim?
Destek forumunu ziyaret edebilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9).