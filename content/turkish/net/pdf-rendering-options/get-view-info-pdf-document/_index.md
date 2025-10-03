---
"description": "Bu kapsamlı eğitimde, .NET için GroupDocs.Viewer'ı kullanarak PDF belgelerinden görünüm bilgilerinin nasıl çıkarılacağını öğrenin."
"linktitle": "PDF Belgesi için Görünüm Bilgisini Alın"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF Belgesi için Görünüm Bilgisini Alın"
"url": "/tr/net/pdf-rendering-options/get-view-info-pdf-document/"
"weight": 16
type: docs
---
# PDF Belgesi için Görünüm Bilgisini Alın

## giriiş
.NET için GroupDocs.Viewer, .NET uygulamaları içinde belge görüntülemeyi kolaylaştırmak için tasarlanmış güçlü bir araçtır. İster PDF'lerle, ister Word belgeleriyle, ister Excel elektronik tablolarıyla veya PowerPoint sunumlarıyla uğraşıyor olun, bu kitaplık çeşitli dosya biçimleriyle işleme ve etkileşim kurma sürecini basitleştirir. Bu eğitimde, özellikle PDF belgelerinden görünüm bilgilerini çıkarmak için GroupDocs.Viewer'ın yeteneklerinden yararlanmaya odaklanacağız.

![GroupDocs.Viewer .NET ile PDF Belgesi için Görünüm Bilgisi Alın](/viewer/pdf-rendering-options/get-view-iInfo-for-pdf-document.png)

## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. .NET için GroupDocs.Viewer Kurulumu: GroupDocs.Viewer kütüphanesini indirip kurduğunuzdan emin olun. Bunu şu adresten edinebilirsiniz: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).   
2. Temel C# Bilgisi: Sağlanan kod örneklerini anlamak ve uygulamak için C# programlama diline aşina olmak şarttır.
3. PDF Belgesine Erişim: Görünüm bilgilerini çıkarmak için kullanacağınız bir PDF belgeniz hazır olsun.

## Ad Alanlarını İçe Aktar
C# projenizde GroupDocs.Viewer fonksiyonlarını kullanabilmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Şimdi, .NET için GroupDocs.Viewer'ı kullanarak bir PDF belgesinden görünüm bilgilerini alma sürecini parçalara ayıralım.
## Adım 1: Görüntüleyici Nesnesini Başlat
Bir Görüntüleyici nesnesi oluşturun ve parametre olarak PDF belgesinin yolunu sağlayın.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Adım 2: ViewInfoOptions'ı tanımlayın
Görünüm bilgilerini almak için HTML görünümü gibi görünüm seçeneklerini belirtin.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Adım 3: Görünüm Bilgilerini Alın
PDF belgesinden görünüm bilgilerini çıkarmak için GetViewInfo metodunu çağırın.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Adım 4: Çıkış Görünümü Bilgileri
Belge türü, sayfa sayısı ve yazdırma izinleri gibi çıkarılan görünüm bilgilerini görüntüleyin.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Çözüm
Bu eğitimde, PDF belgelerinden görünüm bilgilerini çıkarmak için GroupDocs.Viewer for .NET'i nasıl kullanacağınızı inceledik. Sağlanan adımları izleyerek, bu işlevselliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, belge yönetimi ve görüntüleme yeteneklerini geliştirebilirsiniz.
## SSS
### GroupDocs.Viewer PDF dışındaki diğer dosya formatlarıyla uyumlu mudur?
Evet, GroupDocs.Viewer Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Uygulamamın gereksinimlerine göre görünüm seçeneklerini özelleştirebilir miyim?
Kesinlikle, GroupDocs.Viewer, görüntüleme deneyiminizi özel ihtiyaçlarınıza göre kişiselleştirmek için çeşitli seçenekler sunar.
### GroupDocs.Viewer hem masaüstü hem de web uygulamaları için uygun mudur?
Evet, GroupDocs.Viewer çok yönlüdür ve hem masaüstü hem de web tabanlı .NET uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### Uygulama sırasında herhangi bir sorunla karşılaşırsam GroupDocs.Viewer destek ve yardım sağlıyor mu?
Elbette, GroupDocs.Viewer topluluk forumundan yardım alabilir veya herhangi bir sorunun hızlı bir şekilde çözülmesi için profesyonel destek hizmetlerine erişebilirsiniz.
### Satın alma işlemi yapmadan önce GroupDocs.Viewer'ı deneyebilir miyim?
Evet, GroupDocs.Viewer'ın özelliklerini, web sitemizde bulunan ücretsiz deneme sürümüne erişerek keşfedebilirsiniz. [web sitesi](https://purchase.groupdocs.com/buy).