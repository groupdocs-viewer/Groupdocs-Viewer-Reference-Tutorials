---
title: SVG ve SVGZ Görüntülerini İşleme
linktitle: SVG ve SVGZ Görüntülerini İşleme
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak SVG ve SVGZ görüntülerini nasıl oluşturacağınızı öğrenin. Vektör grafiklerini zahmetsizce HTML, JPG, PNG ve PDF'ye dönüştürün.
type: docs
weight: 16
url: /tr/net/image-rendering/render-svg-svgz-images/
---
## giriiş
Bu eğitimde, GroupDocs.Viewer for .NET'i kullanarak SVG ve SVGZ görüntülerini oluşturma sürecinde size rehberlik edeceğiz. GroupDocs.Viewer for .NET, geliştiricilerin .NET uygulamalarında çeşitli belge formatlarını oluşturmasına olanak tanıyan güçlü bir belge işleme API'sidir. SVG ve SVGZ, vektör grafikleri için kullanılan popüler görüntü formatlarıdır ve GroupDocs.Viewer for .NET ile bunları kolayca HTML, JPG, PNG ve PDF gibi farklı çıktı formatlarına dönüştürebilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların yüklendiğinden ve ayarlandığından emin olun:
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için Visual Studio gibi çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun.
3. Örnek SVGZ Dosyası: Test için örnek bir SVGZ dosyasını hazır bulundurun.

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
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak SVG ve SVGZ görüntülerinin nasıl oluşturulacağını öğrendik. Yalnızca birkaç basit adımla SVGZ görüntülerini HTML, JPG, PNG ve PDF gibi çeşitli çıktı formatlarına dönüştürebilir, böylece onları farklı ortamlarda erişilebilir ve görüntülenebilir hale getirebilirsiniz.
## SSS'ler
### GroupDocs.Viewer diğer resim formatlarını işleyebilir mi?
Evet, GroupDocs.Viewer PNG, JPEG, BMP, TIFF, GIF ve daha fazlası dahil olmak üzere çeşitli görüntü formatlarının oluşturulmasını destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ile uyumludur.
### Oluşturma seçeneklerini özelleştirebilir miyim?
Evet, GroupDocs.Viewer, çıktıyı gereksinimlerinize göre özelleştirmenize olanak tanıyan kapsamlı işleme seçenekleri sunar.
### GroupDocs.Viewer herhangi bir üçüncü taraf bağımlılığı gerektiriyor mu?
Hayır, GroupDocs.Viewer bağımsız bir API'dir ve belgelerin işlenmesi için herhangi bir üçüncü taraf bağımlılığı gerektirmez.
### Test için mevcut bir deneme sürümü var mı?
Evet, GroupDocs.Viewer'ın ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.groupdocs.com/) Bir satın alma işlemi yapmadan önce özelliklerini değerlendirmek için.