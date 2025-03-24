---
title: Notları Oluşturma ve Zaman Birimlerini Ayarlama (MS Project)
linktitle: Notları Oluşturma ve Zaman Birimlerini Ayarlama (MS Project)
second_title: GroupDocs.Viewer .NET API'si
description: .NET için GroupDocs.Viewer ile MS Project belgelerinin ana işlenmesi. Notları işleyin, zaman birimlerini ayarlayın ve çeşitli çıktı formatlarını zahmetsizce keşfedin.
weight: 11
url: /tr/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin .NET uygulamaları içindeki çeşitli belge formatlarını görüntülemesine ve değiştirmesine olanak tanıyan güçlü bir belge işleme API'sidir. Bu eğitimde, özellikle MS Project belgeleri için notların oluşturulmasına ve zaman birimlerinin ayarlanmasına odaklanacağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET kitaplığını indirip yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: Tercih ettiğiniz geliştirme ortamını .NET desteğiyle kurun.
3. MS Proje Belgesi: Test için örnek bir MS Project belgesini hazır bulundurun.
## Ad Alanlarını İçe Aktar
Öncelikle MS Project belgelerini oluşturmaya başlamak için gerekli ad alanlarını içe aktaralım:
## 1. Adım: Ad Alanlarını İçe Aktarın
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Artık gerekli ad alanlarını içe aktardığımıza göre, kapsamlı bir anlayış için her örneği birden çok adıma ayıralım.
## MS Project Belgesini HTML'ye Dönüştürme
Bir MS Project belgesini notlarla birlikte HTML biçimine dönüştürmek için şu adımları izleyin:
### Adım 2: Çıktı Dizinini ve Dosya Formatını Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 3. Adım: Görüntüleyici Nesnesini Başlatın ve Seçenekleri Ayarlayın
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
Ayrıca MS Project belgelerini JPG ve PNG gibi görüntü formatlarına dönüştürebilirsiniz. İşte nasıl:
### Adım 5: JPG için Çıktı Dizinini ve Dosya Formatını Ayarlayın
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
### Adım 7: Belgeyi JPG'ye Oluşturun
```csharp
viewer.View(options);
```
PNG'ye ve diğer görüntü formatlarına dönüştürmek için benzer adımları tekrarlayın.
## MS Proje Belgesini PDF'ye Dönüştürme
Bir MS Project belgesini PDF formatına dönüştürmek için aşağıdakileri yapın:
### Adım 8: PDF için Çıktı Dizinini ve Dosya Formatını Ayarlayın
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 9. Adım: Görüntüleyici Nesnesini Başlatın ve PDF Seçeneklerini Ayarlayın
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
Tebrikler! GroupDocs.Viewer for .NET'i kullanarak MS Project belgelerini nasıl oluşturacağınızı ve zaman birimlerini nasıl ayarlayacağınızı başarıyla öğrendiniz. Belge görüntüleme yeteneklerini geliştirmek için bu bilgiyi projelerinize ekleyin.
## SSS'ler
### MS Project belgelerini HTML, görseller ve PDF dışında başka formatlara da dönüştürebilir miyim?
Evet, GroupDocs.Viewer for .NET, DOCX, XLSX, PPTX ve daha fazlası gibi çeşitli formatlarda görüntü oluşturmayı destekler.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
 Evet, şu adresten ücretsiz deneme alabilirsiniz:[Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için nasıl geçici lisans alabilirim?
 Ziyaret etmek[bu bağlantı](https://purchase.groupdocs.com/temporary-license/) geçici lisans almak için.
### GroupDocs.Viewer for .NET belgelerini nerede bulabilirim?
 Belgelere bakın[Burada](https://tutorials.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET ile ilgili desteği nereden alabilirim veya soru sorabilirim?
 Destek forumunu ziyaret edebilirsiniz[Burada](https://forum.groupdocs.com/c/viewer/9).