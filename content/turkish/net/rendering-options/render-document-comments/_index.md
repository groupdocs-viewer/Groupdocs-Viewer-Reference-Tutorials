---
title: Belgeyi Yorumlarla Oluştur
linktitle: Belgeyi Yorumlarla Oluştur
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak yorum içeren belgeleri nasıl oluşturacağınızı öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 13
url: /tr/net/rendering-options/render-document-comments/
---

# Belgeyi Yorumlarla Oluştur

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin belge işleme yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir kitaplıktır. Word belgelerini, Excel elektronik tablolarını, PowerPoint sunumlarını, PDF dosyalarını veya diğer formatları görüntülemeniz gerekiyorsa, GroupDocs.Viewer basit bir çözüm sunar.
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak yorumları içeren belgeleri oluşturmaya odaklanacağız. Önkoşullar, ad alanlarının içe aktarılması konusunda size yol göstereceğiz ve her bir kavramı iyice kavramanızı sağlayacak şekilde, yorumları içeren belgeleri işlemek için adım adım bir kılavuz sunacağız.
## Önkoşullar
GroupDocs.Viewer for .NET'i kullanarak yorumları içeren belgeleri oluşturmaya başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### .NET Geliştirme Ortamı Kurulumu
.NET geliştirme için ayarlanmış bir geliştirme ortamınız olduğundan emin olun. Makinenizde Visual Studio ve .NET SDK gibi uyumlu bir IDE'nin yüklü olması gerekir.
### .NET Kurulumu için GroupDocs.Viewer
GroupDocs.Viewer for .NET'i web sitesinden indirip yükleyin veya sağlanan indirme bağlantısını kullanın:
[.NET için GroupDocs.Viewer'ı indirin](https://releases.groupdocs.com/viewer/net/)

## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını .NET projenize aktarın. Bu ad alanları, yorumlarla belge oluşturma için gereken sınıflara ve yöntemlere erişim sağlar.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Adım 1: Çıkış Dizinini Tanımlayın
Yorumlarla birlikte oluşturulan belgenin kaydedileceği çıktı dizinini ayarlayın.
```csharp
string outputDirectory = "Your Document Directory";
```
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
Yorumlarla birlikte işlenmiş belgenin ayrı sayfaları için dosya yolu formatını tanımlayın.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3. Adım: Görüntüleyici Nesnesini Örneklendirin
 Bir örneğini oluşturun`Viewer` sınıf, parametre olarak yorumların bulunduğu belgenin yolunu iletir.
```csharp
using (Viewer viewer = new Viewer("Path to Your Document with Comments"))
{
    // Oluşturma seçenekleri
}
```
## 4. Adım: Oluşturma Seçeneklerini Yapılandırın
Gömülü kaynaklara ve yorumlara ilişkin ayarlar dahil, oluşturma seçeneklerini belirtin.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderComments = true;
```
## Adım 5: Belgeyi Yorumlarla Oluşturun
 Çağır`View` yöntemi`Viewer` oluşturma seçeneklerini ileten nesne.
```csharp
viewer.View(options);
```
## Adım 6: Başarı Mesajını Görüntüleyin
Yorum içeren belgenin başarıyla işlendiğini kullanıcıya bildirin.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Çözüm
Bu öğreticide, GroupDocs.Viewer for .NET'i kullanarak yorumları içeren belgeleri işleme sürecini ele aldık. Adım adım kılavuzu izleyerek ve önkoşulları karşıladığınızı garantileyerek, belge oluşturma yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### GroupDocs.Viewer karmaşık biçimlendirmeye sahip belgeleri görüntüleyebilir mi?
Evet, GroupDocs.Viewer tablolar, resimler ve yazı tipleri dahil olmak üzere çeşitli biçimlendirme öğeleriyle belgelerin oluşturulmasını destekler.
### GroupDocs.Viewer farklı belge formatlarıyla uyumlu mu?
GroupDocs.Viewer kesinlikle PDF, DOCX, XLSX, PPTX ve daha fazlası dahil çok çeşitli belge formatlarını görüntüleyebilir.
### Oluşturma seçeneklerini belirli gereksinimlere göre özelleştirebilir miyim?
Evet, GroupDocs.Viewer, çıktıyı uygulamanızın ihtiyaçlarına göre uyarlamanıza olanak tanıyan esnek işleme seçenekleri sunar.
### GroupDocs.Viewer harici kaynaklardan belge oluşturulmasını destekliyor mu?
Evet, yerel dosyalar, akışlar ve URL'ler dahil olmak üzere çeşitli kaynaklardan belge oluşturabilirsiniz.
### GroupDocs.Viewer'ın deneme sürümü mevcut mu?
Evet, özelliklerini ve yeteneklerini keşfetmek için GroupDocs.Viewer'ın ücretsiz deneme sürümünü kullanmaya başlayabilirsiniz.