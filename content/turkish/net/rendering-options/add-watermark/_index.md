---
title: Belgeye Filigran Ekle
linktitle: Belgeye Filigran Ekle
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak belgelere sorunsuz bir şekilde filigran eklemeyi öğrenin. Takip edilmesi kolay bu eğitimle belge güvenliğini ve markalamayı geliştirin.
weight: 10
url: /tr/net/rendering-options/add-watermark/
---

# Belgeye Filigran Ekle

## giriiş
Günümüzün dijital çağında, çeşitli belge formatlarını sorunsuz bir şekilde yönetmek ve görüntülemek, birçok işletme ve benzer bireyler için bir zorunluluktur. Neyse ki, GroupDocs.Viewer for .NET gibi araçlarla belgeleri yönetmek çocuk oyuncağı haline geliyor. Bu güçlü .NET kitaplığı, geliştiricilerin belge görüntüleme işlevini uygulamalarına zahmetsizce entegre etmelerine olanak tanıyarak, kullanıcıların belgeleri, onları oluşturan orijinal yazılıma ihtiyaç duymadan görüntülemelerine olanak tanır.
## Önkoşullar
Belgelere filigran eklemek için GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Ortam Kurulumu: .NET Framework veya .NET Core yüklü olarak ayarlanmış bir geliştirme ortamına sahip olun.
2.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET kitaplığını şuradan indirip yükleyin:[indirme sayfası](https://releases.groupdocs.com/viewer/net/).
3. Belge Dosyaları: Çalışmak istediğiniz DOCX, PDF veya diğerleri gibi belge dosyalarını hazırlayın.
4. Temel C# Bilgisi: Kod örneklerini uygulamak için C# programlama diline aşinalık gereklidir.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET kullanarak belgelere filigran eklemeye başlamadan önce, gerekli ad alanlarını C# kodunuza aktardığınızdan emin olun. Bu adım, kütüphanenin sağladığı sınıflara ve yöntemlere sorunsuz bir şekilde erişmenizi sağlar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi GroupDocs.Viewer for .NET'i kullanarak bir belgeye filigran ekleme sürecini inceleyelim. Filigranlama işlevini uygulamanıza sorunsuz bir şekilde entegre etmek için bu adımları izleyin.
## Adım 1: Çıkış Dizinini Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
```
Filigranı uyguladıktan sonra çıktı dosyalarının kaydedilmesini istediğiniz dizini belirtin.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
İşlenen sayfaların dosya yollarının formatını ayarlayın. Bu örnekte sayfa numaralarını içeren HTML dosyaları oluşturulacaktır.
## 3. Adım: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kod bir sonraki adımda devam ediyor...
}
```
Belge dosyasının yolunu parametre olarak ileterek Viewer sınıfının bir örneğini oluşturun. Bu örnekte örnek bir DOCX dosyası kullanıyoruz.
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Belgeye eklemek istediğiniz filigran metni de dahil olmak üzere HTML görünüm seçeneklerini yapılandırın.
## Adım 5: Belgeyi Filigranla Görüntüleyin
```csharp
viewer.View(options);
```
Yapılandırılmış seçenekleri ileterek Viewer nesnesinin View yöntemini çağırın. Bu, belgeyi belirtilen filigranla oluşturacaktır.
## Adım 6: Çıkış Dizini Yolunu Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Kullanıcıyı belgenin başarıyla oluşturulduğu konusunda bilgilendirin ve çıktı dosyalarının kaydedildiği dizini belirtin.

## Çözüm
GroupDocs.Viewer for .NET, belgelere program aracılığıyla filigran eklemenin kolay bir yolunu sağlar. Bu eğitimde özetlenen adımları izleyerek filigran işlevini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir, belge güvenliğini ve markalamayı geliştirebilirsiniz.
## SSS'ler
### Filigranın görünümünü özelleştirebilir miyim?
Evet, filigranın metin, yazı tipi, renk, boyut ve konum gibi çeşitli özelliklerini özelleştirebilirsiniz.
### GroupDocs.Viewer uzak kaynaklardan belge görüntülemeyi destekliyor mu?
Evet, GroupDocs.Viewer, uzak URL'lerin yanı sıra yerel depolama alanındaki belgelerin görüntülenmesini de destekler.
### GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.groupdocs.com/).
### Bir belgenin birden fazla sayfasına filigran ekleyebilir miyim?
GroupDocs.Viewer kesinlikle bir belgenin tek tek sayfalarına veya tüm sayfalarına filigran eklenmesine olanak tanır.
### Herhangi bir sorunla karşılaşırsam nasıl destek veya yardım alabilirim?
 GroupDocs topluluk forumlarından yardım ve destek alabilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).