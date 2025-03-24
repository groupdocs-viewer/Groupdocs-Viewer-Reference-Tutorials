---
title: İşlenen PDF'de JPG Görüntü Kalitesini Ayarlama
linktitle: İşlenen PDF'de JPG Görüntü Kalitesini Ayarlama
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak oluşturulmuş PDF belgelerinde JPG görüntü kalitesini nasıl ayarlayacağınızı öğrenin. Belge görüntüleme deneyiminizi geliştirin.
weight: 11
url: /tr/net/rendering-documents-pdf/adjust-jpg-quality-pdf/
---

# İşlenen PDF'de JPG Görüntü Kalitesini Ayarlama

## giriiş
Bu eğitimde, GroupDocs.Viewer for .NET'i kullanarak bir PDF oluştururken JPG görüntülerinin kalitesini nasıl ayarlayacağımızı öğreneceğiz. Bu güçlü kitaplık, .NET uygulamalarınızdaki çeşitli belge formatlarını sorunsuz bir şekilde görüntülemenize ve değiştirmenize olanak tanır.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  GroupDocs.Viewer for .NET Kitaplığı: GroupDocs.Viewer for .NET kitaplığını indirip yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET çerçevesinin kurulu olduğu, çalışan bir geliştirme ortamına sahip olun.

## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu, uygulamanızın GroupDocs.Viewer for .NET tarafından sağlanan işlevlere erişmesine olanak tanır.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıktı Dizinini ve Dosya Yolunu Tanımlayın
İşlenen PDF'nin kaydedileceği çıktı dizinini ayarlayın ve çıktı PDF dosyası için dosya yolunu tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Adım 2: PDF'yi Ayarlanmış JPG Görüntü Kalitesiyle Oluşturun
Viewer sınıfını oluşturun ve JPG resimlerini içeren belgenin yolunu iletin. Ardından, JPG görüntü kalitesini ayarlamak için PDF oluşturma seçeneklerini yapılandırın.
```csharp
using (Viewer viewer = new Viewer(TestFiles.JPG_IMAGE_PPTX))
{               
    PdfViewOptions options = new PdfViewOptions(filePath);
    viewer.View(options);
}
```
## 3. Adım: Başarı Mesajını Görüntüleyin
PDF'yi başarıyla oluşturduktan sonra, kullanıcıya tamamlama ve çıktı dosyasının konumu hakkında bilgi veren bir mesaj görüntüleyin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu eğitimde, GroupDocs.Viewer for .NET kullanarak bir PDF oluştururken JPG görüntü kalitesinin nasıl ayarlanacağını araştırdık. Bu adımları izleyerek, işlenmiş PDF belgelerinizdeki görüntülerin kalitesini etkili bir şekilde kontrol edebilir ve en iyi görsel temsili sağlayabilirsiniz.
## SSS'ler
### Görüntü kalitesini JPG'nin yanı sıra diğer formatlar için de ayarlayabilir miyim?
Evet, GroupDocs.Viewer for .NET çeşitli görüntü formatlarını destekler ve kaliteyi PNG, TIFF ve diğer formatlar için de ayarlayabilirsiniz.
### GroupDocs.Viewer for .NET, .NET framework'ün tüm sürümleriyle uyumlu mu?
GroupDocs.Viewer for .NET, .NET Core ve .NET Standard dahil olmak üzere .NET çerçevesinin birden çok sürümüyle uyumludur.
### GroupDocs.Viewer for .NET'i kullanarak belgeleri eşzamansız olarak işleyebilir miyim?
Evet, GroupDocs.Viewer for .NET, eşzamansız işleme yetenekleri sunarak uygulamalarınızın performansını artırmanıza olanak tanır.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET ile ilgili nasıl destek veya yardım alabilirim?
 GroupDocs.Viewer for .NET forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9) yardım almak, sorular sormak ve diğer kullanıcılar ve geliştiricilerle etkileşimde bulunmak için.