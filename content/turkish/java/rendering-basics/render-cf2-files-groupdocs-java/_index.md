---
date: '2026-06-30'
description: GroupDocs.Viewer for Java kullanarak cf2'yi pdf ve diğer formatlara nasıl
  dönüştüreceğinizi öğrenin. Bu adım adım rehber, CF2 dosyalarını HTML, JPG, PNG ve
  PDF formatlarına verimli bir şekilde render etmeyi kapsar.
keywords:
- convert cf2 to pdf
- groupdocs viewer java
- java convert cad drawings
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to convert cf2 to pdf and other formats using GroupDocs.Viewer
    for Java. This step‑by‑step guide covers rendering CF2 files to HTML, JPG, PNG,
    and PDF efficiently.
  headline: How to Convert CF2 to PDF, HTML, JPG, PNG with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert cf2 to pdf and other formats using GroupDocs.Viewer
    for Java. This step‑by‑step guide covers rendering CF2 files to HTML, JPG, PNG,
    and PDF efficiently.
  name: How to Convert CF2 to PDF, HTML, JPG, PNG with GroupDocs.Viewer for Java
  steps:
  - name: Initialize Viewer and Configure Options
    text: '**Explanation** – The `PdfViewOptions` class configures the output path
      and rendering quality. After rendering, dispose of the `Viewer` object to free
      resources.'
  - name: Define Paths and Initialize Viewer
    text: Set directory paths for your CF2 document and output HTML file. **Explanation**
      – This snippet initializes the `Viewer` with a CF2 file and specifies HTML view
      options to embed resources within the output.
  - name: Initialize Viewer and Configure Options
    text: Set up the output path for the JPG file and render the document. **Explanation**
      – The `JpgViewOptions` class specifies the output file path and renders the
      CF2 document as a JPEG image.
  - name: Initialize Viewer and Configure Options
    text: Define the output path for the PNG file and render it. **Explanation** –
      By using `PngViewOptions`, the CF2 file is rendered as a PNG image, ensuring
      high resolution and quality.
  type: HowTo
- questions:
  - answer: Yes—`HtmlViewOptions`, `JpgViewOptions`, `PngViewOptions`, and `PdfViewOptions`
      expose properties such as resolution, image quality, and resource embedding
      to fine‑tune the result.
    question: Can I customize the output for better quality or smaller file size?
  - answer: Absolutely. Loop through a directory, instantiate a `Viewer` for each
      file, and call the appropriate `view` method. This pattern works for any supported
      output format.
    question: Does GroupDocs.Viewer support batch conversion of multiple CF2 files?
  - answer: You can start with a 30‑day free trial. Production use requires a paid
      license, which removes watermarks and unlocks unlimited conversions.
    question: Is GroupDocs.Viewer free to use?
  - answer: Yes—the self‑contained HTML output can be placed directly into any web
      page, enabling instant in‑browser CAD viewing without additional plugins.
    question: Can I embed the rendered HTML in my website?
  - answer: A Java runtime (JDK 8+), at least 2 GB of RAM for large files, and sufficient
      disk space for temporary rendering buffers. The library runs on Windows, Linux,
      and macOS.
    question: What are the system requirements for using GroupDocs.Viewer?
  type: FAQPage
title: GroupDocs.Viewer for Java ile CF2'yi PDF, HTML, JPG ve PNG'ye Dönüştürme
type: docs
url: /tr/java/rendering-basics/render-cf2-files-groupdocs-java/
weight: 1
---

# Kapsamlı Kılavuz: CF2 Dosyalarını Çeşitli Formatlarda GroupDocs.Viewer ile Java'da Görüntüleme

## Giriş

cf2'yi pdf'ye ve diğer web‑dostu formatlara sadece birkaç satır Java kodu ile dönüştürün. CF2 gibi karmaşık CAD dosyalarını HTML, JPG, PNG veya PDF'ye görüntülemek zor olabilir, ancak **GroupDocs.Viewer for Java** süreci büyük ölçüde basitleştirir. Bu öğreticide CAD çizimlerini kullanıcı‑dostu belgelere nasıl dönüştüreceğinizi, bunun modern uygulamalar için neden önemli olduğunu ve hangi API'leri çağırmanız gerektiğini keşfedeceksiniz.

![Render CF2 Files to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/rendering-basics/render-cf2-files-to-html-jpg-png-pdf-java.png)

### Öğrenecekleriniz
- GroupDocs.Viewer for Java kullanarak CF2 dosyalarını HTML, JPG, PNG ve PDF'ye görüntüleme.  
- GroupDocs.Viewer için geliştirme ortamınızı kurma.  
- Ana yapılandırmaları ve özelleştirme seçeneklerini anlama.  
- Yaygın dönüşüm sorunlarını giderme.

## Hızlı Cevaplar
- **CF2'yi PDF'ye dönüştürebilir miyim?** Evet—tek adımlı dönüşüm için `PdfViewOptions` ve `Viewer` sınıfını kullanın.  
- **Hangi format en küçük dosya boyutunu verir?** JPG genellikle en küçük görüntü dosyalarını üretir, PDF ise vektör kalitesini korur.  
- **Üretim için lisansa ihtiyacım var mı?** Ücretli bir GroupDocs.Viewer lisansı deneme sınırlamalarını kaldırır ve sınırsız dönüşüm sağlar.  
- **Toplu dönüşüm destekleniyor mu?** Kesinlikle—bir klasörü döngüyle işleyip her dosya için aynı görüntüleme kodunu çağırın.  
- **Hangi Java sürümü gereklidir?** JDK 8 veya üzeri; en iyi performans için JDK 11+ önerilir.

## GroupDocs.Viewer Nedir?
GroupDocs.Viewer, orijinal uygulamaya ihtiyaç duymadan 100'den fazla belge ve CAD formatını HTML, görüntü veya PDF'ye dönüştüren bir Java kütüphanesidir. 2 GB'a kadar dosyaları destekler, düşük bellek tüketimiyle işler ve çözünürlük, yazı tipi yönetimi ve kaynak gömme seçenekleri sunar; bu da sunucu‑tarafı belge önizlemesi için idealdir.

## Önkoşullar

1. **Gerekli Kütüphaneler** – Bağımlılık yönetimini kolaylaştırmak için Maven kullanarak projenize GroupDocs.Viewer'ı ekleyin.  
2. **Ortam Kurulumu** – Java Development Kit (JDK) 8+ kurun ve IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.  
3. **Bilgi Önkoşulları** – Temel Java programlama, IDE'lere aşinalık ve Java'da dosya I/O deneyimi.

## GroupDocs.Viewer'ı Java için Kurma

### Maven Kurulumu
Add this configuration to your `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</dependencies>
<dependency>
   <groupId>com.groupdocs</groupId>
   <artifactId>groupdocs-viewer</artifactId>
   <version>25.2</version>
</dependency>
```

### Lisans Edinimi
GroupDocs.Viewer için resmi siteden ücretsiz deneme sürümüyle başlayın ve sınırsız kullanım için bir lisans satın almayı düşünün.

### Temel Başlatma ve Kurulum
Ortamınız hazır olduğunda, GroupDocs.Viewer'ı başlatın:

```java
import com.groupdocs.viewer.Viewer;
// Initialize viewer with file path or stream
Viewer viewer = new Viewer("path/to/your/document.cf2");
```

Şimdi CF2 dosyalarını çeşitli formatlarda görüntülemeye dalalım.

## CF2'yi PDF'ye Nasıl Dönüştürürsünüz?

`PdfViewOptions` PDF çıkış ayarlarını, dosya yolu ve görüntü kalitesi gibi, yapılandırır.

`new Viewer("sample.cf2")` ile CF2 dosyanızı yükleyin ve `viewer.view(new PdfViewOptions("output.pdf"))` çağrısını yapın – bu tek çağrı, katmanları, metni ve vektör grafikleri koruyarak tam bir dönüşüm gerçekleştirir. İşlem bellekte çalıştığından, 500 MB'den büyük dosyalar bile verimli bir şekilde işlenir.

### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

### Adım 2: Viewer'ı Başlatın ve Seçenekleri Yapılandırın
```java
Path pageFilePathFormat = outputDirectory.resolve("CF2_result.pdf");
try (Viewer viewer = new Viewer(inputDirectory.resolve("Sample.cf2"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama** – `PdfViewOptions` sınıfı çıkış yolunu ve görüntü kalitesini yapılandırır. Görüntüleme sonrası, kaynakları serbest bırakmak için `Viewer` nesnesini yok edin.

## CF2'yi HTML'ye Nasıl Dönüştürürsünüz?

`HtmlViewOptions` HTML çıktısının nasıl üretileceğini, kaynakların gömülmesi ve çıkış yollarının ayarlanması dahil olmak üzere tanımlar.

CF2 dosyasını yükleyin ve tüm görüntü ve CSS'yi satır içi olarak içeren bağımsız bir HTML sayfası oluşturmak için `HtmlViewOptions` kullanın.

### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;
```

### Adım 2: Yolları Tanımlayın ve Viewer'ı Başlatın
Set directory paths for your CF2 document and output HTML file.

```java
Path inputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY");
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("CF2_result.html");
try (Viewer viewer = new Viewer(inputDirectory.resolve("Sample.cf2"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama** – Bu kod parçacığı, `Viewer`'ı bir CF2 dosyasıyla başlatır ve çıktıya kaynakları gömmek için HTML görüntüleme seçeneklerini belirtir.

## CF2'yi JPG'ye Nasıl Dönüştürürsünüz?

`JpgViewOptions` JPEG çıkış parametrelerini, dosya konumu ve görüntü kalitesi gibi, belirler.

CAD çiziminin her sayfasını yüksek çözünürlüklü bir JPEG görüntüsü olarak renderleyin; hızlı ön izlemeler veya e-posta ekleri için idealdir.

### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

### Adım 2: Viewer'ı Başlatın ve Seçenekleri Yapılandırın
Set up the output path for the JPG file and render the document.

```java
Path pageFilePathFormat = outputDirectory.resolve("CF2_result.jpg");
try (Viewer viewer = new Viewer(inputDirectory.resolve("Sample.cf2"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama** – `JpgViewOptions` sınıfı çıkış dosya yolunu belirler ve CF2 belgesini JPEG görüntüsü olarak renderler.

## CF2'yi PNG'ye Nasıl Dönüştürürsünüz?

`PngViewOptions` PNG renderleme seçeneklerini, çıkış yolu ve çözünürlük gibi, yapılandırır.

PNG çıktısı kayıpsız kaliteyi korur, bu da net çizgi çalışması gerektiren belgeler için mükemmeldir.

### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

### Adım 2: Viewer'ı Başlatın ve Seçenekleri Yapılandırın
Define the output path for the PNG file and render it.

```java
Path pageFilePathFormat = outputDirectory.resolve("CF2_result.png");
try (Viewer viewer = new Viewer(inputDirectory.resolve("Sample.cf2"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**Açıklama** – `PngViewOptions` kullanılarak CF2 dosyası PNG görüntüsü olarak renderlenir, yüksek çözünürlük ve kalite sağlanır.

## Pratik Uygulamalar

1. **Mimari Sunumlar** – CAD çizimlerini HTML veya PDF'ye dönüştürerek müşteriye yönelik sunumlar hazırlayın.  
2. **Mühendislik Dokümantasyonu** – Ayrıntılı tasarımları JPG veya PNG görüntüleri olarak ekip üyeleriyle paylaşın.  
3. **Çapraz Platform Uyumluluğu** – CF2 dosyalarını evrensel formatlara dönüştürerek özel yazılım gerektirmeyen cihazlarda erişilebilir hale getirin.  
4. **Belge Yönetim Sistemleri ile Entegrasyon** – Kurumsal iş akışlarında dönüşüm ve arşivlemeyi otomatikleştirin.  
5. **Çevrimiçi Görüntüleme Platformları** – Kullanıcıların CAD tasarımlarını doğrudan web tarayıcılarında HTML çıktısı ile görüntülemelerini sağlayın.

## Performans Düşünceleri

GroupDocs.Viewer kullanırken optimal performans için:

- CPU ve bellek tüketimini azaltmak için belirli ihtiyaçlara göre viewer seçeneklerini yapılandırın.  
- Bellek sızıntılarını önlemek için renderleme sonrası `Viewer` nesnelerini hemen yok edin.  
- Aynı belgenin birden çok kez renderlendiği senaryolarda önbelleği etkinleştirin; bu, işlem süresini %40'a kadar azaltabilir.  

Bu en iyi uygulamaları izleyerek belge renderleme süreçlerinizin verimliliğini ve yanıt süresini artırabilirsiniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|----------|
| **PDF'de Boş Sayfalar** | Eksik yazı tipleri veya desteklenmeyen öğeler | En son yazı tipi paketlerinin kurulu olduğundan emin olun ve `PdfViewOptions` içinde `setRenderFontResources(true)`'ı etkinleştirin. |
| **Büyük CAD dosyalarında yavaş renderleme** | Varsayılan çözünürlük çok yüksek | Kalite kaybı olmadan işleme hızını artırmak için `setResolution(150)` ile DPI'yi düşürün. |
| **HTML kaynakları yüklenmiyor** | Göreli yollar bozuk | `HtmlViewOptions.setEmbedResources(true)` kullanarak CSS ve görüntüleri doğrudan HTML dosyasına gömün. |

## Sık Sorulan Sorular

**S: Çıktıyı daha iyi kalite veya daha küçük dosya boyutu için özelleştirebilir miyim?**  
A: Evet—`HtmlViewOptions`, `JpgViewOptions`, `PngViewOptions` ve `PdfViewOptions` çözünürlük, görüntü kalitesi ve kaynak gömme gibi özellikleri ortaya çıkararak sonucu ince ayar yapmanıza olanak tanır.

**S: GroupDocs.Viewer birden fazla CF2 dosyasının toplu dönüşümünü destekliyor mu?**  
A: Kesinlikle. Bir dizini döngüyle işleyin, her dosya için bir `Viewer` örneği oluşturun ve uygun `view` metodunu çağırın. Bu desen, desteklenen herhangi bir çıktı formatı için çalışır.

**S: GroupDocs.Viewer ücretsiz olarak kullanılabilir mi?**  
A: 30‑günlük ücretsiz deneme ile başlayabilirsiniz. Üretim kullanımı ücretli bir lisans gerektirir; bu lisans su işaretlerini kaldırır ve sınırsız dönüşüm sağlar.

**S: Renderlenen HTML'i web siteme gömebilir miyim?**  
A: Evet—bağımsız HTML çıktısı doğrudan herhangi bir web sayfasına yerleştirilebilir, ek eklentiler olmadan tarayıcıda anında CAD görüntüleme sağlar.

**S: GroupDocs.Viewer'ı kullanmak için sistem gereksinimleri nelerdir?**  
A: Java çalışma zamanı (JDK 8+), büyük dosyalar için en az 2 GB RAM ve geçici render tamponları için yeterli disk alanı. Kütüphane Windows, Linux ve macOS'ta çalışır.

---

**Last Updated:** 2026-06-30  
**Tested With:** GroupDocs.Viewer 23.10 for Java  
**Author:** GroupDocs

## İlgili Öğreticiler

- [GroupDocs.Viewer Java ile CAD Çizimlerini JPG Olarak Render Etme: Kapsamlı Kılavuz](/viewer/java/rendering-basics/render-cad-drawings-jpg-groupdocs-viewer-java/)
- [GroupDocs.Viewer Kullanarak Java'da OBJ'yi HTML, JPG, PNG ve PDF'ye Nasıl Dönüştürürsünüz](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [GroupDocs.Viewer Java ile IGS'yi PDF, HTML, JPG ve PNG'ye Dönüştürme](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)