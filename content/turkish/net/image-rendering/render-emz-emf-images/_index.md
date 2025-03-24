---
title: EMZ ve EMF Görüntülerini Oluşturun
linktitle: EMZ ve EMF Görüntülerini Oluşturun
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak EMZ ve EMF görüntülerini çeşitli formatlarda nasıl oluşturacağınızı öğrenin. Geliştiriciler için takip edilmesi kolay eğitim.
weight: 14
url: /tr/net/image-rendering/render-emz-emf-images/
---
## giriiş

GroupDocs.Viewer for .NET, geliştiricilerin .NET uygulamalarında EMZ (Gelişmiş Windows Meta Dosyası) ve EMF (Gelişmiş Meta Dosyası) görüntüleri de dahil olmak üzere çeşitli belge türlerini görüntülemelerine olanak tanıyan güçlü bir belge işleme API'sidir. Bu eğitimde, GroupDocs.Viewer for .NET'i kullanarak EMZ ve EMF görüntülerinin HTML, JPG, PNG ve PDF gibi farklı formatlara nasıl dönüştürüleceğini keşfedeceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  GroupDocs.Viewer for .NET: Kitaplığı şu adresten indirebilirsiniz:[Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için uyumlu bir geliştirme ortamına sahip olduğunuzdan emin olun.
3. Örnek EMZ/EMF Görüntüleri: Oluşturma için örnek EMZ ve EMF görüntülerini hazır bulundurun.

## Ad Alanlarını İçe Aktar

Koda dalmadan önce gerekli ad alanlarını içe aktaralım:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Şimdi, adım adım kılavuz formatında her örneği birden fazla adıma ayıralım:

## EMZ/EMF Görüntülerini HTML'ye Dönüştürme

### Adım 1: Çıkış Dizinini Ayarlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"`oluşturulan HTML dosyasını kaydetmek istediğiniz yolu belirtin.

### Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Bu, oluşturulan HTML dosyası için dosya yolu formatını belirleyecektir.

### 3. Adım: HTML'ye dönüştürün:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Bu kod,`Viewer` örnek EMZ görüntüsüyle nesneyi oluşturur ve belirtilen seçenekleri kullanarak onu HTML formatına dönüştürür.

## EMZ/EMF Görüntülerini JPG, PNG ve PDF'ye Dönüştürme

JPG, PNG ve PDF formatlarında işlemek için aşağıdaki adımları tekrarlayın:

### Adım 1: Sayfa Dosya Yolu Formatını Tanımlayın:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Dosya adını ve uzantısını istediğiniz çıktı formatına göre ayarlayın (`jpg`, `png` , veya`pdf`).

### Adım 2: İlgili Formata Dönüştürün:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Seçenekleri çıktı formatına göre ayarlayın (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Yer değiştirmek`JpgViewOptions` ile`PngViewOptions` veya`PdfViewOptions` İstenilen çıktı formatına göre.

## Çözüm

Sonuç olarak, GroupDocs.Viewer for .NET, .NET uygulamalarında EMZ ve EMF görüntülerini çeşitli formatlara dönüştürmek için kusursuz bir çözüm sağlar. Geliştiriciler, bu eğitimde özetlenen adımları izleyerek, belge oluşturma yeteneklerini uygulamalarına zahmetsizce entegre edebilirler.

## SSS'ler

### S: GroupDocs.Viewer, EMZ ve EMF görüntüleri dışındaki diğer belge formatlarını görüntüleyebilir mi?
C: Evet, GroupDocs.Viewer PDF, DOCX, PPTX, XLSX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.

### S: GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.groupdocs.com/).

### S: GroupDocs.Viewer geliştiricilere destek sunuyor mu?
 C: Evet, GroupDocs, kendi aracılığıyla destek sağlar.[forum](https://forum.groupdocs.com/c/viewer/9) geliştiricilerin soru sorabileceği ve yardım isteyebileceği yer.

### S: GroupDocs.Viewer for .NET için geçici bir lisans satın alabilir miyim?
 C: Evet, geçici lisanslar satın alınabilir[Burada](https://purchase.groupdocs.com/temporary-license/).

### S: GroupDocs.Viewer for .NET'e ilişkin ayrıntılı belgeleri nerede bulabilirim?
 C: Belgelere başvurabilirsiniz[Burada](https://tutorials.groupdocs.com/viewer/net/)API'nin kullanımına ilişkin kapsamlı rehberlik için.