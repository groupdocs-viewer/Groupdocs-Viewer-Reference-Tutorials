---
"description": "Groupdocs.Viewer for .NET kullanarak belgelerden seçili sayfaların nasıl işleneceğini öğrenin. Kod örneklerinin de dahil olduğu adım adım eğitim."
"linktitle": "Seçili Sayfaları Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Seçili Sayfaları Oluştur"
"url": "/tr/net/rendering-options/render-selected-pages/"
"weight": 17
---

# Seçili Sayfaları Oluştur

## giriiş

Bu eğitimde, .NET için Groupdocs.Viewer'ı bir belgeden seçili sayfaları işlemek için nasıl kullanacağımızı inceleyeceğiz. İster deneyimli bir geliştirici olun, ister yeni başlıyor olun, bu adım adım kılavuz sizi bu süreçte kolaylıkla yönlendirecektir.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

### 1. Kurulum

Geliştirme ortamınızda Groupdocs.Viewer for .NET'in yüklü olduğundan emin olun. Değilse, şuradan indirebilirsiniz: [İndirme bağlantısı](https://releases.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktarma

C# kod dosyanızda, gerekli sınıflara ve yöntemlere erişmek için gerekli ad alanlarını içe aktarın. Bunu kullanarak yapabilirsiniz `using` direktif:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi verilen örnek kodu birden fazla adıma bölelim:

## Adım 1: Çıktı Dizinini Ayarla

İşlenen sayfaların kaydedilmesini istediğiniz dizini tanımlayın. Değiştir `"Your Document Directory"` İstenilen dizin yolu ile.

```csharp
string outputDirectory = "Your Document Directory";
```

## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın

İşlenen sayfaların dosya yolları için biçimi belirtin. Bu, her sayfayı çıktı dizininde bir HTML dosyası olarak kaydetmek için kullanılacaktır.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Adım 3: Görüntüleyici Nesnesini Örneklendirin

Görüntülemek istediğiniz belgenin yolunu argüman olarak geçirerek Viewer sınıfının bir örneğini oluşturun.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Adım 4: HTML Görünüm Seçeneklerini Yapılandırın

İşleme için HTML görünüm seçeneklerini ayarlayın. Bu örnekte, HTML çıktısına kaynakları yerleştirmek için seçenekleri yapılandırıyoruz.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Adım 5: Seçili Sayfaları Oluştur

İşlemek istediğiniz sayfa numaralarını belirtin. Bu durumda, 1 ila 3 arasındaki sayfaları işliyoruz. Ardından, Viewer nesnesinde View metodunu çağırın ve seçenekleri ve sayfa numaralarını argüman olarak geçirin.

```csharp
viewer.View(options, 1, 3);
```

## Adım 6: Çıktı Sonucu

Son olarak, belgenin başarıyla oluşturulduğunu ve çıktı dosyalarının kaydedildiği konumu belirten bir mesaj görüntüleyin.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

Tebrikler! Groupdocs.Viewer for .NET kullanarak bir belgeden seçili sayfaları nasıl işleyeceğiniz konusunda başarılı bir şekilde bilgi edindiniz. Bu bilgiyle artık belge işleme yeteneklerini .NET uygulamalarınıza kolaylıkla entegre edebilirsiniz.

## SSS

### S: PDF veya resim gibi farklı türdeki belgelerden sayfalar oluşturabilir miyim?

C: Evet, Groupdocs.Viewer for .NET, PDF'ler, Microsoft Office belgeleri ve resim dosyaları dahil olmak üzere çeşitli belge biçimlerinden sayfaların işlenmesini destekler.

### S: Satın almadan önce test etmek için deneme sürümü mevcut mu?

A: Evet, Groupdocs.Viewer for .NET'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz: [web sitesi](https://releases.groupdocs.com/).

### S: HTML dışındaki çıktı formatını özelleştirebilir miyim?

C: Kesinlikle, Groupdocs.Viewer for .NET, HTML'e ek olarak sayfaları resim, PDF ve daha fazlası olarak işleme seçenekleri sunar.

### S: Test amaçlı geçici lisansları nasıl alabilirim?

A: Geçici lisanslar, [geçici lisans sayfası](https://purchase.groupdocs.com/temporary-license/) Groupdocs web sitesinde.

### S: Karşılaştığım herhangi bir sorunla ilgili olarak nereden yardım alabilirim veya nereye başvurabilirim?

A: Ziyaret edebilirsiniz [Groupdocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) Topluluktan ve geliştiricilerden destek ve rehberlik için.