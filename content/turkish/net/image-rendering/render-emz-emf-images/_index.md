---
"description": "GroupDocs.Viewer for .NET kullanarak EMZ ve EMF görüntülerinin çeşitli formatlara nasıl dönüştürüleceğini öğrenin. Geliştiriciler için kolay takip edilebilir eğitim."
"linktitle": "EMZ ve EMF Görüntülerini Oluşturun"
"second_title": "GroupDocs.Viewer .NET API"
"title": "EMZ ve EMF Görüntülerini Oluşturun"
"url": "/tr/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# EMZ ve EMF Görüntülerini Oluşturun

## giriiş

GroupDocs.Viewer for .NET, geliştiricilerin EMZ (Gelişmiş Windows Meta Dosyası) ve EMF (Gelişmiş Meta Dosyası) görüntüleri de dahil olmak üzere çeşitli belge türlerini .NET uygulamalarında görüntülemelerine olanak tanıyan güçlü bir belge oluşturma API'sidir. Bu eğitimde, GroupDocs.Viewer for .NET kullanarak EMZ ve EMF görüntülerinin HTML, JPG, PNG ve PDF gibi farklı biçimlere nasıl dönüştürüleceğini inceleyeceğiz.

![.NET için GroupDocs.Viewer ile EMZ ve EMF Görüntülerini Oluşturun](/viewer/image-rendering/render-emz-and-emf-images.png)

## Ön koşullar

Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. GroupDocs.Viewer for .NET: Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için uyumlu bir geliştirme ortamı kurduğunuzdan emin olun.
3. Örnek EMZ/EMF Görüntüleri: İşleme için örnek EMZ ve EMF görüntüleri bulundurun.

## Ad Alanlarını İçe Aktar

Koda dalmadan önce gerekli ad alanlarını içe aktaralım:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Şimdi her örneği adım adım bir rehber formatında birden fazla adıma bölelim:

## EMZ/EMF Görüntülerinin HTML'ye Dönüştürülmesi

### Adım 1: Çıktı Dizinini Ayarlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
Yer değiştirmek `"Your Document Directory"` işlenmiş HTML dosyasını kaydetmek istediğiniz yolu belirtin.

### Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Bu, oluşturulan HTML dosyası için dosya yolu biçimini belirleyecektir.

### Adım 3: HTML'e dönüştürün:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Bu kod şunu başlatır: `Viewer` Örnek EMZ görüntüsüne sahip nesneyi, belirtilen seçenekleri kullanarak HTML formatına dönüştürür.

## EMZ/EMF Görüntülerini JPG, PNG ve PDF'ye Dönüştürme

JPG, PNG ve PDF formatlarına dönüştürmek için aşağıdaki adımları tekrarlayın:

### Adım 1: Sayfa Dosyası Yolu Biçimini Tanımlayın:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
İstenilen çıktı biçimine göre dosya adını ve uzantısını ayarlayın (`jpg`, `png`, veya `pdf`).

### Adım 2: İlgili Biçime Dönüştürün:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Seçenekleri çıktı formatına (Jpg, Png, Pdf) göre ayarlayın
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Yer değiştirmek `JpgViewOptions` ile `PngViewOptions` veya `PdfViewOptions` İstenilen çıktı formatına göre.

## Çözüm

Sonuç olarak, GroupDocs.Viewer for .NET, EMZ ve EMF görüntülerini .NET uygulamalarında çeşitli biçimlerde işlemek için kusursuz bir çözüm sunar. Geliştiriciler, bu eğitimde özetlenen adımları izleyerek belge işleme yeteneklerini uygulamalarına zahmetsizce entegre edebilirler.

## SSS

### S: GroupDocs.Viewer, EMZ ve EMF görüntüleri dışında başka belge formatlarını da işleyebilir mi?
C: Evet, GroupDocs.Viewer PDF, DOCX, PPTX, XLSX ve daha fazlası dahil olmak üzere çok çeşitli belge formatlarını destekler.

### S: GroupDocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?
A: Evet, ücretsiz denemeye erişebilirsiniz [Burada](https://releases.groupdocs.com/).

### S: GroupDocs.Viewer geliştiricilere destek sunuyor mu?
A: Evet, GroupDocs kendi aracılığıyla destek sağlıyor [forum](https://forum.groupdocs.com/c/viewer/9) Geliştiricilerin soru sorabilecekleri ve yardım alabilecekleri bir yer.

### S: GroupDocs.Viewer for .NET için geçici bir lisans satın alabilir miyim?
A: Evet, geçici lisanslar satın alınabilir [Burada](https://purchase.groupdocs.com/temporary-license/).

### S: GroupDocs.Viewer for .NET için ayrıntılı belgeleri nerede bulabilirim?
A: Belgelere başvurabilirsiniz [Burada](https://tutorials.groupdocs.com/viewer/net/) API'yi kullanma konusunda kapsamlı rehberlik için.