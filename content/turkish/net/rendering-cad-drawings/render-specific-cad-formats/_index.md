---
title: Render'a Özel CAD Formatları (CF2)
linktitle: Render'a Özel CAD Formatları (CF2)
second_title: GroupDocs.Viewer .NET API'si
description: Groupdocs.Viewer for .NET'i kullanarak CF2 gibi belirli CAD formatlarını HTML, JPG, PNG ve PDF'ye nasıl dönüştüreceğinizi öğrenin.
weight: 12
url: /tr/net/rendering-cad-drawings/render-specific-cad-formats/
---
## giriiş
Bu eğitimde, Groupdocs.Viewer for .NET'i kullanarak belirli CAD formatlarının nasıl oluşturulacağını keşfedeceğiz. Groupdocs.Viewer, geliştiricilerin herhangi bir harici yazılım kurulumu gerektirmeden uygulamalarında 170'in üzerinde belge türünü görüntülemesine olanak tanıyan güçlü bir belge görüntüleme API'sidir. Özellikle, CF2 gibi CAD formatlarını HTML, JPG, PNG ve PDF gibi çeşitli çıktı formatlarına dönüştürmeye odaklanacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Sisteminizde Visual Studio yüklü.
-  .NET SDK için Groupdocs.Viewer. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
- Temel C# programlama dili bilgisi.
## Ad Alanlarını İçe Aktar
Öncelikle CAD formatlarını oluşturmak için gereken gerekli ad alanlarını içe aktaralım.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Şimdi her örneği birden fazla adıma ayıralım:
## CF2'yi HTML'ye dönüştür
### Adım 1: İşlenen HTML'nin kaydedileceği çıktı dizinini tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
### Adım 2: HTML çıktısı için dosya yolu formatını tanımlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Adım 3: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Gerekirse ek oluşturma seçeneklerini ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2'yi JPG'ye dönüştür
### Adım 1: JPG çıktısı için dosya yolu formatını tanımlayın.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Adım 2: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Gerekirse ek oluşturma seçeneklerini ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2'yi PNG'ye dönüştür

### Adım 1: PNG çıktısı için dosya yolu formatını tanımlayın.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Adım 2: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Gerekirse ek oluşturma seçeneklerini ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2'yi PDF'ye dönüştür
### Adım 1: PDF çıktısı için dosya yolu formatını tanımlayın.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Adım 2: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Gerekirse ek oluşturma seçeneklerini ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Çözüm
Bu eğitimde, Groupdocs.Viewer for .NET'i kullanarak CF2 gibi belirli CAD formatlarının nasıl oluşturulacağını öğrendik. Adım adım kılavuzu takip ederek belge oluşturma yeteneklerini .NET uygulamalarınıza kolayca entegre edebilirsiniz.
## SSS'ler
### Groupdocs.Viewer, CF2 dışındaki diğer CAD formatlarını görüntüleyebilir mi?
Evet, Groupdocs.Viewer, DWG, DXF, DGN ve daha fazlasını içeren çok çeşitli CAD formatlarını destekler.
### Groupdocs.Viewer, web uygulamalarında belge oluşturmaya uygun mudur?
Kesinlikle Groupdocs.Viewer, belgeleri doğrudan tarayıcıda görüntülemek için web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### Groupdocs.Viewer, oluşturma için herhangi bir dış bağımlılığa ihtiyaç duyuyor mu?
Hayır, Groupdocs.Viewer bağımsız bir API'dir ve herhangi bir harici bağımlılık veya yazılım kurulumu gerektirmez.
### Oluşturma seçeneklerini gereksinimlerime göre özelleştirebilir miyim?
Evet, Groupdocs.Viewer özel ihtiyaçlarınızı karşılayacak şekilde özelleştirilebilecek çeşitli işleme seçenekleri sunar.
### Groupdocs.Viewer'ın deneme sürümü mevcut mu?
 Evet, Groupdocs.Viewer'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.groupdocs.com/).