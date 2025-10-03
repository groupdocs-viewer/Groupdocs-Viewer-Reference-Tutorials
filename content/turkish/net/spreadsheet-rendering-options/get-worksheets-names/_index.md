---
"description": "GroupDocs.Viewer for .NET'in büyüsünü keşfedin – belge görüntülemeyi uygulamalarınıza sorunsuz bir şekilde entegre edin. Ücretsiz denemeyi şimdi deneyin!"
"linktitle": "Çalışma Sayfaları Adlarını Alın"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Çalışma Sayfaları Adlarını Alın"
"url": "/tr/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
type: docs
---
# Çalışma Sayfaları Adlarını Alın

## giriiş
.NET için GroupDocs.Viewer'ın büyüleyici dünyasına hoş geldiniz! .NET uygulamalarınızda güçlü belge görüntüleme yeteneklerini keşfetmeye meraklı bir geliştirici veya meraklıysanız, sizi bir şölene götürüyoruz. Bu kapsamlı kılavuzda, GroupDocs.Viewer kullanarak çalışma sayfası adlarını almanın inceliklerini inceleyeceğiz. O halde emniyet kemerlerinizi bağlayın ve bu heyecan verici yolculuğa çıkalım!
## Ön koşullar
Kodlamanın büyüsüne dalmadan önce her şeyin ayarlandığından emin olalım:
1. .NET için GroupDocs.Viewer'ı yükleyin: Şuraya gidin: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/) .NET için GroupDocs.Viewer'ın en son sürümünü edinmek için. Geliştirme ortamınıza sorunsuz bir şekilde entegre etmek için kurulum talimatlarını izleyin.
2. Belgenizi Hazırlayın: Belirlediğiniz belge dizininde "file.xlsx" adında bir Excel dosyası gibi hedef bir belgenizin olduğundan emin olun.
## Ad Alanlarını İçe Aktar
Artık ön koşullar yerli yerinde olduğuna göre, gerekli ad alanlarını içe aktararak işe koyulalım. Bu, uygulamanızın GroupDocs.Viewer for .NET tarafından sağlanan işlevleri tanımasını ve kullanabilmesini sağlar.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Belge Dizinini Ayarlama
```csharp
string outputDirectory = "Your Document Directory";
```
"Belge Dizininiz" ifadesini hedef belgenizin bulunduğu dizinin yoluyla değiştirin.
## 2. Görüntüleyiciyi Başlatma
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Bu adımda, Excel dosyanızın yolunu sağlayarak Viewer sınıfının bir örneğini oluşturuyoruz.
## 3. Görünüm Bilgi Seçeneklerini Yapılandırma
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Burada, HTML görünümleri oluşturmak ve elektronik tablo oluşturma için ek seçenekler belirlemek üzere ViewInfoOptions'ı yapılandırıyoruz.
## 4. Görünüm Bilgilerini Alma
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Yapılandırılan seçeneklere göre görünüm bilgilerini almak için Görüntüleyici örneğini kullanın.
## 5. Çalışma Sayfası Adlarını Görüntüleme
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Alınan sayfalar arasında dolaşın ve her çalışma sayfasının adını konsola yazdırın.
## Çözüm
Tebrikler! GroupDocs.Viewer for .NET kullanarak çalışma sayfası adlarını alma sürecinde başarılı bir şekilde gezindiniz. Bu, uygulamalarınızdaki belge görüntüleme işlevlerini geliştirmek için sayısız olasılık sunar.
## SSS
### GroupDocs.Viewer for .NET'i diğer belge formatlarıyla birlikte kullanabilir miyim?
Kesinlikle! GroupDocs.Viewer, PDF, Microsoft Office ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Ücretsiz deneme imkanı var mı?
Evet, .NET için GroupDocs.Viewer'ı şurada keşfedebilirsiniz: [ücretsiz deneme](https://releases.groupdocs.com/).
### Ek desteği nereden bulabilirim?
Başlamak için [GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) Topluluk desteği ve tartışmaları için.
### Geçici ehliyet alabilir miyim?
Kesinlikle! Ziyaret edin [bu bağlantı](https://purchase.groupdocs.com/temporary-license/) Geçici ehliyetinizi almak için.
### Ayrıntılı dokümantasyon kaynakları mevcut mu?
Kesinlikle! Şuna bir göz atın [resmi belgeler](https://tutorials.groupdocs.com/viewer/net/) Ayrıntılı bilgi ve rehberler için.