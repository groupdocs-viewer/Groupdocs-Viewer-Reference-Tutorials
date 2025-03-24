---
title: PDF'de Metin Seçimini Devre Dışı Bırak
linktitle: PDF'de Metin Seçimini Devre Dışı Bırak
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak PDF'de metin seçimini nasıl devre dışı bırakacağınızı öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 13
url: /tr/net/pdf-rendering-options/disable-text-selection-pdf/
---

# PDF'de Metin Seçimini Devre Dışı Bırak

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin belge görüntüleme yeteneklerini .NET uygulamalarına zahmetsizce entegre etmelerine olanak tanıyan güçlü bir belge işleme API'sidir. GroupDocs.Viewer tarafından sağlanan temel işlevlerden biri, PDF belgelerinde metin seçimini devre dışı bırakma yeteneğidir. Bu özellik özellikle kullanıcıların hassas belgelerden metin kopyalamasını engellemeniz gereken senaryolarda kullanışlıdır, böylece belge güvenliği ve bütünlüğü sağlanır.
## Önkoşullar
GroupDocs.Viewer for .NET kullanılarak PDF'de metin seçiminin nasıl devre dışı bırakılacağına ilişkin adım adım kılavuza dalmadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  GroupDocs.Viewer for .NET Kurulumu: GroupDocs.Viewer for .NET'i şuradan indirip yüklediğinizden emin olun:[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
2. Doküman Dizini: Dokümanlarınızın saklanacağı bir dizin hazırlayın. PDF belgesini oluşturmak için bu dizini kod pasajında belirtmeniz gerekir.

## Ad Alanlarını İçe Aktar
Öncelikle GroupDocs.Viewer for .NET tarafından sağlanan işlevlere erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi, GroupDocs.Viewer for .NET kullanarak bir PDF belgesinde metin seçimini devre dışı bırakma sürecini birden çok adıma ayıralım:
## Adım 1: Çıkış Dizinini Belirleyin
```csharp
string outputDirectory = "Your Document Directory";
```
 Bu adımda değiştirin`"Your Document Directory"` PDF belgenizin bulunduğu dizin yolu ile.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bu adım, oluşturulan HTML sayfalarının dosya yollarının formatını tanımlar. PDF belgesinin her sayfası sıralı sayfa numarasına sahip bir HTML dosyasına dönüştürülecektir.
## Adım 3: PDF Belgesini Metin Seçimi Devre Dışı Bırakılarak Oluşturun
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Yer değiştirmek`"Path to Your PDF Document"` PDF dosyanızın gerçek yolunu belirtin. Bu kod parçacığı bir başlatır`Viewer` nesnesi, kaynakları gömmek için HTML görünüm seçeneklerini yapılandırır ve ayarlayarak metin seçimini devre dışı bırakır`RenderTextAsImage` mülkiyet`true`.
## Adım 4: Başarı Mesajını Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
PDF belgesini oluşturduktan sonra bu adım, oluşturulan HTML sayfalarının saklandığı dizinle birlikte bir başarı mesajı görüntüler.

## Çözüm
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak PDF belgelerinde metin seçiminin nasıl devre dışı bırakılacağını öğrendik. Adım adım kılavuzu takip ederek bu özelliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, belge güvenliğini sağlayabilir ve kullanıcı deneyimini geliştirebilirsiniz.
## SSS'ler
### İşlenen HTML sayfaları için çıktı dizinini özelleştirebilir miyim?
Evet, oluşturulan HTML sayfalarının saklanmasını istediğiniz herhangi bir dizin yolunu belirtebilirsiniz.
### GroupDocs.Viewer for .NET, .NET framework'ün farklı sürümleriyle uyumlu mu?
Evet, GroupDocs.Viewer for .NET, .NET Core ve .NET Framework dahil olmak üzere .NET framework'ün çeşitli sürümleriyle uyumludur.
### Metin seçiminin devre dışı bırakılması PDF belgesinin diğer işlevlerini etkiler mi?
Hayır, metin seçiminin devre dışı bırakılması yalnızca kullanıcıların belgedeki metni seçip kopyalamasını engeller. Diğer işlevler bozulmadan kalır.
### Belgeyi oluşturduktan sonra metin seçimini tekrar etkinleştirebilir miyim?
 Evet, yalnızca metin seçimini ayarlayarak etkinleştirebilirsiniz.`RenderTextAsImage` mülkiyet`false` HTML görünüm seçeneklerinde.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).