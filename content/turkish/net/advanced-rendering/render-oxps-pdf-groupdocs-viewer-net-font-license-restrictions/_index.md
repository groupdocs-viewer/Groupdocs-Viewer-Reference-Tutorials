---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET kullanarak font lisans kısıtlamalarını aşarak PDF ve OXPS belgelerini nasıl oluşturacağınızı öğrenin. Kurulumu, uygulamayı ve pratik uygulamaları keşfedin."
"title": "GroupDocs.Viewer .NET&#58;i Kullanarak Yazı Tipi Kısıtlamalarıyla PDF/OXPS Oluşturun Kapsamlı Bir Kılavuz"
"url": "/tr/net/advanced-rendering/render-oxps-pdf-groupdocs-viewer-net-font-license-restrictions/"
"weight": 1
---

# GroupDocs.Viewer .NET Kullanarak Yazı Tipi Kısıtlamalarıyla PDF/OXPS Oluşturma: Kapsamlı Bir Kılavuz

## giriiş

XPS veya OXPS belgelerini işlemek, font lisans kısıtlamaları nedeniyle zor olabilir. Bu eğitim, bu belgeleri etkili bir şekilde işlemeniz için size rehberlik edecektir. **.NET için GroupDocs.Viewer**Belge yönetim sistemleri, içerik yayınlama platformları ve kusursuz belge dönüşümü gerektiren uygulamalar için ideal olan bu çözüm paha biçilmezdir.

![.NET için GroupDocs.Viewer'da Yazı Tipi Kısıtlamalarıyla PDF/OXPS Oluşturma](/viewer/advanced-rendering/render-pdf-oxps-font-restrictions-img.png)

Bu kılavuzda şunları öğreneceksiniz:
- .NET için GroupDocs.Viewer'ı ayarlayın
- XPS/OXPS belgelerini gömülü yazı tipleriyle işleyin
- İşleme sırasında font lisans kısıtlamalarını devre dışı bırak

## Ön koşullar

Başlamadan önce aşağıdakileri sağlayın:

### Gerekli Kütüphaneler ve Sürümler
- **.NET için GroupDocs.Viewer**: Sürüm 25.3.0 veya üzeri.
- **Geliştirme Ortamı**: Visual Studio (2017 veya daha yenisi) veya .NET geliştirmeyi destekleyen herhangi bir uyumlu IDE.

### Çevre Kurulum Gereksinimleri
- Seçtiğiniz IDE'de AC# projesi.
- Kütüphane kurulumu için NuGet Paket Yöneticisine erişim.

### Bilgi Önkoşulları
- C# ve .NET framework kavramlarının temel düzeyde anlaşılması.
- .NET ortamında dosya yolları ve dizinleri kullanma konusunda bilgi sahibi olmak.

Önkoşulları tamamladıktan sonra, .NET için GroupDocs.Viewer'ı kuralım.

## .NET için GroupDocs.Viewer Kurulumu

### Kurulum Bilgileri

GroupDocs.Viewer'ı NuGet Paket Yöneticisi Konsolu'nu veya .NET CLI'yi kullanarak yükleyin:

**NuGet Paket Yöneticisi Konsolu**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET Komut Satırı Arayüzü**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Özellikleri keşfetmek için ücretsiz denemeyle başlayın.
- **Geçici Lisans**:Uzun süreli değerlendirme için geçici lisans alın.
- **Satın almak**: Tam erişim ve destek için satın almayı düşünün.

### Temel Başlatma ve Kurulum

Kurulumdan sonra, C# projenizde GroupDocs.Viewer'ı başlatın:

```csharp
using System;
using GroupDocs.Viewer;

namespace DocumentRendering
{
    class Program
    {
        static void Main(string[] args)
        {
            // Viewer nesnesini belgenizin yoluyla başlatın
            using (Viewer viewer = new Viewer("path/to/your/document.oxps"))
            {
                Console.WriteLine("GroupDocs.Viewer is set up and ready!");
            }
        }
    }
}
```

GroupDocs.Viewer yapılandırıldıktan sonra, yazı tipi lisans kısıtlamaları devre dışı bırakılmış OXPS belgelerinin işlenmesini uygulayalım.

## Uygulama Kılavuzu

### XPS/OXPS Belgelerinin Font Lisans Kısıtlamaları Devre Dışı Bırakılarak İşlenmesi

#### Genel bakış
Bu özellik, gömülü font lisans doğrulamalarını atlayarak XPS veya OXPS belgelerini işlemenize olanak tanır. Lisans kısıtlamaları olan tescilli fontlarla uğraşırken faydalıdır.

#### Adım Adım Uygulama
**Çıktı Dizini ve Sayfa Dosyası Yolu Biçimini Tanımlayın**
Çıktı dizininizi ayarlayın:

```csharp
string outputDirectory = "YOUR_OUTPUT_DIRECTORY"; // İstediğiniz çıktı dizini yolunu kullanın
string pageFilePathFormat = System.IO.Path.Combine(outputDirectory, "page_{0}.png");
```
Bu kod parçası, işlenen sayfaların nereye kaydedileceğini belirtir.

**Bir Görüntüleyici Örneği Oluşturun**
Başlat `Viewer` OXPS belgesi için nesne:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TestFiles.OXPS_EMBEDDED_FONT")) // Gerçek belge yolunuzla değiştirin
{
    // Daha sonraki yapılandırma ve render adımları burada yer alacak.
}
```
Bu adım, belgeyi işleme hazırlar.

**HTML Görünüm Seçeneklerini Ayarla**
Yapılandır `HtmlViewOptions` gömülü kaynaklarla işlemek için:

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Bu seçenek, tüm gerekli kaynakların her sayfa dosyasına yerleştirilmesini sağlayarak çevrimdışı erişimi kolaylaştırır.

**Font Lisans Doğrulamalarını Devre Dışı Bırak**
Bu özelliği ayarlayarak yazı tipi lisans doğrulamalarını devre dışı bırakın:

```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
Bu doğrulamayı devre dışı bırakarak, font lisanslama sorunlarının engellemesine maruz kalmadan belgeleri işleyebilirsiniz.

**Belgeyi Oluştur**
Son olarak, şunu kullanın: `View` Belgenizi belirtilen seçeneklerle oluşturma yöntemi:

```csharp
viewer.View(options);
```
Bu komut, yapılandırmalarınıza göre işleme sürecini yürütür.

#### Sorun Giderme İpuçları
- **Eksik Yazı Tipleri**: Gerekli tüm yazı tiplerinin belgeye yüklendiğinden veya yerleştirildiğinden emin olun.
- **Dosya Yolu Sorunları**: Dizin yollarını ve dosya adlarını yazım hatalarına karşı iki kez kontrol edin.
- **Lisans Hataları**Lisanslama sorunlarıyla karşılaşırsanız geçerli bir lisansınız olduğunu doğrulayın.

## Pratik Uygulamalar

### Gerçek Dünya Kullanım Örnekleri
1. **İçerik Yayınlama Platformları**: Yasal kısıtlamalar olmaksızın, tescilli yazı tipleriyle belgeleri oluşturun.
2. **Belge Yönetim Sistemleri**: Farklı platformlarda kesintisiz belge görüntülemeyi garantileyin.
3. **Hukuk ve Finans Endüstrileri**: Belirli yazı tipi kullanımını gerektiren hassas belgeleri işleyin.
4. **Akademik Kurumlar**Diyagramlar ve metinler içeren araştırma makalelerini paylaşın.
5. **Pazarlama Ajansları**:Görsel olarak tutarlı sunumlar ve raporlar oluşturun.

### Entegrasyon Olanakları
- Dinamik belge görüntüleme için .NET web uygulamalarıyla bütünleştirin.
- İşlenmiş belgelere çevrimdışı erişim sağlamak için masaüstü uygulamalarında kullanın.
- Ölçeklenebilir belge yönetimi için Azure Blob Storage veya AWS S3 gibi bulut depolama çözümleriyle birleştirin.

## Performans Hususları

### Performansı Optimize Etme
- **Bellek Yönetimi**: Belleği etkin bir şekilde yöneterek elden çıkarın `Viewer` kullanımdan sonra nesneler.
- **Kaynak Kullanımı**: Özellikle büyük belge grupları oluşturulurken kaynak kullanımını izleyin.
- **Toplu İşleme**: Birden fazla belgeyi verimli bir şekilde işlemek için toplu işlemeyi uygulayın.

### GroupDocs.Viewer ile .NET Bellek Yönetimi için En İyi Uygulamalar
- Her zaman sarın `Viewer` bir örnekte `using` uygun şekilde bertaraf edilmesini sağlamak için yapılan açıklama.
- Bellek sızıntılarını veya yüksek kaynak tüketim alanlarını belirlemek ve gidermek için uygulamanızın profilini çıkarın.

## Çözüm

Bu eğitimde, yazı tipi lisans kısıtlamalarını devre dışı bırakarak XPS/OXPS belgelerinin nasıl işleneceğini inceledik. **.NET için GroupDocs.Viewer**. Belirtilen adımları izleyerek çeşitli uygulamalarda belge oluşturmayı etkili bir şekilde yönetebilirsiniz.

Sonraki adımlar olarak, ek GroupDocs.Viewer özelliklerini keşfetmeyi ve bunları projelerinize entegre etmeyi düşünün. Bu güçlü kütüphaneden tam olarak yararlanmak için farklı belge türleri ve yapılandırmaları deneyin.

## SSS Bölümü

1. **GroupDocs.Viewer for .NET nedir?**
   - Geliştiricilerin yerel yazılım kurulumlarına ihtiyaç duymadan uygulamaları içerisinde çeşitli belge formatlarını oluşturmalarına olanak tanıyan çok yönlü bir kütüphanedir.

2. **GroupDocs.Viewer ile font lisanslama sorunlarını nasıl çözebilirim?**
   - Kullanarak `DisableFontLicenseVerifications` özelliği sayesinde, render sırasında font lisans kısıtlamalarını aşabilirsiniz.

3. **GroupDocs.Viewer'ı bulut ortamında kullanabilir miyim?**
   - Evet, bulut uygulamaları ve hizmetleriyle kusursuz bir şekilde çalışacak şekilde tasarlanmıştır.

4. **GroupDocs.Viewer'ı entegre ederken karşılaşılan yaygın zorluklar nelerdir?**
   - Karşılaşılabilecek zorluklar arasında bağımlılıkları yönetmek, çıktı yollarını yapılandırmak ve büyük belge hacimlerini verimli bir şekilde yönetmek yer alabilir.

5. **GroupDocs.Viewer'da standart dışı fontlar için destek var mı?**
   - Gömülü yazı tiplerini işleyebilse de, işleme sorunlarından kaçınmak için gerekli tüm yazı tiplerinin mevcut olduğundan veya belgelerinize gömüldüğünden emin olun.