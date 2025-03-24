---
title: Belgeleri Yerel Diskten Yükleme
linktitle: Belgeleri Yerel Diskten Yükleme
second_title: GroupDocs.Viewer .NET API'si
description: Groupdocs.Viewer for .NET'i kullanarak yerel diskinizdeki belgeleri sorunsuz bir şekilde nasıl oluşturacağınızı öğrenin. .NET uygulamalarınızı verimli belgelerle geliştirin.
weight: 10
url: /tr/net/loading-documents/loading-document-local-disk/
---

# Belgeleri Yerel Diskten Yükleme

## giriiş
Günümüzün dijital çağında, çeşitli uygulamalar için verimli belge oluşturma çok önemlidir. Groupdocs.Viewer for .NET, belgeleri doğrudan yerel diskinizden işlemek için güçlü bir çözüm sunar. Bu öğreticide, Groupdocs.Viewer for .NET'i kullanarak yerel diskinizden belge yükleme işlemi boyunca size rehberlik edeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz, belge oluşturmayı .NET uygulamalarınıza sorunsuz bir şekilde entegre etmenize yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  .NET için Groupdocs.Viewer: En son sürümü şuradan indirin ve yükleyin:[Burada](https://releases.groupdocs.com/viewer/net/).
2. .NET Geliştirme Ortamı: Sisteminizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun.
3. Yerel Belgeler: Oluşturmak istediğiniz belgelerin yerel olarak diskinizde saklanmasını sağlayın.

## Ad Alanlarını İçe Aktar
Öncelikle Groupdocs.Viewer for .NET'in işlevlerine erişmek için gerekli ad alanlarını içe aktaralım.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. Adım: Belgeleri Yerel Diskten Yükleme
İşlenen HTML sayfalarının kaydedileceği çıktı dizinini ayarlayarak başlayın.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 2: Görüntüleyiciyi Başlatın ve Belgeleri Oluşturun
Viewer nesnesini belgenin yolu ile başlatın ve HTML görünüm seçeneklerini kullanarak işleyin.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 3: Ekran Çıkışı
Oluşturma tamamlandığında, kaynak belgenin başarıyla oluşturulduğunu ve çıktı dosyalarının konumunu belirten bir mesaj görüntüleyin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Tebrikler! Groupdocs.Viewer for .NET'i kullanarak yerel diskinizden nasıl belge yükleyeceğinizi başarıyla öğrendiniz. Bu güçlü araç, .NET uygulamalarınızda belge işlemeye yönelik bir olasılıklar dünyasının kapılarını açar.
## SSS'ler
### Groupdocs.Viewer for .NET'i kullanarak farklı formatlardaki belgeleri işleyebilir miyim?
Evet, Groupdocs.Viewer for .NET, DOCX, PDF, XLSX, PPTX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### Groupdocs.Viewer for .NET tüm .NET çerçeveleriyle uyumlu mu?
Groupdocs.Viewer for .NET; .NET Core, .NET Framework ve .NET Standard dahil çoğu .NET çerçevesiyle uyumludur.
### Belgelerimin işleme seçeneklerini özelleştirebilir miyim?
Kesinlikle! Groupdocs.Viewer for .NET, işleme sürecini özel gereksinimlerinize göre uyarlamanıza olanak tanıyan kapsamlı özelleştirme seçenekleri sunar.
### Groupdocs.Viewer for .NET'in deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.groupdocs.com/).
### Groupdocs.Viewer for .NET için desteği veya ek kaynakları nerede bulabilirim?
 Destek ve ek kaynaklar için Groupdocs.Viewer for .NET'i ziyaret edin.[forum](https://forum.groupdocs.com/c/viewer/9).