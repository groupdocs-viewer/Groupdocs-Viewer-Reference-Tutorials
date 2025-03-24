---
title: XML SpreadSheetML Oluşturma
linktitle: XML SpreadSheetML Oluşturma
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak çeşitli formatlardaki XML SpreadSheetML dosyalarının kusursuz şekilde oluşturulmasını keşfedin. Uygulamalarınıza zahmetsizce entegre edin.
weight: 16
url: /tr/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---

# XML SpreadSheetML Oluşturma

## giriiş
.NET için GroupDocs.Viewer dünyasına hoş geldiniz! Bu öğreticide, güçlü bir .NET kitaplığı olan GroupDocs.Viewer'ı kullanarak XML SpreadSheetML dosyalarını kolaylıkla oluşturma konusunda size rehberlik edeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz, XML SpreadSheetML oluşturmayı uygulamalarınıza zahmetsizce entegre etmenize yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
- .NET desteğine sahip bir geliştirme ortamı.
-  .NET kitaplığı için GroupDocs.Viewer yüklendi. İndirebilirsin[Burada](https://releases.groupdocs.com/viewer/net/).
- C# programlamanın temel anlayışı.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# projenize aktararak başlayın. Bu, GroupDocs.Viewer tarafından sağlanan işlevlere erişebilmenizi sağlar.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Adım: Belge Dizininizi Kurun
Çıktının kaydedileceği belge dizininizin yolunu tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Çıktı Dosyası Yollarını Belirleyin
HTML, JPG, PNG ve PDF çıktı dosyalarının tam yollarını ayarlayın.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Adım 3: Yükleme Seçeneklerini Belirleyin
Doğru şekilde oluşturmak için dosya türünü açıkça Excel 2003 XML SpreadSheetML olarak belirtin.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Adım 4: Çok Sayfalı HTML'ye Dönüştür
XML SpreadSheetML dosyasını çok sayfalı bir HTML belgesine dönüştürmek için HTML görünüm seçeneklerini kullanın.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 5: JPG'ye dönüştürün
Belirtilen seçenekleri kullanarak XML SpreadSheetML dosyasını JPG görüntüsüne dönüştürün.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 6: PNG'ye dönüştürün
Benzer şekilde, belirtilen seçeneklerle dosyayı PNG görüntüsüne dönüştürün.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 7: PDF'ye Dönüştür
Son olarak, belirtilen seçenekleri kullanarak XML SpreadSheetML dosyasını bir PDF belgesine dönüştürün.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Çözüm
Tebrikler! GroupDocs.Viewer for .NET'i kullanarak XML SpreadSheetML dosyalarının nasıl oluşturulacağını başarıyla öğrendiniz. Bu çok yönlü kitaplığın sağladığı daha fazla özellik ve seçeneği keşfederek belge görüntüleme yeteneklerinizi geliştirin.
## SSS
### GroupDocs.Viewer diğer dosya formatlarıyla uyumlu mu?
Evet, GroupDocs.Viewer PDF, Word, Excel ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### İşlenen belgelerin görünümünü özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, çıktıyı özel ihtiyaçlarınıza göre uyarlamanıza olanak tanıyan çeşitli özelleştirme seçenekleri sunar.
### Ek destek ve kaynakları nerede bulabilirim?
 Ziyaret edin[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) topluluk desteği için ve keşfetmek için[dokümantasyon](https://tutorials.groupdocs.com/viewer/net/)detaylı bilgi için.
### Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.groupdocs.com/).
### Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.groupdocs.com/temporary-license/).