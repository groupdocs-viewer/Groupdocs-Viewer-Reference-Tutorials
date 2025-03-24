---
title: PDF'de Katmanlı İşlemeyi Etkinleştir
linktitle: PDF'de Katmanlı İşlemeyi Etkinleştir
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak PDF belgelerinde katmanlı oluşturmayı nasıl etkinleştireceğinizi öğrenin. Belge görüntüleme deneyimini zahmetsizce geliştirin.
weight: 15
url: /tr/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## giriiş
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak PDF belgelerinde katmanlı görüntülemeyi etkinleştirme sürecini ayrıntılı olarak ele alacağız. Katmanlı oluşturma, gelişmiş belge görüntüleme ve işleme olanağı sağlayarak kullanıcılara daha etkileşimli bir görüntüleme deneyimi sunar.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: Projenizde GroupDocs.Viewer for .NET'i kullanmak için gerekli paketi veya kitaplığı yüklediğinizden emin olun.
2. Visual Studio: Sunulan örneklerin kodlanması ve çalıştırılması için sisteminizde Visual Studio'nun kurulu olması gerekir.
3. Temel C# Anlayışı: Bu eğitimde C# programlama dili sözdizimi ve kavramlarına aşina olunduğu varsayılmaktadır.

## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını projenize aktararak başlayın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen çıktının kaydedilmesini istediğiniz dizin yolunu belirttiğinizden emin olun.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Bu adım, oluşturulan çıktıdaki tek tek sayfaların dosya yollarının formatını ayarlar.`{0}` sayfa numarası için bir yer tutucudur.
## 3. Adım: Katmanlı İşlemeyi Etkinleştirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Burada bir oluşturuyoruz`Viewer` nesneyi seçin ve işlenecek PDF belgesini belirtin. Daha sonra yapılandırıyoruz`HtmlViewOptions` tanımlanmış sayfa dosyası yolu formatıyla. Ayarlayarak`EnableLayeredRendering` mülkiyet`true` içinde`PdfOptions`PDF belgesi için katmanlı oluşturmayı etkinleştiriyoruz.
## Adım 4: Çıkış Dizinini Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Son olarak, kaynak belgenin başarıyla oluşturulduğunu belirten bir mesaj yazdırırız ve kullanıcıdan belirtilen dizindeki çıktıyı kontrol etmesini isteriz.

## Çözüm
GroupDocs.Viewer for .NET kullanılarak PDF belgelerinde katmanlı görüntülemenin etkinleştirilmesi, belge görüntüleme yeteneklerini geliştirerek kullanıcılara daha zengin ve daha etkileşimli bir deneyim sağlar. Bu öğreticide özetlenen adımları izleyerek bu özelliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### PDF belgelerinde katmanlı oluşturma nedir?
Katmanlı oluşturma, bir PDF belgesindeki farklı bileşenlerin ayrılmasına ve değiştirilmesine olanak tanıyarak etkileşimli görüntülemeye ve gelişmiş kullanıcı deneyimine olanak tanır.
### İşlenen belgeler için çıktı dizinini özelleştirebilir miyim?
Evet, gereksinimlerinize göre çıktı için herhangi bir dizin yolunu belirtebilirsiniz.
### GroupDocs.Viewer, PDF'nin yanı sıra diğer dosya formatlarını da destekliyor mu?
Evet, GroupDocs.Viewer, Word, Excel, PowerPoint ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ortamlarıyla uyumludur.
### Nerede ek destek veya yardım bulabilirim?
Görüntüleyici kitaplığıyla ilgili sorularınız veya yardım için GroupDocs.Viewer forumunu ziyaret edebilirsiniz.