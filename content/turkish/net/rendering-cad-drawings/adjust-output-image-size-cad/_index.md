---
title: CAD Çizimleri için Çıktı Görüntü Boyutunu Ayarlama
linktitle: CAD Çizimleri için Çıktı Görüntü Boyutunu Ayarlama
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak CAD çizimleri için çıktı görüntü boyutunu nasıl ayarlayacağınızı öğrenin. Görünürlüğü ve kullanılabilirliği zahmetsizce geliştirin.
weight: 15
url: /tr/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# CAD Çizimleri için Çıktı Görüntü Boyutunu Ayarlama

## giriiş
CAD çizimleri genellikle optimum görüntüleme ve sunum için özel ayarlamalar gerektirir. GroupDocs.Viewer for .NET, CAD çizimleri çıktısını yönetmek ve özelleştirmek için güçlü bir araç seti sağlar. Bu eğitimde, CAD çizimleri için çıktı görüntü boyutunu ayarlama sürecinde size adım adım rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.groupdocs.com/viewer/net/).
2. Belge Dizini: Belgenizin bulunduğu dizini hazırlayın.
3. Temel Anlama: .NET programlamanın temel kavramlarına aşina olun.

## Ad Alanlarını İçe Aktar
Öncelikle GroupDocs.Viewer işlevlerine erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıkış Dizinini Ayarlayın
CAD çizimlerinin çıktı görüntülerini saklamak istediğiniz dizini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Sayfa dosyası yollarının biçimini ayarlayın. Bu format, tek tek sayfaları adlandırmak ve HTML dosyaları olarak kaydetmek için kullanılacaktır:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntü Boyutunu Ayarlayın
Viewer nesnesine yönelik bir kullanım bloğunun içinde, uygun seçenekleri ayarlayarak CAD çizimlerinin görüntü boyutunu ayarlayın:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Adım 4: Çıkış Dizinini Görüntüleyin
Belgeyi oluşturduktan sonra, oluşturmanın başarılı olduğunu belirten bir mesaj görüntüleyin ve çıktı dizininin konumunu belirtin:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
CAD çizimleri için çıktı görüntü boyutunu ayarlamak, görünürlüklerini ve kullanılabilirliklerini artırmak açısından çok önemlidir. GroupDocs.Viewer for .NET ile bu süreç kolaylaştırılmış ve verimli hale gelir ve çıktıyı özel gereksinimlerinize göre özelleştirmenize olanak tanır.
## SSS'ler
### Çıktı görüntü boyutunu CAD çizimlerinin yanı sıra diğer belge türleri için de ayarlayabilir miyim?
Evet, GroupDocs.Viewer for .NET çeşitli belge türlerini destekler ve çoğu belge biçimi için çıktı görüntüsü boyutunu ayarlayabilirsiniz.
### GroupDocs.Viewer for .NET, .NET çerçevesinin farklı sürümleriyle uyumlu mu?
Evet, GroupDocs.Viewer for .NET, .NET çerçevesinin birden çok sürümüyle uyumludur ve farklı ortamlarda esneklik ve kullanılabilirlik sağlar.
### GroupDocs.Viewer for .NET için herhangi bir lisanslama seçeneği mevcut mu?
Evet, ihtiyaçlarınıza uyacak şekilde geçici lisanslar ve ticari lisanslar dahil farklı lisanslama seçeneklerini keşfedebilirsiniz.
### İşlenen belgelerin çıktı biçimini özelleştirebilir miyim?
Kesinlikle GroupDocs.Viewer for .NET, çıktı formatını tercihlerinize göre uyarlamanıza olanak tanıyan çeşitli özelleştirme seçenekleri sunar.
### GroupDocs.Viewer for .NET ile ilgili ek desteği veya yardımı nerede bulabilirim?
 GroupDocs.Viewer forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9) destek almak, sorular sormak ve toplulukla etkileşime geçmek için.