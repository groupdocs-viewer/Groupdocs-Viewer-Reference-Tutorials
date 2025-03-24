---
title: Çalışma Sayfası Adlarını Alma
linktitle: Çalışma Sayfası Adlarını Alma
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'in büyüsünü keşfedin; belge görüntülemeyi uygulamalarınıza sorunsuz bir şekilde entegre edin. Ücretsiz denemeyi şimdi deneyin!
weight: 11
url: /tr/net/spreadsheet-rendering-options/get-worksheets-names/
---

# Çalışma Sayfası Adlarını Alma

## giriiş
.NET için GroupDocs.Viewer'ın büyüleyici dünyasına hoş geldiniz! .NET uygulamalarınızdaki güçlü belge görüntüleme yeteneklerini keşfetmeye hevesli bir geliştirici veya meraklıysanız, büyük bir sürprizle karşı karşıyasınız. Bu kapsamlı kılavuzda, GroupDocs.Viewer'ı kullanarak çalışma sayfası adlarını almanın inceliklerini ele alacağız. O halde emniyet kemerinizi bağlayın ve bu heyecan verici yolculuğa başlayalım!
## Önkoşullar
Kodlama büyüsüne dalmadan önce her şeyin ayarlandığından emin olalım:
1.  .NET için GroupDocs.Viewer'ı yükleyin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/).NET için GroupDocs.Viewer'ın en son sürümünü edinmek için. Geliştirme ortamınıza sorunsuz bir şekilde entegre etmek için kurulum talimatlarını izleyin.
2. Belgenizi Hazırlayın: Belirlediğiniz belge dizininizde, örneğin "file.xlsx" adında bir Excel dosyası gibi bir hedef belgenizin olduğundan emin olun.
## Ad Alanlarını İçe Aktar
Artık önkoşulları yerine getirdiğinize göre, gerekli ad alanlarını içe aktararak işe başlayalım. Bu, uygulamanızın GroupDocs.Viewer for .NET tarafından sağlanan işlevleri tanımasını ve kullanabilmesini sağlar.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Belge Dizinini Kurma
```csharp
string outputDirectory = "Your Document Directory";
```
"Belge Dizininiz"i, hedef belgenizin bulunduğu dizinin yolu ile değiştirin.
## 2. Görüntüleyiciyi Başlatma
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Bu adımda, Excel dosyanızın yolunu sağlayan Viewer sınıfının bir örneğini oluşturuyoruz.
## 3. Görünüm Bilgisi Seçeneklerini Yapılandırma
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Burada, ViewInfoOptions'ı HTML görünümleri oluşturacak ve elektronik tablo oluşturma için ek seçenekler ayarlayacak şekilde yapılandırıyoruz.
## 4. Görünüm Bilgilerini Alma
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Yapılandırılmış seçeneklere göre görünüm bilgilerini almak için Viewer örneğini kullanın.
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
Tebrikler! GroupDocs.Viewer for .NET'i kullanarak çalışma sayfası adlarını alma işlemini başarıyla tamamladınız. Bu, uygulamalarınızdaki belge görüntüleme işlevlerini geliştirmek için sayısız olasılığın önünü açar.
## SSS
### GroupDocs.Viewer for .NET'i diğer belge formatlarıyla kullanabilir miyim?
Kesinlikle! GroupDocs.Viewer, PDF, Microsoft Office ve daha fazlası dahil olmak üzere çok çeşitli belge formatlarını destekler.
### Ücretsiz deneme mevcut mu?
 Evet, GroupDocs.Viewer for .NET'i aşağıdaki uygulamamızla keşfedebilirsiniz:[ücretsiz deneme](https://releases.groupdocs.com/).
### Ek desteği nerede bulabilirim?
 Şuraya gidin:[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) topluluk desteği ve tartışmalar için.
### Geçici lisans alabilir miyim?
 Kesinlikle! Ziyaret etmek[bu bağlantı](https://purchase.groupdocs.com/temporary-license/) Geçici lisansınızı almak için.
### Ayrıntılı dokümantasyon kaynakları mevcut mu?
 Kesinlikle! Kontrol et[resmi belgeler](https://tutorials.groupdocs.com/viewer/net/) Ayrıntılı bilgi ve kılavuzlar için.