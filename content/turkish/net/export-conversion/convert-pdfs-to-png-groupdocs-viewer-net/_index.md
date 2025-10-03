---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET kullanarak PDF sayfalarını orijinal boyutları koruyarak PNG görüntülerine nasıl dönüştüreceğinizi öğrenin. Bu kılavuz kurulum, yapılandırma ve en iyi uygulamaları kapsar."
"title": "GroupDocs.Viewer for .NET kullanarak PDF'leri orijinal boyutta PNG'ye dönüştürün"
"url": "/tr/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# GroupDocs.Viewer for .NET kullanarak PDF'leri orijinal boyutta PNG'ye dönüştürün

## giriiş

PDF dosyalarını orijinal sayfa boyutunu koruyarak PNG görüntülerine dönüştürmek, yüksek kaliteli belge dijitalleştirme veya web içeriği hazırlama için önemlidir. Bu eğitim, PDF sayfalarını orijinal boyutlarını koruyarak PNG dosyaları olarak işlemek için GroupDocs.Viewer for .NET'i kullanma konusunda size rehberlik edecektir.

![GroupDocs.Viewer for .NET ile PDF'leri Orijinal Boyutlu PNG'ye Dönüştürün](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Ne Öğreneceksiniz:**
- Projenizde .NET için GroupDocs.Viewer nasıl kurulur ve yapılandırılır
- Sayfa boyutlarını koruyarak PDF'leri PNG görüntülerine dönüştürmenin adım adım süreci
- En iyi performans için temel yapılandırma seçenekleri ve en iyi uygulamalar

Bu eğitimin sonunda, bu işlevselliği uygulamalarınıza sorunsuz bir şekilde entegre edebileceksiniz. Başlamak için gerekli ön koşullarla başlayalım.

## Ön koşullar

GroupDocs.Viewer for .NET'i projenize uygulamadan önce aşağıdaki gereksinimlerin karşılandığından emin olun:

### Gerekli Kütüphaneler ve Sürümler
- **.NET için GroupDocs.Viewer**: Sürüm 25.3.0 veya üzeri.

### Çevre Kurulum Gereksinimleri
- Visual Studio gibi uyumlu bir geliştirme ortamı.
- C# programlamanın temel bilgisi.

### Bilgi Önkoşulları
- NuGet paket yönetimi konusunda bilgi sahibi olmak.
- .NET uygulamalarında PDF'ler ve görüntü işleme konusunda deneyim.

Bu ön koşullar sağlandıktan sonra GroupDocs.Viewer for .NET kurulumuna geçebiliriz.

## .NET için GroupDocs.Viewer Kurulumu

GroupDocs.Viewer for .NET'i kullanmaya başlamak için aşağıdaki kurulum adımlarını izleyin:

### NuGet Paket Yöneticisi Konsolu aracılığıyla kurulum
Projenizi Visual Studio'da açın ve aşağıdaki komutu kullanın:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### .NET CLI aracılığıyla kurulum
Alternatif olarak, şu komutla .NET CLI'yi kullanarak yükleyebilirsiniz:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Lisans Edinme Adımları
1. **Ücretsiz Deneme**: Deneme sürümünü şu adresten indirin: [GroupDocs İndirmeleri](https://releases.groupdocs.com/viewer/net/).
2. **Geçici Lisans**: Tam özellikleri keşfetmek için geçici bir lisans edinin [Geçici Lisans Sayfası](https://purchase.groupdocs.com/temporary-license/).
3. **Satın almak**: Uzun süreli kullanım için, şu adresten bir lisans satın alın: [Sayfayı satın al](https://purchase.groupdocs.com/buy).

### Temel Başlatma ve Kurulum
C# projenizde .NET için GroupDocs.Viewer'ı başlatmak için şu adımları izleyin:
1. Gerekli ad alanlarını içe aktarın:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Giriş PDF'niz ve çıkış dizininiz için yolları ayarlayın.
3. Başlat `Viewer` kaynak belgenizin yolunu şu kod parçacığında gösterildiği gibi belirtin:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Uygulama Kılavuzu
Bu bölüm, PDF sayfalarının orijinal boyutlarını koruyarak PNG görüntüleri olarak işlenmesinin uygulanmasını kapsamaktadır.

### PDF Sayfalarını Orijinal Sayfa Boyutuyla PNG'ye Dönüştürme
#### Genel bakış
Bu özellik, bir PDF belgesinin her sayfasını orijinal boyutlarını koruyarak bir PNG görüntüsüne dönüştürmenize olanak tanır. Bu, belgelerin hassas görsel temsilini gerektiren uygulamalar için özellikle yararlıdır.

##### Adım 1: Yolları Ayarlayın ve Görüntüleyiciyi Başlatın
Giriş PDF yolunuz ve çıktı dizininiz için değişkenler oluşturun:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Başlat `Viewer` kaynak belgenizin yolunu içeren sınıf:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Kod bloğu bir sonraki adımda devam edecek
}
```
##### Adım 2: PngViewOptions'ı yapılandırın
Bir örnek oluşturun `PngViewOptions`, çıktı görüntüleri için bir dosya adlandırma düzeni belirterek:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Görüntüleyici seçeneklerini her sayfanın orijinal boyutunda görüntülenmesini sağlayacak şekilde yapılandırın:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Adım 3: Belge Sayfalarını Oluşturun
Ara `View` yönteminiz `Viewer` örneğin, yapılandırılmış görünüm seçeneklerini iletmek:
```csharp
viewer.View(viewOptions);
```
### Sorun Giderme İpuçları
- Yolların doğru olduğundan ve dizinlerin mevcut olduğundan emin olun.
- Giriş dizinlerinden okuma ve çıkış dizinlerine yazma için gerekli izinlere sahip olduğunuzu doğrulayın.

## Pratik Uygulamalar
1. **Belge Dijitalleştirme**: Arşiv PDF belgelerini daha kolay erişim ve dağıtım için dijital görüntülere dönüştürün.
2. **Web Portalları**: PDF okuyucularına ihtiyaç duymadan web sitelerinde belge önizlemelerini görüntüleyin.
3. **İçerik Yönetim Sistemleri (CMS)**: Büyük hacimli PDF içeriklerini etkin bir şekilde yönetmek ve görüntülemek için CMS platformlarıyla entegre edin.

## Performans Hususları
GroupDocs.Viewer for .NET kullanarak uygulamanızın performansını optimize etmek için:
- Büyük dosyalarla uğraşıyorsanız, belgeleri parçalar halinde işleyerek bellek kullanımını sınırlayın.
- İşleme sırasında iş parçacıklarının engellenmesini önlemek için mümkün olduğunca asenkron yöntemleri kullanın.
- Elden çıkarmak `Viewer` Kaynakları serbest bırakmak için kullanımdan hemen sonra örnekler.

## Çözüm
Bu eğitimde, .NET için GroupDocs.Viewer kullanarak PDF sayfalarını orijinal boyutlarını koruyarak PNG görüntüleri olarak nasıl işleyeceğiniz konusunda bilgi edindiniz. Ortamınızı kurmayı, en iyi sonuçlar için gerekli seçenekleri yapılandırmayı ve bu işlevsellik için pratik uygulamaları inceledik.

Sonraki adımlar arasında GroupDocs.Viewer'da bulunan diğer işleme seçeneklerini denemek veya gelişmiş belge yönetimi yetenekleri için bunu daha büyük projelere entegre etmek yer alıyor.

## SSS Bölümü
1. **GroupDocs.Viewer ile büyük PDF dosyalarını yönetmenin en iyi yolu nedir?**
   - Belgeleri daha küçük parçalara bölün ve performansı korumak için eşzamansız yöntemler kullanın.
2. **Çıktı PNG dosya adlarını özelleştirebilir miyim?**
   - Evet, bir adlandırma kalıbı belirterek `PngViewOptions`.
3. **Sadece belirli sayfaları oluşturmak mümkün mü?**
   - Kesinlikle yapılandırabilirsiniz `PageNumbers` içinde `PngViewOptions` hangi sayfaların işleneceğini belirtmek için.
4. **GroupDocs.Viewer için lisanslamayı nasıl hallederim?**
   - Seçenekler arasında ücretsiz deneme, geçici lisans veya tam lisans satın alma yer alıyor.
5. **Bu kurulum web uygulamalarında kullanılabilir mi?**
   - Evet, ASP.NET Core ve diğer .NET tabanlı web çerçevelerinde PDF'lerin sunucu tarafında işlenmesi için uygundur.

## Kaynaklar
- [Belgeleme](https://docs.groupdocs.com/viewer/net/)
- [API Referansı](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer'ı indirin](https://releases.groupdocs.com/viewer/net/)
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme](https://releases.groupdocs.com/viewer/net/)
- [Geçici Lisans](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)