---
title: Eksik Yazı Tipini Değiştir
linktitle: Eksik Yazı Tipini Değiştir
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer'ı kullanarak .NET belgelerindeki eksik yazı tiplerini zahmetsizce nasıl değiştireceğinizi öğrenin. Basit adımlarla doğru işlemeyi sağlayın.
type: docs
weight: 20
url: /tr/net/rendering-options/replace-missing-font/
---
## giriiş
.NET geliştirme dünyasında, verimli belge yönetimi çok önemlidir. GroupDocs.Viewer for .NET, .NET uygulamalarınızdaki çeşitli belge formatlarını görüntülemek için güçlü bir çözüm sağlar. Bu öğreticide, belgelerdeki eksik yazı tiplerini değiştirmek için GroupDocs.Viewer for .NET'in nasıl kullanılacağını keşfedeceğiz. İster PDF'lerle, ister PowerPoint sunumlarıyla, ister Word belgeleriyle çalışıyor olun, GroupDocs.Viewer süreci basitleştirerek yazı tipleri eksik olsa bile belgelerinizin doğru şekilde oluşturulmasını sağlar.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. .NET için GroupDocs.Viewer: GroupDocs.Viewer kitaplığını web sitesinden indirip yükleyin](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurun.
3. Temel C# Bilgisi: C# programlama dili ve .NET çerçevesine aşinalık.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer işlevlerine erişmek için C# kodunuzda gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi GroupDocs.Viewer for .NET'i kullanarak belgelerdeki eksik yazı tiplerini değiştirme sürecini inceleyelim.
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen belge sayfalarının kaydedileceği dizini ayarlayın.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Çıktı HTML dosyalarını adlandırma biçimini belirtin. Bu örnekte, her sayfa "sayfa" adlandırma kuralıyla bir HTML dosyası olarak kaydedilecektir._{page_number}.html".
## 3. Adım: Görüntüleyici Nesnesini Başlatın
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Belge dosyasının yolunu (bu durumda, eksik yazı tiplerine sahip bir PowerPoint sunumu) parametre olarak ileterek Viewer sınıfının yeni bir örneğini başlatın.
## 4. Adım: HTML Görünüm Seçeneklerini Ayarlayın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Bir HtmlViewOptions örneği oluşturun ve bunu, kaynakları HTML çıkışına katıştıracak şekilde yapılandırın. Eksik yazı tiplerinin yerine kullanılacak varsayılan yazı tipi adını belirtin.
## Adım 5: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
HTML görünüm seçeneklerini ileterek Viewer nesnesinin View yöntemini çağırın. Bu, belirtilen seçenekleri kullanarak belge sayfalarını oluşturacaktır.
## Adım 6: Çıkış Yolunu Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Belgenin başarıyla oluşturulduğunu belirten bir mesaj yazdırın ve çıktı HTML dosyalarının kaydedildiği yolu belirtin.

## Çözüm
Bu öğreticide, belgelerdeki eksik yazı tiplerini değiştirmek için GroupDocs.Viewer for .NET'in nasıl kullanılacağını öğrendik. Bu adımları izleyerek, belirli yazı tipleri kullanılamadığında bile belgelerinizin doğru şekilde oluşturulduğundan emin olabilirsiniz. GroupDocs.Viewer süreci basitleştirerek yazı tipi uyumluluğu sorunları hakkında endişelenmeden sağlam .NET uygulamaları oluşturmaya odaklanmanıza olanak tanır.
## SSS'ler
### GroupDocs.Viewer yazı tipiyle ilgili diğer tür sorunları çözebilir mi?
Evet, GroupDocs.Viewer, yazı tipi değiştirme ve yazı tipi algılama dahil, yazı tipiyle ilgili çeşitli işlevler sağlar.
### GroupDocs.Viewer tüm .NET çerçeveleriyle uyumlu mu?
GroupDocs.Viewer, .NET Core ve .NET Standard dahil olmak üzere çok çeşitli .NET çerçevelerini destekler.
### GroupDocs.Viewer'da varsayılan yazı tipi değiştirmeyi özelleştirebilir miyim?
Kesinlikle, eksik yazı tiplerinin varsayılan değişimi olarak seçtiğiniz herhangi bir yazı tipini belirleyebilirsiniz.
### GroupDocs.Viewer belgelerin toplu işlenmesini destekliyor mu?
Evet, GroupDocs.Viewer aynı anda birden fazla belgeyi işlemenize olanak tanır, bu da onu toplu işleme senaryoları için ideal kılar.
### GroupDocs.Viewer için daha fazla yardım veya desteği nerede bulabilirim?
 GroupDocs.Viewer forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9) Herhangi bir yardım veya destek sorgusu için.