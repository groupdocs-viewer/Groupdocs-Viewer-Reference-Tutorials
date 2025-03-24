---
title: İşlenen HTML Belgesini Küçült
linktitle: İşlenen HTML Belgesini Küçült
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak .NET uygulamalarında HTML belgelerini sorunsuz bir şekilde nasıl oluşturacağınızı öğrenin.
weight: 11
url: /tr/net/rendering-documents-html/minify-html/
---

# İşlenen HTML Belgesini Küçült

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin .NET uygulamalarında HTML belgelerini sorunsuz bir şekilde oluşturmasına olanak tanıyan güçlü bir araçtır. Sezgisel API'si ve sağlam işlevselliği sayesinde geliştiriciler, belge görüntüleme yeteneklerini uygulamalarına kolayca entegre ederek kullanıcı deneyimini ve üretkenliğini artırabilir.
## Önkoşullar
GroupDocs.Viewer for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. C# ve .NET Framework bilgisi
GroupDocs.Viewer for .NET'i etkili bir şekilde kullanmak için C# programlama dili ve .NET Framework hakkında temel bilgiye sahip olmanız gerekir.
### 2.Visual Studio IDE'si
Sisteminizde Visual Studio IDE'nin kurulu olduğundan emin olun. Resmi web sitesinden indirebilirsiniz.
### 3. .NET Kitaplığı için GroupDocs.Viewer
 Sağlanan kaynaktan GroupDocs.Viewer for .NET kitaplığını indirin.[İndirme: {link](https://releases.groupdocs.com/viewer/net/) ve bunu projenize dahil edin.
### 4. Belge Dosyaları
Oluşturmak istediğiniz belge dosyalarını GroupDocs.Viewer for .NET'i kullanarak hazırlayın. Desteklenen dosya formatları arasında DOCX, PDF, PPTX ve daha fazlası bulunur.
### 5. Geçici Lisans (İsteğe bağlı)
 GroupDocs.Viewer for .NET'i deneme veya test ortamında kullanıyorsanız, şu adresten geçici bir lisans edinin:[geçici lisans sayfası](https://purchase.groupdocs.com/temporary-license/).

## Ad Alanlarını İçe Aktar
.NET uygulamanızda, GroupDocs.Viewer for .NET'in işlevselliğine erişmek için gerekli ad alanlarını içe aktararak başlayın.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi, GroupDocs.Viewer for .NET kullanarak oluşturulan HTML belgelerini küçültme işlemini birden çok adıma ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
İşlenen HTML sayfalarını kaydetmek istediğiniz dizini belirtin.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
İşlenen her HTML sayfası için dosya yolunun biçimini tanımlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Adım 3: HTML Belgesini Oluşturun
Bir Viewer nesnesi oluşturun ve oluşturmak istediğiniz belge dosyasının yolunu iletin.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.Minify = true;
    viewer.View(options);
}
```
## Adım 4: Başarı Mesajını Görüntüleyin
Belgenin başarıyla işlendiğini belirten bir mesaj görüntüler.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Sonuç olarak, GroupDocs.Viewer for .NET, HTML belgelerinin .NET uygulamaları içinde işlenmesi için kusursuz bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, belge görüntüleme özelliklerini uygulamalarınıza zahmetsizce entegre edebilir, kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS'ler
### GroupDocs.Viewer for .NET'i kullanarak harici kaynaklardan belge oluşturabilir miyim?
Evet, GroupDocs.Viewer for .NET, yerel dosyalar, akışlar ve URL'ler de dahil olmak üzere çeşitli kaynaklardan belge oluşturulmasını destekler.
### GroupDocs.Viewer for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[resmi internet sitesi](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET belgenin diğer formatlara dönüştürülmesini destekliyor mu?
Evet, GroupDocs.Viewer for .NET, belgeleri PDF, HTML ve görüntüler gibi farklı formatlara dönüştürmek için API'ler sağlar.
### GroupDocs.Viewer for .NET'te belgelerin görüntü oluşturma seçeneklerini özelleştirebilir miyim?
Evet, sayfa yönü, kalite ve filigran ekleme gibi çeşitli oluşturma seçeneklerini gereksinimlerinize göre özelleştirebilirsiniz.
### .NET için GroupDocs.Viewer desteğini nereden arayabilirim?
 Destek arayabilir ve toplulukla etkileşime geçebilirsiniz.[GroupDocs.Viewer forumu](https://forum.groupdocs.com/c/viewer/9).