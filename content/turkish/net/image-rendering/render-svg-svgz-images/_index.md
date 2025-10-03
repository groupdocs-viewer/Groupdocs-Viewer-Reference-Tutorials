---
"description": "GroupDocs.Viewer for .NET kullanarak SVG ve SVGZ resimlerinin nasıl işleneceğini öğrenin. Vektör grafiklerini zahmetsizce HTML, JPG, PNG ve PDF'ye dönüştürün."
"linktitle": "SVG ve SVGZ Görüntülerini Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "SVG ve SVGZ Görüntülerini Oluştur"
"url": "/tr/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# SVG ve SVGZ Görüntülerini Oluştur

## giriiş
Bu eğitimde, GroupDocs.Viewer for .NET kullanarak SVG ve SVGZ resimlerini işleme sürecinde size rehberlik edeceğiz. GroupDocs.Viewer for .NET, geliştiricilerin .NET uygulamalarında çeşitli belge biçimlerini işlemelerine olanak tanıyan güçlü bir belge işleme API'sidir. SVG ve SVGZ, vektör grafikleri için kullanılan popüler resim biçimleridir ve GroupDocs.Viewer for .NET ile bunları HTML, JPG, PNG ve PDF gibi farklı çıktı biçimlerine kolayca işleyebilirsiniz.

![GroupDocs.Viewer for .NET ile SVG ve SVGZ Görüntülerini Oluşturun](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Ön koşullar
Başlamadan önce aşağıdaki ön koşulların kurulu ve ayarlanmış olduğundan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirin ve yükleyin: [Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: Visual Studio gibi .NET geliştirme için çalışan bir geliştirme ortamınız olduğundan emin olun.
3. Örnek SVGZ Dosyası: Test için hazır bir örnek SVGZ dosyanız olsun.

## Ad Alanlarını İçe Aktar
Koda dalmadan önce gerekli ad alanlarını içe aktaralım:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Adım 1: SVGZ'yi HTML'ye dönüştürün
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Adım 2: SVGZ'yi JPG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Adım 3: SVGZ'yi PNG'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Adım 4: SVGZ'yi PDF'ye dönüştürün
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Çözüm
Bu eğitimde, GroupDocs.Viewer for .NET kullanarak SVG ve SVGZ resimlerinin nasıl işleneceğini öğrendik. Sadece birkaç basit adımla, SVGZ resimlerini HTML, JPG, PNG ve PDF gibi çeşitli çıktı biçimlerine dönüştürebilir, bunları farklı ortamlarda erişilebilir ve görüntülenebilir hale getirebilirsiniz.
## SSS
### GroupDocs.Viewer diğer resim formatlarını da işleyebilir mi?
Evet, GroupDocs.Viewer PNG, JPEG, BMP, TIFF, GIF ve daha fazlası dahil olmak üzere çeşitli görüntü formatlarını işlemeyi destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mudur?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ile uyumludur.
### İşleme seçeneklerini özelleştirebilir miyim?
Evet, GroupDocs.Viewer ihtiyaçlarınıza göre çıktıyı özelleştirmenize olanak tanıyan kapsamlı işleme seçenekleri sunar.
### GroupDocs.Viewer herhangi bir üçüncü taraf bağımlılığı gerektiriyor mu?
Hayır, GroupDocs.Viewer bağımsız bir API'dir ve belgeleri oluşturmak için herhangi bir üçüncü taraf bağımlılığı gerektirmez.
### Test için deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/) Satın almadan önce özelliklerini değerlendirmek.