---
title: CMX Görüntülerini İşle
linktitle: CMX Görüntülerini İşle
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak CMX görüntülerini zahmetsizce çeşitli formatlara nasıl dönüştüreceğinizi öğrenin. Belge yönetiminizi geliştirin.
type: docs
weight: 13
url: /tr/net/image-rendering/render-cmx-images/
---
## giriiş
Belge yönetimi ve manipülasyonu alanında, çeşitli formatlardaki görüntülerin işlenmesi çok önemli bir görevdir. GroupDocs.Viewer for .NET, CMX görüntülerini HTML, JPG, PNG ve PDF gibi farklı formatlara dönüştürmek için kapsamlı işlevler sağlayarak bu süreci basitleştirir. Bu eğitim, GroupDocs.Viewer for .NET'i kullanarak CMX görüntülerini adım adım işleme sürecinde size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  GroupDocs.Viewer for .NET Kitaplığı: GroupDocs.Viewer for .NET kitaplığını şuradan indirip yükleyin:[Burada](https://releases.groupdocs.com/viewer/net/).
2. Geliştirme Ortamı: .NET çerçevesiyle kurulmuş, çalışan bir geliştirme ortamına sahip olun.
3. CMX Görüntü Dosyası: Oluşturmak istediğiniz bir CMX görüntü dosyasını edinin.

## Ad Alanlarını İçe Aktarma
Devam etmeden önce, .NET uygulamanızdaki GroupDocs.Viewer işlevlerine erişmek için gerekli ad alanlarını içe aktardığınızdan emin olun:
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
- Çıktı Dizinini Tanımla: Oluşturulan HTML dosyalarını depolamak istediğiniz dizini ayarlayın.
- Dosya Yolu Formatını Belirtin: Çıktı HTML dosyalarının formatını tanımlayın.
- Görüntüleyici Nesnesini Örneklendirin: CMX görüntü dosyasıyla Viewer sınıfının bir örneğini oluşturun.
- HTML İşleme Seçenekleri: Kaynakları gömme gibi HTML işleme seçeneklerini yapılandırın.
- CMX'i HTML'ye Oluştur: CMX görüntüsünü HTML'ye dönüştürmek için görüntüleyici nesnesinin View yöntemini çağırın.
## JPG'ye dönüştürülüyor
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Çıkış Dizinini Tanımla: Oluşturulan JPG dosyalarının saklanacağı dizini ayarlayın.
- Dosya Yolu Formatını Belirtin: Çıktı JPG dosyalarının formatını tanımlayın.
- Görüntüleyici Nesnesini Örneklendirin: CMX görüntü dosyasıyla Viewer sınıfının bir örneğini oluşturun.
- JPG Oluşturma Seçenekleri: JPG oluşturma seçeneklerini yapılandırın.
- CMX'i JPG'ye Oluştur: CMX görüntüsünü JPG'ye dönüştürmek için görüntüleyici nesnesinin View yöntemini çağırın.
## PNG'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Çıktı Dizinini Tanımla: İşlenen PNG dosyalarını depolamak için dizini ayarlayın.
- Dosya Yolu Formatını Belirtin: Çıktı PNG dosyalarının formatını tanımlayın.
- Görüntüleyici Nesnesini Örneklendirin: CMX görüntü dosyasıyla Viewer sınıfının bir örneğini oluşturun.
- PNG Oluşturma Seçenekleri: PNG oluşturma seçeneklerini yapılandırın.
- CMX'i PNG'ye Oluştur: CMX görüntüsünü PNG'ye dönüştürmek için görüntüleyici nesnesinin View yöntemini çağırın.
## PDF'ye dönüştürme
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Çıktı Dizinini Tanımla: İşlenen PDF dosyasının saklanacağı dizini ayarlayın.
- Dosya Yolu Formatını Belirtin: Çıktı PDF dosyasının formatını tanımlayın.
- Görüntüleyici Nesnesini Örneklendirin: CMX görüntü dosyasıyla Viewer sınıfının bir örneğini oluşturun.
- PDF Oluşturma Seçenekleri: PDF oluşturma seçeneklerini yapılandırın.
- CMX'i PDF'ye Oluştur: CMX görüntüsünü PDF'ye dönüştürmek için görüntüleyici nesnesinin View yöntemini çağırın.

## Çözüm
Sonuç olarak GroupDocs.Viewer for .NET, CMX görüntülerini çeşitli formatlara sorunsuz bir şekilde dönüştürmek için güçlü bir çözüm sunar. Bu eğitimde özetlenen adımları izleyerek, CMX görüntü oluşturma yeteneklerini zahmetsizce .NET uygulamalarınıza entegre edebilir, belge yönetimi verimliliğini artırabilirsiniz.
## SSS'ler
### Bir CMX görüntüsünün belirli sayfalarını oluşturabilir miyim?
Evet, oluşturma seçeneklerinde sayfa numarasını belirterek belirli sayfaları oluşturabilirsiniz.
### GroupDocs.Viewer for .NET tüm .NET çerçeveleriyle uyumlu mu?
Evet, GroupDocs.Viewer for .NET, .NET Core ve .NET Framework dahil olmak üzere birden fazla .NET çerçevesiyle uyumludur.
### GroupDocs.Viewer şifrelenmiş CMX görüntülerinin oluşturulmasını destekliyor mu?
Evet, GroupDocs.Viewer şifrelenmiş CMX görüntülerinin uygun şifre çözme anahtarlarıyla oluşturulmasını destekler.
### Farklı çıktı formatları için işleme seçeneklerini özelleştirebilir miyim?
GroupDocs.Viewer kesinlikle gereksinimlerinize göre işleme parametrelerini özelleştirmek için kapsamlı seçenekler sunar.
### GroupDocs.Viewer desteği için bir topluluk forumu var mı?
 Evet, destek forumunda yardım isteyebilir ve GroupDocs.Viewer topluluğuyla etkileşime geçebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).