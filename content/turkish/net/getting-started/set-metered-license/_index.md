---
title: Ölçülü Lisansı Ayarla
linktitle: Ölçülü Lisansı Ayarla
second_title: GroupDocs.Viewer .NET API'si
description: Kusursuz belge görüntüleme için .NET uygulamalarınızı GroupDocs.Viewer ile geliştirin. Belge oluşturma işlevlerini projelerinize kolayca entegre edin.
weight: 12
url: /tr/net/getting-started/set-metered-license/
---
## giriiş
.NET geliştirme dünyasında, güçlü belge görüntüleme yeteneklerini uygulamalarınıza dahil etmek, kullanıcı deneyimini ve işlevselliğini geliştirmek için çok önemlidir. GroupDocs.Viewer for .NET, belge görüntüleme işlevlerini .NET projelerinize sorunsuz bir şekilde entegre etmek için güçlü bir çözüm sunar. İster PDF'lerle, Microsoft Office belgeleriyle ister çeşitli görüntü formatlarıyla çalışıyor olun, GroupDocs.Viewer bu belgeleri uygulamalarınız içinde oluşturma ve görüntüleme sürecini basitleştirir.
## Önkoşullar
GroupDocs.Viewer for .NET uygulamasına geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### 1. .NET için GroupDocs.Viewer'ı yükleyin
 Başlamak için GroupDocs.Viewer for .NET'i indirip yüklemeniz gerekir. İndirme linkini bulabilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/). Kitaplığı geliştirme ortamınızda kurmak için sağlanan kurulum talimatlarını izleyin.
### 2. Ölçülü Lisans Alın
GroupDocs.Viewer for .NET'i kullanmak için ölçülü bir lisans almanız gerekir. Bu lisans, önceden tanımlanmış kotalara göre API kullanımınızı kontrol etmenize ve izlemenize olanak tanır. Ölçülü lisansınızı ayarlamak için aşağıdaki adımları izleyin:

## Ad Alanlarını İçe Aktar
Öncelikle GroupDocs.Viewer for .NET tarafından sağlanan işlevselliğe erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
```

Şimdi sağlanan örnek kodu birden çok adıma ayıralım:
## Adım 1: Genel ve Özel Anahtarları Bildirin
Genel ve özel anahtarlarınızı saklamak için değişkenleri bildirin:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Değiştirildiğinden emin olun`"YOUR_PUBLIC_KEY"` Ve`"YOUR_PRIVATE_KEY"` gerçek anahtarlarınızla.
## 2. Adım: Ölçülü Lisansı Ayarlayın
Ortak anahtarın sağlanıp sağlanmadığını kontrol edin. Değilse, kullanıcıdan tuşları ayarlamasını isteyin:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://satın alma.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## 3. Adım: Ölçülen Nesneyi Başlatın ve Lisansı Ayarlayın
Ölçülen nesneyi başlatın ve genel ve özel anahtarlarınızı kullanarak ölçülü lisansı ayarlayın:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Adım 4: Onay Mesajı
Lisansın başarıyla ayarlandığını belirten bir onay mesajı görüntüleyin:
```csharp
Console.WriteLine("License set successfully.");
```

## Çözüm
Sonuç olarak GroupDocs.Viewer for .NET, belge görüntüleme işlevlerini .NET uygulamalarınıza dahil etmek için kapsamlı bir çözüm sunar. Belirtilen adımları izleyerek kolayca ölçülü bir lisans ayarlayabilir ve projelerinizde GroupDocs.Viewer'ın özelliklerinden yararlanmaya başlayabilirsiniz.
## SSS'ler
### S: GroupDocs.Viewer for .NET belgelerini nerede bulabilirim?
 Belgeleri bulabilirsiniz[Burada](https://tutorials.groupdocs.com/viewer/net/).
### S: GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.groupdocs.com/).
### S: Test amaçlı geçici lisansları nasıl alabilirim?
 Geçici lisans alınabilecek[Burada](https://purchase.groupdocs.com/temporary-license/).
### S: GroupDocs.Viewer for .NET ile ilgili desteği nereden alabilirim veya soru sorabilirim?
 GroupDocs.Viewer forumunda destek arayabilir ve sorular sorabilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).
### S: GroupDocs.Viewer for .NET lisansını nereden satın alabilirim?
 Lisans satın alabilirsiniz[Burada](https://purchase.groupdocs.com/buy).