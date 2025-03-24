---
title: PDF Belgesi için Görüntüleme Bilgisini Alın
linktitle: PDF Belgesi için Görüntüleme Bilgisini Alın
second_title: GroupDocs.Viewer .NET API'si
description: Bu kapsamlı eğitimde GroupDocs.Viewer for .NET'i kullanarak PDF belgelerinden görünüm bilgilerini nasıl çıkaracağınızı öğrenin.
weight: 16
url: /tr/net/pdf-rendering-options/get-view-info-pdf-document/
---
## giriiş
GroupDocs.Viewer for .NET, .NET uygulamalarında belge görüntülemeyi kolaylaştırmak için tasarlanmış güçlü bir araçtır. İster PDF'ler, Word belgeleri, Excel elektronik tabloları veya PowerPoint sunumlarıyla çalışıyor olun, bu kitaplık çeşitli dosya formatlarını oluşturma ve bunlarla etkileşim kurma sürecini basitleştirir. Bu eğitimde, özellikle PDF belgelerinden görünüm bilgilerinin çıkarılmasına yönelik GroupDocs.Viewer'ın özelliklerinden yararlanmaya odaklanacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  .NET için GroupDocs.Viewer kurulumu: GroupDocs.Viewer kitaplığını indirip yüklediğinizden emin olun. adresinden temin edebilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).   
2. Temel C# Bilgisi: Sağlanan kod örneklerini anlamak ve uygulamak için C# programlama diline aşina olmak çok önemlidir.
3. PDF Belgesine Erişim: Görünüm bilgilerini çıkarmak için kullanacağınız bir PDF belgesini hazır bulundurun.

## Ad Alanlarını İçe Aktar
C# projenizde GroupDocs.Viewer işlevlerini kullanmak için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Şimdi GroupDocs.Viewer for .NET'i kullanarak bir PDF belgesinden görünüm bilgilerini alma sürecini inceleyelim.
## 1. Adım: Görüntüleyici Nesnesini Başlatın
Bir Viewer nesnesi oluşturun ve PDF belgesinin yolunu parametre olarak belirtin.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Adım 2: ViewInfoOptions'ı tanımlayın
Görünüm bilgilerini almak için HTML görünümü gibi görünüm seçeneklerini belirtin.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## 3. Adım: Görünüm Bilgilerini Alın
PDF belgesinden görünüm bilgilerini ayıklamak için GetViewInfo yöntemini çağırın.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Adım 4: Çıktı Görünümü Bilgileri
Belge türü, sayfa sayısı ve yazdırma izinleri gibi çıkarılan görünüm bilgilerini görüntüleyin.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Çözüm
Bu eğitimde, PDF belgelerinden görünüm bilgilerini çıkarmak için GroupDocs.Viewer for .NET'in nasıl kullanılacağını araştırdık. Verilen adımları izleyerek, bu işlevselliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, belge yönetimi ve görüntüleme yeteneklerini geliştirebilirsiniz.
## SSS'ler
### GroupDocs.Viewer, PDF'nin yanı sıra diğer dosya formatlarıyla da uyumlu mu?
Evet, GroupDocs.Viewer, aralarında Word, Excel, PowerPoint ve daha fazlasının da bulunduğu çok çeşitli belge formatlarını destekler.
### Görünüm seçeneklerini uygulamamın gereksinimlerine göre özelleştirebilir miyim?
Kesinlikle GroupDocs.Viewer, izleme deneyiminizi özel ihtiyaçlarınıza göre uyarlamak için çeşitli seçenekler sunar.
### GroupDocs.Viewer hem masaüstü hem de web uygulamaları için uygun mudur?
Evet, GroupDocs.Viewer çok yönlüdür ve hem masaüstü hem de web tabanlı .NET uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### Uygulama sırasında herhangi bir sorunla karşılaşırsam GroupDocs.Viewer destek ve yardım sağlıyor mu?
Elbette, herhangi bir sorunun hızlı bir şekilde çözülmesi için GroupDocs.Viewer topluluk forumundan yardım isteyebilir veya profesyonel destek hizmetlerine erişebilirsiniz.
### Satın alma işlemi yapmadan önce GroupDocs.Viewer'ı deneyebilir miyim?
 Evet, şu adreste bulunan ücretsiz deneme sürümüne erişerek GroupDocs.Viewer'ın özelliklerini keşfedebilirsiniz.[İnternet sitesi](https://purchase.groupdocs.com/buy).