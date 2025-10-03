---
"description": "Gelişmiş kullanıcı deneyimi ve üretkenlik için GroupDocs.Viewer'ı kullanarak .NET'te belgeleri JPG/PNG'ye sorunsuz bir şekilde nasıl dönüştürebileceğinizi keşfedin."
"linktitle": "Belgeyi JPGPNG'ye Dönüştür"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Belgeyi JPGPNG'ye Dönüştür"
"url": "/tr/net/rendering-documents-images/render-jpg-png/"
"weight": 10
type: docs
---
# Belgeyi JPGPNG'ye Dönüştür

## giriiş

.NET geliştirme dünyasında, belgeleri verimli bir şekilde işlemek çeşitli uygulamalar için olmazsa olmazdır. İster bir belge yönetim sistemi, ister bir e-ticaret platformu veya içerik açısından zengin bir uygulama oluşturuyor olun, belgeleri sorunsuz bir şekilde görüntüleme yeteneği çok önemlidir. İşte tam bu noktada GroupDocs.Viewer for .NET devreye girerek belgeleri JPG ve PNG gibi çeşitli biçimlerde işlemek için kapsamlı bir çözüm sunar.

## Ön koşullar

GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce, sağlamanız gereken birkaç ön koşul vardır:

1. .NET Geliştirme Ortamı: Makinenizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun. Buna .NET SDK'nın kurulu olması da dahildir.

2. GroupDocs.Viewer Lisansı: GroupDocs.Viewer için geçerli bir lisans edinin. Değerlendirme amaçlı bir lisans satın alabilir veya geçici bir lisans kullanabilirsiniz.

3. Kurulum: Sağlanan kaynaktan GroupDocs.Viewer for .NET'i indirin ve kurun. [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).

4. Belge Dosyaları: İşlemek istediğiniz belge dosyalarını hazır bulundurun. GroupDocs.Viewer, DOCX, PDF, PPT ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

## Ad Alanlarını İçe Aktar

GroupDocs.Viewer for .NET kullanarak belgeleri işlemeye başlamak için, gerekli ad alanlarını projenize içe aktarmanız gerekir. Bu, kitaplığın sağladığı işlevlere erişmenizi sağlar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bir belgeyi JPG veya PNG formatına dönüştürmek, GroupDocs.Viewer for .NET ile basit bir işlemdir. Aşağıda bunu başarmanıza yardımcı olacak adım adım bir kılavuz bulunmaktadır:

## Adım 1: Çıktı Dizinini Tanımlayın

Öncelikle, işlenmiş sayfaların kaydedilmesini istediğiniz dizini tanımlayın. Bu dizin mevcut olmalı ve uygulama tarafından erişilebilir olmalıdır.

```csharp
string outputDirectory = "Your Document Directory";
```

## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın

Her işlenmiş sayfanın dosya yolları için biçimi belirtin. GroupDocs.Viewer değiştirilecektir `{0}` Dosyaları kaydederken sayfa numarasıyla birlikte.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Adım 3: Görüntüleyici Nesnesini Örneklendirin

Bir örneğini oluşturun `Viewer` Oluşturmak istediğiniz belge dosyasının yolunu sağlayarak sınıfa ekleyin.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // İşleme kodu buraya gelir
}
```

## Adım 4: İşleme Seçeneklerini Tanımlayın

Gereksinimlerinize göre işleme seçeneklerini belirtin. JPG/PNG işleme için şunu kullanacaksınız: `JpgViewOptions` veya `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Adım 5: Belgeyi Oluşturun

Çağırmak `View` yöntemi `Viewer` nesnesini oluşturun ve daha önce oluşturulan işleme seçeneklerini iletin.

```csharp
viewer.View(options);
```

## Adım 6: Sonuçları Çıktılayın

İşleme süreci tamamlandıktan sonra, kullanıcıyı işlemenin başarılı olduğu konusunda bilgilendirebilir ve işlenen sayfaların kaydedildiği dizini sağlayabilirsiniz.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

Sonuç olarak, GroupDocs.Viewer for .NET, JPG ve PNG dahil olmak üzere çeşitli formatlarda belgeleri işlemek için güçlü bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, belge işleme işlevselliğini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, kullanıcı deneyimini ve üretkenliği artırabilirsiniz.

## SSS

### S: GroupDocs.Viewer for .NET kullanarak DOCX dışındaki belgeleri de görüntüleyebilir miyim?

C: Evet, GroupDocs.Viewer PDF, PPT, XLS ve daha fazlası dahil olmak üzere çok çeşitli belge formatlarını destekler.

### S: GroupDocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?

A: Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/).

### S: Değerlendirme amaçlı geçici lisansı nasıl alabilirim?

A: Geçici lisans talebinde bulunabilirsiniz [Burada](https://purchase.groupdocs.com/temporary-license/).

### S: GroupDocs.Viewer for .NET için dokümanları nerede bulabilirim?

A: Ayrıntılı dokümantasyon mevcuttur [Burada](https://tutorials.groupdocs.com/viewer/net/).

### S: GroupDocs.Viewer for .NET ile ilgili desteği nereden alabilirim veya sorularımı nereden sorabilirim?

A: Destek forumunu ziyaret edebilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9) yardım için.