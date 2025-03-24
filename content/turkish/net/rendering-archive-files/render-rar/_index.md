---
title: RAR Arşivlerini Oluştur
linktitle: RAR Arşivlerini Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak RAR arşivlerini HTML, JPG, PNG veya PDF formatlarına nasıl dönüştüreceğinizi öğrenin. RAR arşivlerinin içeriğini kolayca görüntüleyin ve paylaşın.
weight: 13
url: /tr/net/rendering-archive-files/render-rar/
---
## giriiş
RAR arşivleri, birden fazla dosya ve klasörü tek bir kapta sıkıştırmak ve depolamak için kullanılan popüler bir formattır. RAR arşivlerini HTML, JPG, PNG veya PDF gibi çeşitli formatlara dönüştürmek, bu arşivlerin içeriğini görüntülemek veya paylaşmak için gerekli olabilir. Bu eğitimde, GroupDocs.Viewer for .NET'i kullanarak RAR arşivlerinin nasıl oluşturulacağını keşfedeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET kitaplığını şu adresten yükleyin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
2. Örnek RAR Arşivi: Oluşturulmaya hazır örnek bir RAR arşivi bulundurun.

## Ad Alanlarını İçe Aktar
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
## 2. Adım: HTML'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 3. Adım: JPG'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 4: PNG'ye dönüştürün
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 5: PDF'ye Dönüştür
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Çözüm
RAR arşivlerini çeşitli formatlarda oluşturmak GroupDocs.Viewer for .NET ile basitleştirilmiştir. Bu eğitimde özetlenen adımları izleyerek RAR arşivlerini zahmetsizce HTML, JPG, PNG veya PDF formatlarına dönüştürebilir, içeriklerinin kolayca görüntülenmesini ve paylaşılmasını sağlayabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET şifrelenmiş RAR arşivlerini işleyebilir mi?
Evet, GroupDocs.Viewer for .NET, işleme işlemi sırasında gerekli parolaların sağlanması koşuluyla şifrelenmiş RAR arşivlerinin oluşturulmasını destekler.
### İşlenen belgelerin çıktı görünümünü özelleştirmek mümkün mü?
Kesinlikle! GroupDocs.Viewer for .NET, kullanıcıların işlenmiş belgelerin görünümünü tercihlerine göre uyarlamalarına olanak tanıyan kapsamlı özelleştirme seçenekleri sunar.
### GroupDocs.Viewer for .NET, RAR dışında diğer arşiv formatlarının görüntülenmesini destekliyor mu?
Evet, GroupDocs.Viewer for .NET, ZIP, TAR, 7z ve daha fazlası dahil olmak üzere çeşitli arşiv formatlarının oluşturulmasını destekler.
### GroupDocs.Viewer for .NET'i web uygulamama entegre edebilir miyim?
Kesinlikle! GroupDocs.Viewer for .NET, hem masaüstü hem de web uygulamalarına entegrasyona uygun API'ler sağlar.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz denemesinden şu adresten yararlanabilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).