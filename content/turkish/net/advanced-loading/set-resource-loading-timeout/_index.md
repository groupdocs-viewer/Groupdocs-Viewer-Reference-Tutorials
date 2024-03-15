---
title: Kaynak Yükleme Zaman Aşımını Ayarlama (Gelişmiş)
linktitle: Kaynak Yükleme Zaman Aşımını Ayarlama (Gelişmiş)
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'te kaynak yükleme zaman aşımlarını verimli bir şekilde nasıl yapılandıracağınızı öğrenin. Hassas ve kararlı bir şekilde belge oluşturmada ustalaşın.
type: docs
weight: 13
url: /tr/net/advanced-loading/set-resource-loading-timeout/
---
## giriiş
.NET geliştirme alanında GroupDocs.Viewer, belgeleri ve görüntüleri hassas ve verimli bir şekilde işlemek için güçlü bir araç seti sağlar. Yeteneklerinden yararlanmak, kaynak yükleme zaman aşımlarını ayarlamak da dahil olmak üzere karmaşıklıklarını anlamayı gerektirir. Bu öğreticide, GroupDocs.Viewer for .NET'te kaynak yükleme zaman aşımlarını yapılandırma sürecini ayrıntılı olarak ele alacağız.
## Önkoşullar
Bu eğitime başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. .NET Geliştirmeye İlişkin Temel Bilgi: C# programlama ve .NET framework temellerine aşinalık çok önemlidir.
2.  GroupDocs.Viewer for .NET kurulumu: GroupDocs.Viewer for .NET kitaplığını indirip yükleyin.[indirme sayfası](https://releases.groupdocs.com/viewer/net/).
3. Tümleşik Geliştirme Ortamı (IDE): Sisteminizde Visual Studio gibi bir IDE yüklü olsun.

## Ad Alanlarını İçe Aktar
Kodlama sürecine dalmadan önce gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıkış Dizinini Tanımlayın
Öncelikle, oluşturulan belgelerin kaydedileceği dizini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"`İşlenen belgeleri kaydetmek istediğiniz yolla.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Bireysel sayfaların dosya yolları için formatı tanımlayın:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Bu format aşağıdaki gibi dosya adları üretecektir:`page_1.html`, `page_2.html`, vb., belirtilen çıktı dizini içinde.
## 3. Adım: Yükleme Seçeneklerini Yapılandırın
Kaynak yükleme zaman aşımı da dahil olmak üzere yükleme seçeneklerini yapılandırın:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Bu örnekte kaynak yükleme için 5 saniyelik bir zaman aşımı ayarlanmıştır.
## Adım 4: Görüntüleyici Nesnesini Başlatın
 Başlat`Viewer` işlenecek belgeyi ve tanımlanmış yükleme seçeneklerini içeren nesne:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Yer değiştirmek`TestFiles.WITH_EXTERNAL_IMAGE_DOC` oluşturmak istediğiniz belgenin yolu ile birlikte.
## 5. Adım: HTML Görünüm Seçeneklerini Yapılandırma
Gömülü kaynaklar için HTML görünüm seçeneklerini yapılandırın:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Bu yapılandırma, görüntüler gibi gömülü kaynakların, oluşturulan HTML'ye dahil edilmesini sağlar.
## Adım 6: Belgeyi Oluşturun
Yapılandırılmış seçenekleri kullanarak belgeyi oluşturun:
```csharp
viewer.View(options);
```
Bu adım render işlemini başlatır.
## Adım 7: Çıkış Dizinini Görüntüleyin
Başarılı işlemeyi ve çıktı dizininin konumunu belirten bir mesaj görüntüleyin:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET'te kaynak yükleme zaman aşımlarına hakim olmak, belge işleme süreçlerinin sorunsuz olmasını sağlamak için çok önemlidir. Bu öğreticiyi takip ederek, zaman aşımlarını etkili bir şekilde yapılandırmaya ilişkin bilgiler edinerek .NET geliştirme konusundaki uzmanlığınızı artırdınız.
## SSS'ler
### Kaynak yükleme zaman aşımlarını ayarlamanın önemi nedir?
Kaynak yükleme zaman aşımlarının ayarlanması, oluşturma işlemlerinin süresiz olarak askıda kalmamasını sağlayarak uygulama kararlılığını artırır.
### Kaynak yükleme zaman aşımları belge türlerine göre özelleştirilebilir mi?
Evet, kaynak yükleme zaman aşımları, oluşturulan belgelerin karmaşıklığına ve boyutuna göre ayarlanabilir.
### Daha kısa zaman aşımları ayarlamanın herhangi bir performans etkisi var mı?
Daha kısa zaman aşımları, kaynakların belirtilen süre içinde yüklenememesi durumunda karmaşık belgelerin eksik oluşturulmasına yol açabilir.
### GroupDocs.Viewer çeşitli belge formatlarını işlemeye uygun mu?
Evet, GroupDocs.Viewer PDF, DOCX, XLSX ve daha fazlasını içeren çok çeşitli belge formatlarının görüntülenmesini destekler.
### Kaynak yükleme zaman aşımları devre dışı bırakılabilir mi?
Tavsiye edilmese de kaynak yükleme zaman aşımları, belirli gereksinimlere bağlı olarak yüksek bir değere ayarlanabilir veya tamamen devre dışı bırakılabilir.