---
title: CHM Dosyalarını İşleme
linktitle: CHM Dosyalarını İşleme
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer'ı kullanarak CHM dosyalarını .NET'te nasıl oluşturacağınızı öğrenin. CHM'yi zahmetsizce HTML, JPG, PNG ve PDF formatlarına dönüştürün.
type: docs
weight: 10
url: /tr/net/rendering-web-documents/render-chm/
---
## giriiş
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak CHM (Derlenmiş HTML Yardımı) dosyalarının nasıl oluşturulacağını keşfedeceğiz. GroupDocs.Viewer for .NET, geliştiricilerin herhangi bir harici yazılım kurulumu gerektirmeden .NET uygulamalarında 170'in üzerinde belge türünü görüntülemesine olanak tanıyan güçlü bir belge işleme API'sidir.

## Önkoşullar

CHM dosyalarını oluşturmaya başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

### .NET için GroupDocs.Viewer'ı yükleme

 Başlamak için GroupDocs.Viewer for .NET'i yüklemeniz gerekir. Kütüphaneyi adresinden indirebilirsiniz.[GroupDocs web sitesi](https://releases.groupdocs.com/viewer/net/) veya Paket Yöneticisi Konsolunda aşağıdaki komutu çalıştırarak NuGet Paket Yöneticisi aracılığıyla yükleyin:

```bash
Install-Package GroupDocs.Viewer
```

## Ad Alanlarını İçe Aktarma

Gerekli ad alanlarını projenize aktardığınızdan emin olun:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi işleme sürecini birden fazla adıma ayıralım:

## Adım 1: Çıkış Dizinini Tanımlayın

İşlenen dosyaların kaydedilmesini istediğiniz dizini tanımlayın:

```csharp
string outputDirectory = "Your Document Directory";
```

## 2. Adım: HTML'ye dönüştürün

CHM dosyalarını HTML'ye dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Tüm CHM içeriğini tek bir sayfaya dönüştürmek için true olarak ayarlayın

    viewer.View(options); //Tüm sayfaları dönüştür
}
```

## 3. Adım: JPG'ye dönüştürün

CHM dosyalarını JPG görsellerine dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Yalnızca 1, 2, 3. sayfaları dönüştür
}
```

## Adım 4: PNG'ye dönüştürün

CHM dosyalarını PNG görüntülerine dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Yalnızca 1, 2, 3. sayfaları dönüştür
}
```

## Adım 5: PDF'ye Dönüştür

CHM dosyalarını PDF belgesine dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Tüm sayfaları dönüştür
}
```

## Adım 6: Çıktıyı Kontrol Edin

Oluşturma işlemi tamamlandıktan sonra, oluşturulan dosyalar için belirtilen çıktı dizinini kontrol edin:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

CHM dosyalarını GroupDocs.Viewer for .NET kullanarak oluşturmak basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, CHM belgelerini .NET uygulamalarınızda HTML, resimler (JPG, PNG) ve PDF gibi çeşitli formatlara verimli bir şekilde dönüştürebilirsiniz.

## SSS'ler

### S1: GroupDocs.Viewer, CHM dışındaki diğer belge formatlarını görüntüleyebilir mi?

Cevap1: Evet, GroupDocs.Viewer, PDF, DOCX, XLSX, PPTX ve daha fazlasını içeren 170'in üzerinde belge formatının görüntülenmesini destekler.

### S2: GroupDocs.Viewer .NET Core ile uyumlu mu?

C2: Evet, GroupDocs.Viewer geleneksel .NET Framework'e ek olarak .NET Core'u da destekler.

### S3: Farklı çıktı formatları için işleme seçeneklerini özelleştirebilir miyim?

C3: Evet, GroupDocs.Viewer sayfa numaralarını belirlemek, görüntü kalitesini ayarlamak ve çıktı yollarını yapılandırmak gibi işleme sürecini özelleştirmek için çeşitli seçenekler sunar.

### S4: GroupDocs.Viewer, belgelerin işlenmesi için herhangi bir dış bağımlılığa ihtiyaç duyuyor mu?

C4: Hayır, GroupDocs.Viewer bağımsız bir kitaplıktır ve herhangi bir harici bağımlılık veya üçüncü taraf yazılım kurulumu gerektirmez.

### S5: GroupDocs.Viewer'ın ücretsiz deneme sürümü mevcut mu?

 C5: Evet, GroupDocs.Viewer'ın ücretsiz denemesinden şu adresi ziyaret ederek yararlanabilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).