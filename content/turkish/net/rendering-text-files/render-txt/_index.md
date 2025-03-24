---
title: Metin Dosyalarını İşleme (.txt)
linktitle: Metin Dosyalarını İşleme (.txt)
second_title: GroupDocs.Viewer .NET API'si
description: GroupDocs.Viewer for .NET'i kullanarak metin dosyalarının birden fazla formata kusursuz şekilde dönüştürülmesini keşfedin. Belge yönetimi yeteneklerinizi zahmetsizce geliştirin.
weight: 10
url: /tr/net/rendering-text-files/render-txt/
---

# Metin Dosyalarını İşleme (.txt)

## giriiş
Belge yönetimi ve manipülasyonu alanında, GroupDocs.Viewer for .NET, çeşitli belge formatlarını verimli bir şekilde işlemek için çok sayıda işlevsellik sunan güçlü bir araç olarak ortaya çıkıyor. Bu makalede, metin dosyalarını (.txt) birden çok formatta işlemek için GroupDocs.Viewer for .NET'i kullanmanın incelikleri ele alınmaktadır. Metin dosyalarını HTML, JPG, PNG veya PDF'ye dönüştürmeyi hedefliyorsanız, GroupDocs.Viewer sizi bu görevleri sorunsuz bir şekilde gerçekleştirmeniz için gerekli araçlarla donatır.
## Önkoşullar
Dönüştürme sürecine geçmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### 1. .NET için GroupDocs.Viewer'ın kurulumu
 Geliştirme ortamınızda GroupDocs.Viewer for .NET'in kurulu olduğundan emin olun. Gerekli dosyaları adresinden indirebilirsiniz.[İnternet sitesi](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework ile Temel Bilgi
Bir projenin nasıl oluşturulacağı ve kod tabanınızdaki kitaplıkların nasıl kullanılacağı da dahil olmak üzere .NET çerçevesinin temelleri hakkında bilgi edinin.
### 3. Örnek Metin Dosyaları
Dönüştürmeyi planladığınız örnek metin dosyalarını (.txt) hazırlayın. Bu dosyalar dönüştürme işlemi için girdi görevi görecektir.

## Ad Alanlarını İçe Aktar
Dönüştürme sürecine dalmadan önce gerekli ad alanlarını projenize aktardığınızdan emin olun. Bu, GroupDocs.Viewer for .NET tarafından sağlanan işlevlere sorunsuz bir şekilde erişmenizi sağlar.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Dönüşüm sürecinde size etkili bir şekilde rehberlik etmek için her örneği birden fazla adıma ayıralım:

## 1. Adım: HTML Çıkış Yolunu Tanımlayın
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
HTML çıktı dosyasının tam yolunu belirtin.
## Adım 2: Metin Dosyalarını Çok Sayfalı HTML'ye Oluşturun
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Bir örnek oluştur`Viewer` metin dosyasının yolunu içeren nesne. Yapılandır`HtmlViewOptions` gömülü kaynaklar için ve metin dosyasını çok sayfalı HTML'ye dönüştürün.
## 3. Adım: Tek Sayfalı HTML Çıkış Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Tek sayfalı HTML çıktı dosyasının tam yolunu belirtin.
## Adım 4: Metin Dosyalarını Tek Sayfalı HTML'ye Dönüştürün
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Bir örnek oluştur`Viewer` metin dosyasının yolunu içeren nesne. Yapılandır`HtmlViewOptions` gömülü kaynaklar ve set için`RenderToSinglePage` doğru. Metin dosyasını tek sayfalı bir HTML'ye dönüştürün.
## Adım 5: JPG Çıkış Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
JPG çıktı dosyasının tam yolunu belirtin.
## Adım 6: Metin Dosyalarını JPG'ye Oluşturun
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Bir örnek oluştur`Viewer` metin dosyasının yolunu içeren nesne. Yapılandır`JpgViewOptions` çıkış yolu için ve metin dosyasını JPG formatına dönüştürün.
## Adım 7: PNG Çıkış Yolunu Tanımlayın
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
PNG çıktı dosyasının tam yolunu belirtin.
## Adım 8: Metin Dosyalarını PNG'ye Oluşturun
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Bir örnek oluştur`Viewer` metin dosyasının yolunu içeren nesne. Yapılandır`PngViewOptions` çıkış yolu için ve metin dosyasını PNG formatına dönüştürün.
## Adım 9: PDF Çıkış Yolunu Tanımlayın
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
 Bir örnek oluştur`Viewer` metin dosyasının yolunu içeren nesne. Yapılandır`PdfViewOptions` çıkış yolu için ve metin dosyasını PDF formatına dönüştürün.

## Çözüm
Sonuç olarak, GroupDocs.Viewer for .NET, geliştiricilere metin dosyalarını HTML, JPG, PNG ve PDF dahil olmak üzere çeşitli formatlarda zahmetsizce oluşturma olanağı sağlar. Bu makalede özetlenen adım adım kılavuzu izleyerek GroupDocs.Viewer'ı .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir ve belge yönetimi yeteneklerini geliştirebilirsiniz.
## SSS'ler
### S: GroupDocs.Viewer for .NET, .NET çerçevesinin tüm sürümleriyle uyumlu mudur?
Evet, GroupDocs.Viewer for .NET, çok çeşitli .NET framework sürümleriyle uyumlu olacak şekilde tasarlanmıştır ve geliştirmede çok yönlülük ve esneklik sağlar.
### S: İşlenen belgelerin çıktı görünümünü özelleştirebilir miyim?
Kesinlikle! GroupDocs.Viewer, geliştiricilerin oluşturulan belgelerin görünümünü kendi tercihlerine ve gereksinimlerine göre uyarlamalarına olanak tanıyan kapsamlı özelleştirme seçenekleri sunar.
### S: GroupDocs.Viewer for .NET'in deneme sürümü mevcut mu?
 Evet, şu adreste bulunan ücretsiz deneme sürümüne erişerek GroupDocs.Viewer for .NET'in işlevlerini keşfedebilirsiniz.[İnternet sitesi]( https://releases.groupdocs.com/).
### S: GroupDocs.Viewer for .NET ile ilgili nasıl destek alabilirim veya yardım isteyebilirim?
 GroupDocs.Viewer for .NET ile ilgili her türlü soru, destek veya yardım için erişilebilir özel destek forumunu ziyaret edebilirsiniz.[Burada](https://forum.groupdocs.com/c/viewer/9).
### S: GroupDocs.Viewer for .NET için geçici bir lisans satın alabilir miyim?
Evet, kullanıcılara GroupDocs.Viewer for .NET'i belirli süreler boyunca kullanma konusunda esneklik ve kolaylık sağlayan geçici lisanslar satın alınabilir.