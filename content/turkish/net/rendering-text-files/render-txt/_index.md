---
"description": "GroupDocs.Viewer for .NET'i kullanarak metin dosyalarının birden fazla biçime sorunsuz bir şekilde dönüştürülmesini keşfedin. Belge yönetimi yeteneklerinizi zahmetsizce geliştirin."
"linktitle": "Metin Dosyalarını (.txt) Oluştur"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Metin Dosyalarını (.txt) Oluştur"
"url": "/tr/net/rendering-text-files/render-txt/"
"weight": 10
---

# Metin Dosyalarını (.txt) Oluştur

## giriiş
Belge yönetimi ve düzenlemesi alanında, GroupDocs.Viewer for .NET, çeşitli belge biçimlerini verimli bir şekilde işlemek için çok sayıda işlevsellik sunan güçlü bir araç olarak ortaya çıkıyor. Bu makale, metin dosyalarını (.txt) birden fazla biçime işlemek için GroupDocs.Viewer for .NET'i kullanmanın inceliklerini araştırıyor. Metin dosyalarını HTML, JPG, PNG veya PDF'ye dönüştürmeyi amaçlıyor olun, GroupDocs.Viewer bu görevleri sorunsuz bir şekilde gerçekleştirmeniz için gereken araçları size sağlar.
## Ön koşullar
Dönüştürme sürecine başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
### 1. .NET için GroupDocs.Viewer Kurulumu
Geliştirme ortamınızda GroupDocs.Viewer for .NET'in yüklü olduğundan emin olun. Gerekli dosyaları şuradan indirebilirsiniz: [web sitesi](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework ile Temel Bilgi
.NET framework'ünün temellerini öğrenin; bir projeyi nasıl kuracağınızı ve kod tabanınızdaki kütüphaneleri nasıl kullanacağınızı öğrenin.
### 3. Örnek Metin Dosyaları
Dönüştürmeyi planladığınız örnek metin dosyalarını (.txt) hazırlayın. Bu dosyalar dönüştürme işlemi için girdi görevi görecektir.

## Ad Alanlarını İçe Aktar
Dönüştürme sürecine dalmadan önce, gerekli ad alanlarını projenize aktardığınızdan emin olun. Bu, GroupDocs.Viewer for .NET tarafından sağlanan işlevlere sorunsuz bir şekilde erişmenizi sağlar.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Dönüşüm sürecinde sizi etkili bir şekilde yönlendirmek için her örneği birden fazla adıma bölelim:

## Adım 1: HTML Çıktı Yolunu Tanımlayın
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
HTML çıktı dosyasının tam yolunu belirtin.
## Adım 2: Metin Dosyalarını Çok Sayfalı HTML'ye Dönüştürün
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
Bir örnek oluştur `Viewer` metin dosyasına giden yolu olan nesne. Yapılandır `HtmlViewOptions` gömülü kaynaklar için ve metin dosyasını çok sayfalı HTML'e dönüştürmek için.
## Adım 3: Tek Sayfalık HTML Çıktı Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Tek sayfalık HTML çıktı dosyasının tam yolunu belirtin.
## Adım 4: Metin Dosyalarını Tek Sayfalık HTML'ye Dönüştürün
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
Bir örnek oluştur `Viewer` metin dosyasına giden yolu olan nesne. Yapılandır `HtmlViewOptions` gömülü kaynaklar ve set için `RenderToSinglePage` true olarak ayarlayın. Metin dosyasını tek sayfalık bir HTML'ye dönüştürün.
## Adım 5: JPG Çıktı Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
JPG çıktı dosyasının tam yolunu belirtin.
## Adım 6: Metin Dosyalarını JPG'ye Dönüştürün
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Bir örnek oluştur `Viewer` metin dosyasına giden yolu olan nesne. Yapılandır `JpgViewOptions` çıktı yolunu belirleyin ve metin dosyasını JPG formatına dönüştürün.
## Adım 7: PNG Çıkış Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
PNG çıktı dosyasının tam yolunu belirtin.
## Adım 8: Metin Dosyalarını PNG'ye Dönüştürün
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Bir örnek oluştur `Viewer` metin dosyasına giden yolu olan nesne. Yapılandır `PngViewOptions` çıktı yolunu belirleyin ve metin dosyasını PNG formatına dönüştürün.
## Adım 9: PDF Çıktı Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
PDF çıktı dosyasının tam yolunu belirtin.
## Adım 10: Metin Dosyalarını PDF'ye Dönüştürün
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Bir örnek oluştur `Viewer` metin dosyasına giden yolu olan nesne. Yapılandır `PdfViewOptions` çıktı yolunu belirleyin ve metin dosyasını PDF formatına dönüştürün.

## Çözüm
Sonuç olarak, GroupDocs.Viewer for .NET, geliştiricilerin HTML, JPG, PNG ve PDF gibi çeşitli biçimlerde metin dosyalarını zahmetsizce işlemesini sağlar. Bu makalede özetlenen adım adım kılavuzu izleyerek, GroupDocs.Viewer'ı .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir ve belge yönetimi yeteneklerini geliştirebilirsiniz.
## SSS
### S: GroupDocs.Viewer for .NET, .NET framework'ün tüm sürümleriyle uyumlu mudur?
Evet, GroupDocs.Viewer for .NET, .NET framework sürümlerinin geniş bir yelpazesiyle uyumlu olacak şekilde tasarlanmıştır ve bu sayede geliştirmede çok yönlülük ve esneklik sağlanır.
### S: İşlenmiş belgelerin çıktı görünümünü özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, geliştiricilerin kendi programlarına ve gereksinimlerine göre işlenmiş belgelerin görünümünü özelleştirmelerine olanak tanıyan kapsamlı özelleştirme seçenekleri sunar.
### S: GroupDocs.Viewer for .NET için deneme sürümü mevcut mu?
Evet, GroupDocs.Viewer for .NET'in işlevlerini, web sitesinde bulunan ücretsiz deneme sürümüne erişerek keşfedebilirsiniz. [web sitesi]( https://releases.groupdocs.com/).
### S: GroupDocs.Viewer for .NET ile ilgili destek veya yardıma nasıl ulaşabilirim?
GroupDocs.Viewer for .NET ile ilgili herhangi bir soru, destek veya yardım için, erişilebilen özel destek forumunu ziyaret edebilirsiniz. [Burada](https://forum.groupdocs.com/c/viewer/9).
### S: GroupDocs.Viewer for .NET için geçici bir lisans satın alabilir miyim?
Evet, geçici lisanslar satın alınabilir ve kullanıcılara GroupDocs.Viewer for .NET'i belirli süreler boyunca kullanmada esneklik ve kolaylık sağlar.