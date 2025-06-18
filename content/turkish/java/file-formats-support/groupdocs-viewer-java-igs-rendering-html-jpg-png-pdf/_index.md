---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java kullanarak IGS dosyalarını çeşitli biçimlere nasıl dönüştüreceğinizi öğrenin. 3B modelleri HTML, JPG, PNG veya PDF olarak işlemek için bu adım adım kılavuzu izleyin."
"title": "GroupDocs.Viewer Java&#58;da Ustalaşma IGS Dosyalarını HTML, JPG, PNG ve PDF'ye Dönüştürme"
"url": "/tr/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/"
"weight": 1
---

# GroupDocs.Viewer Java'da Uzmanlaşma: IGS Dosyalarını Çoklu Biçimlere Dönüştürme

## giriiş

Karmaşık IGS dosyalarını Java kullanarak HTML, JPG, PNG veya PDF gibi erişilebilir biçimlere mi dönüştürmek istiyorsunuz? Bu kapsamlı kılavuz, GroupDocs.Viewer for Java kütüphanesinde ustalaşmanıza yardımcı olacaktır. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim IGS belgelerini zahmetsizce oluşturmanızı sağlayacaktır.

**Ne Öğreneceksiniz:**
- Java için GroupDocs.Viewer nasıl kurulur ve yapılandırılır.
- IGS dosyalarını HTML, JPG, PNG ve PDF formatlarına dönüştürmeye ilişkin adım adım talimatlar.
- Temel yapılandırma seçenekleri ve sorun giderme ipuçları.
- Bu dönüşümlerin gerçek dünya senaryolarında pratik uygulamaları.

Öncelikle ön koşulları ele alarak başlayalım!

## Ön koşullar

Bu eğitimi etkili bir şekilde takip edebilmek için aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
- **Java için GroupDocs.Viewer**: 25.2 veya üzeri sürüm önerilir.
- **Java Geliştirme Kiti (JDK)**: Sisteminizde JDK 8 veya üzeri sürümün yüklü olduğundan emin olun.

### Çevre Kurulum Gereksinimleri
- IntelliJ IDEA, Eclipse veya NetBeans gibi uygun bir Entegre Geliştirme Ortamı (IDE).
- Java programlama kavramları ve dosya G/Ç işlemlerinin temel düzeyde anlaşılması.

### Bilgi Önkoşulları
Bağımlılık yönetimi için Maven'a aşinalık faydalı olacaktır ancak zorunlu değildir. Her şeyi adım adım ele alacağız!

## Java için GroupDocs.Viewer Kurulumu

IGS dosyalarını oluşturmaya başlamak için öncelikle projenizde GroupDocs.Viewer kütüphanesini kurun.

**Maven Kurulumu**
Aşağıdaki yapılandırmayı şuraya ekleyin: `pom.xml` dosya:

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

### Lisans Edinimi
GroupDocs.Viewer ücretsiz deneme, test için geçici lisanslar ve tam erişim için satın alma seçenekleri sunuyor:
- **Ücretsiz Deneme**: Sınırlı kullanımla temel özelliklere erişin.
- **Geçici Lisans**:Kütüphaneyi kısa bir süre için kısıtlama olmaksızın değerlendirin.
- **Satın almak**: Uzun süreli kullanım için lisans satın alın.

Kurulum tamamlandıktan sonra, GroupDocs.Viewer'ı Java uygulamanızda aşağıdaki şekilde başlatın:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Yapılandırma ve işleme mantığı buraya gelir.
        }
    }
}
```

## Uygulama Kılavuzu

Şimdi, Java için GroupDocs.Viewer'ı kullanarak IGS dosyalarını çeşitli formatlara dönüştürme sürecini inceleyelim.

### IGS'yi HTML'ye dönüştürme

**Genel Bakış:**
Bir IGS dosyasını gömülü kaynaklara sahip etkileşimli bir HTML sayfasına dönüştürün. Bu format, kullanıcıların 3B modelleri doğrudan tarayıcılarında görüntülemeleri gereken web uygulamaları için mükemmeldir.

#### Adım Adım Uygulama:
1. **Çıktı Dizinini ve Dosya Yolunu Ayarlayın:**
   Oluşturulan dosyalarınızın kaydedileceği dizini tanımlayın ve çıktı dosya adını belirtin.

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.HtmlViewOptions;
    import java.nio.file.Path;
    import static java.nio.file.Paths.get;

    public class RenderIgsToHtml {
        public static void run() {
            Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
            Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

            try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
                HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
                viewer.view(options);
            }
        }
    }
    ```

2. **Parametreleri Anlayın:**
   - `HtmlViewOptions.forEmbeddedResources()` kaynakların (resimler gibi) HTML dosyasının içine gömülmesi gerektiğini belirtir ve bu da onu bağımsız bir belge haline getirir.

3. **Sorun Giderme İpuçları:**
   - Çıktı dizin yolunuzun doğru olduğundan emin olun.
   - Belirtilen dizine yazma için dosya izinlerini doğrulayın.

### IGS'yi JPG'ye dönüştürme

**Genel Bakış:**
IGS dosyalarınızı, 3D modellerin küçük resimleri veya önizlemeleri için kullanılabilen yüksek kaliteli JPG resimlerine dönüştürün.

#### Adım Adım Uygulama:
1. **Çıktı Dizinini ve Dosya Yolunu Ayarlayın:**
   HTML dönüşümüne benzer kurulum ancak JPG'ye özgü seçeneklerle.

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.JpgViewOptions;
    import java.nio.file.Path;
    import static java.nio.file.Paths.get;

    public class RenderIgsToJpg {
        public static void run() {
            Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
            Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

            try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
                JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
                viewer.view(options);
            }
        }
    }
    ```

2. **Anahtar Yapılandırmalar:**
   - `JpgViewOptions` Çıktı görüntüsünün çözünürlüğünü ve kalitesini tanımlamanıza olanak tanır.

3. **Sorun Giderme İpuçları:**
   - IGS dosyanızın doğru şekilde referanslandırılıp referanslandırılmadığını kontrol edin.
   - İhtiyaçlarınıza göre en iyi kaliteyi elde etmek için JPG seçeneklerini ayarlayın.

### IGS'yi PNG'ye dönüştürme

**Genel Bakış:**
Detaylı görselleştirmeler için ideal olan PNG formatında IGS dosyalarınızdan şeffaf veya şeffaf olmayan görseller oluşturun.

#### Adım Adım Uygulama:
1. **Çıktı Dizinini ve Dosya Yolunu Ayarlayın:**

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.PngViewOptions;
    import java.nio.file.Path;
    import static java.nio.file.Paths.get;

    public class RenderIgsToPng {
        public static void run() {
            Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
            Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

            try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
                PngViewOptions options = new PngViewOptions(pageFilePathFormat);
                viewer.view(options);
            }
        }
    }
    ```

2. **Yapılandırma Seçenekleri:**
   - `PngViewOptions` Görüntü kalitesini ve şeffaflığı belirtmek için kullanılabilir.

3. **Sorun Giderme İpuçları:**
   - IGS dosya yolunuzun doğru ayarlandığından emin olun.
   - En iyi sonuçları elde etmek için farklı PNG seçeneklerini deneyin.

### IGS'yi PDF'ye dönüştürme

**Genel Bakış:**
IGS belgelerini, ayrıntılı 3B modelleri standart bir formatta paylaşmak için mükemmel olan, herkesin erişebildiği PDF dosyalarına dönüştürün.

#### Adım Adım Uygulama:
1. **Çıktı Dizinini ve Dosya Yolunu Ayarlayın:**

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.PdfViewOptions;
    import java.nio.file.Path;
    import static java.nio.file.Paths.get;

    public class RenderIgsToPdf {
        public static void run() {
            Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
            Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

            try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
                PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
                viewer.view(options);
            }
        }
    }
    ```

2. **Temel Özellikler:**
   - `PdfViewOptions` PDF ayarlarının düzen ve kalite gibi özelleştirilmesine olanak tanır.

3. **Sorun Giderme İpuçları:**
   - Çıktı dizininin yazılabilir olduğunu doğrulayın.
   - IGS dosya biçiminde herhangi bir hata olup olmadığını kontrol edin.

## Pratik Uygulamalar

IGS dosyalarının çeşitli formatlara dönüştürülmesi çok sayıda olasılığı beraberinde getirir:
1. **Web Entegrasyonu**: HTML ile oluşturulmuş 3B modelleri doğrudan web uygulamalarına yerleştirin.
2. **Belge Paylaşımı**: Ayrıntılı görselleştirmeleri PDF'ler veya resim önizlemeleri (JPG/PNG) aracılığıyla paylaşın.
3. **Ürün Görselleştirme**: Ürün katalogları ve pazarlama materyalleri için yüksek kaliteli görseller kullanın.

Bu kılavuz, IGS dosyalarını çeşitli biçimlere dönüştürerek GroupDocs.Viewer for Java'yı etkili bir şekilde kullanmanız için gereken bilgiyle sizi donatır.