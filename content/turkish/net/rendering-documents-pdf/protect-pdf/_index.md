---
"description": "Groupdocs.Viewer for .NET kullanarak işlenmiş PDF'lerinizi parolalarla kolayca koruyun. Belgelerinizi güvenli ve gizli tutun."
"linktitle": "İşlenmiş PDF'yi Parola ile Koru"
"second_title": "GroupDocs.Viewer .NET API"
"title": "İşlenmiş PDF'yi Parola ile Koru"
"url": "/tr/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
---

# İşlenmiş PDF'yi Parola ile Koru

## giriiş
Bu eğitimde, işlenmiş bir PDF'yi parola ile korumak için Groupdocs.Viewer for .NET'i nasıl kullanacağınızı öğreneceksiniz. Güvenlik önlemleri ekleyerek, PDF belgelerinize erişimi kontrol edebilir, gizliliği ve bütünlüğü sağlayabilirsiniz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. .NET Kütüphanesi için Groupdocs.Viewer: Kütüphaneyi şu adresten indirin ve yükleyin: [web sitesi](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET geliştirme için çalışan bir geliştirme ortamı kurduğunuzdan emin olun.

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
## Adım 3: PDF Görünüm Seçeneklerini Ayarlayın
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
## Adım 5: İşlenen Belgeyi Kontrol Edin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bu adımları izleyerek, .NET için Groupdocs.Viewer kullanarak işlenmiş bir PDF'yi bir parola ile koruyabilirsiniz. Bu, belgelerinizin güvenli kalmasını ve yalnızca yetkili kullanıcılar tarafından erişilebilir olmasını sağlar.

## Çözüm
PDF belgelerinin güvenliğini sağlamak, gizliliği ve bütünlüğü korumak için önemlidir. Groupdocs.Viewer for .NET ile işlenmiş PDF'leri parolalarla kolayca koruyabilir, hassas bilgilere erişimi kontrol edebilirsiniz.

## SSS
### PDF'leri farklı izin seviyeleriyle koruyabilir miyim?
Evet, PDF'leri parolalarla korurken görüntüleme, yazdırma, kopyalama ve daha fazlası için farklı izinler belirleyebilirsiniz.
### Groupdocs.Viewer çeşitli dosya formatlarıyla uyumlu mudur?
Kesinlikle! Groupdocs.Viewer, DOCX, XLSX, PPTX, PDF ve daha fazlası dahil olmak üzere çok çeşitli dosya formatlarının işlenmesini destekler.
### Groupdocs.Viewer'ı mevcut .NET uygulamama entegre edebilir miyim?
Elbette! Groupdocs.Viewer, .NET uygulamalarına kusursuz entegrasyon için API'ler sağlar ve güçlü belge görüntüleme yetenekleri sunar.
### Groupdocs.Viewer bulut depolama servislerini destekliyor mu?
Evet, Groupdocs.Viewer, Dropbox, Google Drive ve Amazon S3 gibi popüler bulut depolama hizmetleriyle entegrasyonu destekleyerek bulutta depolanan belgeleri görüntülemenize olanak tanır.
### Groupdocs.Viewer için deneme sürümü mevcut mu?
Evet, Groupdocs.Viewer'ı ücretsiz deneme sürümüne erişerek kullanmaya başlayabilirsiniz. [web sitesi](https://releases.groupdocs.com/).