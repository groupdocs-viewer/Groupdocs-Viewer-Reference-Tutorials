---
"description": "GroupDocs.Viewer for .NET kullanarak PDF belgelerinde katmanlı görüntülemeyi nasıl etkinleştireceğinizi öğrenin. Belge görüntüleme deneyiminizi zahmetsizce geliştirin."
"linktitle": "PDF'de Katmanlı İşlemeyi Etkinleştir"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF'de Katmanlı İşlemeyi Etkinleştir"
"url": "/tr/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# PDF'de Katmanlı İşlemeyi Etkinleştir

## giriiş
Bu eğitimde, .NET için GroupDocs.Viewer kullanarak PDF belgelerinde katmanlı işlemeyi etkinleştirme sürecini inceleyeceğiz. Katmanlı işleme, gelişmiş belge görüntüleme ve düzenleme olanağı sunarak kullanıcılara daha etkileşimli bir görüntüleme deneyimi sağlar.

![GroupDocs.Viewer .NET ile PDF'de Katmanlı İşlemeyi Etkinleştirin](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: Projenizde GroupDocs.Viewer for .NET'i kullanmak için gerekli paket veya kütüphanenin kurulu olduğundan emin olun.
2. Visual Studio: Sağlanan örnekleri kodlamak ve çalıştırmak için sisteminizde Visual Studio yüklü olmalıdır.
3. C# Temel Anlayışı: Bu eğitim, C# programlama dili sözdizimi ve kavramlarına aşina olduğunuzu varsayar.

## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını projenize aktarın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen çıktının kaydedilmesini istediğiniz dizin yolunu belirttiğinizden emin olun.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bu adım, oluşturulan çıktıdaki bireysel sayfaların dosya yollarının biçimini belirler. `{0}` sayfa numarası için bir yer tutucudur.
## Adım 3: Katmanlı İşlemeyi Etkinleştir
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Burada bir tane yaratıyoruz `Viewer` nesneyi seçin ve işlenecek PDF belgesini belirtin. Daha sonra yapılandırırız `HtmlViewOptions` tanımlanmış sayfa dosya yolu biçimiyle. Ayarlayarak `EnableLayeredRendering` mülk `true` içinde `PdfOptions`PDF dokümanı için katmanlı işlemeyi etkinleştiriyoruz.
## Adım 4: Çıktı Dizinini Görüntüle
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Son olarak kaynak belgenin başarılı bir şekilde oluşturulduğunu belirten bir mesaj yazdırıyoruz ve kullanıcıdan belirtilen dizindeki çıktıyı kontrol etmesini istiyoruz.

## Çözüm
.NET için GroupDocs.Viewer'ı kullanarak PDF belgelerinde katmanlı işlemeyi etkinleştirmek, belge görüntüleme yeteneklerini geliştirerek kullanıcılara daha zengin ve daha etkileşimli bir deneyim sunar. Bu eğitimde özetlenen adımları izleyerek, bu özelliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS
### PDF belgelerinde katmanlı işleme nedir?
Katmanlı işleme, bir PDF belgesindeki farklı bileşenlerin ayrılmasına ve düzenlenmesine olanak tanır, etkileşimli görüntüleme ve gelişmiş kullanıcı deneyimi sağlar.
### İşlenmiş belgeler için çıktı dizinini özelleştirebilir miyim?
Evet, ihtiyaçlarınıza göre çıktı için herhangi bir dizin yolunu belirtebilirsiniz.
### GroupDocs.Viewer PDF dışında başka dosya formatlarını da destekliyor mu?
Evet, GroupDocs.Viewer Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mudur?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ortamlarıyla uyumludur.
### Ek destek veya yardımı nereden bulabilirim?
Görüntüleyici kütüphanesi ile ilgili herhangi bir soru veya yardım için GroupDocs.Viewer forumunu ziyaret edebilirsiniz.