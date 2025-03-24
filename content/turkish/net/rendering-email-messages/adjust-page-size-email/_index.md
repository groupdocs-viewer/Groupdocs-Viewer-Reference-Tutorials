---
title: E-posta Mesajlarını Oluştururken Sayfa Boyutunu Ayarlayın
linktitle: E-posta Mesajlarını Oluştururken Sayfa Boyutunu Ayarlayın
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak e-posta mesajlarını PDF'ye dönüştürürken sayfa boyutunu nasıl ayarlayacağınızı öğrenin. Belge görüntüleme verimliliğini artırın.
weight: 10
url: /tr/net/rendering-email-messages/adjust-page-size-email/
---
## giriiş
.NET geliştirme alanında GroupDocs.Viewer, e-posta mesajları da dahil olmak üzere çeşitli belge formatlarının oluşturulmasına yönelik kapsamlı bir çözüm sunar. Bu eğitim, GroupDocs.Viewer for .NET kullanılarak e-posta iletilerini PDF biçiminde görüntülerken sayfa boyutunu ayarlamaya odaklanır. Bu kılavuzda özetlenen adımları izleyerek, özel gereksinimlerinizi karşılamak için sayfa boyutunu sorunsuz bir şekilde nasıl değiştireceğinizi öğreneceksiniz.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. .NET için GroupDocs.Viewer Yüklü
 Geliştirme ortamınızda GroupDocs.Viewer for .NET'in kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Geliştirmenin Temel Anlayışı
C# programlama ve dosya işleme dahil .NET geliştirmenin temellerini öğrenin.
### 3. IDE (Entegre Geliştirme Ortamı)
.NET kodunu yazmak ve yürütmek için Visual Studio gibi bir IDE'nin kurulu olmasını sağlayın.

## Ad Alanlarını İçe Aktar
C# projenizde GroupDocs.Viewer işlevlerini kullanmak için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıkış Dizinini Ayarlayın
Çıktı PDF dosyasının kaydedileceği dizini tanımlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Dosya Yolunu Tanımlayın
Çıktı dizinini çıktı dosyası adıyla birleştirin.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 3. Adım: Görüntüleyici Nesnesini Başlatın
Viewer sınıfının bir örneğini oluşturun ve e-posta mesajı dosya yolunu belirtin.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## 4. Adım: PDF Görünüm Seçeneklerini Yapılandırın
PdfViewOptions örneğini oluşturun ve çıktı dosyası yolunu ayarlayın.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## Adım 5: Sayfa Boyutunu Ayarlayın
PdfViewOptions'ın EmailOptions'ında sayfa boyutu özelliğini değiştirin.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## Adım 6: Belgeyi Oluşturun
Yapılandırılmış PdfViewOptions'ı ileterek görüntüleyici nesnesinin View yöntemini çağırın.
```csharp
viewer.View(options);
```
## Adım 7: Başarı Mesajını Görüntüleyin
Kullanıcıyı başarılı işleme ve çıktı dizini hakkında bilgilendirin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Sonuç olarak bu eğitimde, GroupDocs.Viewer for .NET kullanılarak e-posta iletilerinin PDF formatına dönüştürülmesi sırasında sayfa boyutunun nasıl ayarlanacağı gösterilmiştir. Bu adım adım talimatları izleyerek, sayfa boyutlarını özel gereksinimlerinizi karşılayacak şekilde etkili bir şekilde düzenleyebilir, .NET uygulamalarınızdaki belge görüntüleme ve yönetim yeteneklerini geliştirebilirsiniz.
## SSS'ler
### GroupDocs.Viewer farklı e-posta mesajı formatlarıyla uyumlu mu?
GroupDocs.Viewer, MSG ve EML dahil olmak üzere çeşitli e-posta mesajı formatlarının oluşturulmasını destekler.
### Sayfa boyutunu tercihlerime göre özelleştirebilir miyim?
Evet, belge oluşturmada esneklik sunan GroupDocs.Viewer'ın PdfViewOptions özelliğini kullanarak sayfa boyutunu ayarlayabilirsiniz.
### GroupDocs.Viewer diğer belge formatları için destek sağlıyor mu?
Evet, GroupDocs.Viewer, PDF, Microsoft Office, resimler ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer kurumsal düzeydeki uygulamalar için uygun mu?
GroupDocs.Viewer kesinlikle hem küçük ölçekli hem de kurumsal düzeydeki uygulamalara uygun güçlü işlevler sunarak verimli belge oluşturma ve yönetimi sağlar.
### GroupDocs.Viewer için nereden yardım veya ek destek alabilirim?
 GroupDocs.Viewer forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9) yardım istemek, sorular sormak ve toplulukla etkileşime geçmek.