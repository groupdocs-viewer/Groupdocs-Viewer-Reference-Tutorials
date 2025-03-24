---
title: PDF'de Yazı Tipi Lisansı Doğrulamalarını Devre Dışı Bırak
linktitle: PDF'de Yazı Tipi Lisansı Doğrulamalarını Devre Dışı Bırak
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET ile .NET'inizdeki kusursuz belge görüntüleme yeteneklerinin kilidini açın. Belge oluşturmayı minimum bağımlılıkla kolayca entegre edin ve özelleştirin.
weight: 12
url: /tr/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## giriiş
.NET geliştirme alanında, belgeleri yönetmek ve değiştirmek çoğu uygulamanın çoğu zaman çok önemli bir yönüdür. İster PDF'leri, Word belgelerini veya diğer dosya türlerini görüntülerken, bu görevleri verimli bir şekilde yerine getirecek güçlü araçlara sahip olmak çok önemlidir. GroupDocs.Viewer for .NET tam da burada devreye giriyor. Bu güçlü kitaplık, geliştiricilere belge görüntüleme işlevselliğini .NET uygulamalarına sorunsuz bir şekilde entegre etme yeteneği sağlar.
## Önkoşullar
.NET için GroupDocs.Viewer'ı kullanmaya başlamadan önce, yerine getirmeniz gereken birkaç önkoşul vardır:
### 1. Visual Studio'yu yükleyin
Öncelikle sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Henüz yapmadıysanız Microsoft web sitesinden indirebilirsiniz.
### 2. .NET için GroupDocs.Viewer'ı indirin
 Şuraya gidin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/) .NET için GroupDocs.Viewer'ın en son sürümünü edinmek için. Geliştirme ortamınıza kurmak için sağlanan kurulum talimatlarını izleyin.
### 3. Geçici Lisans Alın
 Geliştirme ve test sırasında GroupDocs.Viewer for .NET'in tüm potansiyelini açığa çıkarmak için geçici bir lisans almanız önerilir. Şu adresten bir tane talep edebilirsiniz:[Burada](https://purchase.groupdocs.com/temporary-license/).

## Ad Alanlarını İçe Aktar
Önkoşulları tamamladıktan sonra projelerinizde GroupDocs.Viewer for .NET'i kullanmaya hazırsınız. Gerekli ad alanlarını kod tabanınıza aktararak başlayın.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Daha net bir anlayış için verilen örneği birden çok adıma ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
İşlenen belge sayfalarının saklanmasını istediğiniz dizini tanımlayarak başlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Belgenin tek tek sayfalarının dosya yollarının formatını ayarlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## 3. Adım: Görüntüleyici Nesnesini Başlatın
Görüntülemek istediğiniz belgenin yolunu ileterek Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
Gömülü kaynakların (örn. görüntüler) formatını belirterek, belgeyi HTML olarak görüntüleme seçeneklerini tanımlayın.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5. Adım: Yazı Tipi Lisansı Doğrulamalarını Devre Dışı Bırakın
Sorunsuz bir şekilde oluşturulmasını sağlamak için yazı tipi lisansı doğrulamalarını devre dışı bırakma seçeneğini etkinleştirin.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Adım 6: Belgeyi Görüntüleyin
Yapılandırılmış seçenekleri ileterek Viewer nesnesinin View yöntemini çağırın.
```csharp
viewer.View(options);
```
## Adım 7: Çıkış Dizinini Görüntüleyin
Kullanıcıyı, oluşturulan belge sayfalarının depolandığı konum hakkında bilgilendirin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET, geliştiricilere belge görüntüleme yeteneklerini zahmetsizce .NET uygulamalarına entegre etmeleri için kapsamlı bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, belge yönetimi iş akışlarınızı geliştirmek için bu güçlü kitaplıktan etkili bir şekilde yararlanabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET birden fazla belge formatını işleyebilir mi?
Evet, GroupDocs.Viewer PDF, Microsoft Word, Excel, PowerPoint ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer for .NET web uygulamalarına uygun mu?
Kesinlikle GroupDocs.Viewer, .NET teknolojileri kullanılarak geliştirilen hem masaüstü hem de web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### GroupDocs.Viewer herhangi bir ek bağımlılık gerektiriyor mu?
Hayır, GroupDocs.Viewer for .NET minimum düzeyde bağımlılığa sahiptir ve mevcut projelerinize kolayca entegre edilebilir.
### İşlenen belgelerin görünümünü özelleştirebilir miyim?
Evet, GroupDocs.Viewer, oluşturulan belgelerin görünümünü ve davranışını özel gereksinimlerinize uyacak şekilde özelleştirmek için çeşitli seçenekler sunar.
### GroupDocs.Viewer for .NET için teknik destek mevcut mu?
 Evet, özel destek ekibinden yardım ve rehberlik alabilirsiniz.[forum](https://forum.groupdocs.com/c/viewer/9).