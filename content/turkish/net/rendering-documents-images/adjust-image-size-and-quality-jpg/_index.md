---
"description": "Groupdocs.Viewer for .NET kullanarak JPEG formatındaki görüntü boyutunu ve kalitesini nasıl optimize edeceğinizi öğrenin. Belge görüntüleme deneyiminizi geliştirin."
"linktitle": "Resim Boyutunu ve Kalitesini Ayarla (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Resim Boyutunu ve Kalitesini Ayarla (JPG)"
"url": "/tr/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Resim Boyutunu ve Kalitesini Ayarla (JPG)

## giriiş
Groupdocs.Viewer for .NET, geliştiricilerin belge görüntüleme işlevselliğini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir kütüphanedir. Belge görüntüleme uygulamalarındaki yaygın gereksinimlerden biri, özellikle JPEG (JPG) görüntüleriyle uğraşırken, görüntü boyutunu ve kalitesini ayarlama yeteneğidir. Bu eğitimde, Groupdocs.Viewer for .NET kullanarak görüntü boyutunu ve kalitesini ayarlama sürecinde size yol göstereceğiz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. C# programlama dilinin temel düzeyde anlaşılması.
2. Sisteminizde Visual Studio yüklü.
3. .NET kütüphanesi için Groupdocs.Viewer yüklendi. Buradan indirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktar
Öncelikle, gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu ad alanları, Groupdocs.Viewer ile çalışmak için gereken sınıflara ve yöntemlere erişim sağlar.
## Adım 1: Ad Alanlarını İçe Aktar
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi daha iyi anlaşılması için verilen örnek kodu birden fazla adıma bölelim.
## Adım 2: Çıktı Dizini ve Sayfa Dosyası Yolu Biçimini Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Bu adımda, oluşturulan görsellerin kaydedileceği çıktı dizinini belirliyoruz ve her sayfa görselinin dosya yolu formatını tanımlıyoruz.
## Adım 3: Görüntüleyiciyi Başlatın ve JPG Görünüm Seçeneklerini Yapılandırın
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Burada, Viewer nesnesini görüntülenecek belgenin yoluyla başlatıyoruz. Sonra, JpgViewOptions'ın bir örneğini oluşturuyoruz ve JPEG görüntüleri için istenen genişliği ve yüksekliği ayarlıyoruz.
## Adım 4: Kaynak Belgeyi Oluşturun
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Son olarak kaynak belgenin başarıyla oluşturulduğunu ve çıktı görüntülerinin kaydedildiği konumu belirten bir mesaj yazdırıyoruz.

## Çözüm
Bu eğitimde, .NET için Groupdocs.Viewer kullanarak JPEG görüntülerinin boyutunu ve kalitesini nasıl ayarlayacağımızı öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevselliği .NET uygulamalarınıza kolayca entegre edebilir ve kullanıcılara optimize edilmiş görüntü görüntüleme deneyimi sağlayabilirsiniz.
## SSS
### Görüntü kalitesini de ayarlayabilir miyim?
Evet, JpgViewOptions'daki Kalite özelliğini ayarlayarak görüntü kalitesini ayarlayabilirsiniz.
### Groupdocs.Viewer for .NET hangi belge biçimlerini destekliyor?
Groupdocs.Viewer for .NET, DOCX, PDF, PPTX, XLSX ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Groupdocs.Viewer for .NET, .NET Core ile uyumlu mudur?
Evet, Groupdocs.Viewer for .NET, geleneksel .NET Framework'ün yanı sıra .NET Core ile de uyumludur.
### Çıktı dosyası adlandırma biçimini özelleştirebilir miyim?
Evet, koddaki pageFilePathFormat değişkenini değiştirerek çıktı dosyası adlandırma biçimini özelleştirebilirsiniz.
### Groupdocs.Viewer for .NET belge açıklamalarını destekliyor mu?
Evet, Groupdocs.Viewer for .NET, metin vurgulama, altını çizme ve yorumlama dahil olmak üzere belge açıklamaları için kapsamlı destek sağlar.