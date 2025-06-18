---
"description": "GroupDocs.Viewer for .NET kullanarak CAD çizimleri için çıktı görüntü boyutunun nasıl ayarlanacağını öğrenin. Görünürlüğü ve kullanılabilirliği zahmetsizce artırın."
"linktitle": "CAD Çizimleri için Çıktı Görüntü Boyutunu Ayarla"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD Çizimleri için Çıktı Görüntü Boyutunu Ayarla"
"url": "/tr/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# CAD Çizimleri için Çıktı Görüntü Boyutunu Ayarla

## giriiş
CAD çizimleri genellikle en iyi görüntüleme ve sunum için belirli ayarlamalar gerektirir. .NET için GroupDocs.Viewer, CAD çizim çıktısını yönetmek ve özelleştirmek için güçlü bir araç seti sağlar. Bu eğitimde, CAD çizimleri için çıktı görüntü boyutunu adım adım ayarlama sürecinde size rehberlik edeceğiz.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirin ve yükleyin: [Burada](https://releases.groupdocs.com/viewer/net/).
2. Belge Dizini: Belgenizin bulunduğu dizini hazırlayın.
3. Temel Anlayış: .NET programlamanın temel kavramlarını öğrenin.

## Ad Alanlarını İçe Aktar
Öncelikle GroupDocs.Viewer işlevlerine erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıktı Dizinini Ayarla
CAD çizimlerinin çıktı görüntülerini depolamak istediğiniz dizini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
Sayfa dosya yolları için biçimi ayarlayın. Bu biçim, tek tek sayfaları HTML dosyaları olarak adlandırmak ve kaydetmek için kullanılacaktır:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: Görüntü Boyutunu Ayarlayın
Görüntüleyici nesnesi için bir blok kullanarak, uygun seçenekleri belirleyerek CAD çizimleri için görüntü boyutunu ayarlayın:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Adım 4: Çıktı Dizinini Görüntüle
Belgeyi işledikten sonra, işlemenin başarılı olduğunu belirten bir mesaj görüntüleyin ve çıktı dizininin konumunu belirtin:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
CAD çizimleri için çıktı görüntü boyutunu ayarlamak, görünürlüklerini ve kullanılabilirliklerini artırmak için çok önemlidir. GroupDocs.Viewer for .NET ile bu süreç kolaylaştırılır ve verimli hale gelir ve çıktıyı özel gereksinimlerinize göre özelleştirmenize olanak tanır.
## SSS
### CAD çizimlerinin yanı sıra diğer belge türleri için de çıktı görüntü boyutunu ayarlayabilir miyim?
Evet, GroupDocs.Viewer for .NET çeşitli belge türlerini destekler ve çoğu belge biçimi için çıktı görüntü boyutunu ayarlayabilirsiniz.
### GroupDocs.Viewer for .NET, .NET framework'ün farklı sürümleriyle uyumlu mudur?
Evet, GroupDocs.Viewer for .NET, .NET framework'ünün birden fazla sürümüyle uyumludur ve bu sayede farklı ortamlarda esneklik ve kullanılabilirlik sağlanır.
### GroupDocs.Viewer for .NET için herhangi bir lisanslama seçeneği mevcut mu?
Evet, ihtiyaçlarınıza uygun geçici lisanslar ve ticari lisanslar dahil olmak üzere farklı lisanslama seçeneklerini keşfedebilirsiniz.
### Oluşturulan belgelerin çıktı formatını özelleştirebilir miyim?
Kesinlikle, GroupDocs.Viewer for .NET çeşitli özelleştirme seçenekleri sunarak çıktı formatını kendi projenize göre düzenlemenize olanak tanır.
### GroupDocs.Viewer for .NET ile ilgili ek destek veya yardımı nerede bulabilirim?
GroupDocs.Viewer forumunu ziyaret edebilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9) Destek almak, soru sormak ve toplulukla etkileşim kurmak için.