---
title: Yazı Tiplerini İşlenen HTML'den Hariç Tut
linktitle: Yazı Tiplerini İşlenen HTML'den Hariç Tut
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak yazı tiplerini oluşturulan HTML'den nasıl hariç tutacağınızı öğrenin. Sorunsuz belge görüntüleme için bu adım adım kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/rendering-documents-html/exclude-fonts-html/
---
## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin harici bağımlılıklara ihtiyaç duymadan .NET uygulamalarında 50'den fazla belge formatını görüntülemesine olanak tanıyan güçlü bir belge işleme kitaplığıdır. Bu öğreticide GroupDocs.Viewer'ın belirli bir özelliğine odaklanacağız: yazı tiplerini oluşturulan HTML çıktısından hariç tutmak. 
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. C# ve .NET geliştirmenin temel anlayışı.
2.  .NET için GroupDocs.Viewer yüklü. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
3. C# geliştirme için Visual Studio veya başka herhangi bir IDE.

## Ad Alanlarını İçe Aktar
C# kodunuzda gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıkış Dizinini Tanımlayın
İşlenen HTML dosyalarının kaydedilmesini istediğiniz dizini ayarlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
İşlenen belgenin tek tek sayfalarının dosya yolları için formatı belirtin.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntüleyici Nesnesini Başlatın
Görüntüleyici nesnesini oluşturmak istediğiniz belgeyle örnekleyin.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Kodunuz buraya gelecek
}
```
## 4. Adım: HTML Görünüm Seçeneklerini Ayarlayın
Hariç tutulacak gömülü kaynakların ve yazı tiplerinin formatı da dahil olmak üzere, HTML oluşturma seçeneklerini tanımlayın.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Adım 5: Belgeyi Oluşturun
Belgeyi oluşturmak için HTML görünümü seçeneklerini Viewer nesnesine iletin.
```csharp
viewer.View(options);
```
## Adım 6: Çıktı Oluşturulan Belgenin Konumu
Kullanıcıyı, oluşturulan HTML dosyalarının kaydedildiği konum hakkında bilgilendirin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu öğreticide, yazı tiplerini oluşturulan HTML çıktısından hariç tutmak için GroupDocs.Viewer for .NET'in nasıl kullanılacağını öğrendik. Yukarıda özetlenen adımları izleyerek, oluşturma sürecini özel gereksinimlerinizi karşılayacak şekilde özelleştirebilir ve uygulamalarınızda belgelerin en iyi şekilde görüntülenmesini sağlayabilirsiniz.
## SSS'ler
### Birden çok yazı tipini oluşturulan HTML'den hariç tutabilir miyim?
 Evet, birden fazla yazı tipi adı ekleyebilirsiniz.`FontsToExclude` HTML görünüm seçeneklerindeki liste.
### GroupDocs.Viewer tüm .NET çerçeveleriyle uyumlu mu?
Evet, GroupDocs.Viewer .NET Framework 4.6.1 ve üstünü destekler.
### Belgeleri uzak depolama konumlarından oluşturabilir miyim?
Evet, GroupDocs.Viewer, yerel depolamanın yanı sıra uzak depolama konumları ve akışlarından da belge oluşturulmasını destekler.
### GroupDocs.Viewer, HTML çıktısı için duyarlı tasarımı destekliyor mu?
Evet, HTML görünüm seçeneklerini uygun şekilde ayarlayarak duyarlı oluşturmayı etkinleştirebilirsiniz.
### GroupDocs.Viewer için teknik destek mevcut mu?
 Evet, yardım isteyebilir ve konuyla ilgili tartışmalara katılabilirsiniz.[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9).