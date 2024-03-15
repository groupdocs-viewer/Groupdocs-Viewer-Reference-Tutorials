---
title: TarihSaat Formatını ve Saat Dilimi Farkını (E-posta) Ayarlayın
linktitle: TarihSaat Formatını ve Saat Dilimi Farkını (E-posta) Ayarlayın
second_title: GroupDocs.Viewer .NET API'si
description: Güçlü belge görüntüleme yetenekleri için GroupDocs.Viewer for .NET'i uygulamalarınıza sorunsuz bir şekilde entegre edin. Özelleştirilebilir seçeneklerle kullanıcı deneyimini geliştirin.
type: docs
weight: 11
url: /tr/net/rendering-email-messages/set-date-time-format-offset-email/
---

## giriiş
GroupDocs.Viewer for .NET, geliştiricilerin belge görüntüleme yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir araçtır. GroupDocs.Viewer ile herhangi bir harici eklentiye veya görüntüleyiciye ihtiyaç duymadan PDF'ler, Microsoft Office belgeleri, resimler ve daha fazlasını içeren çok çeşitli belge formatlarını doğrudan uygulamanızın içinde görüntüleyebilirsiniz. Bu kapsamlı eğitimde, GroupDocs.Viewer for .NET'i kurma sürecinde size rehberlik edeceğiz, özelliklerini keşfedeceğiz ve uygulamanızın belge görüntüleme yeteneklerini geliştirmek için onu etkili bir şekilde nasıl kullanacağınızı göstereceğiz.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşulların ayarlandığından emin olun:
1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. GroupDocs.Viewer for .NET, Visual Studio ile tamamen uyumludur ve .NET projelerinizle kusursuz entegrasyona olanak tanır.
2.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şu adresten indirip yükleyin:[İndirme: {link](https://releases.groupdocs.com/viewer/net/). Kitaplığı geliştirme ortamınızda kurmak için sağlanan kurulum talimatlarını izleyin.
3. .NET Framework: .NET Framework'ün uygun sürümünün yüklü olduğundan emin olun. GroupDocs.Viewer for .NET, .NET Core ve .NET Standard dahil olmak üzere .NET Framework'ün çeşitli sürümlerini destekler.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET'i etkili bir şekilde kullanmak için gerekli ad alanlarını projenize aktarmanız gerekir. Gerekli ad alanlarını içe aktarmak için şu adımları izleyin:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Her bir bileşeni ve işlevselliğini anlamak için verilen örneği birden fazla adıma ayıralım.
## Adım 1: Çıktı Dizinini ve Dosya Yolunu Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Bu adımda, oluşturulan belgenin kaydedileceği çıktı dizinini tanımlıyoruz ve çıktı HTML dosyası için dosya yolunu belirliyoruz.
## Adım 2: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Burada yeni bir örneğini oluşturuyoruz.`Viewer` sınıf, görüntülenecek belgenin yolunu (bu durumda örnek bir EML dosyası) parametre olarak iletir.
## 3. Adım: HTML Görünüm Seçeneklerini Tanımlayın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Bu adımda, oluşturulan HTML belgesinin çıktı dosyası yolunu belirterek, belge oluşturma için HTML görünüm seçeneklerini yapılandırıyoruz.
## 4. Adım: DateTime Formatını ve Saat Dilimi Farkını Ayarlayın
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Burada e-posta mesajları için tarih ve saat formatını özelleştiriyoruz ve saat dilimi farkını istenen saat dilimine göre ayarlıyoruz.
## Adım 5: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
 Son olarak şunu diyoruz:`View` yöntemi`Viewer` Belgeyi HTML biçimine dönüştürmek için yapılandırılmış HTML görünüm seçeneklerini ileten nesne.
## Adım 6: Çıkış Dizinini Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bu adım, belgenin başarıyla oluşturulduğunu belirten bir mesaj görüntüler ve işlenmiş HTML belgesinin bulunduğu çıktı dizininin yolunu sağlar.

## Çözüm
GroupDocs.Viewer for .NET, belge görüntüleme yeteneklerini .NET uygulamalarınıza entegre etmek için güçlü bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek GroupDocs.Viewer'ı kolayca kurabilir, gerekli ad alanlarını içe aktarabilir ve özelleştirilebilir seçeneklerle belgeleri işlemek için özelliklerini kullanabilirsiniz. İster PDF'ler, Microsoft Office belgeleri veya diğer formatlarla çalışıyor olun, GroupDocs.Viewer belge görüntüleme sürecini basitleştirerek uygulamalarınızın kullanıcı deneyimini geliştirir.
## SSS'ler
### GroupDocs.Viewer .NET Core ile uyumlu mu?
Evet, GroupDocs.Viewer for .NET, uygulamalarınız için platformlar arası uyumluluğu mümkün kılan .NET Core'u destekler.
### İşlenen belgelerin görünümünü özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, görüntüleme deneyimini tercihlerinize göre uyarlamak için yakınlaştırma düzeyleri, sayfa döndürme ve daha fazlasını içeren çeşitli özelleştirme seçenekleri sunar.
### Test amaçlı deneme sürümü mevcut mu?
 Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümünü şuradan indirebilirsiniz:[web sitesi bağlantısı](https://releases.groupdocs.com/viewer/net/) Bir satın alma işlemi yapmadan önce özelliklerini değerlendirmek için.
### GroupDocs.Viewer parola korumalı belgelerin görüntülenmesini destekliyor mu?
Evet, GroupDocs.Viewer, parola korumalı belgelerin görüntülenmesi için yerleşik desteğe sahiptir ve uygulamalarınızda güvenli belge görüntüleme sağlar.
### GroupDocs.Viewer ile ilgili ek desteği veya yardımı nerede bulabilirim?
 Teknik sorularınız veya yardım için GroupDocs.Viewer'ı ziyaret edebilirsiniz.[forum](https://forum.groupdocs.com/c/viewer/9) veya hızlı yardım ve rehberlik için destek ekibine ulaşın.