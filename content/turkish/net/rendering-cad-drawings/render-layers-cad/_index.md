---
title: CAD Çizimlerinde Katmanları İşleme
linktitle: CAD Çizimlerinde Katmanları İşleme
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET ile CAD çizimlerini .NET uygulamalarında sorunsuz bir şekilde işleyin. Oluşturma seçeneklerini keşfedin, katmanları özelleştirin ve daha fazlasını yapın.
weight: 13
url: /tr/net/rendering-cad-drawings/render-layers-cad/
---

# CAD Çizimlerinde Katmanları İşleme

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin belge işleme yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir araçtır. CAD çizimlerini, PDF'leri, Microsoft Office belgelerini veya daha fazlasını oluşturmanız gerekip gerekmediğini GroupDocs.Viewer kapsamlı bir çözüm sunar.
## Önkoşullar
GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- C# programlama dilinin temel anlayışı.
- Makinenizde .NET geliştirme ortamı kuruldu.
-  .NET için GroupDocs.Viewer yüklü. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
-  Referans olarak bulunabilecek GroupDocs.Viewer for .NET belgelerine erişim[Burada](https://tutorials.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET'i kullanmaya başlamak için projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu adımları takip et:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Sağlanan örneği birden çok adıma ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntüleyici Nesnesini Başlatın
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Kod bloğu devam ediyor...
}
```
## 4. Adım: HTML Görünüm Seçeneklerini Ayarlayın
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
## Adım 7: Çıktı Oluşturulan Belgenin Konumu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET ile CAD çizimlerinin .NET uygulamalarınızda işlenmesi kusursuz bir süreç haline gelir. Bu kılavuzda özetlenen adımları izleyerek belge oluşturma yeteneklerini projelerinize kolayca entegre edebilirsiniz.
## SSS'ler
### GroupDocs.Viewer her türlü CAD çizimiyle uyumlu mudur?
Evet, GroupDocs.Viewer, DWG ve DXF dahil çok çeşitli CAD çizim formatlarının görüntülenmesini destekler.
### CAD çizimleri için işleme seçeneklerini özelleştirebilir miyim?
Kesinlikle GroupDocs.Viewer, oluşturulacak katmanları belirlemek veya çıktı formatlarını ayarlamak gibi çeşitli özelleştirme seçenekleri sunar.
### GroupDocs.Viewer belgeleri oluşturmak için internet bağlantısı gerektirir mi?
Hayır, GroupDocs.Viewer, oluşturma işlemini internet bağlantısına ihtiyaç duymadan yerel olarak gerçekleştirir.
### GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.groupdocs.com/).
### .NET için GroupDocs.Viewer desteğini nereden alabilirim?
 Her türlü teknik yardım veya sorunuz için GroupDocs.Viewer forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).