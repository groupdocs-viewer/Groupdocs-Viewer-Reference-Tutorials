---
title: PDF'yi Orijinal Sayfa Boyutuyla Oluştur
linktitle: PDF'yi Orijinal Sayfa Boyutuyla Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak PDF'leri orijinal sayfa boyutlarıyla nasıl oluşturacağınızı öğrenin. Adım adım kılavuzumuzu takip edin ve bu işlevselliği sorunsuz bir şekilde entegre edin.
type: docs
weight: 17
url: /tr/net/pdf-rendering-options/render-pdf-original-page-size/
---
## giriiş
.NET geliştirme alanında GroupDocs.Viewer, PDF'ler de dahil olmak üzere çeşitli belge formatlarını işlemek için güçlü bir araç olarak öne çıkıyor. Belge işlemede yaygın bir gereksinim, PDF'lerin orijinal sayfa boyutlarını koruyarak oluşturulmasıdır. Bu görevi sorunsuz bir şekilde gerçekleştirmek, GroupDocs.Viewer for .NET ve işlevlerinin kapsamlı bir şekilde anlaşılmasını gerektirir.
## Önkoşullar
GroupDocs.Viewer for .NET'i kullanarak PDF'leri orijinal sayfa boyutlarıyla oluşturmaya başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### 1. .NET için GroupDocs.Viewer'ı yükleyin
 Web sitesinden GroupDocs.Viewer kitaplığını indirerek başlayın. Kütüphaneyi sağlanan adresten edinebilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/). .NET projenize etkili bir şekilde entegre etmek için belgelerde sağlanan kurulum talimatlarını izleyin.
### 2. Geliştirme Ortamını Kurun
.NET geliştirme için ayarlanmış bir geliştirme ortamınız olduğundan emin olun. Buna, Visual Studio gibi uyumlu bir IDE'nin kurulu olması ve C# programlamanın temel düzeyde anlaşılması da dahildir.
### 3. Bir PDF Belgesi Alın
GroupDocs.Viewer ile oluşturmak için örnek bir PDF belgesine ihtiyacınız olacak. Test amacıyla herhangi bir PDF belgesini kullanabilirsiniz. Elinizde yoksa çeşitli çevrimiçi kaynaklardan örnek bir PDF indirebilirsiniz.

## Ad Alanlarını İçe Aktar
PDF'leri oluşturmaya devam etmeden önce gerekli ad alanlarını C# projenize aktarmanız önemlidir. Bu adım, GroupDocs.Viewer kitaplığından gerekli sınıflara ve yöntemlere erişmenizi sağlar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Artık önkoşulları yerine getirdiğinize ve gerekli ad alanlarını içe aktardığınıza göre, GroupDocs.Viewer for .NET'i kullanarak orijinal sayfa boyutlarına sahip PDF'leri oluşturma sürecini basit adımlara ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
 Oluşturulan sayfaların kaydedilmesini istediğiniz dizini belirttiğinizden emin olun. Yer değiştirmek`"Your Document Directory"` İstediğiniz dizinin yolu ile.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
İşlenen sayfa dosyalarını adlandırmak için formatı ayarlayın. Bu örnekte, sayfalar şu formatta dosya adlarıyla PNG görüntüleri olarak kaydedilecektir:`"page_1.png"`, `"page_2.png"`, ve benzeri.
## 3. Adım: PDF'yi Orijinal Sayfa Boyutuyla Oluşturun
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Bir örnek oluştur`Viewer` PDF dosyanızın yolunu içeren nesne. Daha sonra oluşturun`PngViewOptions` belirtilen sayfa dosyası yolu formatıyla. Ayarlamak`RenderOriginalPageSize` mülkiyet`true` oluşturma sırasında orijinal sayfa boyutlarını korumak için.
## Adım 4: Oluşturulan Belgenin Konumunu Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Başarılı işlemeyi belirten bir mesaj yazdırın ve oluşturulan sayfaların kaydedildiği dizini sağlayın.

## Çözüm
Bu eğitimde özetlenen adımları takip ettiğinizde, GroupDocs.Viewer for .NET'i kullanarak PDF'leri orijinal sayfa boyutlarıyla oluşturmak basit bir işlemdir. Gerekli ad alanlarını içe aktararak ve adım adım kılavuzu izleyerek bu işlevselliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### GroupDocs.Viewer, PDF'nin yanı sıra diğer belge formatlarını da görüntüleyebilir mi?
Evet, GroupDocs.Viewer, Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere çeşitli belge formatlarının görüntülenmesini destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ortamlarıyla uyumludur.
### İşlenen sayfaların çıktı biçimini özelleştirebilir miyim?
Evet, GroupDocs.Viewer tarafından sağlanan farklı görüntü formatlarını ayarlamak veya özel işleme seçeneklerini belirlemek gibi seçenekleri ayarlayarak çıktı formatını özelleştirebilirsiniz.
### GroupDocs.Viewer bulut tabanlı belge oluşturma desteği sunuyor mu?
Evet, GroupDocs.Viewer, bulut tabanlı belge işleme için API'ler sağlayarak belgeleri doğrudan bulut depolama sağlayıcılarından oluşturmanıza olanak tanır.
### GroupDocs.Viewer'ın ücretsiz deneme sürümü mevcut mu?
 Evet, sağlanan adresi ziyaret ederek GroupDocs.Viewer'ı ücretsiz deneme sürümüyle keşfedebilirsiniz.[bağlantı](https://releases.groupdocs.com/).