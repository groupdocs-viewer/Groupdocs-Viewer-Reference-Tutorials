---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET kullanarak arşiv bilgilerinin nasıl verimli bir şekilde çıkarılacağını öğrenin. Bu kılavuz kurulumu, kod örneklerini ve pratik uygulamaları kapsar."
"title": "GroupDocs.Viewer for .NET Kullanılarak Arşiv Bilgileri Nasıl Alınır? Kapsamlı Bir Kılavuz"
"url": "/tr/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
---

# .NET için GroupDocs.Viewer Kullanılarak Arşiv Bilgileri Nasıl Alınır: Kapsamlı Bir Kılavuz

## giriiş

ZIP'ler gibi arşiv dosyalarından ayrıntılı bilgileri verimli bir şekilde çıkarmak mı istiyorsunuz? Yapıyı anlamak belge yönetimi için hayati önem taşıyabilir. Bu kılavuz size nasıl kullanılacağını gösterecektir **.NET için GroupDocs.Viewer** Bir arşiv dosyası hakkında kapsamlı ayrıntıları almak ve görüntülemek için.

![.NET için GroupDocs.Viewer ile Arşiv Bilgilerini Alın](/viewer/metadata-properties/retrieve-archive-information.png)

Bu eğitimde şunları ele alacağız:
- .NET uygulamanızda GroupDocs.Viewer'ı kurma
- Arşiv dosyalarından görünüm bilgilerini alma
- Arşivler içindeki klasör yapılarını görüntüleme

Bu kılavuzun sonunda, bu işlevlerin uygulanmasına dair sağlam bir anlayışa sahip olacaksınız. Koda dalmadan önce neye ihtiyacınız olduğunu öğrenelim.

### Ön koşullar

Aşağıdakilerin hazır olduğundan emin olun:

- **Kütüphaneler ve Sürümler**: .NET için GroupDocs.Viewer'ı (sürüm 25.3.0) yükleyin.
- **Çevre Kurulumu**: Visual Studio gibi uygun bir .NET geliştirme ortamı kullanın.
- **Bilgi Önkoşulları**: .NET uygulamalarında C# ve dosya kullanımı hakkında temel bilgi.

## .NET için GroupDocs.Viewer Kurulumu

GroupDocs.Viewer for .NET'i kullanmak için NuGet Paket Yöneticisi aracılığıyla yükleyin:

### Kurulum Talimatları

**NuGet Paket Yöneticisi Konsolu**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET Komut Satırı Arayüzü**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Lisans Edinme

GroupDocs.Viewer çeşitli lisanslama seçenekleri sunmaktadır:
- **Ücretsiz Deneme**Temel işlevleri keşfedin.
- **Geçici Lisans**: Değerlendirme sırasında tüm özelliklere erişim.
- **Satın almak**: Uzun süreli kullanım için lisans satın almayı düşünebilirsiniz.

Kurulum ve lisansınızı ayarladıktan sonra, uygulamanızda GroupDocs.Viewer'ı başlatın. İşte bir örnek kurulum:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // Burada Görüntüleyici işlevlerini kullanın.
}
```

## Uygulama Kılavuzu

Yapılandırılmış bir yaklaşım için uygulamayı temel özelliklere ayıracağız.

### Arşiv Dosyaları için Görünüm Bilgilerini Al

Arşivinizin yapısını anlamak çok önemlidir. Bunu nasıl başaracağınız aşağıda açıklanmıştır:

#### Görüntüleyici Nesnesini Başlat

Bir örneğini oluşturun `Viewer` Arşiv dosyanızın yolunu içeren sınıf:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // İşlem için kodunuz buraya gelecek.
}
```

#### Görünüm Bilgilerini Edinin

JPG resimleri olarak biçimlendirilmiş görünüm bilgilerini al:

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### Kök Klasör Bilgilerini Görüntüle

Kapsamlı bir genel bakış için kök klasör ayrıntılarını yazdırın:

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### Alt Klasör Adlarını Tekrarlı Olarak Oku ve Yazdır

Arşivinizdeki alt klasörleri keşfetmek için şu yinelemeli yöntemi kullanın:

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### Pratik Uygulamalar

.NET için GroupDocs.Viewer çeşitli senaryolarda kullanılabilir:
- **Belge Yönetim Sistemleri**: Arşiv yapılarını otomatik olarak çıkar ve görüntüle.
- **İçerik Dağıtım Platformları**: Kullanıcılara arşivlenmiş içeriğin önizlemelerini sağlayın.
- **Veri Analiz Araçları**:İş öngörüleri için arşivlerdeki klasör hiyerarşilerini analiz edin.

ASP.NET veya WPF gibi diğer çerçevelerle entegrasyonu kolaydır ve mevcut sistemlere sorunsuz bir şekilde dahil edilebilir.

## Performans Hususları

En iyi performans için:
- **Kaynak Kullanımını Optimize Edin**: Belleği etkin bir şekilde yönetin ve büyük dosyaları işleyin.
- **Bellek Yönetimi En İyi Uygulamaları**: Bertaraf etmek `Viewer` Kaynakların hızla serbest bırakılması için nesneleri düzgün bir şekilde kullanın.

## Çözüm

Bu eğitimde, arşiv dosyalarından ayrıntılı bilgileri almak için GroupDocs.Viewer for .NET'i nasıl kullanacağınızı öğrendiniz. Bu özellikleri uygulamak, belge yönetimi yeteneklerinizi önemli ölçüde artırabilir.

### Sonraki Adımlar

GroupDocs.Viewer tarafından sunulan daha gelişmiş özellikleri keşfetmeyi veya bunu uygulamanızın diğer bileşenleriyle entegre etmeyi düşünün. Anlayışınızı derinleştirmek için farklı dosya türleri ve karmaşık klasör yapılarıyla deneyler yapın.

## SSS Bölümü

1. **Amacı nedir? `ViewInfoOptions`?**
   - JPG gibi belirli formatların işlenmesi gibi bir belgeyi nasıl görüntülemek istediğinizi yapılandırır.

2. **Büyük arşivleri nasıl verimli bir şekilde yönetebilirim?**
   - Bellek yönetim tekniklerini kullanın ve kaynakları doğru şekilde kullanın.

3. **GroupDocs.Viewer parola korumalı dosyaları işleyebilir mi?**
   - Evet, doğru lisans ve yapılandırma ile şifrelenmiş belgeleri işleyebilir.

4. **İşlenebilecek arşiv dosyasının boyutunda bir sınır var mı?**
   - Sınır, sisteminizin bellek kapasitesine bağlıdır; daha büyük dosyalar daha fazla kaynak gerektirir.

5. **GroupDocs.Viewer'ı ASP.NET uygulamalarıyla nasıl entegre edebilirim?**
   - Denetleyici eylemlerinizde veya hizmetlerinizde Viewer sınıfını, bir konsol uygulamasında yaptığınız gibi kullanın.

## Kaynaklar

- [Belgeleme](https://docs.groupdocs.com/viewer/net/)
- [API Referansı](https://reference.groupdocs.com/viewer/net/)
- [.NET için GroupDocs.Viewer'ı indirin](https://releases.groupdocs.com/viewer/net/)
- [Lisans Satın Alın](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.groupdocs.com/viewer/net/)
- [Geçici Lisans Başvurusu](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)