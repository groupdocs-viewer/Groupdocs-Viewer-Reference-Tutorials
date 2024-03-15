---
title: Resim Boyutunu ve Kalitesini Ayarlayın (JPG)
linktitle: Resim Boyutunu ve Kalitesini Ayarlayın (JPG)
second_title: GroupDocs.Viewer .NET API'si
description: Groupdocs.Viewer for .NET'i kullanarak JPEG formatında görüntü boyutunu ve kalitesini nasıl optimize edeceğinizi öğrenin. Belge görüntüleme deneyiminizi geliştirin.
type: docs
weight: 11
url: /tr/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## giriiş
Groupdocs.Viewer for .NET, geliştiricilerin belge görüntüleme işlevselliğini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir kitaplıktır. Belge görüntüleme uygulamalarında yaygın bir gereksinim, özellikle JPEG (JPG) görüntülerle çalışırken görüntülerin boyutunu ve kalitesini ayarlama yeteneğidir. Bu öğreticide, Groupdocs.Viewer for .NET'i kullanarak görüntü boyutunu ve kalitesini ayarlama sürecinde size yol göstereceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. C# programlama dilinin temel anlayışı.
2. Sisteminizde Visual Studio yüklü.
3.  .NET kitaplığı için Groupdocs.Viewer yüklendi. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu ad alanları, Groupdocs.Viewer ile çalışmak için gereken sınıflara ve yöntemlere erişim sağlar.
## 1. Adım: Ad Alanlarını İçe Aktarın
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi daha iyi anlaşılması için verilen örnek kodu birden fazla adıma ayıralım.
## Adım 2: Çıktı Dizinini ve Sayfa Dosya Yolu Formatını Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Bu adımda, render edilen görsellerin kaydedileceği çıktı dizinini belirliyoruz ve her sayfa görselinin dosya yolu için formatı tanımlıyoruz.
## 3. Adım: Görüntüleyiciyi Başlatın ve JPG Görünüm Seçeneklerini Yapılandırın
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Burada Viewer nesnesini görüntülenecek belgenin yolu ile başlatıyoruz. Daha sonra JpgViewOptions'ın bir örneğini oluşturuyoruz ve JPEG görüntüleri için istenilen genişlik ve yüksekliği ayarlıyoruz.
## Adım 4: Kaynak Belgeyi Oluşturun
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Son olarak, kaynak belgenin başarıyla oluşturulduğunu ve çıktı görüntülerinin kaydedildiği konumu belirten bir mesaj yazdırıyoruz.

## Çözüm
Bu eğitimde, Groupdocs.Viewer for .NET'i kullanarak JPEG görüntülerinin boyutunu ve kalitesini nasıl ayarlayacağımızı öğrendik. Yukarıda özetlenen adımları izleyerek bu işlevselliği .NET uygulamalarınıza kolayca dahil edebilir ve kullanıcılara optimize edilmiş görüntü görüntüleme deneyimi sunabilirsiniz.
## SSS'ler
### Görüntü kalitesini de ayarlayabilir miyim?
Evet, JpgViewOptions'ta Kalite özelliğini ayarlayarak görüntü kalitesini ayarlayabilirsiniz.
### .NET için Groupdocs.Viewer tarafından hangi belge formatları desteklenir?
Groupdocs.Viewer for .NET, DOCX, PDF, PPTX, XLSX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### .NET için Groupdocs.Viewer .NET Core ile uyumlu mu?
Evet, Groupdocs.Viewer for .NET, geleneksel .NET Framework'ün yanı sıra .NET Core ile de uyumludur.
### Çıktı dosyası adlandırma biçimini özelleştirebilir miyim?
Evet, koddaki pageFilePathFormat değişkenini değiştirerek çıktı dosyası adlandırma biçimini özelleştirebilirsiniz.
### Groupdocs.Viewer for .NET belge açıklamalarını destekliyor mu?
Evet, Groupdocs.Viewer for .NET, metin vurgulama, altını çizme ve yorum ekleme dahil belge açıklamaları için kapsamlı destek sağlar.