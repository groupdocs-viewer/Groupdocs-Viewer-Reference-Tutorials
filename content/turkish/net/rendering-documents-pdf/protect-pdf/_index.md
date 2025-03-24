---
title: Oluşturulan PDF'yi Şifreyle Koruyun
linktitle: Oluşturulan PDF'yi Şifreyle Koruyun
second_title: GroupDocs.Viewer .NET API'si
description: Oluşturulan PDF'lerinizi Groupdocs.Viewer for .NET'i kullanarak kolayca parolalarla koruyun. Belgelerinizi güvende ve gizli tutun.
weight: 12
url: /tr/net/rendering-documents-pdf/protect-pdf/
---
## giriiş
Bu öğreticide, oluşturulmuş bir PDF'yi parolayla korumak için Groupdocs.Viewer for .NET'i nasıl kullanacağınızı öğreneceksiniz. Güvenlik önlemleri ekleyerek PDF belgelerinize erişimi kontrol edebilir, gizliliği ve bütünlüğü sağlayabilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Groupdocs.Viewer for .NET Kitaplığı: Kitaplığı şu adresten indirip yükleyin:[İnternet sitesi](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun.

## Ad Alanlarını İçe Aktar
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Adım 1: Çıktı Dizinini ve Dosya Yolunu Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Adım 2: Görüntüleyici Nesnesini Başlatın ve Güvenlik Seçeneklerini Ayarlayın
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## 3. Adım: PDF Görünüm Seçeneklerini Ayarlayın
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Adım 4: Belgeyi Güvenlik Seçenekleriyle Oluşturun
```csharp
    viewer.View(options);
}
```
## Adım 5: Oluşturulan Belgeyi Kontrol Edin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bu adımları izleyerek, oluşturulmuş bir PDF'yi Groupdocs.Viewer for .NET'i kullanarak bir parolayla koruyabilirsiniz. Bu, belgelerinizin güvende kalmasını ve yalnızca yetkili kullanıcılar tarafından erişilebilir olmasını sağlar.

## Çözüm
PDF belgelerinin güvenliğini sağlamak, gizliliği ve bütünlüğü korumak için çok önemlidir. Groupdocs.Viewer for .NET ile işlenmiş PDF'leri parolalarla kolayca koruyabilir, hassas bilgilere erişimi kontrol edebilirsiniz.

## SSS'ler
### PDF'leri farklı izin düzeyleriyle koruyabilir miyim?
Evet, PDF'leri parolalarla korurken görüntüleme, yazdırma, kopyalama ve daha fazlası için farklı izinler belirleyebilirsiniz.
### Groupdocs.Viewer çeşitli dosya formatlarıyla uyumlu mu?
Kesinlikle! Groupdocs.Viewer, DOCX, XLSX, PPTX, PDF ve daha fazlasını içeren çok çeşitli dosya formatlarının görüntülenmesini destekler.
### Groupdocs.Viewer'ı mevcut .NET uygulamama entegre edebilir miyim?
Kesinlikle! Groupdocs.Viewer, .NET uygulamalarına sorunsuz entegrasyon için API'ler sağlayarak güçlü belge görüntüleme yetenekleri sunar.
### Groupdocs.Viewer bulut depolama hizmetleri için destek sunuyor mu?
Evet, Groupdocs.Viewer, Dropbox, Google Drive ve Amazon S3 gibi popüler bulut depolama hizmetleriyle entegrasyonu destekleyerek bulutta depolanan belgeleri oluşturmanıza olanak tanır.
### Groupdocs.Viewer'ın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne şuradan erişerek Groupdocs.Viewer'ı kullanmaya başlayabilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).