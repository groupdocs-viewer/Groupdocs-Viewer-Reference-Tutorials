---
date: '2025-12-21'
description: GroupDocs.Viewer for Java ile PDF'lerde gruplamayı nasıl devre dışı bırakacağınızı,
  metin temsiliyetinin hassas olmasını sağlamak için PDF render seçeneklerinden Java
  HTML kullanarak öğrenin.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Java için GroupDocs.Viewer ile PDF'lerde Gruplamayı Nasıl Devre Dışı Bırakılır?
type: docs
url: /tr/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# PDF'lerde Gruplamayı Devre Dışı Bırakma (GroupDocs.Viewer for Java)

PDF'leri işlerken **gruplamayı devre dışı bırakma** ihtiyacınız olduğunda, özellikle karmaşık betikler veya eski diller söz konusu olduğunda, karakterlerin kesin konumlandırılması hayati önem taşır. Varsayılan *Character Grouping* özelliği karakterleri yanlış bir şekilde birleştirerek içeriğin yanlış yorumlanmasına yol açabilir. Bu rehberde, GroupDocs.Viewer for Java kullanarak gruplamayı nasıl devre dışı bırakacağınızı adım adım göstereceğiz, böylece her glif tam olarak ait olduğu yerde kalır.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Quick Answers
- **“Gruplamayı devre dışı bırakma” ne yapar?** Renderlayıcıyı her karakteri bağımsız bir öğe olarak işlemeye zorlar ve tam düzeni korur.  
- **Bu ayarı kontrol eden API seçeneği nedir?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Lisans almam gerekiyor mu?** Deneme sürümü test için çalışır, ancak üretim ortamı için tam lisans gereklidir.  
- **PDF'den aynı anda Java HTML oluşturabilir miyim?** Evet—gruplamayı devre dışı bırakırken HTML çıktısı oluşturmak için `HtmlViewOptions` kullanın.  
- **Bu özellik sadece PDF'lerle mi sınırlı?** Öncelikli olarak PDF'ler için tasarlanmıştır, ancak viewer birçok diğer formatı da destekler.

## Introduction

PDF belgeleriyle çalışırken, özellikle hiyeroglifler veya karakter temsili açısından hassas metin yapıları gerektiren diller söz konusu olduğunda, renderlama hassasiyeti kritik öneme sahiptir. “Character Grouping” özelliği, karakterleri hatalı bir şekilde gruplayarak belge içeriğinin yanlış yorumlanmasına neden olabilir. Bu durum, belgelerinin metin düzenini tam olarak kopyalamaları gereken kullanıcılar için özellikle sorunludur.

### Prerequisites

Kod uygulamasına geçmeden önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:
- **Kütüphaneler & Bağımlılıklar**: GroupDocs.Viewer for Java sürüm 25.2 veya üzeri gerekir.  
- **Ortam Kurulumu**: Java Development Kit (JDK) yüklü olmalı ve IDE'niz Maven projeleriyle çalışacak şekilde ayarlanmış olmalıdır.  
- **Bilgi Gereksinimleri**: Dosya yollarını yönetme ve harici kütüphaneleri kullanma konusunda temel Java programlama bilgisi.

## How to Disable Grouping in PDF Rendering

### Setting Up GroupDocs.Viewer for Java

#### Installation via Maven

Projeye gerekli kütüphaneyi ekleyin. `pom.xml` dosyanıza aşağıdaki yapılandırmayı ekleyin:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

#### License Acquisition

GroupDocs.Viewer'ı tam olarak kullanabilmek için lisans edinmeyi düşünün:
- **Ücretsiz Deneme**: Özellikleri test etmek için ücretsiz deneme sürümüyle başlayın.  
- **Geçici Lisans**: Daha fazla zamana ihtiyacınız varsa geçici lisans başvurusu yapın.  
- **Satın Alma**: Uzun vadeli projeler için lisans satın almanız tavsiye edilir.

#### Basic Initialization and Setup

Proje ortamınızı aşağıdaki şekilde başlatın:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Implementation Guide

#### Feature: Disable Characters Grouping

##### Step 1: Define Output Directory

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Neden?** Çıktınızın düzenli ve kolay erişilebilir olmasını sağlar.

##### Step 2: Configure File Path Format

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Neden?** PDF belgesinin sayfalarını sistematik bir şekilde organize etmenize yardımcı olur.

##### Step 3: Initialize HTML View Options

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Neden?** Gömülü kaynaklar, her sayfanın HTML dosyasına gerekli tüm varlıkların dahil edilmesini sağlar.

##### Step 4: Disable Character Grouping

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Neden?** Karakterlerin bireysel olarak renderlanmasını sağlayarak amaçlanan düzen ve anlam korunur.

##### Step 5: Render the Document

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Neden?** Tüm kaynakların uygun şekilde kapatılmasını sağlayarak bellek sızıntılarını önler.

### Generating Java HTML from PDF without Grouping

`HtmlViewOptions` sınıfı, **java html from pdf** üretirken her karakteri ayrı tutmanıza olanak tanır. Bu, renderlanmış sayfaları bir web portalına veya tam glif yerleşiminin önemli olduğu bir e‑öğrenme platformuna gömmek istediğinizde özellikle kullanışlıdır.

### Troubleshooting Tips

- `FileNotFoundException` almamak için belge yolunun doğru olduğundan emin olun.  
- Çıktı dizininin yazma izinlerine sahip olduğunu doğrulayın.  
- GroupDocs.Viewer for Java'ın uyumlu bir sürümünü kullandığınızı iki kez kontrol edin.

## Practical Applications

1. **Dil Koruma**: Çince, Japonca veya karakter hassasiyetinin kritik olduğu antik betikler gibi dillerde belge renderlaması için idealdir.  
2. **Hukuki ve Finansal Belgeler**: Uyum gerektiren belgelerde metin temsili kesinliği sağlar.  
3. **Eğitim Kaynakları**: Karmaşık diyagramlar veya ek açıklamalar içeren ders kitapları ve akademik makaleler için mükemmeldir.

## Performance Considerations

- **Kaynak Kullanımını Optimize Edin**: Sunucunuzun büyük PDF dosyalarını işleyebilecek yeterli kaynağa sahip olduğundan emin olun.  
- **Java Bellek Yönetimi**: Belleği etkili bir şekilde yönetmek için verimli veri yapıları ve çöp toplama uygulamaları kullanın.  
- **Toplu İşleme**: Birden fazla belge renderlarken verimliliği artırmak için belgeleri toplu olarak işleyin.

## Conclusion

Artık GroupDocs.Viewer for Java ile PDF renderlaması sırasında **gruplamayı devre dışı bırakma** konusunda uzmanlaştınız. Bu yetenek, kesin metin temsili gerektiren uygulamalar için hayati öneme sahiptir. Daha fazla keşfetmek için bu özelliği diğer belge yönetim sistemleriyle entegre etmeyi deneyin veya büyük ölçekli dağıtımlar için ek render seçenekleriyle deney yapın.

Sonraki adımlar, GroupDocs.Viewer’ın daha gelişmiş özelliklerini incelemek ve büyük ölçekli dağıtımlar için performansı ince ayar yapmaktır.

## FAQ Section

1. **Karakter gruplamasını devre dışı bırakmak ne sağlar?**  
   - Karakterlerin bireysel olarak renderlanmasını sağlayarak orijinal düzeni korur.  
2. **Bu özelliği diğer belge türleriyle kullanabilir miyim?**  
   - Evet, odak burada PDF'ler olsa da GroupDocs.Viewer birçok formatı destekler.  
3. **Büyük belgeleri verimli bir şekilde nasıl yönetirim?**  
   - Toplu işleme kullanın ve sunucu kaynaklarınızı optimize edin.  
4. **Çıktı dizini yazılabilir değilse ne yapmalıyım?**  
   - İzinleri kontrol edin veya erişim haklarına sahip farklı bir dizin seçin.  
5. **GroupDocs.Viewer için lisans sınırlamaları var mı?**  
   - Ücretsiz deneme mevcuttur, ancak uzun vadeli kullanım için satın alınmış bir lisans gerekir.

## Frequently Asked Questions

**S:** *Karakter gruplamasını devre dışı bırakmamın nedeni ne olabilir?*  
**C:** Gruplamayı devre dışı bırakmak, renderlayıcının ayrı gliflere ait karakterleri birleştirmesini engeller; bu, boşluk ve sıralamanın anlam taşıdığı betikler için kritiktir.

**S:** *`setDisableCharsGrouping` ayarı sadece HTML çıktısı için mi geçerlidir?*  
**C:** Hayır, temel PDF renderlama motorunu etkiler; dolayısıyla HTML, PNG vb. tüm çıktı formatları bu değişikliği yansıtır.

**S:** *Bu ayarı özel fontlarla birleştirebilir miyim?*  
**C:** Evet—`Viewer`'ı başlatmadan önce özel fontlarınızı yükleyin, gruplama kuralı hâlâ uygulanır.

**S:** *Gruplamayı devre dışı bırakmak performansı etkiler mi?*  
**C:** Biraz artar, çünkü motor her karakteri ayrı ayrı işler; ancak çoğu belge için etki minimaldir.

**S:** *Gruplamayı sayfa bazında açıp kapatmak mümkün mü?*  
**C:** Şu anda seçenek `PdfOptions` örneği başına globaldır; farklı sayfalar için ayrı `Viewer` örnekleri oluşturmanız gerekir.

## Resources

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2025-12-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs