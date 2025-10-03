---
"description": "GroupDocs.Viewer for .NET kullanarak belgeleri yüklerken dosya türünü nasıl belirleyeceğinizi öğrenin. .NET uygulamalarınızda çeşitli biçimleri doğru bir şekilde işleyin."
"linktitle": "Belgeleri Yüklerken Dosya Türünü Belirleyin"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Belgeleri Yüklerken Dosya Türünü Belirleyin"
"url": "/tr/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Belgeleri Yüklerken Dosya Türünü Belirleyin

## giriiş
.NET için GroupDocs.Viewer, DOCX, PDF, PPTX ve daha fazlası dahil olmak üzere çok çeşitli dosya biçimlerini destekleyen çok yönlü bir belge oluşturma API'sidir. Belgeleri yüklerken dosya türünü belirterek, kullanıcılarınız için doğru oluşturma ve sorunsuz görüntüleme deneyimi sağlayabilirsiniz.

![.NET için GroupDocs.Viewer'da Belgeleri Yüklerken Dosya Türünü Belirtin](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- C# ve .NET framework hakkında temel bilgi.
- Sisteminizde Visual Studio yüklü.
- Projenize .NET için GroupDocs.Viewer yüklendi. Bunu şuradan indirebilirsiniz: [Burada](https://releases.groupdocs.com/viewer/net/).
##
## Ad Alanlarını İçe Aktar
Öncelikle, gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu ad alanları, belge oluşturma için gereken sınıflara ve yöntemlere erişim sağlar.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıktı Dizinini Ayarlayın
Oluşturulan belge sayfalarını kaydetmek istediğiniz dizini tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
Belgenin her sayfası için çıktı HTML dosyalarını adlandırma biçimini belirtin.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: Yükleme Seçeneklerini Belirleyin
Bir örneğini oluşturun `LoadOptions` sınıfını seçin ve istediğiniz dosya türünü ayarlayın.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Adım 4: Belgeyi Yükle ve Oluştur
Kullanın `Viewer` Belgeyi yüklemek ve HTML formatına dönüştürmek için sınıf.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 5: Başarı Mesajını Göster
Kullanıcıya belgenin başarıyla işlendiğini bildirin ve çıktı dosyalarının konumunu belirtin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu eğitimde, belgeleri yüklerken dosya türünü belirtmek için .NET için GroupDocs.Viewer'ı nasıl kullanacağımızı öğrendik. Bu basit adımları izleyerek, .NET uygulamalarınızda çeşitli belge biçimlerinin doğru şekilde işlenmesini sağlayabilirsiniz.
## SSS
### GroupDocs.Viewer for .NET kullanarak DOCX dışındaki belgeleri de görüntüleyebilir miyim?
Evet, GroupDocs.Viewer PDF, PPTX, XLSX ve daha fazlası dahil olmak üzere çok çeşitli dosya biçimlerini destekler.
### GroupDocs.Viewer for .NET, .NET Core ile uyumlu mudur?
Evet, GroupDocs.Viewer for .NET hem .NET Framework hem de .NET Core ile uyumludur.
### GroupDocs.Viewer tarafından oluşturulan çıktı HTML dosyalarını özelleştirebilir miyim?
Evet, API tarafından sağlanan çeşitli seçenekleri kullanarak HTML çıktısını özelleştirebilirsiniz.
### GroupDocs.Viewer for .NET herhangi bir harici bağımlılık gerektiriyor mu?
Hayır, GroupDocs.Viewer for .NET bağımsız bir kütüphanedir ve herhangi bir harici bağımlılığa ihtiyaç duymaz.
### GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/viewer/net/).