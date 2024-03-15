---
title: Gizli Sütunları ve Satırları Oluştur
linktitle: Gizli Sütunları ve Satırları Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak e-tablolardaki gizli verilerin kilidini zahmetsizce açın. Gizli sütunları ve satırları ortaya çıkarmak için adım adım kılavuzumuzu izleyin.
type: docs
weight: 13
url: /tr/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## giriiş
Belge görselleştirme alanında, GroupDocs.Viewer for .NET, çeşitli belge formatlarının kusursuz şekilde oluşturulmasını kolaylaştıran güçlü bir araç olarak öne çıkıyor. İlgi çekici yeteneklerden biri, e-tablolardaki gizli sütunları ve satırları ortaya çıkarma yeteneğidir. Bu eğitimde, bu özelliğin kilidini açmak ve verilerinizin potansiyelini ortaya çıkarmak için gereken adımları inceleyeceğiz.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- GroupDocs.Viewer for .NET: En son sürümün kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[resmi internet sitesi](https://releases.groupdocs.com/viewer/net/).
- Belge Dosyası: Gizli sütun ve satırlarla denemeler yapmak için elektronik tablo formatında (örneğin, SAMPLE.XLSX) örnek bir belge hazırlayın.
- Geliştirme Ortamı: Tercihen Visual Studio'yu veya .NET geliştirme için uygun herhangi bir IDE'yi kullanarak bir çalışma ortamı oluşturun.
## Ad Alanlarını İçe Aktar
.NET projenizde, GroupDocs.Viewer işlevselliklerinden etkili bir şekilde yararlanmak için gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. Adım: Çıkış Dizinini Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
İşlenen HTML sayfalarının depolanacağı çıktı dizinini tanımlayın. Dosya yolu formatını buna göre ayarlayın.
## 2. Adım: Görüntüleyiciyi Başlatın ve Seçenekleri Yapılandırın
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Elektronik tablo belgenizin yolunu sağlayarak bir Viewer örneği oluşturun. Kaynakları gömmek ve gizli sütun ve satırların oluşturulmasını etkinleştirmek için HTML görünüm seçeneklerini yapılandırın.
## Adım 3: Oluşturma İşlemini Yürütün
```csharp
    viewer.View(options);
}
```
Yapılandırılmış seçenekleri ileterek görüntüleyici nesnesinde View yöntemini çağırın. Bu, oluşturma sürecini başlatır.
## Adım 4: Çıktıyı Kontrol Edin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Kaynak belgenin başarıyla oluşturulduğunu doğrulayın ve çıktıyı belirtilen dizinde bulun.
## Çözüm
GroupDocs.Viewer for .NET ile e-tablolarınızdaki gizli sütunların ve satırların kilidini açmak artık çok kolay. Bu eğitim, belgelerinizin daha kapsamlı bir görünümünü sunarak sizi gizli verileri açığa çıkarmak için gerekli adımlarla donattı.
## Sıkça Sorulan Sorular
### Gizli sütunları ve satırları e-tabloların yanı sıra diğer belge formatlarında da görüntüleyebilir miyim?
Evet, GroupDocs.Viewer elektronik tabloların yanı sıra Word, PDF ve PowerPoint dahil çeşitli belge formatlarını da destekler.
### Oluşturulabilecek gizli sütun ve satır sayısında bir sınır var mı?
GroupDocs.Viewer, çok çeşitli gizli sütun ve satırların görüntülenmesini verimli bir şekilde yönetir. Ancak, çok miktarda gizli veri içeren aşırı durumlar performansı etkileyebilir.
### İşlenen verilerin çıktı formatını özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, çıktıyı özelleştirmek için esnek seçenekler sunarak, oluşturulan verileri özel ihtiyaçlarınıza göre uyarlamanıza olanak tanır.
### GroupDocs.Viewer'ın kullanımıyla ilgili lisanslamayla ilgili hususlar var mı?
 Evet, kullanımınıza uygun lisansa sahip olduğunuzdan emin olun. Lisanslama seçeneklerini şu adreste keşfedin:[GroupDocs Satın Alma](https://purchase.groupdocs.com/buy) veya bir tane edinin[geçici lisans](https://purchase.groupdocs.com/temporary-license/) test için.
### Nereden yardım isteyebilirim veya destek için GroupDocs topluluğuyla bağlantı kurabilirim?
 Ziyaret edin[GroupDocs.Viewer Forumu](https://forum.groupdocs.com/c/viewer/9) Destek, tartışmalar ve topluluk etkileşimi için.