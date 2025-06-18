---
"description": "Kusursuz belge görüntüleme için .NET uygulamalarınızı GroupDocs.Viewer ile geliştirin. Adım adım kılavuzumuzu izleyin ve güçlü belge görüntüleme yeteneklerini zahmetsizce entegre edin."
"linktitle": "Akıştan Lisans Ayarla"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Akıştan Lisans Ayarla"
"url": "/tr/net/getting-started/set-license-from-stream/"
"weight": 11
---

# Akıştan Lisans Ayarla

## giriiş
.NET uygulamalarınızı gelişmiş belge görüntüleme yetenekleriyle güçlendirmek mi istiyorsunuz? GroupDocs.Viewer for .NET, belge görüntüleme işlevlerini projelerinize sorunsuz bir şekilde entegre etmek için kapsamlı bir çözüm sunar. Bu eğitimde, uygulamalarınızı güçlü belge görüntüleme yetenekleriyle zenginleştirmek için GroupDocs.Viewer for .NET'i kullanma sürecini inceleyeceğiz. 

![.NET için GroupDocs.Viewer ile Akıştan Lisans Ayarlama](/viewer/getting-started/set-license-from-stream.png)

## Ön koşullar
Entegrasyon sürecine başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
1. .NET Geliştirmenin Temel Bilgileri: Bu eğitimi takip etmek için C# ve .NET framework'üne aşinalık şarttır.
   
2. GroupDocs.Viewer for .NET Paketi: GroupDocs.Viewer for .NET paketini indirip kurduğunuzdan emin olun. Bunu şu adresten edinebilirsiniz: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).
3. GroupDocs Belgelerine Erişim: [belgeleme](https://tutorials.groupdocs.com/viewer/net/) Entegrasyon süreci boyunca eğitimler için kullanışlıdır.

## Ad Alanlarını İçe Aktar
Başlamak için, gerekli ad alanlarını .NET uygulamanıza aktarın. Şu adımları izleyin:
### Adım 1: .NET projenizi açın.
.NET projenizin tercih ettiğiniz geliştirme ortamında açık olduğundan emin olun.
### Adım 2: GroupDocs.Viewer Ad Alanını Ekleyin.
GroupDocs.Viewer işlevlerine erişmek için kod dosyanıza aşağıdaki ad alanını ekleyin:
```csharp
using System;
using System.IO;
```
## Akıştan Lisans Ayarla
Bir sonraki adım, lisansı bir akıştan ayarlamayı içerir. Aşağıdaki ayrıntılı adımları izleyin:
### Adım 1: Çıktı Dizinini Tanımlayın.
Çıktı dizinini tanımlayarak belgelerinizin saklanacağı dizini ayarlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
### Adım 2: Lisans Dosyasının Varlığını Kontrol Edin.
Lisans dosyasının proje dizininizde olup olmadığını kontrol edin:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Adım 3: Lisansı Ayarlayın.
Lisans dosyası mevcutsa, sağlanan akışı kullanarak lisansı ayarlayın:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Adım 4: Lisans Eksikliğini Giderin.
Lisans dosyası bulunamazsa, lisans almak için talimatları sağlayın:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/geçici-lisans.");
}
```

## Çözüm
Tebrikler! GroupDocs.Viewer for .NET'i uygulamalarınıza nasıl entegre edeceğinizi başarıyla öğrendiniz. Bu güçlü araçla, artık .NET projeleriniz içinde çeşitli belge biçimlerini zahmetsizce görüntüleyebilir, kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS
### GroupDocs.Viewer for .NET'i kullanmak için lisansa ihtiyacım var mı?
Evet, GroupDocs.Viewer for .NET'i kullanmak için bir lisansa ihtiyacınız var. GroupDocs web sitesinden geçici veya kalıcı bir lisans edinebilirsiniz.
### GroupDocs.Viewer'ı ASP.NET uygulamama entegre edebilir miyim?
Kesinlikle! GroupDocs.Viewer for .NET, ASP.NET dahil olmak üzere masaüstü ve web uygulamalarına sorunsuz bir şekilde entegre olur.
### GroupDocs.Viewer hangi belge biçimlerini destekliyor?
GroupDocs.Viewer, PDF, Microsoft Office (Word, Excel, PowerPoint), resimler ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mudur?
Evet, GroupDocs.Viewer for .NET hem .NET Framework hem de .NET Core ile uyumludur.
### Uygulamamın temasına göre görüntüleyici arayüzünü özelleştirebilir miyim?
Evet, GroupDocs.Viewer kapsamlı özelleştirme seçenekleri sunarak görüntüleyici arayüzünü uygulamanızın temasına kusursuz bir şekilde uyacak şekilde özelleştirmenize olanak tanır.