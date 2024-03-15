---
title: Seçilen Sayfaları Oluştur
linktitle: Seçilen Sayfaları Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: Groupdocs.Viewer for .NET'i kullanarak belgelerden seçilen sayfaları nasıl oluşturacağınızı öğrenin. Kod örnekleri içeren adım adım eğitim.
type: docs
weight: 17
url: /tr/net/rendering-options/render-selected-pages/
---
## giriiş

Bu eğitimde, bir belgeden seçilen sayfaları oluşturmak için Groupdocs.Viewer for .NET'in nasıl kullanılacağını inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz süreç boyunca size kolaylıkla yol gösterecektir.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

### 1. Kurulum

 Geliştirme ortamınızda Groupdocs.Viewer for .NET'in kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).

## Ad Alanlarını İçe Aktarma

Gerekli sınıflara ve yöntemlere erişmek için C# kod dosyanızda gerekli ad alanlarını içe aktarın. Bunu kullanarak yapabilirsiniz`using` direktif:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi sağlanan örnek kodu birden çok adıma ayıralım:

## Adım 1: Çıkış Dizinini Ayarlayın

 Oluşturulan sayfaların kaydedilmesini istediğiniz dizini tanımlayın. Yer değiştirmek`"Your Document Directory"` İstenilen dizin yolu ile.

```csharp
string outputDirectory = "Your Document Directory";
```

## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın

İşlenen sayfaların dosya yolları için formatı belirtin. Bu, her sayfayı çıktı dizinine bir HTML dosyası olarak kaydetmek için kullanılacaktır.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3. Adım: Görüntüleyici Nesnesini Örneklendirin

Oluşturmak istediğiniz belgenin yolunu bağımsız değişken olarak ileterek Viewer sınıfının bir örneğini oluşturun.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma

Oluşturma için HTML görünüm seçeneklerini ayarlayın. Bu örnekte, kaynakları HTML çıktısına gömmek için seçenekleri yapılandırıyoruz.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Adım 5: Seçilen Sayfaları Oluşturun

Oluşturmak istediğiniz sayfa numaralarını belirtin. Bu durumda, 1'den 3'e kadar olan sayfaları oluşturuyoruz. Ardından, seçenekleri ve sayfa numaralarını argüman olarak ileterek Viewer nesnesinde View yöntemini çağırın.

```csharp
viewer.View(options, 1, 3);
```

## Adım 6: Çıktı Sonucu

Son olarak, belgenin başarıyla oluşturulduğunu ve çıktı dosyalarının kaydedildiği konumu belirten bir mesaj görüntüleyin.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

Tebrikler! Groupdocs.Viewer for .NET'i kullanarak bir belgeden seçilen sayfaları nasıl oluşturacağınızı başarıyla öğrendiniz. Bu bilgiyle artık belge işleme yeteneklerini .NET uygulamalarınıza kolaylıkla entegre edebilirsiniz.

## SSS'ler

### S: PDF veya resim gibi farklı türdeki belgelerden sayfalar oluşturabilir miyim?

C: Evet, Groupdocs.Viewer for .NET, PDF'ler, Microsoft Office belgeleri ve görüntü dosyaları da dahil olmak üzere çeşitli belge biçimlerinden sayfaların oluşturulmasını destekler.

### S: Satın almadan önce test edilebilecek bir deneme sürümü var mı?

 C: Evet, Groupdocs.Viewer for .NET'in ücretsiz deneme sürümüne şuradan erişebilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).

### S: HTML dışındaki çıktı biçimini özelleştirebilir miyim?

C: Kesinlikle, Groupdocs.Viewer for .NET, HTML'nin yanı sıra sayfaları resim, PDF ve daha fazlası olarak işlemek için seçenekler sunar.

### S: Test amaçlı geçici lisansları nasıl alabilirim?

C: Geçici lisanslar şu adresten alınabilir:[geçici lisans sayfası](https://purchase.groupdocs.com/temporary-license/) Groupdocs web sitesinde.

### S: Karşılaştığım sorunlarla ilgili nereden yardım alabilirim veya yardım alabilirim?

 C: Ziyaret edebilirsiniz[Groupdocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) topluluktan ve geliştiricilerden destek ve rehberlik için.