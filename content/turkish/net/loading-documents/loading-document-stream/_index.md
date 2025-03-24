---
title: Belgeleri Akıştan Yükle
linktitle: Belgeleri Akıştan Yükle
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak akışlardan belgeleri sorunsuz bir şekilde nasıl yükleyeceğinizi öğrenin. .NET uygulamalarınızı güçlü belge görüntüleme yetenekleriyle geliştirin.
weight: 12
url: /tr/net/loading-documents/loading-document-stream/
---

# Belgeleri Akıştan Yükle

## giriiş
.NET geliştirme alanında, belgeleri verimli bir şekilde yönetmek ve görüntülemek çok önemlidir. Gelişmiş araçların ve kitaplıkların ortaya çıkmasıyla, bir zamanlar göz korkutucu görünen görevler artık basitleştirildi. Bu araçlar arasında GroupDocs.Viewer for .NET, çeşitli belge formatlarını sorunsuz bir şekilde yönetmeye yönelik çok yönlü bir çözüm olarak öne çıkıyor. Bu kapsamlı kılavuzda, bir akıştan belge yüklemek için GroupDocs.Viewer for .NET'i kullanmanın inceliklerini ele alıyoruz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim sizi GroupDocs.Viewer'ın gücünden etkili bir şekilde yararlanmanız için gerekli bilgilerle donatacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. C# ve .NET Çerçevesine İlişkin Temel Anlayış: C# programlama diline ve .NET çerçevesine aşinalık, tartışılan kavramların anlaşılmasına yardımcı olacaktır.
   
2.  GroupDocs.Viewer for .NET kurulumu: GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[İnternet sitesi](https://releases.groupdocs.com/viewer/net/).
3. IDE: Kodlama ve test için Visual Studio gibi bir Tümleşik Geliştirme Ortamı'nın (IDE) kurulu olmasını sağlayın.
4. Belge Akışı: Yükleme için bir belge akışı hazırlayın. Bu bir dosya akışı veya başka herhangi bir uyumlu akış kaynağı olabilir.

## Ad Alanlarını İçe Aktar
Bir akıştan belge yüklemek için kodu uygulamadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen belgenin kaydedileceği dizin yolunu ayarlayın.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Her sayfanın dosya yolu için formatı tanımlayın. Burada "{0}" yerine sayfa numarası kullanılacaktır.
## 3. Adım: Belge Akışını Alın
```csharp
Stream stream = GetFileStream();
```
Belge akışını istediğiniz kaynaktan alın. Bu bir dosya akışı, bellek akışı veya başka herhangi bir uyumlu akış olabilir.
## Adım 4: Görüntüleyiciyi Kullanarak Belgeyi Yükleyin
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Belge akışıyla Viewer sınıfının yeni bir örneğini başlatın. Ardından HTML görünüm seçeneklerini yapılandırın ve belgeyi oluşturun.
## Adım 5: Çıkış Dizinini Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Kullanıcıyı belgenin başarıyla oluşturulduğu konusunda bilgilendirin ve çıktının kaydedildiği konumu sağlayın.

## Çözüm
Sonuç olarak, GroupDocs.Viewer for .NET, akışlardaki belgeleri zahmetsizce yüklemek ve görüntülemek için güçlü bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre ederek kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS
### .NET için GroupDocs.Viewer farklı belge formatlarını işleyebilir mi?
Evet, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer for .NET hem web hem de masaüstü uygulamaları için uygun mu?
Kesinlikle! GroupDocs.Viewer, .NET kullanılarak geliştirilen hem web hem de masaüstü uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### GroupDocs.Viewer belge oluşturma için özelleştirme seçenekleri sunuyor mu?
Evet, filigran ekleme, sayfa döndürme ve yakınlaştırma düzeyi gibi belge oluşturmanın çeşitli yönlerini gereksinimlerinize göre özelleştirebilirsiniz.
### GroupDocs.Viewer for .NET'i ticari projelerde kullanabilir miyim?
Evet, GroupDocs.Viewer ticari projelere uygun lisanslama seçenekleri sunar. Lisansları yetkiliden satın alabilirsiniz.[İnternet sitesi](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET için teknik destek mevcut mu?
 Evet, tarafından sağlanan özel destek forumundan teknik yardım ve rehberlik alabilirsiniz.[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).