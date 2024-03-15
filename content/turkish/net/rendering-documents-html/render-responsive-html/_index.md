---
title: Duyarlı HTML Oluştur
linktitle: Duyarlı HTML Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: Cihazlar arasında en iyi görüntüleme deneyimini sağlamak için Groupdocs.Viewer for .NET'i kullanarak duyarlı HTML'yi nasıl oluşturacağınızı öğrenin.
type: docs
weight: 13
url: /tr/net/rendering-documents-html/render-responsive-html/
---
## giriiş
Groupdocs.Viewer for .NET, geliştiricilerin çeşitli belge formatlarını duyarlı HTML'ye dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Bu eğitim, Groupdocs.Viewer for .NET'i kullanarak duyarlı HTML oluşturma sürecinde size rehberlik edecektir. Bu eğitimin sonunda, belgeleri farklı ekran boyutlarına uyum sağlayan HTML'ye sorunsuz bir şekilde dönüştürebilecek ve cihazlar arasında en iyi görüntüleme deneyimini sağlayabileceksiniz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Groupdocs.Viewer for .NET Kitaplığı: Kitaplığı şu adresten indirip yükleyin:[İnternet sitesi](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için uygun bir geliştirme ortamına sahip olduğunuzdan emin olun.
3. Belge Dosyaları: Duyarlı HTML'ye dönüştürmek istediğiniz belge dosyalarını hazırlayın.

## Ad Alanlarını İçe Aktar
Duyarlı HTML oluşturmaya başlamak için gerekli ad alanlarını projenize aktarın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Oluşturma sürecini birden fazla adıma ayıralım:
## Adım 1: Çıkış Dizinini Ayarlayın
Oluşturulan HTML sayfalarının kaydedilmesini istediğiniz dizini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Her sayfa için HTML dosyalarını adlandırma biçimini belirtin:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntüleyici Nesnesini Başlatın
Viewer sınıfının bir örneğini oluşturun ve işlenecek belgeyi belirtin:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Oluşturma kodu buraya gelecek
}
```
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
Duyarlı oluşturmanın etkinleştirilmesi de dahil olmak üzere HTML görünümü seçeneklerini ayarlayın:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderResponsive = true;
```
## Adım 5: Belgeyi HTML'ye Dönüştürün
Belgeyi HTML'ye dönüştürmek için Viewer nesnesinin View yöntemini kullanın:
```csharp
viewer.View(options);
```
## Adım 6: Başarı Mesajını Çıkarın
Belgenin başarıyla oluşturulduğunu belirten bir mesaj görüntüleyin:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Sonuç olarak, Groupdocs.Viewer for .NET, belgeleri duyarlı HTML'ye dönüştürmek için kusursuz bir çözüm sağlar. Bu eğitimde özetlenen adımları izleyerek belgelerinizi zahmetsizce farklı ekran boyutlarına uyum sağlayan HTML biçimine dönüştürebilir ve kullanıcılarınız için en iyi görüntüleme deneyimini sağlayabilirsiniz.
## SSS'ler
### Groupdocs.Viewer for .NET tüm belge formatlarıyla uyumlu mu?
Groupdocs.Viewer for .NET, DOCX, PDF, PPTX, XLSX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### İşlenen HTML'nin görünümünü özelleştirebilir miyim?
Evet, sayfa yönü, kalite ve filigran ekleme gibi çeşitli oluşturma seçeneklerini gereksinimlerinize göre özelleştirebilirsiniz.
### Groupdocs.Viewer for .NET ticari kullanım için lisans gerektiriyor mu?
 Evet, Groupdocs.Viewer for .NET'i üretim ortamlarında kullanmak için ticari bir lisans gereklidir. adresinden lisans satın alabilirsiniz.[İnternet sitesi](https://purchase.groupdocs.com/buy).
### Groupdocs.Viewer for .NET'in ücretsiz deneme sürümü var mı?
 Evet, Groupdocs.Viewer for .NET'in ücretsiz denemesinden şu adresten yararlanabilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).
### .NET için Groupdocs.Viewer desteğini nereden alabilirim?
Groupdocs.Viewer topluluk forumlarından destek alabilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).