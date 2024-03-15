---
title: CAD Çizimlerinde Tek Düzen Oluşturma
linktitle: CAD Çizimlerinde Tek Düzen Oluşturma
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak CAD çizimlerinde tek mizanpajın nasıl oluşturulacağını öğrenin. .NET uygulamalarınızla kusursuz entegrasyon için kolay adımlar.
type: docs
weight: 14
url: /tr/net/rendering-cad-drawings/render-single-layout-cad/
---
## giriiş
.NET geliştirme alanında, CAD çizimlerinin işlenmesi ve görüntülenmesi ortak bir gereksinimdir. GroupDocs.Viewer for .NET, .NET uygulamalarında CAD çizimlerinin işlenmesi için kapsamlı bir çözüm sağlayarak bu görevi basitleştirir. Bu eğitimde, GroupDocs.Viewer for .NET'i kullanarak CAD çizimlerinde tek bir düzenin görüntülenmesini ele alacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- C# programlama dili ve .NET çerçevesi hakkında temel bilgi.
- Sisteminizde Visual Studio yüklü.
-  GroupDocs.Viewer for .NET kitaplığı indirildi ve projenizde başvuruldu. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
- CAD dosya formatları ve yapılarına aşinalık.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer işlevlerine erişmek için öncelikle gerekli ad alanlarını C# kodunuza aktarın.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıkış Dizinini Tanımlayın
İşlenen çıktının kaydedilmesini istediğiniz dizini belirtin.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
İşlenen her sayfanın dosya yolu için formatı tanımlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntüleyici Nesnesini Örneklendirin
GroupDocs.Viewer tarafından sağlanan Viewer sınıfının bir örneğini oluşturun.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
Gömülü kaynaklarla HTML çıktısı oluşturmaya yönelik seçenekleri yapılandırın.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Adım 5: CAD Düzeni Adını Belirleyin
Oluşturmak istediğiniz CAD düzeninin adını belirtin.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Adım 6: CAD Çizimini Oluşturun
Belirtilen seçeneklerle Viewer nesnesinin View yöntemini çağırın.
```csharp
viewer.View(options);
```
## Adım 7: Başarı Mesajını Görüntüleyin
Kullanıcıyı kaynak belgenin başarıyla oluşturulduğu konusunda bilgilendirin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
CAD çizimlerini oluşturmak, özellikle mizanpajlarla uğraşırken göz korkutucu bir iş olabilir. Ancak GroupDocs.Viewer for .NET ile süreç sorunsuz ve verimli hale gelir. Bu eğitimde özetlenen adımları takip ederek, .NET uygulamalarınızdaki CAD çizimlerinde tek bir düzeni zahmetsizce oluşturabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET'i kullanarak aynı anda birden fazla düzeni görüntüleyebilir miyim?
Evet, GroupDocs.Viewer for .NET, CAD çizimlerinden birden fazla mizanpajın oluşturulmasını destekler.
### GroupDocs.Viewer farklı CAD dosya formatlarıyla uyumlu mu?
Kesinlikle GroupDocs.Viewer, DWG, DXF, DGN ve daha fazlası dahil olmak üzere çok çeşitli CAD dosya formatlarını destekler.
### CAD çizimleri için işleme seçeneklerini özelleştirebilir miyim?
Evet, GroupDocs.Viewer, oluşturma ayarlarını gereksinimlerinize göre özelleştirmeniz için kapsamlı seçenekler sunar.
### GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer'ın özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz[Burada](https://releases.groupdocs.com/).
### .NET için GroupDocs.Viewer desteğini nereden alabilirim?
 Sorularınız veya yardım için GroupDocs.Viewer forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).