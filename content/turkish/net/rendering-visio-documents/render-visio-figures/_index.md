---
title: Visio Şekillerini Oluştur
linktitle: Visio Şekillerini Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: Bu kapsamlı içerikle GroupDocs.Viewer for .NET'i kullanarak Visio rakamlarını nasıl oluşturacağınızı öğrenin. .NET uygulamalarınızdaki belge görüntüleme yeteneklerini geliştirin.
weight: 10
url: /tr/net/rendering-visio-documents/render-visio-figures/
---
## giriiş
Günümüzün dijital çağında, belge oluşturma çeşitli uygulamalarda çok önemli bir rol oynamaktadır. Belgelerin bir web sitesinde görüntülenmesi veya farklı formatlara dönüştürülmesi olsun, verimli görüntü oluşturma çok önemlidir. GroupDocs.Viewer for .NET, .NET uygulamaları içindeki belgeleri görüntülemek ve değiştirmek için güçlü bir çözüm sağlar. Bu öğreticide, süreci basit adımlara bölerek GroupDocs.Viewer for .NET'i kullanarak Visio şekillerini oluşturmayı ayrıntılı olarak ele alacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Ortam Kurulumu: .NET geliştirme için bir çalışma ortamınızın olduğundan emin olun.
2.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
3. Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.
4. Örnek Visio Belgesi: Oluşturulmaya hazır örnek bir Visio belgesi hazırlayın.

## Ad Alanlarını İçe Aktar
C# projenizde gerekli ad alanlarını içe aktararak başlayın:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. HTML'ye Dönüştürme
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Çıkış Dizini: Oluşturulan HTML'nin kaydedileceği dizini tanımlayın.
- Sayfa Dosyası Yolu Formatı: HTML sayfasının yol formatını belirtin.
- Görüntüleyici Başlatma: Viewer nesnesini Visio belgesinin yolu ile başlatın.
- HTML Görünüm Seçenekleri: HTML oluşturmaya yönelik seçenekleri yapılandırın.
- Visio İşleme Seçenekleri: Yalnızca şekilleri işleme ve şekil genişliği gibi Visio işlemeye özel seçenekleri ayarlayın.
## 2. JPG'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- HTML'ye dönüştürmeye benzer şekilde, JPG biçimine dönüştürme seçeneklerini yapılandırın.
## 3. PNG'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- PNG formatına dönüştürme yapılandırması, JPG oluşturmayla benzer bir modeli izler.
## 4. PDF'ye Dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- PDF'ye dönüştürmek için PDF formatına özel seçenekleri yapılandırın.

## Çözüm
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak Visio rakamlarının nasıl oluşturulacağını araştırdık. Adım adım kılavuzu izleyerek, belge oluşturma yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre ederek kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS'ler
### Visio figürleri için işleme seçeneklerini özelleştirebilir miyim?
Evet, GroupDocs.Viewer for .NET, şekil genişliği, yalnızca şekillerin işlenmesi ve daha fazlası dahil olmak üzere, işlemeyi özelleştirmek için kapsamlı seçenekler sunar.
### GroupDocs.Viewer for .NET büyük ölçekli belge oluşturmaya uygun mu?
GroupDocs.Viewer for .NET kesinlikle büyük ölçekli belge oluşturmayı verimli bir şekilde gerçekleştirmek için optimize edilmiştir.
### GroupDocs.Viewer, Visio dışında diğer belge formatlarını destekliyor mu?
Evet, GroupDocs.Viewer, PDF, Microsoft Office, AutoCAD ve daha fazlası dahil çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer'ı web uygulamalarına entegre edebilir miyim?
Evet, GroupDocs.Viewer, belge görüntüleme ve işleme için web uygulamalarına sorunsuz bir şekilde entegre edilebilir.
### Satın almadan önce test edebileceğiniz bir deneme sürümü var mı?
Evet, ücretsiz deneme sürümünden yararlanabilirsiniz.[İnternet sitesi](https://releases.groupdocs.com/) GroupDocs.Viewer for .NET'in yeteneklerini test etmek için.