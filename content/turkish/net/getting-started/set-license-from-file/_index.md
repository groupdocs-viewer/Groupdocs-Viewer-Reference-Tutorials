---
"description": "GroupDocs.Viewer for .NET'i uygulamalarınıza zahmetsizce nasıl entegre edeceğinizi öğrenin. Lisans ayarlayın, belgeleri görüntüleyin ve görüntüleyici görünümünü özelleştirin."
"linktitle": "Lisansı Dosyadan Ayarla"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Lisansı Dosyadan Ayarla"
"url": "/tr/net/getting-started/set-license-from-file/"
"weight": 10
---

# Lisansı Dosyadan Ayarla

## giriiş
.NET için GroupDocs.Viewer, .NET geliştiricilerinin belge görüntüleme yeteneklerini uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir belge görüntüleyici API'sidir. PDF, Microsoft Office veya resimler gibi çeşitli biçimlerde belgeleri görüntülemeniz gerekip gerekmediğine bakılmaksızın, GroupDocs.Viewer kapsamlı özelleştirme seçenekleriyle güvenilir bir çözüm sunar.

![.NET için GroupDocs.Viewer ile Dosyadan Lisans Ayarlama](/viewer/getting-started/set-license-from-file.png)

## Ön koşullar
GroupDocs.Viewer for .NET uygulamasına başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
### 1. .NET Framework Yüklendi
Geliştirme makinenizde .NET Framework'ün yüklü olduğundan emin olun. Resmi Microsoft web sitesinden indirebilirsiniz.
### 2. .NET Paketi için GroupDocs.Viewer
GroupDocs.Viewer for .NET paketini şuradan indirin ve yükleyin: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).
### 3. Lisans Dosyası
Lisans dosyasını edinin [GrupDokümanları](https://purchase.groupdocs.com/buy) .NET için GroupDocs.Viewer'ı herhangi bir sınırlama olmaksızın kullanmak.
### 4. Geçici Lisans (Opsiyonel)
.NET için GroupDocs.Viewer'ın yeteneklerini bir lisans satın almadan önce keşfetmek istiyorsanız, geçici bir lisans talep edebilirsiniz. [Burada](https://purchase.groupdocs.com/temporary-license/).
### 5. C# Programlama Dili ile aşinalık
Bu eğitimde verilen örnekleri takip edebilmek için temel C# programlama dili bilgisine sahip olmak gerekmektedir.

## Ad Alanlarını İçe Aktar
C# projenizde, GroupDocs.Viewer for .NET işlevselliklerini kullanmak için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.IO;
```

## Adım 1: Lisans Dosyasının Varlığını Kontrol Edin
```csharp
if (File.Exists(Utils.LicensePath))
{
```
## Adım 2: Lisansı Dosyadan Ayarlayın
```csharp
    License license = new License();
    license.SetLicense(Utils.LicensePath);
    Console.WriteLine("License set successfully.");
}
```
## Adım 3: Eksik Lisans Dosyasını Yönetin
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request temporary license at https://purchase.groupdocs.com/geçici-lisans.");
}
```
Bu adımları izleyerek, GroupDocs.Viewer'ı kullanarak .NET uygulamanızdaki bir dosyadan lisansı ayarlayabilirsiniz.

## Çözüm
Sonuç olarak, .NET için GroupDocs.Viewer, .NET uygulamalarınıza belge görüntüleme yeteneklerini entegre etmek için kusursuz bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, lisansı bir dosyadan kolayca ayarlayabilir ve GroupDocs.Viewer'ın tüm potansiyelini ortaya çıkarabilirsiniz.
## SSS
### GroupDocs.Viewer for .NET için kalıcı lisansı nasıl alabilirim?
Kalıcı bir lisansı şu adresten satın alabilirsiniz: [GrupDokümanları](https://purchase.groupdocs.com/buy) GroupDocs.Viewer'ı herhangi bir sınırlama olmaksızın kullanmak için.
### Değerlendirme amaçlı geçici lisans mevcut mudur?
Evet, geçici bir lisans talebinde bulunabilirsiniz. [Burada](https://purchase.groupdocs.com/temporary-license/) Satın almadan önce GroupDocs.Viewer for .NET'i değerlendirin.
### Belge görüntüleyicisinin görünümünü özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET, görüntüleyiciyi ihtiyaçlarınıza göre uyarlamak için kapsamlı özelleştirme seçenekleri sunar.
### GroupDocs.Viewer birden fazla belge biçimini destekliyor mu?
Evet, GroupDocs.Viewer PDF, Microsoft Office, resimler ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### GroupDocs.Viewer for .NET için desteği nerede bulabilirim?
Destek ve yardıma şu adresten ulaşabilirsiniz: [GroupDocs Görüntüleyici forumu](https://forum.groupdocs.com/c/viewer/9).