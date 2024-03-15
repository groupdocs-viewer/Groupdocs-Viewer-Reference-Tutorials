---
title: Arşiv Klasörünü Oluştur
linktitle: Arşiv Klasörünü Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: Verimli belge oluşturma ve görüntüleme yetenekleri için GroupDocs.Viewer for .NET'i .NET uygulamalarınıza sorunsuz bir şekilde entegre edin.
type: docs
weight: 11
url: /tr/net/rendering-archive-files/render-archive-folder/
---
## giriiş
Günümüzün dijital çağında belgelere sorunsuz bir şekilde erişmek ve görüntülemek, hem işletmeler hem de bireyler için çok önemlidir. Neyse ki, teknolojinin ilerlemesiyle birlikte geliştiricilerin elinde artık belge görüntüleme yeteneklerini zahmetsizce uygulamalarına entegre edebilecek güçlü araçlar var. Böyle bir araç, geliştiricilerin .NET uygulamalarında çeşitli belge formatlarını oluşturmasına olanak tanıyan çok yönlü bir kitaplık olan GroupDocs.Viewer for .NET'tir.
## Önkoşullar
GroupDocs.Viewer for .NET'in projenize entegrasyonuna dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### C# Programlama bilgisi
GroupDocs.Viewer for .NET'i etkili bir şekilde kullanmak için C# programlama dilinin temel düzeyde anlaşılması gerekir. Sınıflar, yöntemler ve değişkenler gibi kavramlara aşina olun.
### .NET için GroupDocs.Viewer'ın kurulumu
.NET için GroupDocs.Viewer'ı indirip yüklediğinizden emin olun. Kütüphaneyi sağlanan adresten edinebilirsiniz.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
### Geliştirme Ortamının Kurulumu
Visual Studio veya .NET geliştirme için tercih edilen herhangi bir IDE ile yapılandırılmış bir geliştirme ortamına sahip olun.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET'i projenize dahil etmeden önce, işlevselliğine sorunsuz bir şekilde erişmek için gerekli ad alanlarını içe aktarın:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi GroupDocs.Viewer for .NET'i kullanarak bir arşiv klasörü oluşturma işlemini yönetilebilir adımlara ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
İşlenen belgelerin kaydedilmesini istediğiniz dizini belirtin.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Bireysel sayfa dosyalarını adlandırma biçimini ayarlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntüleyici Nesnesini Örneklendirin
Arşiv dosyasının yolunu parametre olarak ileterek Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP_WITH_FOLDERS))
```
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
Gömülü kaynakların formatı ve arşiv içindeki hedef klasör dahil olmak üzere HTML görünüm seçeneklerini ayarlayın.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.ArchiveOptions.Folder = "ThirdFolderWithItems";
```
## Adım 5: Arşiv Klasörünü Oluşturun
Yapılandırılmış HTML görünüm seçeneklerini ileterek Viewer nesnesinin View yöntemini çağırın.
```csharp
viewer.View(options);
```
## Adım 6: Başarı Mesajını Görüntüleyin
Kullanıcıya belge oluşturma işleminin tamamlandığını bildirin ve çıktı dizinini sağlayın.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET'i .NET uygulamalarınıza dahil etmek, kusursuz belge işleme için bir dünya olasılıklar dünyasının kapılarını açar. Belirtilen adımları izleyerek belge görüntüleme yeteneklerini zahmetsizce entegre edebilir, uygulamalarınızın işlevselliğini artırabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET tüm belge formatlarıyla uyumlu mu?
GroupDocs.Viewer for .NET, PDF, Microsoft Office belgeleri, resimler ve daha fazlasını içeren çok çeşitli belge formatlarını destekler. Kapsamlı bir liste için belgelere bakın.
### İşlenen belgelerin görünümünü özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET, işlenmiş belgelerin görünümünü özelleştirmek için filigran ekleme, sayfa döndürme ve yakınlaştırma gibi çeşitli seçenekler sunar.
### GroupDocs.Viewer for .NET, bulut depolama hizmetleri için destek sağlıyor mu?
Evet, sorunsuz belge alımı ve işleme için GroupDocs.Viewer for .NET'i Dropbox, Google Drive ve Amazon S3 gibi popüler bulut depolama hizmetleriyle entegre edebilirsiniz.
### Değerlendirme amaçlı deneme sürümü mevcut mu?
Evet, satın alma kararını vermeden önce özelliklerini ve yeteneklerini keşfetmek için GroupDocs.Viewer for .NET'in ücretsiz denemesinden yararlanabilirsiniz.
### GroupDocs.Viewer for .NET ile ilgili herhangi bir sorunla karşılaşırsam veya sorularım olursa nereden yardım isteyebilirim?
 Ziyaret edebilirsiniz[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) topluluktan ve GroupDocs ekibinden destek istemek.