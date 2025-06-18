---
"description": "GroupDocs.Viewer'ı kullanarak .NET belgelerindeki eksik fontları zahmetsizce nasıl değiştireceğinizi öğrenin. Basit adımlarla doğru işlemeyi sağlayın."
"linktitle": "Eksik Yazı Tipini Değiştir"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Eksik Yazı Tipini Değiştir"
"url": "/tr/net/rendering-options/replace-missing-font/"
"weight": 20
---

# Eksik Yazı Tipini Değiştir

## giriiş
.NET geliştirme dünyasında, verimli belge işleme hayati önem taşır. .NET için GroupDocs.Viewer, .NET uygulamalarınızda çeşitli belge biçimlerini görüntülemek için güçlü bir çözüm sunar. Bu eğitimde, belgelerdeki eksik yazı tiplerini değiştirmek için .NET için GroupDocs.Viewer'ı nasıl kullanacağınızı inceleyeceğiz. İster PDF'lerle, ister PowerPoint sunumlarıyla veya Word belgeleriyle uğraşıyor olun, GroupDocs.Viewer süreci basitleştirir ve yazı tipleri eksik olsa bile belgelerinizin doğru şekilde işlenmesini sağlar.
## Ön koşullar
Bu eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. .NET için GroupDocs.Viewer: GroupDocs.Viewer kütüphanesini web sitesinden indirin ve kurun](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurun.
3. Temel C# Bilgisi: C# programlama dili ve .NET framework'üne aşinalık.

## Ad Alanlarını İçe Aktar
C# kodunuzda GroupDocs.Viewer işlevlerine erişmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi, .NET için GroupDocs.Viewer'ı kullanarak belgelerdeki eksik yazı tiplerini değiştirme sürecini inceleyelim.
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen belge sayfalarının kaydedileceği dizini ayarlayın.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Çıktı HTML dosyalarını adlandırma biçimini belirtin. Bu örnekte, her sayfa "page_{page_number}.html" adlandırma kuralıyla bir HTML dosyası olarak kaydedilecektir.
## Adım 3: Görüntüleyici Nesnesini Başlatın
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Viewer sınıfının yeni bir örneğini başlatın ve belge dosyasının yolunu (bu durumda, eksik yazı tiplerine sahip bir PowerPoint sunumu) parametre olarak geçirin.
## Adım 4: HTML Görünüm Seçeneklerini Ayarlayın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
HtmlViewOptions örneğini oluşturun ve HTML çıktısına kaynakları gömecek şekilde yapılandırın. Eksik yazı tiplerinin yerine kullanılacak varsayılan bir yazı tipi adı belirtin.
## Adım 5: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
Viewer nesnesinin View metodunu çağırın ve HTML görünüm seçeneklerini iletin. Bu, belirtilen seçenekleri kullanarak belge sayfalarını işler.
## Adım 6: Çıkış Yolunu Görüntüle
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Belgenin başarıyla oluşturulduğunu belirten bir mesaj yazdırın ve çıktı HTML dosyalarının kaydedildiği yolu belirtin.

## Çözüm
Bu eğitimde, belgelerdeki eksik yazı tiplerini değiştirmek için GroupDocs.Viewer for .NET'i nasıl kullanacağımızı öğrendik. Bu adımları izleyerek, belirli yazı tipleri kullanılamadığında bile belgelerinizin doğru bir şekilde işlendiğinden emin olabilirsiniz. GroupDocs.Viewer, yazı tipi uyumluluk sorunları hakkında endişelenmeden sağlam .NET uygulamaları oluşturmaya odaklanmanızı sağlayarak süreci basitleştirir.
## SSS
### GroupDocs.Viewer diğer yazı tipiyle ilgili sorunları da çözebilir mi?
Evet, GroupDocs.Viewer, font değiştirme ve font algılama gibi çeşitli fontla ilgili işlevler sağlar.
### GroupDocs.Viewer tüm .NET framework'leriyle uyumlu mudur?
GroupDocs.Viewer, .NET Core ve .NET Standard dahil olmak üzere çok çeşitli .NET çerçevelerini destekler.
### GroupDocs.Viewer'da varsayılan yazı tipi değişimini özelleştirebilir miyim?
Elbette, eksik fontların yerine varsayılan yedek olarak istediğiniz herhangi bir fontu belirleyebilirsiniz.
### GroupDocs.Viewer belgelerin toplu işlenmesini destekliyor mu?
Evet, GroupDocs.Viewer birden fazla belgeyi aynı anda işlemenize olanak tanır ve bu da onu toplu işlem senaryoları için ideal hale getirir.
### GroupDocs.Viewer için daha fazla yardım veya desteği nerede bulabilirim?
GroupDocs.Viewer forumunu ziyaret edebilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9) Herhangi bir yardım veya destek sorunuz için.