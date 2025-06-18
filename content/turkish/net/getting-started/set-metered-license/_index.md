---
"description": "Kusursuz belge görüntüleme için .NET uygulamalarınızı GroupDocs.Viewer ile geliştirin. Belge işleme işlevlerini projelerinize kolayca entegre edin."
"linktitle": "Ölçülü Lisans Ayarla"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ölçülü Lisans Ayarla"
"url": "/tr/net/getting-started/set-metered-license/"
"weight": 12
---

# Ölçülü Lisans Ayarla

## giriiş
.NET geliştirme dünyasında, güçlü belge görüntüleme yeteneklerini uygulamalarınıza dahil etmek, kullanıcı deneyimini ve işlevselliğini geliştirmek için önemlidir. .NET için GroupDocs.Viewer, belge görüntüleme işlevlerini .NET projelerinize sorunsuz bir şekilde entegre etmek için sağlam bir çözüm sunar. İster PDF'lerle, ister Microsoft Office belgeleriyle veya çeşitli görüntü biçimleriyle çalışın, GroupDocs.Viewer bu belgeleri uygulamalarınızda işleme ve görüntüleme sürecini basitleştirir.

![.NET için GroupDocs.Viewer ile Ölçülü Lisans Ayarlayın](/viewer/getting-started/set-metered-license.png)

## Ön koşullar
GroupDocs.Viewer for .NET uygulamasına başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
### 1. .NET için GroupDocs.Viewer'ı yükleyin
Başlamak için, .NET için GroupDocs.Viewer'ı indirip yüklemeniz gerekir. İndirme bağlantısını bulabilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/)Geliştirme ortamınızda kütüphaneyi kurmak için verilen kurulum talimatlarını izleyin.
### 2. Ölçülü Lisans Alın
GroupDocs.Viewer for .NET'i kullanmak için, ölçülü bir lisans edinmeniz gerekir. Bu lisans, önceden tanımlanmış kotalara göre API kullanımınızı kontrol etmenizi ve izlemenizi sağlar. Ölçülü lisansınızı ayarlamak için aşağıdaki adımları izleyin:

## Ad Alanlarını İçe Aktar
Öncelikle, .NET için GroupDocs.Viewer tarafından sağlanan işlevselliğe erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
```

Şimdi verilen örnek kodu birden fazla adıma bölelim:
## Adım 1: Genel ve Özel Anahtarları Bildirin
Açık ve özel anahtarlarınızı saklamak için değişkenler bildirin:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Değiştirdiğinizden emin olun `"YOUR_PUBLIC_KEY"` Ve `"YOUR_PRIVATE_KEY"` gerçek anahtarlarınızla.
## Adım 2: Ölçülü Lisans Ayarlayın
Genel anahtarın sağlanıp sağlanmadığını kontrol edin. Sağlanmamışsa, kullanıcıdan anahtarları ayarlamasını isteyin:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://satınalma.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Adım 3: Ölçülü Nesneyi Başlatın ve Lisansı Ayarlayın
Metered nesnesini başlatın ve genel ve özel anahtarlarınızı kullanarak metered lisansı ayarlayın:
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
Sonuç olarak, GroupDocs.Viewer for .NET, .NET uygulamalarınıza belge görüntüleme işlevlerini dahil etmek için kapsamlı bir çözüm sunar. Belirtilen adımları izleyerek, kolayca ölçülü bir lisans ayarlayabilir ve projelerinizde GroupDocs.Viewer'ın yeteneklerinden yararlanmaya başlayabilirsiniz.
## SSS
### S: GroupDocs.Viewer for .NET için dokümanları nerede bulabilirim?
Belgeleri bulabilirsiniz [Burada](https://tutorials.groupdocs.com/viewer/net/).
### S: GroupDocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz denemeye erişebilirsiniz [Burada](https://releases.groupdocs.com/).
### S: Test amaçlı geçici lisansları nasıl alabilirim?
Geçici lisanslar alınabilir [Burada](https://purchase.groupdocs.com/temporary-license/).
### S: GroupDocs.Viewer for .NET ile ilgili olarak nereden destek alabilir veya soru sorabilirim?
GroupDocs.Viewer forumunda destek arayabilir ve soru sorabilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9).
### S: GroupDocs.Viewer for .NET lisansını nereden satın alabilirim?
Bir lisans satın alabilirsiniz [Burada](https://purchase.groupdocs.com/buy).