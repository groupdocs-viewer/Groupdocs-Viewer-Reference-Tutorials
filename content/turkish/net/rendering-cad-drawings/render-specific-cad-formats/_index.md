---
"description": "Groupdocs.Viewer for .NET kullanarak CF2 gibi belirli CAD formatlarını HTML, JPG, PNG ve PDF'ye nasıl dönüştüreceğinizi öğrenin."
"linktitle": "Belirli CAD Formatlarını (CF2) Oluşturun"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Belirli CAD Formatlarını (CF2) Oluşturun"
"url": "/tr/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
type: docs
---
# Belirli CAD Formatlarını (CF2) Oluşturun

## giriiş
Bu eğitimde, Groupdocs.Viewer for .NET kullanarak belirli CAD formatlarının nasıl işleneceğini inceleyeceğiz. Groupdocs.Viewer, geliştiricilerin herhangi bir harici yazılım kurulumu gerektirmeden uygulamalarında 170'ten fazla belge türünü görüntülemelerine olanak tanıyan güçlü bir belge görüntüleyici API'sidir. Özellikle, CF2 gibi CAD formatlarını HTML, JPG, PNG ve PDF gibi çeşitli çıktı formatlarına işlemeye odaklanacağız.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Sisteminizde Visual Studio yüklü.
- Groupdocs.Viewer for .NET SDK. Bunu şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/viewer/net/).
- C# programlama dilinin temel bilgisi.
## Ad Alanlarını İçe Aktar
Öncelikle CAD formatlarını render etmek için gerekli olan namespaceleri import edelim.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Şimdi her örneği birden fazla adıma bölelim:
## CF2'yi HTML'ye dönüştür
### Adım 1: Oluşturulan HTML'nin kaydedileceği çıktı dizinini tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
### Adım 2: HTML çıktısı için dosya yolu biçimini tanımlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Adım 3: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Gerekirse ek işleme seçenekleri ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2'yi JPG'ye dönüştür
### Adım 1: JPG çıktısı için dosya yolu biçimini tanımlayın.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Adım 2: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Gerekirse ek işleme seçenekleri ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2'yi PNG'ye dönüştür

### Adım 1: PNG çıktısı için dosya yolu biçimini tanımlayın.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Adım 2: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Gerekirse ek işleme seçenekleri ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2'yi PDF'ye dönüştür
### Adım 1: PDF çıktısı için dosya yolu biçimini tanımlayın.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Adım 2: Viewer nesnesini başlatın ve giriş CF2 dosyasını belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Gerekirse ek işleme seçenekleri ayarlayın
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Çözüm
Bu eğitimde, Groupdocs.Viewer for .NET kullanarak CF2 gibi belirli CAD formatlarını nasıl işleyeceğimizi öğrendik. Adım adım kılavuzu izleyerek, belge işleme yeteneklerini .NET uygulamalarınıza kolayca entegre edebilirsiniz.
## SSS
### Groupdocs.Viewer CF2 haricindeki diğer CAD formatlarını da işleyebilir mi?
Evet, Groupdocs.Viewer DWG, DXF, DGN ve daha fazlası dahil olmak üzere çok çeşitli CAD formatlarını destekler.
### Groupdocs.Viewer web uygulamalarında dokümanların görüntülenmesi için uygun mudur?
Kesinlikle, Groupdocs.Viewer belgeleri doğrudan tarayıcıda görüntülemek için web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### Groupdocs.Viewer'ın render alabilmesi için herhangi bir harici bağımlılığa ihtiyacı var mı?
Hayır, Groupdocs.Viewer bağımsız bir API'dir ve herhangi bir harici bağımlılık veya yazılım kurulumu gerektirmez.
### Gereksinimlerime göre render seçeneklerini özelleştirebilir miyim?
Evet, Groupdocs.Viewer özel ihtiyaçlarınızı karşılamak üzere özelleştirilebilen çeşitli oluşturma seçenekleri sunar.
### Groupdocs.Viewer için deneme sürümü mevcut mu?
Evet, Groupdocs.Viewer'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz: [Burada](https://releases.groupdocs.com/).