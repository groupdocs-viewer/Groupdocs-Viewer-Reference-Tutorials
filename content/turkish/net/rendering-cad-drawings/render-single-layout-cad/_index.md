---
"description": "GroupDocs.Viewer for .NET kullanarak CAD çizimlerinde tek bir düzenin nasıl oluşturulacağını öğrenin. .NET uygulamalarınıza sorunsuz entegrasyon için kolay adımlar."
"linktitle": "CAD Çizimlerinde Tek Düzeni Oluşturma"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD Çizimlerinde Tek Düzeni Oluşturma"
"url": "/tr/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# CAD Çizimlerinde Tek Düzeni Oluşturma

## giriiş
.NET geliştirme alanında, CAD çizimlerini işlemek ve görüntülemek yaygın bir gerekliliktir. .NET için GroupDocs.Viewer, .NET uygulamaları içinde CAD çizimlerini işlemek için kapsamlı bir çözüm sunarak bu görevi basitleştirir. Bu eğitimde, .NET için GroupDocs.Viewer kullanarak CAD çizimlerinde tek bir düzeni işlemeyi inceleyeceğiz.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- C# programlama dili ve .NET framework hakkında temel bilgi.
- Sisteminizde Visual Studio yüklü.
- GroupDocs.Viewer for .NET kütüphanesi indirildi ve tutorialsd projenizde. Buradan indirebilirsiniz [Burada](https://releases.groupdocs.com/viewer/net/).
- CAD dosya formatları ve yapıları hakkında bilgi sahibi olmak.

## Ad Alanlarını İçe Aktar
Öncelikle GroupDocs.Viewer işlevlerine erişmek için gerekli ad alanlarını C# kodunuza aktarın.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıktı Dizinini Tanımlayın
İşlenen çıktının kaydedilmesini istediğiniz dizini belirtin.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
Her oluşturulan sayfanın dosya yolu için formatı tanımlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: Görüntüleyici Nesnesini Örneklendirin
GroupDocs.Viewer tarafından sağlanan Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Adım 4: HTML Görünüm Seçeneklerini Yapılandırın
Gömülü kaynaklarla HTML çıktısını işlemek için seçenekleri yapılandırın.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Adım 5: CAD Düzeni Adını Belirleyin
İşlemek istediğiniz CAD düzeninin adını belirtin.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Adım 6: CAD Çizimini Oluşturun
Viewer nesnesinin View metodunu belirtilen seçeneklerle çağırın.
```csharp
viewer.View(options);
```
## Adım 7: Başarı Mesajını Göster
Kullanıcıyı kaynak belgenin başarılı bir şekilde oluşturulduğu konusunda bilgilendirin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Özellikle düzenlerle uğraşırken CAD çizimlerini işlemek zorlu bir görev olabilir. Ancak, .NET için GroupDocs.Viewer ile süreç sorunsuz ve verimli hale gelir. Bu eğitimde özetlenen adımları izleyerek, .NET uygulamalarınızdaki CAD çizimlerinde tek bir düzeni zahmetsizce işleyebilirsiniz.
## SSS
### GroupDocs.Viewer for .NET kullanarak birden fazla düzeni aynı anda oluşturabilir miyim?
Evet, GroupDocs.Viewer for .NET, CAD çizimlerinden birden fazla düzenin oluşturulmasını destekler.
### GroupDocs.Viewer farklı CAD dosya formatlarıyla uyumlu mudur?
Kesinlikle, GroupDocs.Viewer DWG, DXF, DGN ve daha fazlası dahil olmak üzere çok çeşitli CAD dosya formatlarını destekler.
### CAD çizimleri için render seçeneklerini özelleştirebilir miyim?
Evet, GroupDocs.Viewer gereksinimlerinize göre işleme ayarlarını özelleştirmek için kapsamlı seçenekler sunar.
### GroupDocs.Viewer for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer'ın özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz [Burada](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET için desteği nereden alabilirim?
Herhangi bir soru veya yardım için GroupDocs.Viewer forumunu ziyaret edebilirsiniz. [Burada](https://forum.groupdocs.com/c/viewer/9).