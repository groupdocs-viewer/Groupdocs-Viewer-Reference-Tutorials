---
title: Render Özel Proje Zaman Aralığı (MS Project)
linktitle: Render Özel Proje Zaman Aralığı (MS Project)
second_title: GroupDocs.Viewer .NET API'si
description: Verimli belge görüntüleme için GroupDocs.Viewer for .NET'i uygulamalarınıza sorunsuz bir şekilde entegre edin. Çok yönlü işleme yetenekleriyle üretkenliği artırın.
type: docs
weight: 12
url: /tr/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---
## giriiş
Yazılım geliştirme alanında, çeşitli belge formatlarının verimli bir şekilde kullanılması ve işlenmesi çok önemlidir. İster belge görüntüleme ister değiştirme amaçlı olsun, doğru araçlara sahip olmak üretkenliği önemli ölçüde artırabilir ve süreçleri kolaylaştırabilir. GroupDocs.Viewer for .NET, geliştiricilere belge görüntüleme yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etme yeteneği sunan çok yönlü bir çözüm olarak öne çıkıyor.
## Önkoşullar
.NET için GroupDocs.Viewer entegrasyonuna dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. .NET Framework'e aşinalık
C# programlama dili ve Visual Studio IDE dahil olmak üzere .NET çerçevesine ilişkin temel bilgilere sahip olduğunuzdan emin olun.
### 2. .NET için GroupDocs.Viewer'ın kurulumu
 GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/). Kitaplığı geliştirme ortamınızda kurmak için sağlanan kurulum talimatlarını izleyin.
### 3. Geçerli Lisans veya Geçici Lisans
 Geçerli bir lisans edinin[GrupDoc'ları](https://purchase.groupdocs.com/buy) veya geçici lisans alın[Burada](https://purchase.groupdocs.com/temporary-license/) GroupDocs.Viewer for .NET'in tüm işlevlerini kullanmak için.
### 4. Örnek Belge
İşleme işlevselliğini test etmek için MS Project dosyası gibi örnek bir belgeyi hazır bulundurun.

## Ad Alanlarını İçe Aktar
.NET için GroupDocs.Viewer tarafından sağlanan işlevlere erişmek için gerekli ad alanlarını projenize ekleyin.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Belirli bir proje zaman aralığını bir MS Project dosyasından oluşturma örneğini birden çok adıma ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
İşlenen HTML sayfalarının kaydedileceği dizini belirtin.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
İşlenen her HTML sayfasının dosya yolu formatını ayarlayın.
## 3. Adım: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Örnek MS Project dosyasının yolunu ileterek Viewer sınıfının bir örneğini oluşturun.
## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Gömülü kaynakların formatını belirterek, oluşturma için HTML görünüm seçeneklerini yapılandırın.
## Adım 5: Proje Yönetimi Görünüm Bilgilerini Alın
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Projenin başlangıç ve bitiş tarihlerini belirlemek için proje yönetimi görünüm bilgilerini alın.
## Adım 6: Başlangıç ve Bitiş Tarihlerini Ayarlayın
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Oluşturulacak proje aralığının başlangıç ve bitiş tarihlerini ayarlayın.
## Adım 7: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
Belirtilen seçeneklerle oluşturma işlemini başlatın.
## Adım 8: Çıkış Dizinini Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Başarılı işleme hakkında kullanıcıyı bilgilendirin ve çıktının kaydedildiği dizini görüntüleyin.

## Çözüm
GroupDocs.Viewer for .NET'i projelerinize entegre etmek, belge görüntüleme görevlerini verimli bir şekilde yerine getirmenizi sağlayarak kullanıcı deneyimini ve üretkenliği artırır. Sağlanan adım adım kılavuzu takip ederek belge oluşturma işlevlerini .NET uygulamalarınıza sorunsuz bir şekilde dahil edebilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET tüm belge formatlarıyla uyumlu mu?
GroupDocs.Viewer for .NET, Microsoft Office, PDF, CAD ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### İşlenen belgelerin görünümünü özelleştirebilir miyim?
Evet, sayfa düzeni, filigran ekleme ve sayfa döndürme gibi oluşturma sürecinin çeşitli yönlerini özelleştirebilirsiniz.
### GroupDocs.Viewer for .NET web uygulamalarına uygun mu?
Kesinlikle, GroupDocs.Viewer for .NET, belge görüntüleme yetenekleri sağlamak üzere web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### GroupDocs.Viewer for .NET mobil platformlar için destek sunuyor mu?
Evet, GroupDocs.Viewer for .NET mobil platformları destekleyerek duyarlı belge görüntüleme özelliklerine sahip uygulamalar oluşturmanıza olanak tanır.
### GroupDocs.Viewer for .NET konusunda yardım isteyebileceğim bir topluluk forumu var mı?
 Evet, ziyaret edebilirsiniz[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) sorular sormak, fikirleri paylaşmak ve diğer kullanıcılar ve geliştiricilerle etkileşimde bulunmak için.