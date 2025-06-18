---
"description": "GroupDocs.Viewer for .NET kullanarak belgelere sorunsuz bir şekilde filigran eklemeyi öğrenin. Bu kolay takip edilebilir eğitimle belge güvenliğini ve markalamayı geliştirin."
"linktitle": "Belgeye Filigran Ekle"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Belgeye Filigran Ekle"
"url": "/tr/net/rendering-options/add-watermark/"
"weight": 10
---

# Belgeye Filigran Ekle

## giriiş
Günümüzün dijital çağında, çeşitli belge biçimlerini sorunsuz bir şekilde yönetmek ve görüntülemek birçok işletme ve birey için bir gerekliliktir. Neyse ki, .NET için GroupDocs.Viewer gibi araçlarla belgeleri yönetmek çocuk oyuncağı haline geliyor. Bu güçlü .NET kitaplığı, geliştiricilerin belge görüntüleme işlevselliğini uygulamalarına zahmetsizce entegre etmelerini sağlayarak kullanıcıların belgeleri oluşturan orijinal yazılıma ihtiyaç duymadan görüntülemelerine olanak tanır.
## Ön koşullar
GroupDocs.Viewer for .NET'i kullanarak belgelere filigran eklemeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Ortam Kurulumu: .NET Framework veya .NET Core yüklü bir geliştirme ortamı kurun.
2. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET kitaplığını şu adresten indirin ve yükleyin: [indirme sayfası](https://releases.groupdocs.com/viewer/net/).
3. Belge Dosyaları: DOCX, PDF veya diğerleri gibi çalışmak istediğiniz belge dosyalarını hazırlayın.
4. Temel C# Bilgisi: Kod örneklerini uygulamak için C# programlama diline aşinalık gereklidir.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET kullanarak belgelere filigran eklemeye başlamadan önce, C# kodunuza gerekli ad alanlarını içe aktardığınızdan emin olun. Bu adım, kütüphane tarafından sağlanan sınıflara ve yöntemlere sorunsuz bir şekilde erişmenizi sağlar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi, .NET için GroupDocs.Viewer kullanarak bir belgeye filigran ekleme sürecini inceleyelim. Filigranlama işlevselliğini uygulamanıza sorunsuz bir şekilde entegre etmek için şu adımları izleyin.
## Adım 1: Çıktı Dizinini Ayarla
```csharp
string outputDirectory = "Your Document Directory";
```
Filigran uygulandıktan sonra çıktı dosyalarının kaydedilmesini istediğiniz dizini belirtin.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
İşlenen sayfaların dosya yolları için biçimi ayarlayın. Bu örnekte, sayfa numaralarına sahip HTML dosyaları oluşturulacaktır.
## Adım 3: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kod bir sonraki adımda devam ediyor...
}
```
Viewer sınıfının bir örneğini oluşturun ve belge dosyasının yolunu parametre olarak geçirin. Bu örnekte, örnek bir DOCX dosyası kullanıyoruz.
## Adım 4: HTML Görünüm Seçeneklerini Yapılandırın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Belgeye eklemek istediğiniz filigran metni de dahil olmak üzere HTML görünüm seçeneklerini yapılandırın.
## Adım 5: Filigranlı Belgeyi Görüntüle
```csharp
viewer.View(options);
```
Viewer nesnesinin View metodunu çağırın ve yapılandırılmış seçenekleri iletin. Bu, belgeyi belirtilen filigranla birlikte işleyecektir.
## Adım 6: Çıktı Dizin Yolunu Görüntüle
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Kullanıcıya belgenin başarılı bir şekilde oluşturulduğunu bildirin ve çıktı dosyalarının kaydedildiği dizini belirtin.

## Çözüm
.NET için GroupDocs.Viewer, belgelere programatik olarak filigran eklemenin kullanışlı bir yolunu sunar. Bu eğitimde özetlenen adımları izleyerek, filigranlama işlevselliğini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, belge güvenliğini ve markalamayı geliştirebilirsiniz.
## SSS
### Filigranın görünümünü özelleştirebilir miyim?
Evet, filigranın metin, yazı tipi, renk, boyut ve konum gibi çeşitli özelliklerini özelleştirebilirsiniz.
### GroupDocs.Viewer uzak kaynaklardan belge görüntülemeyi destekliyor mu?
Evet, GroupDocs.Viewer yerel depolama alanından ve uzak URL'lerden belgelerin görüntülenmesini destekler.
### GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/).
### Bir belgenin birden fazla sayfasına filigran ekleyebilir miyim?
Kesinlikle, GroupDocs.Viewer bir belgenin tek tek sayfalarına veya tüm sayfalarına filigran eklemenize olanak tanır.
### Herhangi bir sorunla karşılaşırsam nasıl destek veya yardım alabilirim?
GroupDocs topluluk forumlarından yardım ve destek alabilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9).