---
title: İşleme Sırasında E-posta Alanlarını Yeniden Adlandırın
linktitle: İşleme Sırasında E-posta Alanlarını Yeniden Adlandırın
second_title: GroupDocs.Viewer .NET API'si
description: .NET için GroupDocs.Viewer ile belge görüntüleme deneyimini geliştirin. E-postaları sorunsuz bir şekilde oluşturun ve özelleştirin.
type: docs
weight: 12
url: /tr/net/rendering-email-messages/rename-email-fields/
---
## giriiş

Günümüzün dijital çağında, belgeleri verimli bir şekilde yönetmek ve görüntülemek hem işletmeler hem de bireyler için çok önemlidir. Sözleşmeler, raporlar veya e-postalar olsun, bu belgeler arasında sorunsuz bir şekilde gezinme becerisine sahip olmak üretkenliği büyük ölçüde artırabilir. GroupDocs.Viewer for .NET tam da burada devreye giriyor. Bu güçlü kitaplık, geliştiricilerin belge görüntüleme yeteneklerini doğrudan .NET uygulamalarına entegre etmelerine olanak tanıyarak, çeşitli belge formatlarını işlemek için çok çeşitli özellikler sunar.

## Önkoşullar

GroupDocs.Viewer for .NET'i kullanarak oluşturma sırasında e-posta alanlarını yeniden adlandırma eğitimine dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  GroupDocs.Viewer for .NET Kitaplığı: GroupDocs.Viewer for .NET kitaplığını şuradan indirip yükleyin:[Burada](https://releases.groupdocs.com/viewer/net/).

2. Geliştirme Ortamı: .NET geliştirme için Visual Studio gibi uygun bir geliştirme ortamına sahip olduğunuzdan emin olun.

3. Temel C# Anlayışı: Öğretici C# kod parçacıklarını içereceğinden, C# programlama dilinin temellerine aşina olun.

4. Belge Dizini: İşlenecek belgelerin saklanacağı bir dizin hazırlayın.

## Ad Alanlarını İçe Aktar

GroupDocs.Viewer işlevlerini .NET uygulamanızda kullanmak için gerekli ad alanlarını içe aktarmanız gerekir.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Şimdi GroupDocs.Viewer for .NET'i kullanarak oluşturma sırasında e-posta alanlarını yeniden adlandırma işlemini birden çok adıma ayıralım:

## Adım 1: Çıkış Dizinini Tanımlayın

Öncelikle oluşturulan HTML sayfalarının kaydedileceği dizini belirtin.

```csharp
string outputDirectory = "Your Document Directory";
```

## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın

İşlenen HTML sayfalarının dosya yolları için formatı tanımlayın. Her sayfa ayrı bir HTML dosyası olarak kaydedilecektir.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3. Adım: Görüntüleyici Nesnesini Başlatın

Viewer sınıfının bir örneğini oluşturun ve görüntülenecek belgenin yolunu parametre olarak iletin.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## 4. Adım: HTML Görünüm Seçeneklerini Yapılandırma

Çıktı dosyası biçimini belirlemek ve e-posta alanı eşlemelerini ayarlamak da dahil olmak üzere HTML görünümü seçeneklerini yapılandırın.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Adım 5: Belgeyi Oluşturun

Yapılandırılmış HTML görünüm seçeneklerini ileterek Viewer nesnesinin View yöntemini çağırın.

```csharp
viewer.View(options);
```

## Adım 6: Başarı Mesajını Görüntüleyin

Kullanıcıya belgenin başarıyla işlendiğini bildirin.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm

Sonuç olarak, GroupDocs.Viewer for .NET, .NET uygulamaları içinde belgelerin işlenmesi için kusursuz bir çözüm sağlar. Bu eğitimde özetlenen adımları izleyerek, oluşturma sırasında e-posta alanlarını kolayca yeniden adlandırabilir, böylece e-posta belgelerinin okunabilirliğini ve kullanılabilirliğini artırabilirsiniz. Sezgisel API'si ve kapsamlı özellikleriyle GroupDocs.Viewer, geliştiricilerin belge görüntüleme süreçlerini etkili bir şekilde kolaylaştırmalarına olanak tanır.

## SSS'ler

### S: GroupDocs.Viewer for .NET'i kullanarak e-postalar dışındaki belgeleri oluşturabilir miyim?

C: Evet, GroupDocs.Viewer, PDF, Microsoft Office belgeleri, resimler ve daha fazlası dahil olmak üzere çeşitli belge formatlarının oluşturulmasını destekler.

### S: GroupDocs.Viewer .NET Core ile uyumlu mu?

C: Evet, GroupDocs.Viewer, geleneksel .NET Framework'ün yanı sıra .NET Core'u da destekler.

### S: İşlenen belgelerin görünümünü özelleştirebilir miyim?

C: Kesinlikle GroupDocs.Viewer, oluşturulan belgelerin görünümünü ve davranışını kontrol etmek için kapsamlı özelleştirme seçenekleri sunar.

### S: GroupDocs.Viewer belge akışını destekliyor mu?

C: Evet, GroupDocs.Viewer, belgelerin sunucuda saklanmasına gerek kalmadan doğrudan istemcinin tarayıcısına aktarılmasına olanak tanır.

### S: GroupDocs.Viewer kurumsal düzeydeki uygulamalar için uygun mudur?

C: Kesinlikle GroupDocs.Viewer, ölçeklenebilirliği, güvenilirliği ve sağlam özellikleriyle kurumsal düzeydeki uygulamaların taleplerini karşılamak üzere tasarlanmıştır.
