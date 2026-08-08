---
date: '2026-08-08'
description: GroupDocs.Viewer for Java kullanarak IGS'yi PDF, HTML, JPG ve PNG'ye
  nasıl dönüştüreceğinizi öğrenin. Adım adım kılavuz, önkoşullar ve Java geliştiricileri
  için sorun giderme.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: GroupDocs.Viewer for Java kullanarak IGS'yi PDF, HTML, JPG ve PNG'ye
  dönüştürün. Ayrıntılı kurulum, kod parçacıkları ve Java geliştiricileri için sorun
  giderme.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: IGS'yi PDF, HTML, JPG ve PNG'ye GroupDocs.Viewer Java ile dönüştürün
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: IGS'yi PDF, HTML, JPG ve PNG'ye GroupDocs.Viewer Java ile dönüştürün
type: docs
url: /tr/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# IGS'yi PDF, HTML, JPG ve PNG'ye Dönüştürme, GroupDocs.Viewer Java ile

Java uygulamasından doğrudan **IGS'yi PDF'ye dönüştür** (veya HTML, JPG, PNG'ye) ihtiyacınız varsa doğru yerdesiniz. Bu öğreticide ihtiyacınız olan her şeyi adım adım ele alacağız—kütüphanenin kurulumu, 3‑D modelin projenize uygun formatta render edilmesi gibi. GroupDocs.Viewer'ın hızlı, güvenilir dönüşümler için sağlam bir seçim olduğunu anlayacak ve kendi çözümünüze ekleyebileceğiniz çalıştırmaya hazır kod parçacıklarını elde edeceksiniz.

![GroupDocs.Viewer for Java ile IGS Dosyalarını HTML, JPG, PNG ve PDF'ye Dönüştürme](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Hızlı Yanıtlar
- **Java ile IGS'yi PDF'ye dönüştürebilir miyim?** Evet, `PdfViewOptions` ile `Viewer` API'sini birlikte kullanın.  
- **Hangi çıktı formatları destekleniyor?** HTML, JPG, PNG ve PDF tümü yerel olarak işlenir.  
- **Üretim için lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; ücretsiz deneme sürümü temel özellikleri test etmenizi sağlar.  
- **Hangi Java sürümü gerekiyor?** JDK 8 ve üzeri; kütüphane ayrıca Java 11, 17 ve daha yeni sürümlerde de çalışır.  
- **Maven, kütüphaneyi eklemenin tek yolu mu?** Hayır, Gradle da kullanabilir veya JAR dosyalarını sınıf yolunuza manuel olarak ekleyebilirsiniz.

## IGS'yi PDF'ye Dönüştürme Nedir?
IGS'yi PDF'ye dönüştürmek, nötr bir 3‑D CAD dosyasını statik, evrensel olarak görüntülenebilir bir belgeye çevirmek anlamına gelir. Bu sayede CAD araçları olmayan paydaşlarla tasarım görselleri paylaşabilir, raporlara render ekleyebilir veya modeli uyumluluk amaçlı arşivleyebilirsiniz.

## IGS Dönüşümleri için GroupDocs.Viewer Neden Kullanılmalı?
GroupDocs.Viewer, dış bir CAD yazılımına ihtiyaç duymadan IGS dosyalarını işler. **50+ giriş ve çıkış formatını** destekler, **yüzlerce parçadan oluşan montajları** **200 MB**'nin altında bellek kullanımıyla render edebilir ve tipik modellerde standart bir sunucuda **2 saniyenin** altında sonuç verir. Bu ölçülen avantajlar, kurumsal hatlar için yüksek performanslı ve maliyet etkin bir seçenek olmasını sağlar.

## Önkoşullar
- **GroupDocs.Viewer for Java** ≥ 25.2 (en son kararlı sürüm).  
- **JDK 8+** yüklü ve IDE'nizde (IntelliJ IDEA, Eclipse, NetBeans vb.) yapılandırılmış.  
- Temel Maven bilgisi (isteğe bağlı ancak bağımlılık yönetimi için önerilir).  

## GroupDocs.Viewer for Java'ı Kurma

### Maven Bağımlılığı
`pom.xml` dosyanıza GroupDocs deposunu ve Viewer bağımlılığını ekleyin:

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

### Lisans Edinme
GroupDocs.Viewer üç lisans seçeneği sunar:
- **Ücretsiz deneme** – sınırlı kullanım, hızlı kanıt‑konsept testleri için mükemmel.  
- **Geçici lisans** – kısa bir değerlendirme süresi için tam özellik seti, pilot projeler için ideal.  
- **Ticari lisans** – sınırsız üretim kullanımı, öncelikli destek ve güncellemeler içerir.

### Temel görüntüleyici başlatma
`Viewer` sınıfı tüm render işlemlerinin giriş noktasıdır. Kaynak dosyayı yükler, formatı ayrıştırır ve istenen çıktıyı üretmek için yöntemler sunar.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## IGS'yi HTML'ye Renderleme

### IGS'yi HTML'ye Nasıl Dönüştürürsünüz?
Bir `Viewer` örneğiyle IGS dosyasını yükleyin ve tüm gerekli varlıkları gömülü olarak içeren bir `HtmlViewOptions` nesnesi geçin. Çağrı, tam 3‑D görünümü içeren tek bir HTML dosyası döndürür; bu da web sayfalarına gömmeyi kolaylaştırır. Sayfa boyutu, arka plan rengi ve etkileşimli kontroller gibi seçenekleri ayarlayarak render'ı özelleştirebilirsiniz.  
`HtmlViewOptions`, HTML çıktısının nasıl üretileceğini, kaynak gömme ve sayfa düzeni dahil olmak üzere yapılandırır.

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

## IGS'yi JPG'ye Renderleme

### IGS'yi JPG'ye Nasıl Dönüştürürsünüz?
`JpgViewOptions` nesnesi oluşturun, istenen çözünürlük ve sıkıştırma kalitesini yapılandırın ve `Viewer`'ın modelin her sayfası için raster görüntüler üretmesini sağlayın. Oluşturulan JPG dosyaları belirtilen bir dizine kaydedilebilir; kalite parametresini dosya boyutu ile görsel sadakat arasında dengelemek için ayarlayabilirsiniz; bu, küçük resimler veya yüksek çözünürlüklü baskılar için faydalıdır.  
`JpgViewOptions`, çözünürlük, kalite ve çıktı dizini gibi JPG görüntü üretim ayarlarını belirler.

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

## IGS'yi PNG'ye Renderleme

### IGS'yi PNG'ye Nasıl Dönüştürürsünüz?
`PngViewOptions` sınıfı, isteğe bağlı şeffaflıkla kayıpsız görüntüler üretmenizi sağlar. Bu format, modeli renkli arka planların üzerine yerleştirmek istediğiniz pazarlama materyalleri için idealdir. Çözünürlük ve arka plan rengini marka yönergelerinize uygun şekilde tanımlayabilir, böylece tüm üretilen varlıkların tutarlı görünmesini sağlayabilirsiniz.  
`PngViewOptions`, çözünürlük, şeffaflık ve arka plan rengi dahil olmak üzere PNG render parametrelerini tanımlar.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
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

## IGS'yi PDF'ye Renderleme

### IGS'yi PDF'ye Nasıl Dönüştürürsünüz?
`PdfViewOptions` kullanarak 3‑D modelin görsel düzenini koruyan sayfalı bir PDF oluşturun. Yazı tiplerini gömebilir ve kurumsal marka yönergelerine uyması için sayfa boyutunu kontrol edebilirsiniz. Ek ayarlar, görüntü kalitesi, sıkıştırma seviyesi ve çok sayfalı montajlar için içindekiler tablosu ekleme gibi seçenekleri içerir.  
`PdfViewOptions`, sayfa boyutu, görüntü kalitesi ve yazı tipi gömme yapılandırmasıyla PDF oluşturmayı yönetir.

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

## Pratik Uygulamalar
- **Web portalları** – HTML‑render'lanmış modelleri doğrudan ürün yapılandırıcılarına gömerek, müşterilerin eklenti kurmadan döndürüp yakınlaştırmasını sağlar.  
- **Pazarlama varlıkları** – broşürler, sunumlar ve sosyal medya gönderileri için yüksek çözünürlüklü JPG/PNG görüntüler üretir.  
- **Teknik dokümantasyon** – kullanıcı kılavuzlarına CAD modellerinin PDF render'larını ekleyerek, mühendislerin tasarımları çevrim dışı görmesini sağlar.  
- **Kalite güvencesi** – binlerce IGS dosyası için küçük resim oluşturmayı otomatikleştirerek görsel inceleme iş akışlarını hızlandırır.

## Yaygın Sorunlar ve Çözümler

| Sorun | Çözüm |
|-------|----------|
| **Çıktı klasörü bulunamadı** | `Path outputDirectory` parametresine verilen yolu doğrulayın ve Java işleminin hedef klasörde yazma iznine sahip olduğundan emin olun. |
| **PDF'de boş sayfalar** | Kaynak IGS dosyasının bozuk olmadığını kontrol edin; önce yerel bir CAD görüntüleyicide açın. |
| **Büyük montajlar için yavaş render** | JVM yığın boyutunu artırın (`-Xmx2g` veya daha fazla) ve parçaları işlemek için `viewer.getPageCount()` ile sayfa‑sayfa render etmeyi değerlendirin. |
| **PDF'de eksik yazı tipleri** | Gerekli yazı tiplerini gömmek için `PdfViewOptions` kullanın veya dönüşüm hizmetini barındıran sunucuya eksik yazı tiplerini kurun. |

## Sıkça Sorulan Sorular

**S: Tek bir çalıştırmada birden fazla IGS dosyasını dönüştürebilir miyim?**  
C: Evet. Dosya yolu koleksiyonunu döngüye alıp aynı `Viewer` örneği içinde her dosya için uygun `view` metodunu çağırabilirsiniz.

**S: PDF sayfa boyutunu özelleştirmek mümkün mü?**  
C: Kesinlikle. `PdfViewOptions`, `setPageSize(PageSize.A4)`, `PageSize.Letter` ve `setCustomSize(width, height)` ile özel boyutları sunar.

**S: Her çıktı formatı için ayrı bir lisansa ihtiyacım var mı?**  
C: Hayır. Tek bir GroupDocs.Viewer lisansı, HTML, JPG, PNG ve PDF dahil tüm desteklenen formatları kapsar.

**S: Performans düşmeden bir IGS dosyası ne kadar büyük olabilir?**  
C: Kütüphane **500 MB**'ye kadar dosyaları sorunsuz işler; 200 MB'den büyük modeller için ek JVM belleği ayırın ve toplu render için partiler halinde işleme yapın.

**S: Sadece belirli bir görünüm veya yönlendirme render edebilir miyim?**  
C: GroupDocs.Viewer, IGS dosyasında tanımlı varsayılan yönlendirmeyi render eder. Özel görünümler için dosyayı bir CAD aracıyla ön işleme tabi tutabilir veya dönüşümden önce modeli ayarlayabilirsiniz.

**Son güncelleme:** 2026-08-08  
**Test edildi:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs

## İlgili Eğitimler

- [cdr'yi html, jpg, png, pdf'ye dönüştürme GroupDocs.Viewer Java ile](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Java'da pdf'yi html'ye dönüştürme ve görüntü kalitesini optimize etme GroupDocs.Viewer ile](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)