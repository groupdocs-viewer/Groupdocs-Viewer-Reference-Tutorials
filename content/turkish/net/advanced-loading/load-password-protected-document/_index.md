---
title: Parola Korumalı Belgeleri Yükleyin
linktitle: Parola Korumalı Belgeleri Yükleyin
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak parola korumalı belge görüntülemeyi .NET uygulamalarına zahmetsizce entegre edin. Sorunsuz bir şekilde adım adım eğitimimizi izleyin.
weight: 12
url: /tr/net/advanced-loading/load-password-protected-document/
---
## giriiş
Günümüzün dijital çağında, çeşitli belge formatlarını sorunsuz bir şekilde yönetmek ve görüntülemek, birçok işletme ve benzer bireyler için bir zorunluluktur. Neyse ki GroupDocs.Viewer for .NET, .NET geliştiricilerinin belge görüntüleme yeteneklerini uygulamalarına zahmetsizce entegre etmeleri için kapsamlı bir çözüm sunuyor. Bu eğitimde GroupDocs.Viewer'ın temel işlevlerinden birini inceleyeceğiz: parola korumalı belgeleri yükleme. Geliştiricilerin bu özelliği kolayca takip edebilmelerini ve projelerine uygulayabilmelerini sağlamak için süreci adım adım inceleyeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### 1. .NET için GroupDocs.Viewer'ı yükleyin
 Geliştirme ortamınızda GroupDocs.Viewer for .NET'in kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.groupdocs.com/viewer/net/).
### 2. Parola Korumalı Bir Belge Alın
Test amacıyla, parola korumalı bir belgeyi hazır bulundurun. Bu, yükleme sürecini etkili bir şekilde göstermemize olanak sağlayacaktır.

## Ad Alanlarını İçe Aktar
Eğiticiye devam etmeden önce gerekli ad alanlarını projemize aktaralım:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıkış Dizinini Tanımlayın
İlk olarak, oluşturulan çıktının kaydedilmesini istediğiniz dizini belirtin:
```csharp
string outputDirectory = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"` İstediğiniz dizinin yolu ile.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Daha sonra, oluşturulan her sayfanın dosya yolu formatını tanımlayın:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Bu format aşağıdaki gibi dosya yolları oluşturacaktır:`"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, ve benzeri.
## 3. Adım: Yükleme Seçeneklerini Yapılandırın
Parola da dahil olmak üzere parola korumalı belgenin yükleme seçeneklerini yapılandırın:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
 Yer değiştirmek`"12345"` belgenizin gerçek şifresiyle.
## 4. Adım: Görüntüleyiciyi Başlatın
GroupDocs.Viewer'ı belge ve yükleme seçenekleriyle başlatın:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Görüntüleme seçeneklerine ilişkin kod bir sonraki adımda eklenecektir.
}
```
 Yer değiştirmek`"Path_to_your_document"` şifre korumalı belgenizin yolu ile birlikte.
## 5. Adım: HTML Görünüm Seçeneklerini Yapılandırma
Belgeyi gömülü kaynaklarla oluşturmak için HTML görünüm seçeneklerini yapılandırın:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Adım 6: Belgeyi Oluşturun
Yapılandırılmış görüntüleyiciyi ve görüntüleme seçeneklerini kullanarak belgeyi oluşturun:
```csharp
viewer.View(options);
```
## Adım 7: Başarı Mesajını Görüntüleyin
Kullanıcıya belgenin başarıyla işlendiğini bildirin:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak parola korumalı belgelerin nasıl yükleneceğini araştırdık. Geliştiriciler, adım adım kılavuzu izleyerek bu işlevselliği .NET uygulamalarına sorunsuz bir şekilde entegre edebilir ve kullanıcıların korumalı belgeleri kolaylıkla görüntülemesine olanak tanır.
## SSS'ler
### GroupDocs.Viewer, parola korumalı belgelerin yanı sıra diğer belge formatlarını da işleyebilir mi?
Evet, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### GroupDocs.Viewer .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer hem .NET Framework hem de .NET Core ortamlarıyla uyumluluk sunar.
### Belgelerin oluşturma seçeneklerini özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, çeşitli işleme seçenekleri sunarak geliştiricilerin görüntüleme deneyimini gereksinimlerine göre özelleştirmelerine olanak tanır.
### GroupDocs.Viewer belge açıklamalarını destekliyor mu?
Evet, GroupDocs.Viewer belge açıklamalarını destekleyerek kullanıcıların belgelere yorum, vurgu ve diğer açıklamalar eklemesine olanak tanır.
### GroupDocs.Viewer'ın deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[İnternet sitesi](https://releases.groupdocs.com/).