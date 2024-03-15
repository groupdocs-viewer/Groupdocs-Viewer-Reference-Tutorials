---
title: Belgeleri Yüklerken Dosya Türünü Belirtin
linktitle: Belgeleri Yüklerken Dosya Türünü Belirtin
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak belgeleri yüklerken dosya türünü nasıl belirleyeceğinizi öğrenin. .NET uygulamalarınızda çeşitli formatları doğru şekilde işleyin.
type: docs
weight: 10
url: /tr/net/advanced-loading/specify-file-type/
---
## giriiş
GroupDocs.Viewer for .NET, DOCX, PDF, PPTX ve daha fazlası dahil çok çeşitli dosya formatlarını destekleyen çok yönlü bir belge işleme API'sidir. Belgeleri yüklerken dosya türünü belirterek kullanıcılarınıza doğru oluşturma ve sorunsuz görüntüleme deneyimi sağlayabilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Temel C# ve .NET framework bilgisi.
- Sisteminizde Visual Studio yüklü.
- GroupDocs.Viewer for .NET projenizde yüklü. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
##
## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu ad alanları, belge oluşturma için gereken sınıflara ve yöntemlere erişim sağlar.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1. Adım: Çıkış Dizinini Ayarlayın
İşlenen belge sayfalarını kaydetmek istediğiniz dizini tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Belgenin her sayfası için çıktı HTML dosyalarını adlandırma biçimini belirtin.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: Yükleme Seçeneklerini Belirleyin
 Bir örneğini oluşturun`LoadOptions` class'a gidin ve istediğiniz dosya türünü ayarlayın.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Adım 4: Belgeyi Yükleyin ve Oluşturun
 Kullan`Viewer` belgeyi yüklemek ve HTML biçimine dönüştürmek için sınıf.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 5: Başarı Mesajını Görüntüleyin
Kullanıcıya belgenin başarıyla oluşturulduğunu bildirin ve çıktı dosyalarının konumunu belirtin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu öğreticide, belgeleri yüklerken dosya türünü belirtmek için GroupDocs.Viewer for .NET'in nasıl kullanılacağını öğrendik. Bu basit adımları izleyerek, .NET uygulamalarınızda çeşitli belge formatlarının doğru şekilde işlenmesini sağlayabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET'i kullanarak DOCX dışındaki belgeleri oluşturabilir miyim?
Evet, GroupDocs.Viewer, PDF, PPTX, XLSX ve daha fazlası dahil olmak üzere çok çeşitli dosya formatlarını destekler.
### GroupDocs.Viewer for .NET, .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer for .NET, hem .NET Framework hem de .NET Core ile uyumludur.
### GroupDocs.Viewer tarafından oluşturulan çıktı HTML dosyalarını özelleştirebilir miyim?
Evet, API tarafından sağlanan çeşitli seçenekleri kullanarak HTML çıktısını özelleştirebilirsiniz.
### GroupDocs.Viewer for .NET herhangi bir dış bağımlılık gerektiriyor mu?
Hayır, GroupDocs.Viewer for .NET bağımsız bir kitaplıktır ve herhangi bir dış bağımlılık gerektirmez.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.groupdocs.com/viewer/net/).