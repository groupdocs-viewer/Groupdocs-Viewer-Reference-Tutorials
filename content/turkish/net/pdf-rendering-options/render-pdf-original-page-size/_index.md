---
"description": "GroupDocs.Viewer for .NET kullanarak PDF'leri orijinal sayfa boyutlarıyla nasıl oluşturacağınızı öğrenin. Adım adım kılavuzumuzu izleyin ve bu işlevselliği sorunsuz bir şekilde entegre edin."
"linktitle": "PDF'yi Orijinal Sayfa Boyutuyla Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF'yi Orijinal Sayfa Boyutuyla Oluştur"
"url": "/tr/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# PDF'yi Orijinal Sayfa Boyutuyla Oluştur

## giriiş
.NET geliştirme alanında GroupDocs.Viewer, PDF'ler de dahil olmak üzere çeşitli belge biçimlerini işlemek için güçlü bir araç olarak öne çıkar. Belge işlemede yaygın bir gereklilik, PDF'leri orijinal sayfa boyutlarını koruyarak işlemektir. Bu görevi sorunsuz bir şekilde başarmak, .NET için GroupDocs.Viewer ve işlevleri hakkında kapsamlı bir anlayış gerektirir.

![GroupDocs.Viewer .NET ile PDF'yi Orijinal Sayfa Boyutuyla Oluşturun](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Ön koşullar
GroupDocs.Viewer for .NET kullanarak PDF'leri orijinal sayfa boyutlarıyla işlemeye başlamadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:
### 1. .NET için GroupDocs.Viewer'ı yükleyin
GroupDocs.Viewer kütüphanesini web sitesinden indirerek başlayın. Kütüphaneyi sağlanan [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).NET projenize etkili bir şekilde entegre etmek için dokümantasyonda verilen kurulum talimatlarını izleyin.
### 2. Geliştirme Ortamını Kurun
.NET geliştirme için bir geliştirme ortamı kurduğunuzdan emin olun. Bu, Visual Studio gibi uyumlu bir IDE'nin kurulu olması ve C# programlamaya dair temel bir anlayışa sahip olmayı içerir.
### 3. Bir PDF Belgesi Edinin
GroupDocs.Viewer ile işlemek için bir örnek PDF belgesine ihtiyacınız olacak. Test amaçlı herhangi bir PDF belgesini kullanabilirsiniz. Eğer yoksa, çeşitli çevrimiçi kaynaklardan bir örnek PDF indirebilirsiniz.

## Ad Alanlarını İçe Aktar
PDF'leri işlemeye başlamadan önce, gerekli ad alanlarını C# projenize içe aktarmak önemlidir. Bu adım, GroupDocs.Viewer kitaplığından gerekli sınıflara ve yöntemlere erişmenizi sağlar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Artık ön koşullar yerinde ve gerekli ad alanları içe aktarılmış durumda, .NET için GroupDocs.Viewer'ı kullanarak PDF'leri orijinal sayfa boyutlarıyla işleme sürecini basit adımlara bölelim:
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen sayfaların kaydedilmesini istediğiniz dizini belirttiğinizden emin olun. Değiştir `"Your Document Directory"` İstediğiniz dizinin yolunu yazın.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
İşlenen sayfa dosyalarını adlandırmak için biçimi ayarlayın. Bu örnekte, sayfalar dosya adları biçiminde PNG görüntüleri olarak kaydedilecektir `"page_1.png"`, `"page_2.png"`, ve benzeri.
## Adım 3: PDF'yi Orijinal Sayfa Boyutuyla Oluşturun
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Bir örnek oluştur `Viewer` PDF dosyanızın yolunu içeren nesne. Ardından, oluşturun `PngViewOptions` belirtilen sayfa dosya yolu biçimiyle. Ayarla `RenderOriginalPageSize` mülk `true` İşleme sırasında orijinal sayfa boyutlarını korumak için.
## Adım 4: İşlenen Belge Konumunu Görüntüle
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Başarılı bir şekilde oluşturulduğunu belirten bir mesaj yazdırın ve oluşturulan sayfaların kaydedildiği dizini belirtin.

## Çözüm
Bu eğitimde özetlenen adımları takip ettiğinizde, .NET için GroupDocs.Viewer kullanarak PDF'leri orijinal sayfa boyutlarıyla işlemek basit bir işlemdir. Gerekli ad alanlarını içe aktararak ve adım adım kılavuzu izleyerek, bu işlevselliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS
### GroupDocs.Viewer PDF dışında başka belge formatlarını da işleyebilir mi?
Evet, GroupDocs.Viewer Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere çeşitli belge formatlarının işlenmesini destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mudur?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ortamlarıyla uyumludur.
### Oluşturulan sayfaların çıktı formatını özelleştirebilir miyim?
Evet, GroupDocs.Viewer tarafından sağlanan seçenekleri ayarlayarak (örneğin farklı görüntü biçimleri ayarlamak veya özel işleme seçenekleri belirtmek) çıktı biçimini özelleştirebilirsiniz.
### GroupDocs.Viewer bulut tabanlı belge oluşturma desteği sunuyor mu?
Evet, GroupDocs.Viewer bulut tabanlı belge oluşturma için API'ler sağlar ve belgeleri doğrudan bulut depolama sağlayıcılarından oluşturmanıza olanak tanır.
### GroupDocs.Viewer için ücretsiz deneme sürümü mevcut mu?
Evet, sağlanan sayfayı ziyaret ederek GroupDocs.Viewer'ı ücretsiz deneme sürümüyle keşfedebilirsiniz. [bağlantı](https://releases.groupdocs.com/).