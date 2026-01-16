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

## Hızlı Yanıtlar
- **“Gruplamayı devre dışı bırakma” ne yapar?** Renderleyiciyi her karakteri bağımsız bir öğe olarak işlemeye zorlar ve tam düzeni korur.
- **Bu oranı kontrol eden API seçeneği nedir?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.
- **Lisans almam gerekiyor mu?** Deneme sürümü testi için çalışır, ancak üretim ortamı için tam lisans gereklidir.
- **PDF'den aynı anda Java HTML kullanabilir miyim?** Evet—gruplamayı devre dışı bırakırken HTML çıktısı oluşturmak için `HtmlViewOptions` kullanın.
- **Bu özellik sadece PDF'lerle sınırlı mıdır?** Öncelikli olarak PDF'ler için tasarlanmıştır, ancak görüntüleyici birçok diğer formatı da kullanılabilir.

## Giriiş

PDF belgeleriyle çalışırken, özellikle hiyeroglifler veya karakter temsili açısından hassas metin şekilleri içeren diller söz konusu olduğunda, renderlama hassasiyeti kritik öneme sahiptir. “Karakter Gruplaması” özelliği, karakterleri hatalı bir şekilde gruplayarak belge içeriğinin yanlış yorumlanmasına neden olabilir. Bu durum, belgelerin metin düzenini tam olarak yedeklemeleri gereken kullanıcılar için özellikle sorunludur.

### Önkoşullar

Kod uygulamasının ödemelerinden önce aşağıdaki koşulları sağladığınızdan emin olun:
- **Kütüphaneler ve Bağımlılar**: GroupDocs.Viewer for Java sürüm 25.2 veya üzeri gerekir.
- **Ortam Kurulumu**: Java Development Kit (JDK) yüklü olmalı ve IDE'niz Maven projeleriyle çalıştırılmalı şekilde ayarlanmış olmalıdır.
- **Bilgi Gereksinimleri**: Dosya dosyalarını yönetme ve harici kütüphaneleri kullanma konusunda temel Java programlama bilgisi.

## PDF Oluşturmada Gruplamayı Devre Dışı Bırakma

### Java için GroupDocs.Viewer'ı Kurma

#### Maven aracılığıyla kurulum

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

#### Lisans Alma

GroupDocs.Viewer'ı tam olarak kullanabilmek için lisans edinmeyi düşünün:
- **Ücretsiz Deneme**: Özellikleri test etmek için ücretsiz deneme sürümüyle başlayın.
- **Geçici Lisans**: Daha fazla zamana ihtiyacınız varsa geçici lisans işlemi yapın.
- **Satın Alma**: Uzun vadeli projeler için lisans satın almaları tavsiye edilir.

#### Temel Başlatma ve Kurulum

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

### Uygulama Kılavuzu

#### Özellik: Karakter Gruplandırmayı Devre Dışı Bırakma

##### Adım 1: Çıktı Dizinini Tanımlama

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Neden?** Çıktınızın düzenli ve kolay erişilebilir olmasını sağlar.

##### Adım 2: Dosya Yolu Biçimini Yapılandırın

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Neden?** PDF belgesinin sayfalarını sistematik bir şekilde organize etmenize yardımcı olur.

##### Adım 3: HTML Görünüm Seçeneklerini Başlatın

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Neden?** Gömülü kaynaklar, her sayfanın HTML dosyasına gerekli tüm varlıkların dahil edilmesini sağlar.

##### Adım 4: Karakter Gruplandırmayı Devre Dışı Bırakın

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Neden?** Karakterlerin bireysel olarak renderlanmasını sağlayarak amaçlanan düzen ve anlam korunur.

##### Adım 5: Belgeyi Oluşturun

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Neden?** Tüm kaynakların uygun şekilde kapatılmasını sağlayarak bellek sızıntılarını önler.

### Gruplama olmadan PDF'den Java HTML oluşturma

`HtmlViewOptions` sınıfı, **java html'yi pdf'den** üretirken, onun karakterini ayrı tutmanıza olanak tanır. Bu, renderlenmiş sayfaların bir web portalına veya tam glif yerleşiminin önemli olduğu bir e‑öğrenme platformuna saklanmak istediğinizde özellikle kullanışlıdır.

### Sorun Giderme İpuçları

- `FileNotFoundException` almamak için belge yolunun doğru olduğundan emin olun.
- Çıktı dizininin yazmaya izinlerine sahip olup olmadığını doğrulayın.
- GroupDocs.Viewer için Java'nın uyumlu bir özetini kullandığınızı iki kez kontrol edin.

## Pratik Uygulamalar

1. **Dil Koruma**: Geleneksel, Japonca veya karakter özelliklerinin kritik olduğu antik betikler gibi dillerde belge oluşturma için idealdir.
2. **Hukuki ve Finansal Belgeler**: Uyum dolu belgelerde metin temsili kesinliği sağlar.
3. **Eğitim Kaynakları**: Karmaşık diyagramlar veya ek açıklamalar içeren ders kitapları ve akademik makaleler için kullanılabilir.

## Performansla İlgili Hususlar

- **Kaynak Kullanımını Optimize Edin**: Sunucunuzun büyük PDF işlemlerinin işleyebileceği yeterli kaynağa sahip olduğundan emin olun.
- **Java Bellek Yönetimi**: Belleği etkili bir şekilde oluşturmak için verimli veri yapıları ve çöp toplama uygulamalarını kullanın.
- **Toplu İşleme**: Birden fazla belge render ederken verimliliği artırmak için belgeleri toplu olarak işleyin.

## Çözüm

Artık GroupDocs.Viewer for Java ile PDF renderlaması sırasında **gruplamayı devre dışı bırakma** konusunda uzmanlaştınız. Bu yetenek, kesin metin temsili uygulamalar için hayati öneme sahiptir. Daha fazla bağlantı için bu özellik diğer belge yönetim sistemleriyle entegre etme hataları veya büyük değişiklikler için ek render seçenekleriyle deneyler yapın.

Sonraki adımlar, GroupDocs.Viewer'ın daha gelişmiş özelliklerin değerlendirilmesi ve büyük modüllerin performansı için performansı ince ayar yapmaktır.

## Sıkça Sorulan Sorular

**S:** *Kısa devre dışı gruplamasını devre bırakmamın nedeni ne olabilir?*
**C:** Gruplamayı devre dışı bırakma, renderleyicinin ayrı giflere ait karakterlerin bozulmasını engeller; bu, kalıcı ve sıralamanın anlamını taşıması betikler için kritiktir.

**S:** *`setDisableCharsGrouping` ayarı sadece HTML çıkışı için mi geçerlidir?*
**C:** Hayır, temel PDF renderlama motorunu etkiler; Yani HTML, PNG vb. Çıkan tüm formatlar bu değişiklikleri yansıtır.

**S:** *Bu ayarı özel yazı tipleriyle birleştirebilir miyim?*
**C:** Evet—`Viewer`ı başlatmadan önce özel yazı tiplerinizi yüklemeden önce, gruplama biçimi uygulandı.

**S:** *Gruplamayı devre dışı bırakma performansını etkiler mi?*
**C:** biraz artar, çünkü motor her karakteri ayrı ayrı işler; Ancak çoğu belge için etki minimumdur.

**S:** *Gruplama sayfasının bazında saklanması mümkün mü?*
**C:** Şu ​​anda seçenek `PdfOptions` örneği başına globaldır; Farklı sayfalar için ayrı `Görüntüleyici` örnekleri oluşturmanız gerekir.

## Kaynaklar

- [GroupDocs Dokümantasyonu](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs Viewer'ı İndir](https://releases.groupdocs.com/viewer/java/)
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans Başvurusu](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Destek Forumu](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 21.12.2025
**Şununla Test Edildi:** GroupDocs.Viewer Java için 25.2
**Yazar:** GroupDocs