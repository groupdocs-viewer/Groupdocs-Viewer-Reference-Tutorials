---
"description": "GroupDocs.Viewer for .NET kullanarak çeşitli formatlardaki XML SpreadSheetML dosyalarının kusursuz bir şekilde işlenmesini keşfedin. Uygulamalarınıza zahmetsizce entegre edin."
"linktitle": "XML SpreadSheetML'yi oluşturma"
"second_title": "GroupDocs.Viewer .NET API"
"title": "XML SpreadSheetML'yi oluşturma"
"url": "/tr/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# XML SpreadSheetML'yi oluşturma

## giriiş
.NET için GroupDocs.Viewer dünyasına hoş geldiniz! Bu eğitimde, güçlü bir .NET kütüphanesi olan GroupDocs.Viewer'ı kullanarak XML SpreadSheetML dosyalarını kolayca işlemenize rehberlik edeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz XML SpreadSheetML işlemeyi uygulamalarınıza zahmetsizce entegre etmenize yardımcı olacak.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- .NET desteği olan bir geliştirme ortamı.
- GroupDocs.Viewer for .NET kütüphanesi yüklendi. İndirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).
- C# programlamanın temellerini anlamak.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# projenize aktararak başlayın. Bu, GroupDocs.Viewer tarafından sağlanan işlevlere erişiminizin olmasını sağlar.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Adım 1: Belge Dizininizi Ayarlayın
Çıktının kaydedileceği belgeler dizininize giden yolu tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Çıktı Dosyası Yollarını Belirleyin
HTML, JPG, PNG ve PDF çıktı dosyaları için tam yolları ayarlayın.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Adım 3: Yükleme Seçeneklerini Belirleyin
Doğru bir şekilde işlemek için dosya türünü açıkça Excel 2003 XML SpreadSheetML olarak belirtin.
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
Belirtilen seçenekleri kullanarak XML SpreadSheetML dosyasını JPG resmine dönüştürün.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 6: PNG'ye dönüştürün
Benzer şekilde dosyayı belirtilen seçeneklerle PNG görüntüsüne dönüştürün.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Adım 7: PDF'ye dönüştürün
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
Tebrikler! GroupDocs.Viewer for .NET kullanarak XML SpreadSheetML dosyalarının nasıl işleneceğini başarıyla öğrendiniz. Bu çok yönlü kütüphanenin sağladığı daha fazla özellik ve seçeneği keşfederek belge görüntüleme yeteneklerinizi geliştirin.
## SSS
### GroupDocs.Viewer diğer dosya formatlarıyla uyumlu mudur?
Evet, GroupDocs.Viewer PDF, Word, Excel ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Oluşturulan belgelerin görünümünü özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer çeşitli özelleştirme seçenekleri sunarak çıktıyı özel ihtiyaçlarınıza göre uyarlamanıza olanak tanır.
### Ek destek ve kaynakları nerede bulabilirim?
Ziyaret edin [GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) Topluluk desteği için ve keşfetmek için [belgeleme](https://tutorials.groupdocs.com/viewer/net/) Detaylı bilgi için.
### Ücretsiz deneme imkanı var mı?
Evet, ücretsiz denemeye erişebilirsiniz [Burada](https://releases.groupdocs.com/).
### Geçici ehliyet nasıl alınır?
Geçici bir lisans alabilirsiniz [Burada](https://purchase.groupdocs.com/temporary-license/).