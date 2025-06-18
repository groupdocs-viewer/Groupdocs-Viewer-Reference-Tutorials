---
"description": "GroupDocs.Viewer for .NET'te kaynak yükleme zaman aşımlarını nasıl verimli bir şekilde yapılandıracağınızı öğrenin. Hassasiyet ve kararlılıkla belge oluşturmada ustalaşın."
"linktitle": "Kaynak Yükleme Zaman Aşımını Ayarla (Gelişmiş)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Kaynak Yükleme Zaman Aşımını Ayarla (Gelişmiş)"
"url": "/tr/net/advanced-loading/set-resource-loading-timeout/"
"weight": 13
---

# Kaynak Yükleme Zaman Aşımını Ayarla (Gelişmiş)

## giriiş
.NET geliştirme alanında, GroupDocs.Viewer belgeleri ve görüntüleri hassasiyet ve verimlilikle işlemek için güçlü bir araç seti sağlar. Yeteneklerinden yararlanmak, kaynak yükleme zaman aşımını ayarlama dahil olmak üzere karmaşıklıklarını anlamayı gerektirir. Bu eğitimde, .NET için GroupDocs.Viewer'da kaynak yükleme zaman aşımını yapılandırma sürecini inceleyeceğiz.

![.NET için GroupDocs.Viewer'da Kaynak Yükleme Zaman Aşımını (Gelişmiş) Ayarlama](/viewer/advanced-loading/set-resource-loading-timeout-img.png)

## Ön koşullar
Bu eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. .NET Geliştirmenin Temel Bilgileri: C# programlama ve .NET framework temellerine aşinalık esastır.
2. GroupDocs.Viewer for .NET'in Kurulumu: GroupDocs.Viewer for .NET kitaplığını şu adresten indirin ve kurun: [indirme sayfası](https://releases.groupdocs.com/viewer/net/).
3. Entegre Geliştirme Ortamı (IDE): Sisteminizde Visual Studio gibi bir IDE yüklü olsun.

## Ad Alanlarını İçe Aktar
Kodlama sürecine dalmadan önce gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıktı Dizinini Tanımlayın
Öncelikle render edilmiş dokümanların kaydedileceği dizini tanımlayalım:
```csharp
string outputDirectory = "Your Document Directory";
```
Yer değiştirmek `"Your Document Directory"` Oluşturulan belgeleri kaydetmek istediğiniz yolu belirtin.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
Bireysel sayfaların dosya yollarının biçimini tanımlayın:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bu format şu şekilde dosya adları üretecektir: `page_1.html`, `page_2.html`, vb. belirtilen çıktı dizininde.
## Adım 3: Yükleme Seçeneklerini Yapılandırın
Kaynak yükleme zaman aşımı dahil olmak üzere yükleme seçeneklerini yapılandırın:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Bu örnekte kaynak yüklemesi için 5 saniyelik bir zaman aşımı süresi ayarlanmıştır.
## Adım 4: Görüntüleyici Nesnesini Başlatın
Başlat `Viewer` işlenecek belge ve tanımlanmış yükleme seçenekleriyle nesne:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
Yer değiştirmek `TestFiles.WITH_EXTERNAL_IMAGE_DOC` İşlemek istediğiniz belgenin yolunu belirtin.
## Adım 5: HTML Görünüm Seçeneklerini Yapılandırın
Gömülü kaynaklar için HTML görünüm seçeneklerini yapılandırın:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Bu yapılandırma, resimler gibi gömülü kaynakların işlenen HTML'e dahil edilmesini sağlar.
## Adım 6: Belgeyi Oluşturun
Yapılandırılan seçenekleri kullanarak belgeyi işleyin:
```csharp
viewer.View(options);
```
Bu adım, işleme sürecini başlatır.
## Adım 7: Çıktı Dizinini Görüntüle
Başarılı işlemeyi ve çıktı dizininin konumunu belirten bir mesaj görüntüle:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET'te kaynak yükleme zaman aşımında ustalaşmak, sorunsuz belge işleme süreçlerini sağlamak için çok önemlidir. Bu öğreticiyi takip ederek, zaman aşımını etkili bir şekilde yapılandırma konusunda içgörüler elde ettiniz ve .NET geliştirmedeki yeterliliğinizi artırdınız.
## SSS
### Kaynak yükleme zaman aşımlarını ayarlamanın önemi nedir?
Kaynak yükleme zaman aşımlarının ayarlanması, işleme süreçlerinin süresiz olarak askıda kalmamasını sağlayarak uygulama kararlılığını artırır.
### Kaynak yükleme zaman aşımları belge türlerine göre özelleştirilebilir mi?
Evet, kaynak yükleme zaman aşımları, işlenen belgelerin karmaşıklığına ve boyutuna göre ayarlanabilir.
### Daha kısa zaman aşımı süreleri ayarlamanın performans üzerinde herhangi bir etkisi var mı?
Daha kısa zaman aşımları, kaynakların belirtilen süre içerisinde yüklenememesi durumunda karmaşık belgelerin eksik oluşturulmasına yol açabilir.
### GroupDocs.Viewer çeşitli belge formatlarını görüntülemek için uygun mudur?
Evet, GroupDocs.Viewer PDF, DOCX, XLSX ve daha fazlası dahil olmak üzere çok çeşitli belge formatlarının işlenmesini destekler.
### Kaynak yükleme zaman aşımları devre dışı bırakılabilir mi?
Tavsiye edilmemekle birlikte, kaynak yükleme zaman aşımları belirli gereksinimlere bağlı olarak yüksek bir değere ayarlanabilir veya tamamen devre dışı bırakılabilir.