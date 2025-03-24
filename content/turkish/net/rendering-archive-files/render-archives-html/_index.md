---
title: Arşivleri Tek veya Çoklu HTML Sayfalarına Oluşturma
linktitle: Arşivleri Tek veya Çoklu HTML Sayfalarına Oluşturma
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak arşivleri HTML sayfalarına nasıl aktaracağınızı öğrenin. Belge görüntüleme yeteneklerini .NET uygulamalarınıza zahmetsizce entegre edin.
weight: 12
url: /tr/net/rendering-archive-files/render-archives-html/
---

# Arşivleri Tek veya Çoklu HTML Sayfalarına Oluşturma

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin belge görüntüleme yeteneklerini .NET uygulamalarına zahmetsizce entegre etmelerine olanak tanıyan güçlü bir belge işleme kitaplığıdır. Arşivleri ister tek ister birden fazla HTML sayfasına dönüştürmeniz gerekiyorsa, bu eğitim size süreç boyunca adım adım rehberlik edecektir.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  GroupDocs.Viewer for .NET: Projenizde kitaplığın yüklü olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için ayarlanmış bir çalışma geliştirme ortamına sahip olun.
3. Doküman Dizini: Dokümanlarınızın saklanacağı bir dizin hazırlayın.
4. Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.

## Ad Alanlarını İçe Aktar
C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

GroupDocs.Viewer for .NET'i kullanarak arşivleri tek veya birden fazla HTML sayfasına dönüştürmek için şu adımları izleyin:
## Adım 1: Çıkış Dizinini Ayarlayın
Oluşturulan HTML sayfalarının kaydedilmesini istediğiniz dizini tanımlayın:
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Dosya Yolu Formatını Tanımlayın
HTML sayfaları için dosya yolu formatını belirtin. Tek sayfa oluşturma için:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Çok sayfalı görüntüleme için:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## 3. Adım: Tek Sayfa HTML'ye Dönüştür
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## 4. Adım: Birden Çok Sayfa HTML'sine Oluşturun
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Sayfa başına öğe ayarlama
    viewer.View(options);
}
```
## Adım 5: Çıktıyı Kontrol Edin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
GroupDocs.Viewer for .NET'i kullanarak arşivleri HTML sayfalarına dönüştürmek basit bir işlemdir. Bu öğreticide özetlenen adımları izleyerek belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### Arşivlerin yanı sıra diğer belge formatlarını da görüntüleyebilir miyim?
Evet, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer hem masaüstü hem de web uygulamaları için uygun mudur?
Kesinlikle GroupDocs.Viewer hem masaüstü hem de web uygulamalarında sorunsuz bir şekilde kullanılabilir.
### GroupDocs.Viewer, görüntüleyici arayüzü için özelleştirme seçenekleri sunuyor mu?
Evet, izleyici arayüzünü ihtiyaçlarınıza göre özelleştirebilirsiniz.
### GroupDocs.Viewer ile belgeleri eşzamansız olarak oluşturabilir miyim?
Evet, GroupDocs.Viewer, gelişmiş performans için eşzamansız oluşturma yetenekleri sağlar.
### GroupDocs.Viewer belge açıklamalarını destekliyor mu?
Evet, GroupDocs.Viewer kullanıcıların belge açıklamalarını verimli bir şekilde görüntülemesine ve yönetmesine olanak tanır.