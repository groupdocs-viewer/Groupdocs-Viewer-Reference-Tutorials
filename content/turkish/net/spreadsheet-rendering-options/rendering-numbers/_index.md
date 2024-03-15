---
title: Sayıları Oluşturma
linktitle: Sayıları Oluşturma
second_title: GroupDocs.Viewer .NET API'si
description: Numbers dosyalarını sorunsuz bir şekilde işlemek için Groupdocs.Viewer for .NET'in gücünü keşfedin. Zahmetsizce HTML, JPG, PNG ve PDF'ye dönüştürün.
type: docs
weight: 15
url: /tr/net/spreadsheet-rendering-options/rendering-numbers/
---
## giriiş
.NET için Groupdocs.Viewer'ı kullanarak Numbers dosyalarını işlemeye ilişkin bu adım adım eğitime hoş geldiniz. İster deneyimli bir geliştirici ister yeni başlayan biri olun, bu kılavuz size Numbers belgelerini çeşitli biçimlere dönüştürme sürecinde yol gösterecektir. Groupdocs.Viewer for .NET, belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre etmenize olanak tanıyan güçlü bir araçtır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- C# ve .NET geliştirme konusunda çalışma bilgisi.
-  .NET kitaplığı için Groupdocs.Viewer yüklendi. İndirebilirsin[Burada](https://releases.groupdocs.com/viewer/net/).
- Çıktı dosyalarının kaydedileceği belge dizini yolunuz.
## Ad Alanlarını İçe Aktar
C# projenizde Groupdocs.Viewer kitaplığını kullanmak için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. Adım: Çıkış Dizinini Ayarlayın
Oluşturmaya başlamadan önce, dönüştürülen dosyaların kaydedileceği çıktı dizinini tanımlayın. "Belge Dizininiz"i gerçek yolla değiştirin:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Çok Sayfalı HTML'ye Dönüştür
Numbers dosyasını çok sayfalı HTML'ye dönüştürmek için aşağıdaki kodu kullanın:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 3. Adım: JPG'ye dönüştürün
Numbers dosyasını aşağıdaki kodla JPG formatına dönüştürün:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 4: PNG'ye dönüştürün
Aşağıdaki kodu kullanarak Numbers dosyasını PNG formatına dönüştürün:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 5: PDF'ye Dönüştür
Son olarak, aşağıdaki kodu kullanarak Numbers dosyasını PDF formatına dönüştürün:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Tebrikler! Groupdocs.Viewer for .NET'i kullanarak Numbers dosyalarını başarıyla çeşitli formatlara dönüştürdünüz.
## Çözüm
Bu eğitimde, Numbers dosyalarını Groupdocs.Viewer for .NET kullanarak oluşturmanın temellerini ele aldık. Bu güçlü kitaplık, .NET uygulamalarınızdaki belgeleri görüntülemek ve dönüştürmek için kusursuz entegrasyon sağlar.
## SSS
### Groupdocs.Viewer for .NET'i diğer belge türleriyle kullanabilir miyim?
Evet, Groupdocs.Viewer, aralarında Word, Excel, PDF ve daha fazlasının da bulunduğu çok çeşitli belge formatlarını destekler.
### Test amaçlı geçici bir lisans mevcut mu?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.groupdocs.com/temporary-license/) test için.
### .NET için Groupdocs.Viewer desteğini nerede bulabilirim?
 Ziyaret edin[Groupdocs.Viewer Forumu](https://forum.groupdocs.com/c/viewer/9) Yardım ve tartışmalar için.
### Groupdocs.Viewer for .NET'in tam sürümünü nasıl satın alabilirim?
 Tam sürümünü satın alabilirsiniz[Burada](https://purchase.groupdocs.com/buy).
### Ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.groupdocs.com/).