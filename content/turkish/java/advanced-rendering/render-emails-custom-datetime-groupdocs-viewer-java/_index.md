---
date: '2026-09-15'
description: GroupDocs.Viewer for Java kullanarak özel datetime formatı ve timezone
  offset ile eml'yi html'ye nasıl dönüştüreceğinizi öğrenin—email arşivleme ve destek
  portalları için idealdir.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: GroupDocs.Viewer for Java kullanarak özel datetime formatı ve timezone
  offset ile eml'yi html'ye dönüştürün. Doğru email render'ı için bu adım adım kılavuzu
  izleyin.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: GroupDocs.Viewer kullanarak Java'da özel datetime ile eml'yi html'ye dönüştür
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: GroupDocs.Viewer kullanarak Java'da özel datetime ile eml'yi html'ye dönüştür
type: docs
url: /tr/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer kullanarak Java'da özel tarih‑saat ile eml'yi html'ye dönüştürme

Modern destek ve arşivleme sistemlerinde, **convert eml to html** işlemini hızlıca ve tam zaman damgalarını koruyarak gerçekleştirmek zorunlu bir yetenektir. Bu öğreticide, bir EML e‑postasını HTML'ye nasıl render edeceğinizi, **custom datetime format** uygulamayı ve GroupDocs.Viewer for Java kullanarak **timezone offset** ayarlamayı göstereceğiz. Sonunda, herhangi bir **email to html conversion** iş akışı için doğru, web‑hazır e‑posta görünümleri üreten yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

![GroupDocs.Viewer for Java ile Özel Tarih‑Saat Kullanarak E‑postaları Render Et](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Hızlı cevaplar
- **GroupDocs.Viewer EML'yi HTML'ye dönüştürebilir mi?** Evet – API, EML dosyalarını dış posta istemcileri olmadan doğrudan HTML'ye render eder.  
- **Üretim için lisansa ihtiyacım var mı?** Test için ücretsiz deneme yeterlidir; üretim dağıtımları için ücretli lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 veya daha yenisi tam olarak desteklenir.  
- **Görüntülenen tarih formatını nasıl değiştiririm?** `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")` metodunu çağırın.  
- **Zaman dilimini ayarlayabilir miyim?** Evet, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))` kullanın.

## “convert eml to html” nedir?
`Convert eml to html` bir EML e‑posta dosyasını tarayıcı render'ı için bir HTML belgesine dönüştürme sürecidir. Bir EML dosyasını HTML'ye dönüştürmek, ham e‑postayı (başlıklar, gövde ve ekler dahil) tarayıcıların ek eklentiler olmadan görüntüleyebileceği web‑dostu bir formata çevirir. Bu, e‑postaları web uygulamalarına, arşivlere veya destek panolarına gömmeyi kolaylaştırır.

## Bu görev için GroupDocs.Viewer neden kullanılmalı?
GroupDocs.Viewer **50+ input and output formats** destekler, EML, MSG, PST ve PDF dahil olmak üzere, ve tüm dosyayı belleğe yüklemeden çok sayfalı e‑postaları render edebilir. Sıfır bağımlılık motoru Outlook veya üçüncü‑taraf ayrıştırıcılara gerek kalmadan **custom datetime format** ve **timezone offset** üzerinde tam kontrol sağlar ve kaynak kullanımını düşük tutar.

## Önkoşullar
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ ve bir Java IDE (IntelliJ IDEA, Eclipse, VS Code)  
- Bağımlılık yönetimi için Maven  

## GroupDocs.Viewer for Java'ı kurma

### Maven yapılandırması
GroupDocs deposunu ve Viewer bağımlılığını `pom.xml` dosyanıza ekleyin.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### Lisans edinme
Ücretsiz deneme ile başlayın veya genişletilmiş test için geçici bir lisans isteyin. Üretim kullanımı için tam bir lisans satın alın.

### Temel başlatma
`Viewer` örneğini, dönüştürmek istediğiniz EML dosyasına işaret edecek şekilde oluşturun.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Java'da özel tarih‑saat ile eml'yi html'ye dönüştürme

Aşağıdaki adımlar, bir EML dosyasını HTML'ye render ederken özel tarih‑saat formatı ve zaman dilimi kayması uygulamanızı sağlar.

### Adım 1: çıktı dizinini ve dosya yolunu ayarlama
Oluşturulan HTML'nin nereye kaydedileceğini tanımlayın.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Açıklama:* `Path.of()` HTML'nin kaydedileceği klasöre bir referans oluşturur. `resolve()` dosya adını ekler.

### Adım 2: izleyiciyi e‑posta dosyasıyla başlatma
Hedef EML dosyası için `Viewer` sınıfının bir örneğini oluşturun.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Açıklama:* `Viewer` örneği dönüştürmek istediğiniz EML dosyasına işaret eder.

### Adım 3: HtmlViewOptions yapılandırması
Görselleri ve diğer kaynakları doğrudan HTML çıktısına paketleyen bir `HtmlViewOptions` nesnesi oluşturun.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Açıklama:* `forEmbeddedResources()` görselleri ve diğer kaynakları doğrudan HTML çıktısına paketler.

### Adım 4: özel tarih‑saat formatını ayarla *(custom datetime java)*
`setDateTimeFormat` e‑posta zaman damgalarını render ederken kullanılan tarih‑saat desenini ayarlar.  
Render edilen HTML'deki tüm zaman damgaları için kullanılacak deseni tanımlayın.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Açıklama:* Bu desen ay, gün, yıl, saat, dakika, AM/PM işareti ve zaman dilimi kaymasını (`zzz`) gösterir.

### Adım 5: zaman dilimi kaymasını ayarla *(timezone offset java)*
`setTimeZoneOffset` tüm e‑posta zaman damgalarına uygulanacak zaman dilimini belirler.  
Zaman damgalarını istenen zaman dilimine göre ayarlayın.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Açıklama:* Render edilen zaman damgalarını istenen zaman dilimine ayarlar. `"GMT+1"` ifadesini geçerli bir bölge tanımlayıcısı ile değiştirin.

### Java'da e‑posta zaman dilimini nasıl ayarlarsınız
Basit kaymaların ötesinde **e‑posta zaman dilimini ayarlamanız** gerekiyorsa—örneğin yaz saati değişikliklerini yönetmek gibi—`java.util.TimeZone` API'sinden `"Europe/Paris"` veya `"America/New_York"` gibi bölge kimliklerini kullanarak uygun `TimeZone` nesnesini alabilir ve `setTimeZoneOffset` metoduna geçirebilirsiniz. Bu, e‑posta zaman damgalarının her zaman doğru yerel zamanı yansıtmasını sağlar.

### Adım 6: belgeyi render et
Dönüştürmeyi çalıştırın ve son HTML dosyasını oluşturun.

```java
viewer.view(options);
```
*Açıklama:* Dönüştürmeyi yürütür ve özel tarih‑saat ayarlarınızla bir HTML dosyası üretir.

## Özel tarih‑saat formatı render edilen HTML'yi nasıl etkiler?
Özel tarih‑saat formatı, oluşturulan HTML'de her e‑posta zaman damgasının nasıl görüneceğini belirler, okunabilirliği ve yerel uyumu etkiler. `"MMM dd, yyyy hh:mm a zzz"` gibi bir desen belirleyerek, her tarihin tutarlı şekilde, ay kısaltması, gün, yıl, saat, dakika, AM/PM işareti ve açık zaman dilimi kaymasıyla gösterilmesini sağlarsınız; bu, küresel destek ekipleri için hayati öneme sahiptir.

## GroupDocs.Viewer e‑posta render'ı için hangi dosya formatlarını destekliyor?
GroupDocs.Viewer **EML, MSG, PST, MBOX ve EMLX** dosyalarını HTML, PDF, PNG ve JPEG formatlarına render edebilir. Toplam 50'den fazla belge ve görüntü formatını destekler, ek dönüştürücüler olmadan e‑postaları en yaygın web‑dostu çıktılara dönüştürmenizi sağlar.

## Birden fazla eml dosyasını toplu olarak nasıl dönüştürebilirim?
Tüm EML dosyalarını tek bir dizine koyun, `for` veya `foreach` döngüsüyle her dosyayı dolaşın, aynı `HtmlViewOptions` örneğini yeniden kullanın ve her dosya için `viewer.view` metodunu çağırın. Bu yaklaşım nesne oluşturma yükünü azaltır ve toplu dönüştürmeleri hızlandırır.

## Sorun giderme ipuçları
- **FileNotFoundException:** `Viewer` ve `Path.of()` içinde kullanılan yolları doğrulayın.  
- **Incorrect timestamps:** `TimeZone` kimliğinin hedef bölgenizle eşleştiğinden emin olun.  
- **Missing images:** `HtmlViewOptions.forEmbeddedResources()` kullandığınızı doğrulayın; aksi takdirde dış kaynaklar atlanabilir.

## Pratik uygulamalar
1. **Email archiving:** Uyum denetimleri için e‑postaların aranabilir HTML anlık görüntülerini depolayın.  
2. **Customer support portals:** Gelen biletleri, dünya çapındaki ajanlar için doğru yerel zamanlarla gösterin.  
3. **Legal documentation:** Standartlaştırılmış zaman damgalarıyla mahkeme‑hazır e‑posta kayıtları üretin.

## Performans hususları
- Toplu dönüştürmeler için ayrı bir sunucuya dağıtın.  
- Java yığın kullanımını izleyin; `OutOfMemoryError` alırsanız `-Xmx` değerini artırın.  
- Aynı e‑posta tekrar tekrar istendiğinde render edilen HTML'yi önbelleğe alarak CPU yükünü azaltın.

## Sonuç
Artık GroupDocs.Viewer for Java kullanarak özel tarih‑saat formatı ve zaman dilimi kaymasıyla **convert eml to html** yapabilen eksiksiz, üretim‑hazır bir yönteme sahipsiniz. Bu çözüm okunabilirliği artırır, zaman damgası doğruluğunu garanti eder ve arşivleme, destek veya hukuki iş akışlarına sorunsuz bir şekilde entegre olur.

**Next steps:** Çıktıyı uygulamanızın ihtiyaçlarına daha da uyarlamak için özel CSS enjeksiyonu, sayfalama veya PDF dönüştürme gibi ek Viewer seçeneklerini keşfedin.

## Sıkça sorulan sorular

**S: Eml dosyalarını eklerle nasıl yönetirim?**  
C: `HtmlViewOptions.forEmbeddedResources()` kullandığınızda ekler otomatik olarak gömülür. Ayrı dosyalara ihtiyacınız varsa Viewer API aracılığıyla da çıkarabilirsiniz.

**S: HTML şablonunu değiştirebilir veya özel CSS ekleyebilir miyim?**  
C: Evet, render işleminden sonra oluşturulan HTML dosyasını düzenleyebilir veya kaydetmeden önce programlı olarak CSS enjekte edebilirsiniz.

**S: Birden fazla eml dosyasını toplu olarak render etmek mümkün mü?**  
C: Render mantığını bir döngüye sarın ve her dosya için aynı `HtmlViewOptions` örneğini yeniden kullanın.

**S: MSG gibi diğer e‑posta formatlarını desteklemem gerekirse ne yapmalıyım?**  
C: GroupDocs.Viewer MSG, PST ve diğer e‑posta konteynerlerini de destekler—`Viewer` yapıcısındaki dosya uzantısını değiştirmeniz yeterlidir.

**S: Her sunucu için ayrı bir lisans gerekir mi?**  
C: Lisanslama dağıtım başına yapılır; çok‑sunucu senaryoları için GroupDocs lisans rehberine bakın.

## Kaynaklar

- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [İndirme](https://releases.groupdocs.com/viewer/java/)
- [Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)

---

**Son güncelleme:** 2026-09-15  
**Test edildiği sürüm:** GroupDocs.Viewer 25.2 (Java)  
**Yazar:** GroupDocs

## İlgili Öğreticiler

- [E‑postayı HTML'ye Dönüştür ve Alanları Yeniden Adlandır – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – GroupDocs.Viewer ile E‑posta‑PDF Render'ını Optimize Et](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java Duyarlı Html Render'ı](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
