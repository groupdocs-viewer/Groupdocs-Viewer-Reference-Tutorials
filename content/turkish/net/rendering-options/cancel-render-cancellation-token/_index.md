---
"description": "Verimli belge görüntüleme için Groupdocs.Viewer for .NET'i .NET projelerinize sorunsuz bir şekilde entegre edin."
"linktitle": "İptal Token'ı ile Render'ı İptal Et"
"second_title": "GroupDocs.Viewer .NET API"
"title": "İptal Token'ı ile Render'ı İptal Et"
"url": "/tr/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# İptal Token'ı ile Render'ı İptal Et

## giriiş
Groupdocs.Viewer for .NET, .NET uygulamaları içinde belge görüntüleme ve işlemeyi basitleştirmek için tasarlanmış güçlü bir araçtır. İster PDF'lerle, ister Microsoft Office belgeleriyle veya diğer yaygın biçimlerle uğraşıyor olun, bu kitaplık belge görüntüleme yeteneklerini .NET projelerinize sorunsuz bir şekilde entegre etmek için sağlam işlevler sunar.
## Ön koşullar
Groupdocs.Viewer for .NET entegrasyonuna başlamadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:
1. Kurulum: Sağlanan kaynaktan Groupdocs.Viewer for .NET kitaplığını indirin ve kurun. [indirme bağlantısı](https://releases.groupdocs.com/viewer/net/).
   
2. Lisans: Lisans alın [Grup dokümanları](https://purchase.groupdocs.com/buy) kütüphanenin tüm potansiyelini açığa çıkarmak için. Alternatif olarak, ücretsiz denemeyle başlayabilirsiniz [geçici lisans](https://purchase.groupdocs.com/temporary-license/).
   
3. Geliştirme Ortamı: Visual Studio veya seçtiğiniz herhangi bir .NET IDE dahil olmak üzere uyumlu bir geliştirme ortamı kurduğunuzdan emin olun.

## Ad Alanlarını İçe Aktar
Groupdocs.Viewer for .NET'i etkili bir şekilde kullanmak için, gerekli ad alanlarını projenize aktarmanız gerekir. Şu adımları izleyin:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Şimdi, daha iyi anlaşılması ve uygulanması için verilen örneği birden fazla adıma bölelim:
## Adım 1: Çıktı Dizinini Tanımlayın
```csharp
string outputDirectory = "Your Document Directory";
```
Bu adım, oluşturulan belge sayfalarının saklanacağı dizini belirler.
## Adım 2: Sayfa Dosyası Yolu Biçimini Tanımlayın
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Burada, bireysel belge sayfalarının dosya yollarının biçimini tanımlıyoruz.
## Adım 3: CancellationTokenSource'u başlatın
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource, asenkron işlemleri iptal etmek için kullanılabilen CancellationToken örneklerini oluşturmak için kullanılır.
## Adım 4: CancellationToken'ı edinin
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Bu adım, işleme işlemini iptal etmek için kullanılacak olan token'ı CancellationTokenSource'dan alır.
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
Burada, Task.Run() kullanarak belge sayfalarının eşzamansız olarak işlenmesini başlatıyoruz. Viewer örneği belirtilen belge dosyasıyla (SAMPLE_DOCX) oluşturulur ve işleme seçenekleri yapılandırılır. İşleme süreci daha sonra Viewer sınıfının View yöntemi kullanılarak başlatılır.
## Adım 6: Render Zaman Aşımını Ayarlayın
```csharp
cancellationTokenSource.CancelAfter(10);
```
Bu adım, işleme işlemi için 10 milisaniyelik bir zaman aşımı süresi ayarlar. İşlem bu zaman aşımını aşarsa, otomatik olarak iptal edilir.
## Adım 7: Başarı Mesajını Göster
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Son olarak belgenin başarıyla oluşturulduğunu belirten bir başarı mesajı görüntülenir.

## Çözüm
Bu eğitimde, Groupdocs.Viewer for .NET'i projelerinize entegre etmenin temellerini ele aldık. Yukarıda özetlenen adımları izleyerek, .NET uygulamalarınıza belge görüntüleme yeteneklerini sorunsuz bir şekilde entegre edebilir, kullanıcı deneyimini ve üretkenliği artırabilirsiniz.
## SSS
### Groupdocs.Viewer for .NET tüm belge formatlarıyla uyumlu mudur?
Groupdocs.Viewer for .NET, PDF, Microsoft Office belgeleri, resimler ve daha fazlası dahil olmak üzere çok çeşitli belge biçimlerini destekler.
### İşlenmiş belge sayfalarının görünümünü özelleştirebilir miyim?
Evet, sayfa boyutu, kalite, filigranlama ve daha fazlası dahil olmak üzere oluşturma sürecinin çeşitli yönlerini özelleştirebilirsiniz.
### Groupdocs.Viewer for .NET internet bağlantısı gerektiriyor mu?
Hayır, Groupdocs.Viewer for .NET, .NET ortamınızda yerel olarak çalışır ve belge görüntüleme için internet bağlantısı gerektirmez.
### Groupdocs.Viewer for .NET için teknik destek mevcut mu?
Evet, teknik destek şu şekilde sağlanmaktadır: [Groupdocs forumu](https://forum.groupdocs.com/c/viewer/9)Soru sorabileceğiniz, sorunları bildirebileceğiniz ve toplulukla etkileşimde bulunabileceğiniz bir yer.
### Satın almadan önce Groupdocs.Viewer for .NET'i deneyebilir miyim?
Evet, sağlanan ücretsiz denemeyi kullanarak başlayabilirsiniz [deneme sürümü](https://releases.groupdocs.com/).