---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java kullanarak TXT dosyalarını HTML, JPG, PNG ve PDF gibi birden fazla biçime nasıl verimli bir şekilde dönüştüreceğinizi öğrenin. Bu adım adım kılavuzu izleyin."
"title": "Java için GroupDocs.Viewer'ı Kullanarak TXT Dosyalarını HTML, JPG, PNG ve PDF'ye Dönüştürün"
"url": "/tr/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/"
"weight": 1
---

# Java için GroupDocs.Viewer ile TXT Dosyalarını Dönüştürme: Kapsamlı Bir Kılavuz

## giriiş

Günümüzün dijital dünyasında, etkili belge yönetimi hem işletmeler hem de bireyler için anahtardır. İster web'de metin belgelerini görüntülemeniz, ister dosyaları çeşitli biçimlerde arşivlemeniz gereksin, Metin (TXT) dosyalarını dönüştürmek sık karşılaşılan bir gerekliliktir. **Java için GroupDocs.Viewer** TXT dosyalarını HTML, JPG, PNG ve PDF gibi birden fazla formata kolaylıkla dönüştürmek için etkili bir çözüm sunar. Bu kılavuz, kusursuz dönüşümler elde etmek için bu çok yönlü kütüphaneyi kullanma konusunda size yol gösterecektir.

### Ne Öğreneceksiniz:
- Java ortamınızda GroupDocs.Viewer'ı kurma
- TXT dosyalarını çok sayfalı ve tek sayfalı HTML'ye dönüştürme
- TXT belgelerini resim formatlarına (JPG, PNG) dönüştürme
- TXT içeriğini PDF formatına dönüştürme

Uygulamaya başlamadan önce gerekli ön koşulları inceleyelim.

## Ön koşullar

GroupDocs.Viewer for Java'ya dalmadan önce şunlara sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar:
- **Java için GroupDocs.Viewer** sürüm 25.2 veya üzeri.
  
### Çevre Kurulum Gereksinimleri:
- Sisteminizde yüklü uyumlu bir Java Geliştirme Kiti (JDK) (Java 8+ önerilir).
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir Entegre Geliştirme Ortamı (IDE).

### Bilgi Ön Koşulları:
- Java programlama ve dosya yönetimi konusunda temel bilgi.
- Bağımlılık yönetimi için Maven'a aşinalık faydalı olacaktır.

## Java için GroupDocs.Viewer Kurulumu

Kullanmaya başlamak için **GrupDokümanları.Görüntüleyici**, bunu Maven aracılığıyla projenize aşağıdaki şekilde dahil edebilirsiniz:

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

### Lisans Alma Adımları:
- Bir ile başlayın **ücretsiz deneme** veya bir tane elde edin **geçici lisans** GroupDocs.Viewer'ın tüm yeteneklerini keşfetmek için.
- Resmi lisansları aracılığıyla bir lisans satın almayı düşünün [satın alma sayfası](https://purchase.groupdocs.com/buy) Uzun süreli kullanım için.

### Temel Başlatma ve Kurulum:
1. Maven bağımlılığını projenize ekleyin.
2. Ortamınızı JDK ve IDE ile kurduğunuzdan emin olun.

Şimdi, TXT dosyalarını çeşitli formatlara dönüştürmek için GroupDocs.Viewer'ın farklı özelliklerinin nasıl uygulanacağını inceleyelim.

## Uygulama Kılavuzu

### Özellik 1: TXT'yi Çok Sayfalı HTML'ye Dönüştür

#### Genel Bakış:
Bu özellik, bir TXT belgesini çok sayfalı HTML biçimine dönüştürerek, metin yapısını birden fazla web sayfasında korur.

##### Adımlar:

**Gerekli Kitaplıkları İçe Aktar**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Yolları ve Görüntüleyiciyi Ayarla**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Gömülü kaynaklarla işleme için seçenekleri yapılandırın
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Bu seçenekleri kullanarak belgeyi HTML'ye dönüştürün
    viewer.view(options);
}
```

**Açıklama:**
- `HtmlViewOptions.forEmbeddedResources` Burada, tüm kaynakların çıktı dosyalarına yerleştirildiğinden ve bunların kendi kendine yeterli olduğundan emin olmak için kullanılır.

### Özellik 2: TXT'yi Tek Sayfalık HTML'ye Dönüştür

#### Genel Bakış:
Bu özellik, tüm metin belgenizi tek bir HTML sayfasında yoğunlaştırır; hızlı önizlemeler veya özetler için idealdir.

##### Adımlar:

**Gerekli Kitaplıkları İçe Aktar**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Yolları ve Görüntüleyiciyi Ayarla**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // Gömülü kaynaklarla işleme için seçenekleri yapılandırın
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Tek sayfa HTML olarak işleme seçeneğini ayarlayın
    options.setRenderToSinglePage(true);
    
    // Bu seçenekleri kullanarak belgeyi işleyin
    viewer.view(options);
}
```

**Açıklama:**
The `setRenderToSinglePage(true)` yöntem tüm metni tek bir web sayfasına sıkıştırır.

### Özellik 3: TXT'yi JPG'ye dönüştür

#### Genel Bakış:
TXT dosyalarınızı, paylaşım veya yazdırma amaçlarına uygun, yüksek kaliteli JPEG görüntülerine dönüştürün.

##### Adımlar:

**Gerekli Kitaplıkları İçe Aktar**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**Yolları ve Görüntüleyiciyi Ayarla**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // JPEG görüntüsüne dönüştürme seçeneklerini yapılandırın
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // Bu seçenekleri kullanarak belgeyi JPG olarak işleyin
    viewer.view(options);
}
```

**Açıklama:**
- `JpgViewOptions` Görüntü dönüşümüne göre uyarlanmış çıktı yollarını ve işleme ayarlarını belirtmenize olanak tanır.

### Özellik 4: TXT'yi PNG'ye dönüştür

#### Genel Bakış:
Metin belgelerini Taşınabilir Ağ Grafikleri (PNG) formatına dönüştürerek kayıpsız sıkıştırma ile yüksek kaliteli görüntüler elde edin.

##### Adımlar:

**Gerekli Kitaplıkları İçe Aktar**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**Yolları ve Görüntüleyiciyi Ayarla**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // PNG görüntüsüne dönüştürme seçeneklerini yapılandırın
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // Bu seçenekleri kullanarak belgeyi PNG olarak işleyin
    viewer.view(options);
}
```

**Açıklama:**
- `PngViewOptions` burada, benzer şekilde kullanılır `JpgViewOptions`, ancak PNG formatına özgü avantajları vardır.

### Özellik 5: TXT'yi PDF'ye dönüştür

#### Genel Bakış:
Metin belgelerinden, evrensel olarak kabul görmüş bir formatta dağıtım veya arşivleme için ideal olan PDF dosyaları oluşturun.

##### Adımlar:

**Gerekli Kitaplıkları İçe Aktar**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**Yolları ve Görüntüleyiciyi Ayarla**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // PDF'ye dönüştürme seçeneklerini yapılandırın
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // Bu seçenekleri kullanarak belgeyi PDF olarak işleyin
    viewer.view(options);
}
```

**Açıklama:**
- `PdfViewOptions` Sayfa düzeni ve kaynak yerleştirme dahil olmak üzere PDF dönüşümüne özgü ayarlar sağlar.

## Pratik Uygulamalar

GroupDocs.Viewer for Java'nın yetenekleri birkaç pratik kullanım örneğine kadar uzanmaktadır:

1. **Belge Yönetim Sistemleri:** Dahili portallar için metin tabanlı dokümantasyonun web dostu formatlara dönüştürülmesini otomatikleştirin.
2. **Yayın Platformları:** Yazar gönderilerini içerik yönetim sistemlerine sorunsuz entegrasyon için TXT'den HTML'e dönüştürün.
3. **Arşivleme Çözümleri:** Eski metin dosyalarını modern, kolay erişilebilir PDF veya resim formatlarında koruyun.
4. **Bulut Depolama ile Entegrasyon:** Daha iyi erişilebilirlik için belgeleri bulut platformları arasında otomatik olarak dönüştürün ve depolayın.