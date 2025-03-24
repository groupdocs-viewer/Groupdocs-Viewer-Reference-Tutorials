---
title: Lisansı Dosyadan Ayarla
linktitle: Lisansı Dosyadan Ayarla
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i uygulamalarınıza zahmetsizce nasıl entegre edeceğinizi öğrenin. Lisansı ayarlayın, belgeleri görüntüleyin ve görüntüleyicinin görünümünü özelleştirin.
weight: 10
url: /tr/net/getting-started/set-license-from-file/
---

# Lisansı Dosyadan Ayarla

## giriiş
GroupDocs.Viewer for .NET, .NET geliştiricilerinin belge görüntüleme yeteneklerini uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir belge görüntüleme API'sidir. Belgeleri PDF, Microsoft Office veya görseller gibi çeşitli formatlarda görüntülemeniz gerekiyorsa GroupDocs.Viewer kapsamlı özelleştirme seçenekleriyle güvenilir bir çözüm sunar.
## Önkoşullar
GroupDocs.Viewer for .NET uygulamasına geçmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. .NET Framework Yüklü
Geliştirme makinenizde .NET Framework'ün kurulu olduğundan emin olun. Resmi Microsoft web sitesinden indirebilirsiniz.
### 2. .NET Paketi için GroupDocs.Viewer
 GroupDocs.Viewer for .NET paketini şu adresten indirip yükleyin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
### 3. Lisans Dosyası
 Şuradan bir lisans dosyası edinin:[GrupDoc'ları](https://purchase.groupdocs.com/buy) GroupDocs.Viewer for .NET'i herhangi bir sınırlama olmaksızın kullanmak için.
### 4. Geçici Lisans (İsteğe bağlı)
 Bir lisans satın almadan önce GroupDocs.Viewer for .NET'in yeteneklerini keşfetmek istiyorsanız, adresinden geçici bir lisans talep edebilirsiniz.[Burada](https://purchase.groupdocs.com/temporary-license/).
### 5. C# Programlama Diline aşinalık
Bu eğitimde verilen örneklerin yanı sıra temel C# programlama dili bilgisinin takip edilmesi önemlidir.

## Ad Alanlarını İçe Aktar
C# projenizde, GroupDocs.Viewer for .NET işlevlerini kullanmak için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.IO;
```

## 1. Adım: Lisans Dosyasının Varlığını Kontrol Edin
```csharp
if (File.Exists(Utils.LicensePath))
{
```
## 2. Adım: Lisansı Dosyadan Ayarlayın
```csharp
    License license = new License();
    license.SetLicense(Utils.LicensePath);
    Console.WriteLine("License set successfully.");
}
```
## 3. Adım: Eksik Lisans Dosyasını İşleyin
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://satın alma.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request temporary license at https://satın alma.groupdocs.com/temporary-license.");
}
```
Bu adımları izleyerek, GroupDocs.Viewer'ı kullanarak .NET uygulamanızdaki bir dosyadan lisansı ayarlayabileceksiniz.

## Çözüm
Sonuç olarak GroupDocs.Viewer for .NET, belge görüntüleme yeteneklerini .NET uygulamalarınıza entegre etmek için kusursuz bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek lisansı bir dosyadan kolayca ayarlayabilir ve GroupDocs.Viewer'ın tüm potansiyelinden yararlanabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET için kalıcı lisansı nasıl edinebilirim?
 adresinden kalıcı bir lisans satın alabilirsiniz.[GrupDoc'ları](https://purchase.groupdocs.com/buy) GroupDocs.Viewer'ı herhangi bir sınırlama olmaksızın kullanmak için.
### Değerlendirme amacıyla geçici bir lisans mevcut mu?
 Evet, adresinden geçici lisans talep edebilirsiniz.[Burada](https://purchase.groupdocs.com/temporary-license/) Satın alma işlemi yapmadan önce GroupDocs.Viewer for .NET'i değerlendirmek için.
### Belge görüntüleyicinin görünümünü özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET, görüntüleyiciyi ihtiyaçlarınıza göre uyarlamak için kapsamlı özelleştirme seçenekleri sunar.
### GroupDocs.Viewer birden fazla belge formatını destekliyor mu?
Evet, GroupDocs.Viewer PDF, Microsoft Office, resimler ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### .NET için GroupDocs.Viewer desteğini nerede bulabilirim?
 Destek ve yardıma şu adresten ulaşabilirsiniz:[GroupDocs Görüntüleyici forumu](https://forum.groupdocs.com/c/viewer/9).