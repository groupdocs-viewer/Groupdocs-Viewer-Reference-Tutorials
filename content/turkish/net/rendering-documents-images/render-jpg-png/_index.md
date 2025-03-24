---
title: Belgeyi JPGPNG'ye İşle
linktitle: Belgeyi JPGPNG'ye İşle
second_title: GroupDocs.Viewer .NET API'si
description: Gelişmiş kullanıcı deneyimi ve üretkenlik için GroupDocs.Viewer'ı kullanarak belgeleri .NET'te JPG/PNG'ye sorunsuz bir şekilde nasıl dönüştürebileceğinizi keşfedin.
weight: 10
url: /tr/net/rendering-documents-images/render-jpg-png/
---
## giriiş

.NET geliştirme dünyasında, çeşitli uygulamalar için belgelerin verimli bir şekilde işlenmesi çok önemlidir. İster bir belge yönetim sistemi, ister bir e-ticaret platformu, ister zengin içerikli bir uygulama oluşturuyor olun, belgeleri sorunsuz bir şekilde görüntüleme yeteneği çok önemlidir. Belgelerin JPG ve PNG gibi çeşitli formatlarda işlenmesi için kapsamlı bir çözüm sunan GroupDocs.Viewer for .NET tam da burada devreye giriyor.

## Önkoşullar

GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce sağlamanız gereken birkaç önkoşul vardır:

1. .NET Geliştirme Ortamı: Makinenizde çalışan bir .NET geliştirme ortamının kurulduğundan emin olun. Buna .NET SDK'nın kurulu olması da dahildir.

2. GroupDocs.Viewer Lisansı: GroupDocs.Viewer için geçerli bir lisans edinin. Bir lisans satın alabilir veya değerlendirme amacıyla geçici bir lisans kullanabilirsiniz.

3.  Kurulum: Sağlanan kaynaktan GroupDocs.Viewer for .NET'i indirin ve yükleyin.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).

4. Belge Dosyaları: Oluşturmak istediğiniz belge dosyalarını hazır bulundurun. GroupDocs.Viewer, DOCX, PDF, PPT ve daha fazlasını içeren çeşitli formatları destekler.

## Ad Alanlarını İçe Aktar

GroupDocs.Viewer for .NET'i kullanarak belge oluşturmaya başlamak için gerekli ad alanlarını projenize aktarmanız gerekir. Bu, kütüphanenin sağladığı işlevlere erişmenizi sağlar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

GroupDocs.Viewer for .NET ile bir belgeyi JPG veya PNG formatında oluşturmak basit bir işlemdir. Aşağıda bunu başarmanıza yardımcı olacak adım adım bir kılavuz bulunmaktadır:

## Adım 1: Çıkış Dizinini Tanımlayın

Öncelikle oluşturulan sayfaların kaydedilmesini istediğiniz dizini tanımlayın. Bu dizin mevcut olmalı ve uygulama tarafından erişilebilir olmalıdır.

```csharp
string outputDirectory = "Your Document Directory";
```

## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın

 İşlenen her sayfanın dosya yolları için formatı belirtin. GroupDocs.Viewer yerini alacak`{0}` Dosyaları kaydederken sayfa numarasıyla birlikte.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## 3. Adım: Görüntüleyici Nesnesini Örneklendirin

 Bir örneğini oluşturun`Viewer` Oluşturmak istediğiniz belge dosyasının yolunu sağlayarak sınıf.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Oluşturma kodu buraya gelecek
}
```

## Adım 4: Oluşturma Seçeneklerini Tanımlayın

Gereksinimlerinize göre oluşturma seçeneklerini belirtin. JPG/PNG oluşturmak için şunu kullanacaksınız:`JpgViewOptions` veya`PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Adım 5: Belgeyi Oluşturun

 Çağır`View` yöntemi`Viewer` nesneyi kullanın ve daha önce oluşturulan oluşturma seçeneklerini iletin.

```csharp
viewer.View(options);
```

## Adım 6: Çıktı Sonuçları

Render işlemi tamamlandıktan sonra kullanıcıyı render işleminin başarılı olduğu konusunda bilgilendirebilir ve render edilen sayfaların kaydedildiği dizini sağlayabilirsiniz.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

Sonuç olarak, GroupDocs.Viewer for .NET, belgeleri JPG ve PNG dahil olmak üzere çeşitli formatlarda işlemek için güçlü bir çözüm sunar. Bu öğreticide özetlenen adımları izleyerek, belge oluşturma işlevini .NET uygulamalarınıza sorunsuz bir şekilde entegre ederek kullanıcı deneyimini ve üretkenliği artırabilirsiniz.

## SSS'ler

### S: GroupDocs.Viewer for .NET'i kullanarak DOCX dışındaki belgeleri oluşturabilir miyim?

C: Evet, GroupDocs.Viewer PDF, PPT, XLS ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.

### S: GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?

 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.groupdocs.com/).

### S: Değerlendirme amacıyla nasıl geçici lisans alabilirim?

C: Geçici lisans talebinde bulunabilirsiniz.[Burada](https://purchase.groupdocs.com/temporary-license/).

### S: GroupDocs.Viewer for .NET belgelerini nerede bulabilirim?

 A: Ayrıntılı belgeler mevcut[Burada](https://tutorials.groupdocs.com/viewer/net/).

### S: GroupDocs.Viewer for .NET ile ilgili nereden destek alabilirim veya soru sorabilirim?

 C: Destek forumunu ziyaret edebilirsiniz[Burada](https://forum.groupdocs.com/c/viewer/9) yardım için.