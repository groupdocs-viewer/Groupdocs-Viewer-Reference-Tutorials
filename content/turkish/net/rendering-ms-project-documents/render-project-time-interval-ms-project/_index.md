---
"description": "Verimli belge görüntüleme için GroupDocs.Viewer for .NET'i uygulamalarınıza sorunsuz bir şekilde entegre edin. Çok yönlü işleme yetenekleriyle üretkenliği artırın."
"linktitle": "Belirli Proje Zaman Aralığı Oluşturma (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Belirli Proje Zaman Aralığı Oluşturma (MS Project)"
"url": "/tr/net/rendering-ms-project-documents/render-project-time-interval-ms-project/"
"weight": 12
type: docs
---
# Belirli Proje Zaman Aralığı Oluşturma (MS Project)

## giriiş
Yazılım geliştirme alanında, çeşitli belge biçimlerinin verimli bir şekilde işlenmesi ve işlenmesi çok önemlidir. İster belge görüntüleme ister düzenleme için olsun, doğru araçlara sahip olmak üretkenliği önemli ölçüde artırabilir ve süreçleri kolaylaştırabilir. .NET için GroupDocs.Viewer, geliştiricilere belge görüntüleme yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etme olanağı sunan çok yönlü bir çözüm olarak öne çıkıyor.
## Ön koşullar
GroupDocs.Viewer for .NET entegrasyonuna başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
### 1. .NET Framework'e aşinalık
C# programlama dili ve Visual Studio IDE dahil olmak üzere .NET framework hakkında temel bir anlayışa sahip olduğunuzdan emin olun.
### 2. .NET için GroupDocs.Viewer Kurulumu
GroupDocs.Viewer for .NET'i şuradan indirin ve yükleyin: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/)Geliştirme ortamınızda kütüphaneyi kurmak için verilen kurulum talimatlarını izleyin.
### 3. Geçerli Lisans veya Geçici Lisans
Geçerli bir lisans edinin [GrupDokümanları](https://purchase.groupdocs.com/buy) veya geçici bir lisans alın [Burada](https://purchase.groupdocs.com/temporary-license/) .NET için GroupDocs.Viewer'ın tüm işlevlerinden yararlanmak için.
### 4. Örnek Belge
İşleme işlevselliğini test etmek için MS Project dosyası gibi bir örnek belgeyi hazır bulundurun.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET tarafından sağlanan işlevlere erişmek için gerekli ad alanlarını projenize dahil edin.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Belirli bir proje zaman aralığının bir MS Project dosyasından işlenmesi örneğini birden fazla adıma bölelim:
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
Oluşturulan HTML sayfalarının kaydedileceği dizini belirtin.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Her oluşturulan HTML sayfasının dosya yolu için biçimi ayarlayın.
## Adım 3: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Viewer sınıfının bir örneğini oluşturun ve örnek MS Project dosyasının yolunu iletin.
## Adım 4: HTML Görünüm Seçeneklerini Yapılandırın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Gömülü kaynaklar için biçimi belirterek, oluşturma için HTML görünüm seçeneklerini yapılandırın.
## Adım 5: Proje Yönetimi Görünümü Bilgilerini Alın
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Projenin başlangıç ve bitiş tarihlerini belirlemek için proje yönetimi görünümü bilgilerini alın.
## Adım 6: Başlangıç ve Bitiş Tarihlerini Ayarlayın
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
İşlenecek proje aralığının başlangıç ve bitiş tarihlerini ayarlayın.
## Adım 7: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
Belirtilen seçeneklerle işleme sürecini başlatın.
## Adım 8: Çıktı Dizinini Görüntüle
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Kullanıcıya başarılı işleme hakkında bildirimde bulunun ve çıktının kaydedildiği dizini görüntüleyin.

## Çözüm
GroupDocs.Viewer for .NET'i projelerinize entegre etmek, belge görüntüleme görevlerini etkili bir şekilde halletmenizi, kullanıcı deneyimini ve üretkenliği artırmanızı sağlar. Sağlanan adım adım kılavuzu izleyerek, belge işleme işlevlerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS
### GroupDocs.Viewer for .NET tüm belge formatlarıyla uyumlu mudur?
GroupDocs.Viewer for .NET, Microsoft Office, PDF, CAD ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### Oluşturulan belgelerin görünümünü özelleştirebilir miyim?
Evet, sayfa düzeni, filigranlama ve sayfa döndürme gibi oluşturma sürecinin çeşitli yönlerini özelleştirebilirsiniz.
### GroupDocs.Viewer for .NET web uygulamaları için uygun mudur?
Kesinlikle, GroupDocs.Viewer for .NET, belge görüntüleme yetenekleri sağlamak için web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### GroupDocs.Viewer for .NET mobil platformları destekliyor mu?
Evet, GroupDocs.Viewer for .NET mobil platformları destekler ve duyarlı belge görüntüleme özelliklerine sahip uygulamalar oluşturmanıza olanak tanır.
### GroupDocs.Viewer for .NET konusunda yardım alabileceğim bir topluluk forumu var mı?
Evet, ziyaret edebilirsiniz [GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9) Soru sormak, fikir paylaşmak ve diğer kullanıcılar ve geliştiricilerle etkileşim kurmak.