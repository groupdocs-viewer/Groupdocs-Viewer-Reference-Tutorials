---
"description": "Güçlü belge görüntüleme yetenekleri için GroupDocs.Viewer for .NET'i uygulamalarınıza sorunsuz bir şekilde entegre edin. Özelleştirilebilir seçeneklerle kullanıcı deneyimini geliştirin."
"linktitle": "DateTime Formatını ve Saat Dilimi Ofsetini Ayarla (E-posta)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "DateTime Formatını ve Saat Dilimi Ofsetini Ayarla (E-posta)"
"url": "/tr/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# DateTime Formatını ve Saat Dilimi Ofsetini Ayarla (E-posta)


## giriiş
.NET için GroupDocs.Viewer, geliştiricilerin belge görüntüleme yeteneklerini .NET uygulamalarına sorunsuz bir şekilde entegre etmelerini sağlayan güçlü bir araçtır. GroupDocs.Viewer ile PDF'ler, Microsoft Office belgeleri, resimler ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini doğrudan uygulamanızın içinde, herhangi bir harici eklenti veya görüntüleyiciye ihtiyaç duymadan görüntüleyebilirsiniz. Bu kapsamlı eğitimde, .NET için GroupDocs.Viewer'ı kurma sürecinde size rehberlik edeceğiz, özelliklerini keşfedeceğiz ve uygulamanızın belge görüntüleme yeteneklerini geliştirmek için onu etkili bir şekilde nasıl kullanacağınızı göstereceğiz.
## Ön koşullar
Bu eğitime başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
1. Visual Studio: Sisteminizde Visual Studio'nun yüklü olduğundan emin olun. GroupDocs.Viewer for .NET, Visual Studio ile tamamen uyumludur ve .NET projelerinize sorunsuz entegrasyon sağlar.
2. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET'i şuradan indirin ve yükleyin: [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/)Geliştirme ortamınızda kütüphaneyi kurmak için verilen kurulum talimatlarını izleyin.
3. .NET Framework: .NET Framework'ün uygun sürümünün yüklü olduğundan emin olun. .NET için GroupDocs.Viewer, .NET Core ve .NET Standard dahil olmak üzere .NET Framework'ün çeşitli sürümlerini destekler.

## Ad Alanlarını İçe Aktar
GroupDocs.Viewer for .NET'i etkili bir şekilde kullanmak için, gerekli ad alanlarını projenize içe aktarmanız gerekir. Gerekli ad alanlarını içe aktarmak için şu adımları izleyin:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Her bir bileşeni ve işlevselliğini anlamak için verilen örneği birden fazla adıma bölelim.
## Adım 1: Çıktı Dizini ve Dosya Yolunu Ayarlayın
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Bu adımda, oluşturulan belgenin kaydedileceği çıktı dizinini tanımlıyoruz ve çıktı HTML dosyasının dosya yolunu belirtiyoruz.
## Adım 2: Görüntüleyici Nesnesini Örneklendirin
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Burada, yeni bir örnek oluşturuyoruz `Viewer` sınıf, görüntülenecek belgenin yolunu (bu durumda, örnek bir EML dosyası) parametre olarak geçirerek.
## Adım 3: HTML Görünüm Seçeneklerini Tanımlayın
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Bu adımda, işlenmiş HTML belgesi için çıktı dosyası yolunu belirterek belgenin işlenmesine ilişkin HTML görünüm seçeneklerini yapılandırıyoruz.
## Adım 4: DateTime Formatını ve Saat Dilimi Ofsetini Ayarlayın
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Burada, e-posta mesajları için tarih ve saat biçimini özelleştiriyoruz ve saat dilimi farkını istenilen saat dilimine göre ayarlıyoruz.
## Adım 5: Belgeyi Oluşturun
```csharp
viewer.View(options);
```
Son olarak şunu çağırıyoruz: `View` yöntemi `Viewer` nesne, belgeyi HTML biçimine dönüştürmek için yapılandırılmış HTML görünüm seçeneklerini iletir.
## Adım 6: Çıktı Dizinini Görüntüle
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bu adım, belgenin başarılı bir şekilde oluşturulduğunu belirten bir ileti görüntüler ve oluşturulan HTML belgesinin bulunduğu çıktı dizinine giden yolu sağlar.

## Çözüm
.NET için GroupDocs.Viewer, .NET uygulamalarınıza belge görüntüleme yeteneklerini entegre etmek için sağlam bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, GroupDocs.Viewer'ı kolayca kurabilir, gerekli ad alanlarını içe aktarabilir ve özelleştirilebilir seçeneklerle belgeleri işlemek için özelliklerini kullanabilirsiniz. İster PDF'lerle, ister Microsoft Office belgeleriyle veya diğer biçimlerle çalışın, GroupDocs.Viewer belge görüntüleme sürecini basitleştirir ve uygulamalarınızın kullanıcı deneyimini iyileştirir.
## SSS
### GroupDocs.Viewer .NET Core ile uyumlu mudur?
Evet, GroupDocs.Viewer for .NET, .NET Core'u destekler ve uygulamalarınız için platformlar arası uyumluluğu mümkün kılar.
### Oluşturulan belgelerin görünümünü özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, öğreticilerinize göre görüntüleme deneyiminizi kişiselleştirmek için yakınlaştırma seviyeleri, sayfa döndürme ve daha fazlası dahil olmak üzere çeşitli özelleştirme seçenekleri sunar.
### Test amaçlı deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [web sitesi bağlantısı](https://releases.groupdocs.com/viewer/net/) Satın almadan önce özelliklerini değerlendirmek.
### GroupDocs.Viewer parola korumalı belgelerin işlenmesini destekliyor mu?
Evet, GroupDocs.Viewer parola korumalı belgeleri görüntülemeye yönelik yerleşik desteğe sahiptir ve bu sayede uygulamalarınız içinde güvenli belge görüntüleme sağlanır.
### GroupDocs.Viewer ile ilgili ek destek veya yardımı nerede bulabilirim?
Herhangi bir teknik soru veya yardım için GroupDocs.Viewer'ı ziyaret edebilirsiniz. [forum](https://forum.groupdocs.com/c/viewer/9) veya hızlı yardım ve rehberlik için destek ekibine ulaşın.