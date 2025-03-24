---
title: Lisansı Akıştan Ayarla
linktitle: Lisansı Akıştan Ayarla
second_title: GroupDocs.Viewer .NET API'si
description: Kusursuz belge görüntüleme için .NET uygulamalarınızı GroupDocs.Viewer ile geliştirin. Adım adım kılavuzumuzu takip edin ve güçlü belge görüntüleme özelliklerini zahmetsizce entegre edin.
weight: 11
url: /tr/net/getting-started/set-license-from-stream/
---
## giriiş
.NET uygulamalarınızı gelişmiş belge görüntüleme yetenekleriyle güçlendirmek mi istiyorsunuz? GroupDocs.Viewer for .NET, belge görüntüleme işlevlerini projelerinize sorunsuz bir şekilde entegre etmek için kapsamlı bir çözüm sunar. Bu eğitimde, uygulamalarınızı güçlü belge görüntüleme özellikleriyle zenginleştirmek için GroupDocs.Viewer for .NET'ten yararlanma sürecini ayrıntılı olarak ele alacağız. 
## Önkoşullar
Entegrasyon sürecine dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. .NET Geliştirmeye İlişkin Temel Bilgi: Bu eğitimle birlikte C# ve .NET çerçevesine aşina olmak çok önemlidir.
   
2.  GroupDocs.Viewer for .NET Paketi: GroupDocs.Viewer for .NET paketini indirip yüklediğinizden emin olun. adresinden temin edebilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
3.  GroupDocs Dokümantasyonuna Erişim:[dokümantasyon](https://tutorials.groupdocs.com/viewer/net/) Entegrasyon işlemi sırasında referans olması açısından kullanışlıdır.

## Ad Alanlarını İçe Aktar
Başlangıç olarak gerekli ad alanlarını .NET uygulamanıza aktarın. Bu adımları takip et:
### Adım 1: .NET projenizi açın.
.NET projenizin tercih ettiğiniz geliştirme ortamında açıldığından emin olun.
### Adım 2: GroupDocs.Viewer Ad Alanını ekleyin.
GroupDocs.Viewer işlevlerine erişmek için kod dosyanıza aşağıdaki ad alanını ekleyin:
```csharp
using System;
using System.IO;
```
## Lisansı Akıştan Ayarla
Bir sonraki adım, lisansı bir akıştan ayarlamayı içerir. Şu ayrıntılı adımları izleyin:
### Adım 1: Çıkış Dizinini Tanımlayın.
Çıkış dizinini tanımlayarak belgelerinizin saklanacağı dizini ayarlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
### Adım 2: Lisans Dosyasının Varlığını Kontrol Edin.
Lisans dosyasının proje dizininizde olup olmadığını kontrol edin:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Adım 3: Lisansı Ayarlayın.
Lisans dosyası mevcutsa sağlanan akışı kullanarak lisansı ayarlayın:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Adım 4: Lisans Eksikliğini Giderin.
Lisans dosyası bulunamazsa lisans almak için gerekli talimatları sağlayın:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://satın alma.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://satın alma.groupdocs.com/temporary-license.");
}
```

## Çözüm
Tebrikler! GroupDocs.Viewer for .NET'i uygulamalarınıza nasıl entegre edeceğinizi başarıyla öğrendiniz. Bu güçlü araçla artık .NET projelerinizde çeşitli belge formatlarını zahmetsizce görüntüleyebilir, kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET'i kullanmak için lisansa ihtiyacım var mı?
Evet, GroupDocs.Viewer for .NET'i kullanmak için bir lisansa ihtiyacınız var. GroupDocs web sitesinden geçici veya kalıcı bir lisans alabilirsiniz.
### GroupDocs.Viewer'ı ASP.NET uygulamama entegre edebilir miyim?
Kesinlikle! GroupDocs.Viewer for .NET, ASP.NET dahil olmak üzere hem masaüstü hem de web uygulamalarına sorunsuz bir şekilde entegre olur.
### GroupDocs.Viewer hangi belge formatlarını destekler?
GroupDocs.Viewer, PDF, Microsoft Office (Word, Excel, PowerPoint), resimler ve daha fazlası dahil olmak üzere çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer for .NET, hem .NET Framework hem de .NET Core ile uyumludur.
### Görüntüleyici arayüzünü uygulamamın temasına göre özelleştirebilir miyim?
Evet, GroupDocs.Viewer kapsamlı özelleştirme seçenekleri sunarak görüntüleyici arayüzünü uygulamanızın temasına kusursuz bir şekilde uyacak şekilde uyarlamanıza olanak tanır.