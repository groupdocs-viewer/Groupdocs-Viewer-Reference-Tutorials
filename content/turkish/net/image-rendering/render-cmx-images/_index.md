---
"description": "GroupDocs.Viewer for .NET kullanarak CMX görüntülerini çeşitli formatlara zahmetsizce nasıl dönüştüreceğinizi öğrenin. Belge yönetiminizi geliştirin."
"linktitle": "CMX Görüntülerini Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CMX Görüntülerini Oluştur"
"url": "/tr/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# CMX Görüntülerini Oluştur

## giriiş
Belge yönetimi ve düzenlemesi alanında, çeşitli biçimlerdeki görüntüleri işlemek çok önemli bir görevdir. GroupDocs.Viewer for .NET, CMX görüntülerini HTML, JPG, PNG ve PDF gibi farklı biçimlere işlemek için kapsamlı işlevler sağlayarak bu süreci basitleştirir. Bu eğitim, GroupDocs.Viewer for .NET kullanarak CMX görüntülerini işlemenin adım adım sürecinde size rehberlik edecektir.

![.NET için GroupDocs.Viewer ile CMX Görüntülerini Oluşturun](/viewer/image-rendering/render-cmx-images.png)

## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
1. GroupDocs.Viewer for .NET Kitaplığı: GroupDocs.Viewer for .NET kitaplığını şu adresten indirin ve yükleyin: [Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET Framework ile çalışan bir geliştirme ortamı kurun.
3. CMX Görüntü Dosyası: Oluşturmak istediğiniz bir CMX görüntü dosyası edinin.

## Ad Alanlarını İçe Aktarma
Devam etmeden önce, .NET uygulamanızda GroupDocs.Viewer işlevlerine erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## HTML'ye dönüştürme
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Çıktı Dizinini Tanımla: İşlenen HTML dosyalarını depolamak istediğiniz dizini ayarlayın.
- Dosya Yolu Biçimini Belirle: Çıktı HTML dosyaları için biçimi tanımlayın.
- Görüntüleyici Nesnesini Oluştur: CMX görüntü dosyasıyla Görüntüleyici sınıfının bir örneğini oluşturun.
- HTML Oluşturma Seçenekleri: Kaynakları yerleştirme gibi HTML oluşturma seçeneklerini yapılandırın.
- CMX'i HTML'ye Dönüştür: CMX görüntüsünü HTML'ye dönüştürmek için görüntüleyici nesnesinin Görünüm yöntemini çağırın.
## JPG'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Çıktı Dizinini Tanımla: İşlenen JPG dosyalarının depolanacağı dizini ayarlayın.
- Dosya Yolu Biçimini Belirle: Çıktı JPG dosyaları için biçimi tanımlayın.
- Görüntüleyici Nesnesini Oluştur: CMX görüntü dosyasıyla Görüntüleyici sınıfının bir örneğini oluşturun.
- JPG Oluşturma Seçenekleri: JPG oluşturma seçeneklerini yapılandırın.
- CMX'i JPG'ye Dönüştür: CMX görüntüsünü JPG'ye dönüştürmek için görüntüleyici nesnesinin Görünüm yöntemini çağırın.
## PNG'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Çıktı Dizinini Tanımla: İşlenmiş PNG dosyalarının depolanacağı dizini ayarlayın.
- Dosya Yolu Biçimini Belirleyin: Çıktı PNG dosyaları için biçimi tanımlayın.
- Görüntüleyici Nesnesini Oluştur: CMX görüntü dosyasıyla Görüntüleyici sınıfının bir örneğini oluşturun.
- PNG Oluşturma Seçenekleri: PNG oluşturma seçeneklerini yapılandırın.
- CMX'i PNG'ye dönüştür: CMX görüntüsünü PNG'ye dönüştürmek için görüntüleyici nesnesinin Görünüm yöntemini çağırın.
## PDF'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Çıktı Dizinini Tanımla: İşlenen PDF dosyasının depolanacağı dizini ayarlayın.
- Dosya Yolu Biçimini Belirle: Çıktı PDF dosyasının biçimini tanımlayın.
- Görüntüleyici Nesnesini Oluştur: CMX görüntü dosyasıyla Görüntüleyici sınıfının bir örneğini oluşturun.
- PDF Oluşturma Seçenekleri: PDF oluşturma seçeneklerini yapılandırın.
- CMX'i PDF'e Dönüştür: CMX görüntüsünü PDF'e dönüştürmek için görüntüleyici nesnesinin Görünüm yöntemini çağırın.

## Çözüm
Sonuç olarak, GroupDocs.Viewer for .NET, CMX görüntülerini çeşitli biçimlere sorunsuz bir şekilde işlemek için sağlam bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, CMX görüntü işleme yeteneklerini .NET uygulamalarınıza zahmetsizce entegre edebilir ve belge yönetimi verimliliğini artırabilirsiniz.
## SSS
### CMX görüntüsünün belirli sayfalarını işleyebilir miyim?
Evet, oluşturma seçeneklerinde sayfa numarasını belirterek belirli sayfaları oluşturabilirsiniz.
### GroupDocs.Viewer for .NET tüm .NET framework'leriyle uyumlu mudur?
Evet, GroupDocs.Viewer for .NET, .NET Core ve .NET Framework dahil olmak üzere birden fazla .NET framework ile uyumludur.
### GroupDocs.Viewer şifrelenmiş CMX görüntülerinin işlenmesini destekliyor mu?
Evet, GroupDocs.Viewer şifrelenmiş CMX görüntülerinin uygun şifre çözme anahtarlarıyla işlenmesini destekler.
### Farklı çıktı biçimleri için işleme seçeneklerini özelleştirebilir miyim?
Kesinlikle, GroupDocs.Viewer gereksinimlerinize göre işleme parametrelerini özelleştirmek için kapsamlı seçenekler sunar.
### GroupDocs.Viewer desteği için bir topluluk forumu var mı?
Evet, destek forumunda GroupDocs.Viewer topluluğuyla yardım arayabilir ve etkileşimde bulunabilirsiniz [Burada](https://forum.groupdocs.com/c/viewer/9).