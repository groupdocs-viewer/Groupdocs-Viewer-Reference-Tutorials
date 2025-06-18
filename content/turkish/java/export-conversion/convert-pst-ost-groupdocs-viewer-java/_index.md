---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java kullanarak Outlook PST/OST dosyalarını HTML, JPG, PNG veya PDF gibi erişilebilir biçimlere zahmetsizce nasıl dönüştüreceğinizi öğrenin. Bu kılavuz, gereken tüm adımları ve yapılandırmaları kapsar."
"title": "GroupDocs.Viewer for Java Kullanarak PST/OST'yi HTML, JPG, PNG, PDF'ye Dönüştürme | Dışa Aktarma ve Dönüştürme Kılavuzu"
"url": "/tr/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/"
"weight": 1
---

# Java için GroupDocs.Viewer'ı Kullanarak PST/OST'yi HTML, JPG, PNG, PDF'ye Dönüştürün

## giriiş

Outlook PST veya OST dosyalarınızı HTML, JPG, PNG veya PDF gibi daha erişilebilir biçimlere mi dönüştürmek istiyorsunuz? Güçlü GroupDocs.Viewer for Java kütüphanesiyle bu görev basit ve etkilidir. Bu eğitim, GroupDocs.Viewer for Java kullanarak PST/OST belgelerini işlemenize rehberlik ederek farklı platformlarda kolay paylaşım ve görüntüleme sağlar.

**Ne Öğreneceksiniz:**
- Java için GroupDocs.Viewer ile ortamınızı nasıl kurarsınız.
- PST/OST dosyalarını HTML, JPG, PNG ve PDF formatlarına dönüştürmek için adım adım talimatlar.
- Belge dönüştürme sürecinizi optimize etmek için temel yapılandırma seçenekleri.

Başlamadan önce ihtiyacınız olan ön koşulları gözden geçirelim.

## Ön koşullar

Bu eğitimi takip edebilmek için aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
- **Java için GroupDocs.Viewer**: 25.2 veya üzeri bir versiyona ihtiyacınız olacak.
- **Java Geliştirme Kiti (JDK)**:Uygulamanızı derlemek ve çalıştırmak için JDK 8 veya üzeri gereklidir.

### Çevre Kurulum Gereksinimleri
- IntelliJ IDEA, Eclipse veya NetBeans gibi uyumlu bir Entegre Geliştirme Ortamı (IDE).
- Bağımlılıkları yönetmek için sisteminize Maven yüklendi.

### Bilgi Önkoşulları
- Java programlamanın temel bilgisi.
- Bağımlılık yönetimi için Maven kullanımına aşinalık.

Ön koşullar sağlandıktan sonra, Java için GroupDocs.Viewer'ı kurmaya geçelim.

## Java için GroupDocs.Viewer Kurulumu

GroupDocs.Viewer for Java'yı kullanmak için, bunu projenize bir bağımlılık olarak eklemeniz gerekir. Maven kullanıyorsanız, şu adımları izleyin:

**Maven Yapılandırması:**

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

### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Özellikleri keşfetmek için ücretsiz denemeyle başlayabilirsiniz.
- **Geçici Lisans**: Değerlendirmek için daha fazla zamana ihtiyacınız varsa geçici lisans başvurusunda bulunun.
- **Satın almak**: Uzun süreli kullanım için lisans satın alın.

### Temel Başlatma ve Kurulum

Maven yapılandırmanız tamamlandıktan sonra, Java uygulamanızda GroupDocs.Viewer'ı başlatın:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Görüntüleyiciyi örnek bir PST dosya yolu ile başlatın
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

Kurulum tamamlandıktan sonra, render özelliklerinin uygulanmasına geçelim.

## Uygulama Kılavuzu

Bu bölüm, PST/OST belgelerinizi HTML, JPG, PNG ve PDF olarak dönüştürmek istediğiniz biçime göre mantıksal adımlara ayrılmıştır.

### PST/OST Belgelerini HTML'ye Dönüştürme

**Genel Bakış:**
PST/OST dosyalarını HTML'ye dönüştürmek, bunları web tarayıcılarında kolayca görüntülenebilir hale getirir. Bu özellik, kaynakları doğrudan HTML dosyasına yerleştirerek sorunsuz görüntüleme sağlar.

#### Adım 1: Çıktı Dizinini Ayarlayın

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

**Açıklama**: HTML dosyalarınızın nereye kaydedileceğini tanımlayın. `Paths` sınıf, dosya yollarının etkin bir şekilde yönetilmesine yardımcı olur.

#### Adım 2: Yükleme Seçeneklerini Yapılandırın

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**Açıklama**: İşleme sırasında gecikmeleri önlemek için kaynak yükleme için bir zaman aşımı süresi ayarlayın.

#### Adım 3: Görüntüleyiciyi Başlatın ve HTML'yi Oluşturun

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama**: Kullanın `HtmlViewOptions` HTML dosyasına kaynakları yerleştirmek için. `view()` yöntemi işlemeyi gerçekleştirir.

### PST/OST Belgelerini JPG'ye Dönüştürme

**Genel Bakış:**
Kolay paylaşım ve görüntüleme için PST/OST dosyalarınızın her sayfasını ayrı JPG resimlerine dönüştürün.

#### Adım 1: Çıktı Dizinini Ayarlayın

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

**Açıklama**: Çıkış JPG dosyaları için dizin ve dosya adı desenini belirtin.

#### Adım 2: Yükleme Seçeneklerini Yapılandırın

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**Açıklama**: HTML oluşturmaya benzer şekilde, kaynak yükleme için bir zaman aşımı süresi ayarlayın.

#### Adım 3: Görüntüleyiciyi Başlatın ve JPG'yi İşleyin

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama**: Kullanmak `JpgViewOptions` her sayfayı ayrı bir JPG dosyası olarak işlemek.

### PST/OST Belgelerini PNG'ye Dönüştürme

**Genel Bakış:**
PST/OST dosyalarınızı, yüksek kaliteli sunumlar ve çıktılar için ideal olan PNG görüntülerine dönüştürün.

#### Adım 1: Çıktı Dizinini Ayarlayın

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

**Açıklama**: PNG dosyaları için dizin ve dosya adı düzenini tanımlayın.

#### Adım 2: Yükleme Seçeneklerini Yapılandırın

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**Açıklama**İşleme süresini verimli bir şekilde yönetmek için bir kaynak yükleme zaman aşımı süresi ayarlayın.

#### Adım 3: Görüntüleyiciyi Başlatın ve PNG'yi İşleyin

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama**: Kullanmak `PngViewOptions` her sayfayı ayrı bir PNG dosyası olarak işlemek için.

### PST/OST Belgelerini PDF'ye Dönüştürme

**Genel Bakış:**
Kolay dağıtım ve arşivleme için tüm PST/OST belgenizi tek bir PDF dosyasına dönüştürün.

#### Adım 1: Çıktı Dizinini Ayarlayın

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

**Açıklama**: Çıktı PDF dosyası için dizini ve dosya adını belirtin.

#### Adım 2: Yükleme Seçeneklerini Yapılandırın

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**Açıklama**: Gecikmeler olmadan sorunsuz bir işleme sağlamak için bir zaman aşımı ayarlayın.

#### Adım 3: Görüntüleyiciyi Başlatın ve PDF'yi İşleyin

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama**: Kullanmak `PdfViewOptions` Tüm belgeyi tek bir PDF dosyası olarak sunmak için.

## Pratik Uygulamalar

PST/OST belgelerinin işlenmesine yönelik bazı gerçek dünya kullanım örnekleri şunlardır:

1. **E-posta Arşivleme:** Kolay erişim ve paylaşım için e-posta arşivlerini HTML veya PDF'ye dönüştürün.
2. **Belge Yönetim Sistemleri:** Depolama ve erişim için belge dönüştürme gerektiren sistemlerle bütünleşin.
3. **İşbirliği Araçları:** Dönüştürülen belgeleri Slack veya Microsoft Teams gibi işbirliği araçlarında paylaşın.
4. **Yasal Belgeler:** Hukuki belgeleri herkesin erişebileceği bir formata dönüştürerek hazırlayın.
5. **Yedekleme Çözümleri:** Önemli e-postalarınızın ve eklerinizin yedeklerini çeşitli formatlarda oluşturun.

## Performans Hususları

Java için GroupDocs.Viewer kullanırken performansı iyileştirmek için aşağıdaki ipuçlarını göz önünde bulundurun:
- İşleme sırasında verimli kaynak yönetimini sağlayın.
- Bellek kullanımını izleyin ve darboğazları önlemek için gerektiği gibi yapılandırmaları ayarlayın.
- Uygulama bağlamınız tarafından destekleniyorsa, duyarlılığı artırmak için eşzamansız işlemeyi kullanın.

Bu kılavuzu izleyerek, Java için GroupDocs.Viewer'ı kullanarak PST/OST dosyalarını çeşitli formatlara verimli bir şekilde dönüştürebilir, farklı platformlarda erişilebilirliği ve kullanılabilirliği artırabilirsiniz.