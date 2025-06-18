---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET'i kullanarak Arial gibi yazı tiplerini HTML dönüşümlerinden nasıl hariç tutacağınızı öğrenin ve platformlar arasında tutarlı markalamayı garantileyin."
"title": ".NET için GroupDocs.Viewer Kullanılarak HTML Çıktısından Belirli Yazı Tipleri Nasıl Hariç Tutulur"
"url": "/tr/net/advanced-rendering/exclude-fonts-html-groupdocs-viewer-net/"
"weight": 1
---

# .NET için GroupDocs.Viewer Kullanılarak Yazı Tipleri HTML Çıktısından Nasıl Hariç Tutulur

## giriiş

Belgeleri HTML biçimine dönüştürürken, kullanılan yazı tipleri üzerinde kontrol sağlamak, özellikle marka tutarlılığı için çok önemlidir. Bu eğitim, Arial gibi belirli yazı tiplerini GroupDocs.Viewer for .NET kullanarak nasıl hariç tutacağınızı gösterir. Bu kılavuzu izleyerek, belgeden HTML'e dönüşümlerde yazı tipi oluşturmayı yönetmenin etkili yollarını öğreneceksiniz.

![.NET için GroupDocs.Viewer'da HTML Çıktısından Belirli Yazı Tiplerini Hariç Tutma](/viewer/advanced-rendering/exclude-specific-fonts-from-html-output-img.png)

### Ne Öğreneceksiniz:
- GroupDocs.Viewer'ı .NET için kurma ve yapılandırma
- Belirli yazı tiplerini HTML çıktısından hariç tutma teknikleri
- Performansı optimize etmek ve diğer .NET sistemleriyle entegrasyonu sağlamak için pratik ipuçları
- Bu tekniklerin gerçek dünyadaki uygulamaları

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Kütüphaneler ve Sürümler**: GroupDocs.Viewer sürüm 25.3.0 veya üzeri.
- **Çevre Kurulumu**: .NET Framework veya .NET Core ile kurulmuş bir geliştirme ortamı.
- **Bilgi Önkoşulları**C# ve .NET geliştirme konusunda temel anlayış.

## .NET için GroupDocs.Viewer Kurulumu

### Kurulum Talimatları:

**NuGet Paket Yöneticisi Konsolunu Kullanma:**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI kullanımı:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Lisans Edinimi:
Ücretsiz deneme sürümünü edinebilir veya lisans satın alabilirsiniz. [GroupDocs satın alma sayfası](https://purchase.groupdocs.com/buy)Geçici erişim için, başvuruda bulunmayı düşünün [geçici lisans](https://purchase.groupdocs.com/temporary-license/).

### Temel Başlatma ve Kurulum:

.NET projenizde GroupDocs.Viewer'ı şu şekilde başlatabilirsiniz:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}

using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Yapılandırmalarınız buraya gidecek
}
```
Bu kurulum, GroupDocs.Viewer ile belge oluşturmayı değiştirmeye hazır olmanızı sağlar.

## Uygulama Kılavuzu

### Yazı Tiplerini HTML Çıktısından Hariç Tutma

Bu bölümde, .NET için GroupDocs.Viewer'ı kullanarak belirli yazı tiplerini HTML çıktınızdan nasıl hariç tutacağınıza odaklanacağız. 

#### Adım 1: Ortamınızı Hazırlayın
Çıktı dizininin mevcut olduğundan ve doğru şekilde ayarlandığından emin olun:
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}
```
Bu adım, işlenmiş dosyalarınızın belirlenmiş bir konuma sahip olmasını sağlar.

#### Adım 2: HTML Görünüm Seçeneklerini Yapılandırın
Görüntüleyiciyi gömülü kaynak HTML dosyalarını çıkış verecek şekilde yapılandırma yöntemi:
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
The `HtmlViewOptions` nesnesi, belgelerinizin HTML'e nasıl dönüştürüleceğini belirtmek için çok önemlidir.

#### Adım 3: Belirli Yazı Tiplerini Hariç Tut
Arial yazı tipini hariç tutmak için şunu değiştirin: `options` yapılandırma:
```csharp
options.FontsToExclude.Add("Arial");
```
Bu satır GroupDocs.Viewer'a çıktı HTML'sine gömdüğü tüm yazı tiplerinden Arial'ı çıkarmasını söyler. `FontsToExclude`, belgenizin görsel stilinin farklı ortamlarda nasıl korunacağı üzerinde kontrol sahibi olursunuz.

#### Adım 4: Belgeyi Oluşturun
Son olarak belgenizi şu ayarlarla oluşturun:
```csharp
viewer.View(options);
```
Arayarak `View()`, GroupDocs.Viewer belgenizi belirtilen seçeneklere göre işler ve hariç tutulan yazı tipleri olmadan HTML formatına çıktısını verir.

### Sorun Giderme İpuçları
- Dosya yollarının doğru ayarlandığından emin olun.
- .NET için GroupDocs.Viewer'ın uyumlu bir sürümünü kullandığınızı doğrulayın.
- Yazı tipi adlarının büyük/küçük harf duyarlılığı da dahil olmak üzere tam olarak eşleşmesi gerektiğinden, bunları iki kez kontrol edin.

## Pratik Uygulamalar

### Kullanım Örnekleri:
1. **Tutarlı Markalaşma**Markanızın tipografisinin tüm platformlarda tutarlı kalmasını sağlamak için istenmeyen yazı tiplerini hariç tutun.
2. **Web Entegrasyonu**:Web tasarımında tutarlılık için özel yazı tiplerine ihtiyaç duyan CMS sistemleriyle entegre edin.
3. **Belge Arşivleme**: Belgeleri gereksiz yazı tipleri olmadan HTML formatında arşivleyin, böylece dosya boyutu küçülsün.

### Entegrasyon Olanakları:
- Özel belge görüntüleme çözümleri oluşturmak için .NET uygulamalarında GroupDocs.Viewer'ı kullanın.
- Web üzerinde dinamik belge oluşturma için ASP.NET MVC veya Blazor gibi çerçevelerle birleştirin.

## Performans Hususları

Büyük belgelerle uğraşırken performansı optimize etmek çok önemlidir. İşte birkaç ipucu:

- **Kaynak Yönetimi**:Uygulamanızın bellek kullanımına, özellikle büyük dosyalarda, dikkat edin.
- **Toplu İşleme**: Uygulanabilirse, sistem kaynaklarının aşırı yüklenmesini önlemek için belgeleri gruplar halinde işleyin.
- **Verimli Önbelleğe Alma**:Sık erişilen belgeler için önbelleğe alma stratejileri uygulayın.

## Çözüm

Bu eğitimde, .NET için GroupDocs.Viewer'ı kullanarak belirli yazı tiplerini HTML çıktısından nasıl hariç tutacağınızı inceledik. Bu adımları izleyerek, dönüştürülmüş belgelerinizin görsel sunumu üzerinde kontrol sahibi olabilirsiniz. 

Daha detaylı araştırma için GroupDocs.Viewer tarafından sağlanan daha gelişmiş özellikleri entegre etmeyi veya tüm API yeteneklerini keşfetmeyi düşünebilirsiniz.

## SSS Bölümü

**S1: Birden fazla yazı tipini aynı anda hariç tutabilir miyim?**
Evet, sadece arayın `options.FontsToExclude.Add("FontName")` hariç tutmak istediğiniz her yazı tipi için.

**S2: Belirtilen yazı tipi belgede bulunmazsa ne olur?**
GroupDocs.Viewer bunu yok sayacak ve mevcut yazı tipleriyle işleme devam edecektir.

**S3: Hariç tutabileceğim yazı tipi sayısında bir sınırlama var mı?**
Belirli bir sınır yoktur, ancak çok sayıda yazı tipini hariç tuttuğunuzda performans etkilerini göz önünde bulundurun.

**S4: Bu özellik PDF veya resim gibi diğer çıktı formatlarıyla birlikte kullanılabilir mi?**
GroupDocs.Viewer çeşitli biçimleri destekler, ancak yazı tipi hariç tutma özellikleri değişebilir. Ayrıntılar için belgelere bakın.

**S5: GroupDocs.Viewer'ı kullanarak farklı belge türlerini nasıl işlerim?**
Kütüphane çok yönlüdür ve yerel olarak birden fazla dosya biçimini destekler. Biçim başına desteklenen özellikler için API referansını kontrol edin.

## Kaynaklar
- **Belgeleme**: [GroupDocs Viewer .NET Belgeleri](https://docs.groupdocs.com/viewer/net/)
- **API Referansı**: [GroupDocs API Başvurusu](https://reference.groupdocs.com/viewer/net/)
- **İndirmek**: [GroupDocs İndirmeleri](https://releases.groupdocs.com/viewer/net/)
- **Satın almak**: [GroupDocs Lisansı Satın Al](https://purchase.groupdocs.com/buy)
- **Ücretsiz Deneme**: [Ücretsiz Deneme Alın](https://releases.groupdocs.com/viewer/net/)
- **Geçici Lisans**: [Geçici Lisans Talebi](https://purchase.groupdocs.com/temporary-license/)
- **Destek**: [GroupDocs Destek Forumu](https://forum.groupdocs.com/c/viewer/9)

Belge oluşturma projelerinizi bir üst seviyeye taşımaya hazır mısınız? Bu çözümleri bugün uygulamaya çalışın!