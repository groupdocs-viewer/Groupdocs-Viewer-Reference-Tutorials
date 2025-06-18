---
"description": "GroupDocs.Viewer for .NET ile .NET'inizde kusursuz belge görüntüleme yeteneklerinin kilidini açın. Belge oluşturmayı minimum bağımlılıklarla kolayca entegre edin ve özelleştirin."
"linktitle": "PDF'de Font Lisans Doğrulamalarını Devre Dışı Bırak"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF'de Font Lisans Doğrulamalarını Devre Dışı Bırak"
"url": "/tr/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
---

# PDF'de Font Lisans Doğrulamalarını Devre Dışı Bırak

## giriiş
.NET geliştirme alanında, belgeleri yönetmek ve düzenlemek çoğu uygulamanın önemli bir yönüdür. İster PDF'leri, ister Word belgelerini veya diğer dosya türlerini görüntülemek olsun, bu görevleri verimli bir şekilde halletmek için sağlam araçlara sahip olmak esastır. İşte .NET için GroupDocs.Viewer'ın devreye girdiği yer burasıdır. Bu güçlü kitaplık, geliştiricilere belge görüntüleme işlevselliğini .NET uygulamalarına sorunsuz bir şekilde entegre etme olanağı sağlar.

![GroupDocs.Viewer .NET ile PDF'de Font Lisans Doğrulamalarını Devre Dışı Bırakma](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## Ön koşullar
GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce, yerine getirmeniz gereken birkaç ön koşul vardır:
### 1. Visual Studio'yu yükleyin
Öncelikle, sisteminizde Visual Studio'nun yüklü olduğundan emin olun. Henüz yüklemediyseniz Microsoft web sitesinden indirebilirsiniz.
### 2. .NET için GroupDocs.Viewer'ı indirin
Şuraya doğru ilerleyin: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/) .NET için GroupDocs.Viewer'ın en son sürümünü edinmek için. Geliştirme ortamınızda kurmak için sağlanan kurulum talimatlarını izleyin.
### 3. Geçici Lisans Alın
GroupDocs.Viewer for .NET'in geliştirme ve test sırasında tüm potansiyelini ortaya çıkarmak için geçici bir lisans edinmeniz önerilir. Bir tane talep edebilirsiniz [Burada](https://purchase.groupdocs.com/temporary-license/).

## Ad Alanlarını İçe Aktar
Ön koşulları tamamladıktan sonra, projelerinizde GroupDocs.Viewer for .NET'i kullanmaya başlamaya hazırsınız. Gerekli ad alanlarını kod tabanınıza aktararak başlayın.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Daha net anlaşılması için verilen örneği birden fazla adıma bölelim:
## Adım 1: Çıktı Dizinini Tanımlayın
Öncelikle, işlenmiş belge sayfalarının saklanmasını istediğiniz dizini tanımlayarak başlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
Belgenin her bir sayfasının dosya yollarının biçimini ayarlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Adım 3: Görüntüleyici Nesnesini Başlatın
Görüntülemek istediğiniz belgenin yolunu geçirerek Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Adım 4: HTML Görünüm Seçeneklerini Yapılandırın
Belgeyi HTML olarak görüntüleme seçeneklerini tanımlayın ve gömülü kaynaklar (örneğin resimler) için biçimi belirtin.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Adım 5: Yazı Tipi Lisans Doğrulamalarını Devre Dışı Bırakın
Sorunsuz bir işleme sağlamak için yazı tipi lisans doğrulamalarını devre dışı bırakma seçeneğini etkinleştirin.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Adım 6: Belgeyi Görüntüle
Yapılandırılmış seçenekleri geçirerek Viewer nesnesinin View metodunu çağırın.
```csharp
viewer.View(options);
```
## Adım 7: Çıktı Dizinini Görüntüle
Kullanıcıya, oluşturulan belge sayfalarının nerede saklandığı hakkında bilgi verin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
.NET için GroupDocs.Viewer, geliştiricilere belge görüntüleme yeteneklerini .NET uygulamalarına zahmetsizce entegre etmeleri için kapsamlı bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, belge yönetimi iş akışlarınızı geliştirmek için bu güçlü kütüphaneyi etkili bir şekilde kullanabilirsiniz.
## SSS
### GroupDocs.Viewer for .NET birden fazla belge formatını işleyebilir mi?
Evet, GroupDocs.Viewer PDF, Microsoft Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### GroupDocs.Viewer for .NET web uygulamaları için uygun mudur?
Kesinlikle, GroupDocs.Viewer .NET teknolojileri kullanılarak geliştirilen hem masaüstü hem de web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### GroupDocs.Viewer herhangi bir ek bağımlılığa ihtiyaç duyuyor mu?
Hayır, GroupDocs.Viewer for .NET'in minimum bağımlılıkları vardır ve mevcut projelerinize kolayca entegre edilebilir.
### Oluşturulan belgelerin görünümünü özelleştirebilir miyim?
Evet, GroupDocs.Viewer, oluşturulan belgelerin görünümünü ve davranışını özel gereksinimlerinize uyacak şekilde özelleştirmek için çeşitli seçenekler sunar.
### GroupDocs.Viewer for .NET için teknik destek mevcut mu?
Evet, özel destek ekibinden yardım ve rehberlik alabilirsiniz. [forum](https://forum.groupdocs.com/c/viewer/9).