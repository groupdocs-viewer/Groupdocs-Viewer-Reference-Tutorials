---
title: İptal Jetonuyla İşlemeyi İptal Et
linktitle: İptal Jetonuyla İşlemeyi İptal Et
second_title: GroupDocs.Viewer .NET API'si
description: Verimli belge görüntüleme için Groupdocs.Viewer for .NET'i .NET projelerinize sorunsuz bir şekilde entegre edin.
type: docs
weight: 11
url: /tr/net/rendering-options/cancel-render-cancellation-token/
---
## giriiş
Groupdocs.Viewer for .NET, .NET uygulamalarında belge görüntülemeyi ve işlemeyi basitleştirmek için tasarlanmış güçlü bir araçtır. İster PDF'lerle, Microsoft Office belgeleriyle, ister diğer yaygın formatlarla çalışıyor olun, bu kitaplık, belge görüntüleme yeteneklerini .NET projelerinize sorunsuz bir şekilde entegre etmek için güçlü işlevsellik sunar.
## Önkoşullar
.NET için Groupdocs.Viewer entegrasyonuna dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Kurulum: Groupdocs.Viewer for .NET kitaplığını sağlanan kaynaktan indirip yükleyin.[İndirme: {link](https://releases.groupdocs.com/viewer/net/).
   
2.  Lisans: Şu adresten lisans alın:[Grup dokümanları](https://purchase.groupdocs.com/buy) Kütüphanenin tüm potansiyelini ortaya çıkarmak için. Alternatif olarak, ücretsiz deneme sürümünü kullanarak başlayabilirsiniz.[geçici lisans](https://purchase.groupdocs.com/temporary-license/).
   
3. Geliştirme Ortamı: Visual Studio veya seçtiğiniz herhangi bir başka .NET IDE dahil, uyumlu bir geliştirme ortamının kurulduğundan emin olun.

## Ad Alanlarını İçe Aktar
Groupdocs.Viewer for .NET'i etkili bir şekilde kullanmak için gerekli ad alanlarını projenize aktarmanız gerekir. Bu adımları takip et:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Şimdi, daha iyi anlamak ve uygulamak için verilen örneği birden fazla adıma ayıralım:
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
Bu adım, oluşturulan belge sayfalarının saklanacağı dizini ayarlar.
## Adım 2: Sayfa Dosya Yolu Formatını Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Burada, ayrı ayrı belge sayfalarının dosya yollarının formatını tanımlarız.
## 3. Adım: CancellationTokenSource'u başlatın
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource, eşzamansız işlemleri iptal etmek için kullanılabilecek CancellationToken örnekleri oluşturmak için kullanılır.
## 4. Adım: CancellationToken'ı edinin
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Bu adım, oluşturma işlemini iptal etmek için kullanılacak olan CancellationTokenSource'tan belirteci alır.
## Adım 5: Belge Sayfalarını Oluşturun
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Burada, Task.Run() kullanarak belge sayfalarının eşzamansız olarak oluşturulmasını başlatıyoruz. Viewer örneği, belirtilen belge dosyasıyla (SAMPLE_DOCX) oluşturulur ve işleme seçenekleri yapılandırılır. Oluşturma işlemi daha sonra Viewer sınıfının View yöntemi kullanılarak başlatılır.
## Adım 6: İşleme Zaman Aşımını Ayarlayın
```csharp
cancellationTokenSource.CancelAfter(10);
```
Bu adım, işleme işlemi için 10 milisaniyelik bir zaman aşımı süresi ayarlar. İşlem bu süreyi aşarsa otomatik olarak iptal edilecektir.
## Adım 7: Başarı Mesajını Görüntüleyin
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Son olarak belgenin başarıyla işlendiğini belirten bir başarı mesajı görüntülenir.

## Çözüm
Bu eğitimde Groupdocs.Viewer for .NET'i projelerinize entegre etmenin temellerini ele aldık. Yukarıda özetlenen adımları izleyerek, belge görüntüleme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde dahil ederek kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS'ler
### Groupdocs.Viewer for .NET tüm belge formatlarıyla uyumlu mu?
Groupdocs.Viewer for .NET, PDF, Microsoft Office belgeleri, resimler ve daha fazlasını içeren çok çeşitli belge formatlarını destekler.
### İşlenen belge sayfalarının görünümünü özelleştirebilir miyim?
Evet, sayfa boyutu, kalite, filigran ekleme ve daha fazlası dahil olmak üzere oluşturma işleminin çeşitli yönlerini özelleştirebilirsiniz.
### Groupdocs.Viewer for .NET internet bağlantısı gerektiriyor mu?
Hayır, Groupdocs.Viewer for .NET, .NET ortamınızda yerel olarak çalışır ve belge görüntüleme için internet bağlantısı gerektirmez.
### Groupdocs.Viewer for .NET için teknik destek mevcut mu?
 Evet, teknik destek şu adresten sağlanmaktadır:[Grup belgeleri forumu](https://forum.groupdocs.com/c/viewer/9)Soru sorabileceğiniz, sorunları bildirebileceğiniz ve toplulukla etkileşimde bulunabileceğiniz yer.
### Satın almadan önce Groupdocs.Viewer for .NET'i deneyebilir miyim?
 Evet, sağlanan ücretsiz deneme sürümünü kullanarak başlayabilirsiniz.[Deneme sürümü](https://releases.groupdocs.com/).