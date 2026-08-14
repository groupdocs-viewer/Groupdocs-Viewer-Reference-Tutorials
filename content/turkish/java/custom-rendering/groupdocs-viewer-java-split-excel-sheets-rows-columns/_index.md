---
date: '2026-06-15'
description: Excel'i PDF'ye Java ile dönüştürmeyi ve GroupDocs Viewer kullanarak Excel
  sheets'i satır ve sütunlara göre bölmeyi öğrenin. Kurulum, code ve en iyi uygulamaları
  içerir.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel'i PDF'ye Dönüştür Java & Sheets'i Satır ve Sütunlara Göre Böl
type: docs
url: /tr/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel'i PDF'ye Java ile Dönüştür & Satır ve Sütunlara Göre Sayfaları Böl (Java)

Büyük Excel çalışma kitapları genellikle tek bir ekran veya yazdırılmış sayfada rahatça görüntülenebilecekten daha fazla veri içerir. **excel'i pdf'ye java ile dönüştür** yaygın bir gereksinimdir, sabit ve paylaşılabilir bir format gerektiğinde, **Excel sayfalarını satır ve sütunlara göre bölmek** ise verinin web veya baskı düzenlerinde daha kolay tüketilmesini sağlar. Bu rehberde **GroupDocs Viewer for Java** kullanarak her iki görevi de ele alacağız, sayfalama nasıl yapılandırılır gösterecek ve performans ile sorun giderme için en iyi uygulama ipuçlarını açıklayacağız.

![Satır ve Sütunlara Göre Excel Sayfalarını Bölme - GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Satır ve Sütunlara Göre Excel Sayfalarını Bölme - GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** GroupDocs Viewer for Java.  
- **Satır ve sütunlara göre aynı anda bölme yapabilir miyim?** Evet – sayfa başına satır ve sütun sayısını birlikte tanımlayabilirsiniz.  
- **Lisans gerekir mi?** Geliştirme için bir deneme veya geçici lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi çıktı formatları destekleniyor?** HTML (gömülü kaynaklar) gösterilmektedir; aynı seçeneklerle PDF de oluşturulabilir.  
- **Maven gerekli mi?** Maven, bağımlılıkları yönetmenin önerilen yoludur.  
- **Excel'i PDF'ye de dönüştürebilir miyim?** Kesinlikle – sadece `HtmlViewOptions`'ı `PdfViewOptions` ile değiştirin ve aynı sayfalama ayarlarını yeniden kullanın.

## “Excel Nasıl Bölünür” Nedir?
Excel sayfasını bölmek, tek bir çalışma sayfasını sabit sayıda satır, sütun veya her ikisine göre birden çok sayfa veya dosyaya ayırmak anlamına gelir. Bu teknik, sayfalı raporlar oluşturmanız, veriyi web sayfalarına gömmeniz veya tüm çalışma kitabını bir kerede yüklemeden yazdırılabilir bölümler üretmeniz gerektiğinde kullanışlıdır.

## Neden GroupDocs Viewer for Java Kullanmalısınız?
GroupDocs Viewer, elektronik tabloları tek bir geçişte işler ve otomatik olarak sayfalar, manuel hesaplamaları ortadan kaldırır. **Hızlı renderleme, tipik bir 2 çekirdekli sunucuda 250 sayfalık bir XLSX çalışma kitabını 2 saniyeden kısa sürede işler** ve **kütüphane 50'den fazla giriş ve çıkış formatını destekler**, bunlar arasında XLS, XLSX, CSV, PDF ve HTML bulunur. Windows, Linux, macOS, Docker konteynerleri veya bulut tabanlı sunucusuz çalışma ortamları gibi herhangi bir JVM uyumlu platformda çalışır; böylece Java uygulamanızın bulunduğu her yerde entegre edebilirsiniz.

## Önkoşullar
- Java 17 veya daha yeni bir sürüm yüklü.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Bağımlılık yönetimi için Maven.  
- Temel Java bilgisi ve Excel dosya işleme konusundaki aşinalık.

### Gerekli Kütüphaneler, Sürümler ve Bağımlılıklar
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
Ücretsiz deneme, geçici lisans alın veya tam lisans satın almak için [GroupDocs](https://purchase.groupdocs.com/buy) adresini ziyaret edin.

## Excel'i PDF'ye Java ile Nasıl Dönüştürürsünüz?

`Viewer` sınıfı, GroupDocs Viewer'ın bir belgeyi yükleyen ve çeşitli çıktı formatları için renderleme yöntemleri sağlayan çekirdek bileşenidir. `SpreadsheetOptions`, elektronik tablo renderlemesi için sayfa başına satır ve sütun gibi sayfalama ayarlarını kontrol etmenizi sağlar.

Excel dosyanızı `new Viewer("source.xlsx")` ile yükleyin, sayfalama için `SpreadsheetOptions` yapılandırın ve `viewer.view(pdfOptions, stream)` çağrısını yapın – bu tek çağrı, belirlediğiniz satır/sütun limitlerine uyarak çalışma kitabını PDF'ye dönüştürür. Dönüşüm formülleri, resimleri ve hücre stillerini korur, dağıtıma hazır doğru bir PDF kopyası üretir.

## Excel Sayfalarını Satırlara Göre Bölme

Satırlara göre bölmek, her biri sabit bir satır sayısı (ör. 15) içeren bir dizi HTML sayfası oluşturur. Bu yaklaşım, her görünümde sınırlı sayıda kaydı gösteren panolar için idealdir. Görüntüleyici, `page_0.html`, `page_1.html` vb. gibi ayrı HTML dosyaları üretir; her biri belirtilen satır sayısını içerir. Bu, bir web arayüzünde yalnızca gerekli kısmı yüklemeyi basitleştirir, bant genişliğini ve render süresini azaltır.

### Tanım Bağlantısı
`Viewer`, GroupDocs Viewer’ın bir belgeyi yükleyen ve seçilen çıktı formatına renderleme işlemini yöneten çekirdek sınıfıdır.

### Adım‑Adım Uygulama

#### Adım 1: Yolları Ayarlayın ve Viewer'ı Başlatın
İlk olarak, bölünmüş sayfaların nereye kaydedileceğini tanımlayın ve kaynak çalışma kitabı için bir `Viewer` örneği oluşturun.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Adım 2: Sayfa Başına Satır Sayısını Yapılandırın
Viewer'a her sayfanın kaç satır içermesi gerektiğini söyleyin.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Adım 3: Belgeyi Renderleyin
Son olarak, tanımladığınız seçeneklerle çalışma kitabını renderleyin.

```java
viewer.view(viewOptions);
```

## Excel Sayfalarını Satır ve Sütunlara Göre Bölme

Bazen tek bir sayfa, satır **ve** sütun (ör. 15 satır × 7 sütun) matrisini göstermek zorundadır. Bu, her HTML sayfasının düzeni üzerinde tam kontrol sağlar. Oluşan sayfalar, örneğin ilk sayfada 1‑15 satır ve A‑G sütunları, sonraki sayfada 16‑30 satır ve H‑N sütunları gibi dikdörtgen bir hücre bloğu gösterir. Bu ızgara‑stili sayfalama, standart kağıt boyutlarına uyan yazdırılabilir raporlar oluşturmak için kullanışlıdır.

### Tanım Bağlantısı
`SpreadsheetOptions`, oluşturulan her sayfada kaç satır ve sütun görüneceğini yapılandırır.

### Adım‑Adım Uygulama

#### Adım 1: Yolları Ayarlayın ve Viewer'ı Başlatın
Ayarlar, sadece dosya adının değiştiği satır‑only örnekle aynıdır.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Adım 2: Sayfa Başına Satır ve Sütun Sayısını Yapılandırın
Her iki boyutu da belirterek ızgara‑stili bir bölme oluşturun.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Adım 3: Belgeyi Renderleyin
Aynı `view` çağrısını kullanarak renderleyin.

```java
viewer.view(options);
```

## Pratik Uygulamalar
- **Excel raporu Java oluştur**: Büyük finansal modelleri sayfalı HTML rapor serisine dönüştür.  
- **GroupDocs Viewer Excel**: Bölünmüş sayfaları doğrudan bir web portalına gömerek etkileşimli veri keşfi sağlayın.  
- **Render Excel HTML Java**: Oluşturulan HTML sayfalarını bir servlet veya Spring denetleyicisi aracılığıyla sunarak istemci‑tarafı hızlı renderleme sağlayın.  

## Performans Düşünceleri
- **Bellek kullanımı** – Büyük çalışma kitapları önemli miktarda heap tüketebilir; JVM `-Xmx` ayarını artırmayı düşünün.  
- **Parça boyutu** – Sayfa boyutu ve render hızı arasında denge kuracak satır/sütun sayılarını seçin.  
- **Sürüm güncellemeleri** – Performans iyileştirmelerinden yararlanmak için GroupDocs Viewer'ı güncel tutun; en son 25.2 sürümü, 24.x'e göre render hızını %30'a kadar artırıyor.

## Yaygın Sorunlar ve Sorun Giderme

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| `OutOfMemoryError` | Çok büyük bir sayfayı, sayfa başına çok fazla satırla renderlemek | `countRowsPerPage` değerini azaltın veya JVM heap'ini artırın |
| Boş çıktı dosyaları | Yanlış dosya yolu veya yazma izinlerinin eksik olması | `outputDirectory`'nin var olduğunu ve yazılabilir olduğunu doğrulayın |
| HTML kaynakları yüklenmiyor | `forEmbeddedResources` kullanılıyor ancak dosyalar farklı bir temel URL'den servis ediliyor | Tüm çıktı klasörünü servis edin veya `forExternalResources`'a geçin |

## Sıkça Sorulan Sorular

**S: HTML yerine PDF oluşturabilir miyim?**  
C: Evet. `HtmlViewOptions` yerine `PdfViewOptions` kullanın ve aynı `SpreadsheetOptions` yapılandırmasını koruyun.

**S: Sabit satır/sütun yerine hücre içeriğine göre bölme mümkün mü?**  
C: Doğrudan içerik‑tabanlı bölme GroupDocs Viewer’da yerleşik değildir, ancak renderlemeden önce Apache POI ile çalışma kitabını ön işleyerek ayrı sayfalar oluşturabilirsiniz.

**S: GroupDocs Viewer eski Excel formatlarını (XLS) destekliyor mu?**  
C: Kesinlikle. Viewer, XLS, XLSX, CSV ve diğer elektronik tablo formatlarını işler.

**S: Oluşturulan HTML'i bir Spring MVC görünümüne nasıl gömebilirim?**  
C: Çıktı klasörünü statik bir kaynak olarak servis edin ve Thymeleaf ya da JSP şablonlarınızdan `page_0.html`, `page_1.html` vb. dosyalara referans verin.

**S: Ticari dağıtım için hangi lisansa ihtiyacım var?**  
C: GroupDocs'tan tam bir üretim lisansı gereklidir; deneme lisansları yalnızca değerlendirme amaçlıdır.

## Kaynaklar
- **Dokümantasyon**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Referansı**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **İndirme**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Satın Alma**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Ücretsiz Deneme**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Geçici Lisans**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Destek**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

**Son Güncelleme:** 2026-06-15  
**Test Edilen Versiyon:** GroupDocs Viewer 25.2 for Java  
**Yazar:** GroupDocs  

## İlgili Eğitimler

- [Java Elektronik Tablolarda Gizli Satır ve Sütunları Render Etme - GroupDocs.Viewer Kullanarak](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Java'da Boş Satırların Renderlenmesini Atlamak - GroupDocs.Viewer ile: Performans Rehberi](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Kapsamlı Kılavuz: Excel 2003 XML'i HTML/JPG/PNG/PDF'ye GroupDocs.Viewer Java ile Dönüştürme](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)