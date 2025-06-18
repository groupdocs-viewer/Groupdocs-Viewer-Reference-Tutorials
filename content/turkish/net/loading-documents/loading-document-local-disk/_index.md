---
"description": "Groupdocs.Viewer for .NET kullanarak yerel diskinizdeki belgeleri sorunsuz bir şekilde nasıl oluşturacağınızı öğrenin. .NET uygulamalarınızı verimli belgelerle geliştirin."
"linktitle": "Yerel Diskten Belgeleri Yükle"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Yerel Diskten Belgeleri Yükle"
"url": "/tr/net/loading-documents/loading-document-local-disk/"
"weight": 10
---

# Yerel Diskten Belgeleri Yükle

## giriiş
Günümüzün dijital çağında, çeşitli uygulamalar için verimli belge oluşturma olmazsa olmazdır. Groupdocs.Viewer for .NET, belgeleri doğrudan yerel diskinizden oluşturmak için güçlü bir çözüm sunar. Bu eğitimde, Groupdocs.Viewer for .NET kullanarak yerel diskinizden belge yükleme sürecinde size rehberlik edeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz, belge oluşturmayı .NET uygulamalarınıza sorunsuz bir şekilde entegre etmenize yardımcı olacaktır.

![GroupDocs.Viewer .NET ile Yerel Diskten Belgeleri Yükleyin](/viewer/loading-documents/load-documents-from-local-disk.png)

## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. Groupdocs.Viewer for .NET: En son sürümü şu adresten indirin ve yükleyin: [Burada](https://releases.groupdocs.com/viewer/net/).
2. .NET Geliştirme Ortamı: Sisteminizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun.
3. Yerel Belgeler: Oluşturmak istediğiniz belgeleri yerel olarak diskinizde saklayın.

## Ad Alanlarını İçe Aktar
Öncelikle .NET için Groupdocs.Viewer'ın işlevlerine erişmek için gerekli ad alanlarını içe aktaralım.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Yerel Diskten Belgeleri Yükle
Öncelikle işlenmiş HTML sayfalarının kaydedileceği çıktı dizinini ayarlayarak başlayalım.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 2: Görüntüleyiciyi Başlatın ve Belgeleri İşleyin
Viewer nesnesini belgenin yoluyla başlatın ve HTML görünüm seçeneklerini kullanarak işleyin.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Adım 3: Çıktıyı Görüntüle
İşleme tamamlandıktan sonra, kaynak belgenin başarıyla işlendiğini ve çıktı dosyalarının konumunu belirten bir mesaj görüntülenir.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Tebrikler! Groupdocs.Viewer for .NET kullanarak yerel diskinizden belgeleri nasıl yükleyeceğinizi başarıyla öğrendiniz. Bu güçlü araç, .NET uygulamalarınızda belge oluşturma için bir olasılıklar dünyasının kapılarını açar.
## SSS
### Groupdocs.Viewer for .NET kullanarak farklı formatlardaki belgeleri işleyebilir miyim?
Evet, Groupdocs.Viewer for .NET DOCX, PDF, XLSX, PPTX ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Groupdocs.Viewer for .NET tüm .NET framework'leriyle uyumlu mudur?
Groupdocs.Viewer for .NET, .NET Core, .NET Framework ve .NET Standard dahil olmak üzere çoğu .NET framework'üyle uyumludur.
### Belgelerim için oluşturma seçeneklerini özelleştirebilir miyim?
Kesinlikle! Groupdocs.Viewer for .NET, işleme sürecini özel gereksinimlerinize göre uyarlamanıza olanak tanıyan kapsamlı özelleştirme seçenekleri sunar.
### Groupdocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.groupdocs.com/).
### Groupdocs.Viewer for .NET için destek veya ek kaynakları nerede bulabilirim?
Destek ve ek kaynaklar için .NET için Groupdocs.Viewer'ı ziyaret edin [forum](https://forum.groupdocs.com/c/viewer/9).