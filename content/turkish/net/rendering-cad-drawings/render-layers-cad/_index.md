---
"description": "GroupDocs.Viewer for .NET ile .NET uygulamalarında CAD çizimlerini sorunsuz bir şekilde işleyin. İşleme seçeneklerini keşfedin, katmanları özelleştirin ve daha fazlasını yapın."
"linktitle": "CAD Çizimlerinde Katmanları Oluşturma"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD Çizimlerinde Katmanları Oluşturma"
"url": "/tr/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
---

# CAD Çizimlerinde Katmanları Oluşturma

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin belge oluşturma yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir araçtır. CAD çizimleri, PDF'ler, Microsoft Office belgeleri veya daha fazlasını oluşturmanız gerekip gerekmediğine bakılmaksızın, GroupDocs.Viewer kapsamlı bir çözüm sunar.
## Ön koşullar
GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- C# programlama dilinin temel düzeyde anlaşılması.
- Makinenizde .NET geliştirme ortamını kurun.
- GroupDocs.Viewer for .NET yüklü. Buradan indirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).
- .NET için GroupDocs.Viewer belgelerine erişim için eğitimlere buradan ulaşabilirsiniz. [Burada](https://tutorials.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET'i kullanmaya başlamak için projenize gerekli ad alanlarını içe aktarmanız gerekir. Şu adımları izleyin:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Verilen örneği birden fazla adıma bölelim:
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: Görüntüleyici Nesnesini Başlatın
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Kod bloğu devam ediyor...
}
```
## Adım 4: HTML Görünüm Seçeneklerini Ayarlayın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Adım 5: CAD Katmanlarını Tanımlayın
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Adım 6: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
## Adım 7: Çıktı Oluşturulan Belge Konumu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET ile .NET uygulamalarınızda CAD çizimlerini işlemek sorunsuz bir süreç haline gelir. Bu kılavuzda özetlenen adımları izleyerek, belge işleme yeteneklerini projelerinize kolayca entegre edebilirsiniz.
## SSS
### GroupDocs.Viewer her türlü CAD çizimiyle uyumlu mudur?
Evet, GroupDocs.Viewer, DWG ve DXF dahil olmak üzere çok çeşitli CAD çizim formatlarının işlenmesini destekler.
### CAD çizimleri için render seçeneklerini özelleştirebilir miyim?
Kesinlikle, GroupDocs.Viewer, işlenecek katmanları belirtme veya çıktı formatlarını ayarlama gibi çeşitli özelleştirme seçenekleri sunar.
### GroupDocs.Viewer'ın belgeleri görüntüleyebilmesi için internet bağlantısına ihtiyacı var mı?
Hayır, GroupDocs.Viewer internet bağlantısına ihtiyaç duymadan yerel olarak işleme gerçekleştirir.
### GroupDocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümüne erişebilirsiniz [Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için desteği nereden alabilirim?
Herhangi bir teknik yardım veya sorunuz için GroupDocs.Viewer forumunu ziyaret edebilirsiniz. [Burada](https://forum.groupdocs.com/c/viewer/9).