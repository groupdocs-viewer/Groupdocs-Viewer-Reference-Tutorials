---
"description": "GroupDocs.Viewer kullanarak CHM dosyalarını .NET'te nasıl oluşturacağınızı öğrenin. CHM'yi HTML, JPG, PNG ve PDF formatlarına zahmetsizce dönüştürün."
"linktitle": "CHM Dosyalarını Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CHM Dosyalarını Oluştur"
"url": "/tr/net/rendering-web-documents/render-chm/"
"weight": 10
---

# CHM Dosyalarını Oluştur

## giriiş
Bu eğitimde, .NET için GroupDocs.Viewer'ı kullanarak CHM (Derlenmiş HTML Yardımı) dosyalarının nasıl işleneceğini inceleyeceğiz. .NET için GroupDocs.Viewer, geliştiricilerin herhangi bir harici yazılım kurulumu gerektirmeden .NET uygulamalarında 170'ten fazla belge türünü görüntülemelerine olanak tanıyan güçlü bir belge işleme API'sidir.

## Ön koşullar

CHM dosyalarının işlenmesine başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

### .NET için GroupDocs.Viewer'ı yükleme

Başlamak için, .NET için GroupDocs.Viewer'ı yüklemeniz gerekir. Kütüphaneyi şuradan indirebilirsiniz: [GroupDocs web sitesi](https://releases.groupdocs.com/viewer/net/) veya NuGet Paket Yöneticisi Konsolunda aşağıdaki komutu çalıştırarak NuGet Paket Yöneticisi aracılığıyla yükleyin:

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

Şimdi render sürecini birden fazla adıma bölelim:

## Adım 1: Çıktı Dizinini Tanımlayın

İşlenen dosyaların kaydedilmesini istediğiniz dizini tanımlayın:

```csharp
string outputDirectory = "Your Document Directory";
```

## Adım 2: HTML'ye dönüştürün

CHM dosyalarını HTML'ye dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Tüm CHM içeriğini tek bir sayfaya dönüştürmek için doğru olarak ayarlayın

    viewer.View(options); // Tüm sayfaları dönüştür
}
```

## Adım 3: JPG'ye dönüştürün

CHM dosyalarını JPG resimlerine dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Yalnızca 1, 2, 3 sayfalarını dönüştür
}
```

## Adım 4: PNG'ye dönüştürün

CHM dosyalarını PNG görüntülerine dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Yalnızca 1, 2, 3 sayfalarını dönüştür
}
```

## Adım 5: PDF'ye dönüştürün

CHM dosyalarını PDF belgesine dönüştürmek için aşağıdaki kod parçacığını kullanın:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Tüm sayfaları dönüştür
}
```

## Adım 6: Çıktıyı Kontrol Edin

İşleme süreci tamamlandıktan sonra, işlenen dosyalar için belirtilen çıktı dizinini kontrol edin:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

GroupDocs.Viewer for .NET kullanarak CHM dosyalarını işlemek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, CHM belgelerini .NET uygulamalarınızda HTML, resim (JPG, PNG) ve PDF gibi çeşitli biçimlere verimli bir şekilde dönüştürebilirsiniz.

## SSS

### S1: GroupDocs.Viewer CHM dışındaki diğer belge formatlarını da işleyebilir mi?

C1: Evet, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX ve daha fazlası dahil olmak üzere 170'ten fazla belge formatının işlenmesini destekler.

### S2: GroupDocs.Viewer .NET Core ile uyumlu mudur?

C2: Evet, GroupDocs.Viewer geleneksel .NET Framework'ün yanı sıra .NET Core'u da destekler.

### S3: Farklı çıktı biçimleri için işleme seçeneklerini özelleştirebilir miyim?

C3: Evet, GroupDocs.Viewer, sayfa numaralarını belirtme, görüntü kalitesini ayarlama ve çıktı yollarını yapılandırma gibi, işleme sürecini özelleştirmek için çeşitli seçenekler sunar.

### S4: GroupDocs.Viewer'ın belgeleri işlemek için herhangi bir harici bağımlılığa ihtiyacı var mı?

C4: Hayır, GroupDocs.Viewer bağımsız bir kütüphanedir ve herhangi bir harici bağımlılık veya üçüncü taraf yazılım kurulumu gerektirmez.

### S5: GroupDocs.Viewer için ücretsiz deneme sürümü var mı?

C5: Evet, GroupDocs.Viewer'ın ücretsiz deneme sürümünden yararlanmak için şu adresi ziyaret edebilirsiniz: [web sitesi](https://releases.groupdocs.com/).