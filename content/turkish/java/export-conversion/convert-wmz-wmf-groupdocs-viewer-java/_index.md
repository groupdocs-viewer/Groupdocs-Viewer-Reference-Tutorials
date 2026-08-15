---
date: '2026-07-19'
description: GroupDocs Viewer for Java ile WMZ'yi PDF, HTML, JPG ve PNG formatlarına
  nasıl dönüştüreceğinizi öğrenin. Java ile vector graphics'i adım adım dönüştürme
  rehberi.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: GroupDocs Viewer for Java kullanarak WMZ'yi PDF, HTML, JPG ve PNG
  formatlarına dönüştürün. Bu öğretici, yüksek doğrulukla Java ile vector graphics'i
  adım adım dönüştürmeyi gösterir.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: GroupDocs Viewer for Java ile WMZ'yi PDF'ye Dönüştürün – Hızlı Rehber
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: GroupDocs Viewer for Java ile WMZ'yi PDF ve Diğer Formatlara Dönüştürün
type: docs
url: /tr/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# WMZ'yi PDF ve Diğer Formatlara Dönüştürme GroupDocs Viewer for Java ile

WMZ (Web Metafile) ve WMF (Windows Metafile) dosyalarını daha erişilebilir formatlara—özellikle **convert WMZ to PDF**—dönüştürmek zor olabilir çünkü bu vektör grafik formatları piksel verisi yerine çizim talimatlarını depolar. **GroupDocs Viewer for Java** ile WMZ/WMF belgelerini HTML, JPG, PNG, **PDF** ve diğer popüler formatlara sadece birkaç satır kodla render edebilir, orijinal görsel bütünlüğü korunur.

![GroupDocs.Viewer for Java ile WMZ/WMF Belgelerini Dönüştür](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[GroupDocs.Viewer for Java ile WMZ/WMF Belgelerini Dönüştür](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Hızlı Yanıtlar
- **WMZ/WMF hangi formatlara dönüştürülebilir?** HTML, JPG, PNG ve PDF tam olarak desteklenir.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü test için çalışır; ticari lisans değerlendirme sınırlamalarını kaldırır.  
- **Hangi Java sürümü gereklidir?** Java 8 veya daha yenisi önerilir.  
- **Yalnızca belirli sayfaları render edebilir miyim?** Evet, görüntüleme seçeneklerinde sayfa aralıklarını belirtebilirsiniz.  
- **Büyük dosyalar için bellek kullanımı bir sorun mu?** Belleği düşük tutmak için try‑with‑resources kullanın ve yalnızca gerekli sayfaları render edin.

## “convert WMZ to PDF” nedir?
**Convert WMZ to PDF**, bir WMZ vektör dosyasını alıp çizim talimatlarını bir PDF konteynerine yerleştirmek anlamına gelir; bu, evrensel olarak görüntülenebilir, aranabilir ve yazdırılabilir bir belge üretir. Dönüşüm, çizgi kalitesini ve şekilleri korur, böylece ortaya çıkan PDF herhangi bir cihazda orijinal grafiğe tamamen aynı görünür.

## Vektör grafiklerini dönüştürmek için GroupDocs Viewer for Java neden kullanılmalı?
GroupDocs Viewer for Java, WMZ ve WMF render işlemlerini **yüksek doğrulukta** gerçekleştirir, PDF, PNG veya HTML çıktısı verirken vektör detayını korur. Kütüphane, JDK yüklü herhangi bir platformda çalışır, yerel Windows bileşenlerine ihtiyaç duymaz ve tek‑çağrı API'si sayesinde tek‑ikon dosyalarından çok‑sayfalı teknik çizimlere kadar ölçeklenir. Benchmark testlerinde, standart 4‑çekirdek sunucuda **12 saniyeden kısa sürede 200‑sayfalık WMZ dosyalarını** işler.

## Önkoşullar

- **GroupDocs.Viewer for Java** – temel render motoru.  
- Java Development Kit (JDK) 8 veya daha yenisi.  
- IntelliJ IDEA veya Eclipse gibi bir IDE (isteğe bağlı ancak önerilir).  
- Bağımlılık yönetimi için Maven (veya Gradle).  

Java NIO (`java.nio.file.Path`) ve temel dosya I/O konularına aşina olmak, örnekleri sorunsuz takip etmenizi sağlar.

## GroupDocs.Viewer for Java Kurulumu

`Viewer` sınıfı, tüm render işlemlerinin giriş noktasını temsil eder. Çoklu dönüşüm işlemleri arasında yeniden kullanılabilen, thread‑safe bir motor sağlar.

`pom.xml` dosyanıza (veya Gradle eşdeğerine) depo ve bağımlılığı ekleyin. Maven artefaktı çözüldükten sonra, her dönüşüm adımında yeniden kullanılacak bir `Viewer` örneği oluşturabilirsiniz.

> **Lisans ipucu:** Değerlendirme için ücretsiz deneme sürümünü kullanın, ardından tam işlevselliği açmak için geçici ya da satın alınmış bir lisans uygulayın.

## Uygulama Kılavuzu

Aşağıda dört dönüşüm senaryosunu—HTML, JPG, PNG ve PDF—adım adım inceliyoruz. Her senaryo aynı üç‑adımlı modeli izler:

1. **Adım 1: Çıktı Dizini Yolunu Tanımla** render edilen dosyaların kaydedileceği klasör.  
2. **Adım 2: Viewer'ı Başlat ve İlgili Formata Render Et** kaynak WMZ/WMF dosyasına işaret eden bir `Viewer` örneği oluştur.  
3. **Adım 3: Formata Özgü Görüntüleme Seçeneklerini Yapılandır ve `view` metodunu çağır.**

`view` metodu, sağlanan seçeneklere göre render işlemini gerçekleştirir.

### WMZ/WMF'yi HTML'ye Render Etme

#### Genel Bakış
HTML çıktısı, grafiği doğrudan web sayfalarına yerleştirmenizi sağlar; tüm kaynaklar (görseller, CSS) tek bir dosyada bulunur.

**Adım 1: Çıktı Dizini Yolunu Tanımla**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Adım 2: Viewer'ı Başlat ve HTML'ye Render Et**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF'yi JPG'ye Render Etme

#### Genel Bakış
JPG, hızlı ön izlemeler veya e‑posta ekleri için ideal, yaygın desteklenen bir raster formattır.

**Adım 1: Çıktı Dizini Yolunu Tanımla**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Adım 2: Viewer'ı Başlat ve JPG'ye Render Et**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF'yi PNG'ye Render Etme

#### Genel Bakış
PNG şeffaflığı destekler; farklı arka planlarla uyumlu grafikler için mükemmeldir.

**Adım 1: Çıktı Dizini Yolunu Tanımla**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Adım 2: Viewer'ı Başlat ve PNG'ye Render Et**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF'yi PDF'ye Render Etme

#### Genel Bakış
PDF, platform bağımsız, aranabilir ve orijinal düzeni koruyan bir belge sunar.

**Adım 1: Çıktı Dizini Yolunu Tanımla**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Adım 2: Viewer'ı Başlat ve PDF'ye Render Et**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Yaygın Sorunlar ve Çözümler

`PageStreamViewOptions` belirli sayfaları akış olarak render etmeye olanak tanır.  
`PdfViewOptions` PDF çıktı ayarlarını (sayfa aralığı, DPI vb.) yapılandırır.  
`FontSettings` kaynak belgede eksik fontlar referans edildiğinde özel fontlar sağlamanızı mümkün kılar.

| Sorun | Neden | Çözüm |
|-------|-------|----------|
| **OutOfMemoryError** büyük WMZ dosyalarında | Viewer tüm belgeyi belleğe yüklüyor | Sayfa başına `PageStreamViewOptions` kullanarak render edin veya JVM yığın boyutunu (`-Xmx`) artırın. |
| **Eksik fontlar** PDF'de | Font kaynak WMZ'de gömülü değil | Gerekli fontları host makineye kurun veya `FontSettings` ile özel font sağlayın. |
| **Boş PNG çıktısı** | Yanlış çıktı yolu veya yetersiz yazma izinleri | `outputDirectory` varlığını ve uygulamanın yazma erişimini doğrulayın. |
| **HTML kaynakları yüklenmiyor** | `forExternalResources` kullanırken dosyaları kopyamamak | Self‑contained HTML dosyası için `forEmbeddedResources` kullanın. |

## Sık Sorulan Sorular

**S: Aynı kodu kullanarak WMF'yi PNG'ye dönüştürebilir miyim?**  
**C:** Evet. PNG örneği hem WMZ hem de WMF dosyaları için çalışır; sadece `TestFiles.SAMPLE_WMZ` ifadesini WMF kaynağınızla değiştirin.

**S: Yalnızca bir sayfa alt kümesini dönüştürmek mümkün mü?**  
**C:** Kesinlikle. `PdfViewOptions` (veya diğer formatlar için ilgili seçenekler) kullanın ve render öncesinde `setPageNumbers(List<Integer>)` metodunu çağırın.

**S: Her çıktı formatı için ayrı bir lisansa ihtiyacım var mı?**  
**C:** Hayır. Tek bir GroupDocs Viewer lisansı, HTML, JPG, PNG ve PDF dahil tüm desteklenen formatları kapsar.

**S: “java convert vector graphics” performansı nasıl etkiler?**  
**C:** Vektör‑to‑raster dönüşümü CPU‑yoğun bir işlemdir. Büyük toplu işler için çoklu iş parçacığı (multi‑threading) kullanın ve dosyalar arasında tek bir `Viewer` örneği yeniden kullanın.

**S: PDF vektör kalitesini korur mu, yoksa rasterleştirilecek mi?**  
**C:** WMZ/WMF'yi PDF'ye dönüştürürken GroupDocs Viewer mümkün olduğunca vektör talimatlarını korur; böylece ölçeklenebilir bir PDF elde edilir.

## Sonuç

Artık **convert WMZ to PDF** ve diğer yaygın formatlara **GroupDocs Viewer for Java** kullanarak nasıl dönüştüreceğinize dair eksiksiz, üretim‑hazır bir kılavuzunuz var. Grafikleri anlık olarak sunan bir web servisi ya da belgeleri PDF olarak arşivleyen bir araç geliştirin; yukarıdaki adımlar hızlı ve güvenilir bir şekilde hedefinize ulaşmanızı sağlar. API'yi daha da keşfederek sayfa aralıkları, DPI ayarları veya filigran ekleme gibi özelleştirmeleri projenizin ihtiyaçlarına göre uygulayın.

---

**Son Güncelleme:** 2026-07-19  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs

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

## İlgili Eğitimler

- [OBJ'yi HTML, JPG, PNG ve PDF'ye Java ile GroupDocs.Viewer Kullanarak Nasıl Dönüştürülür](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [IGS'yi PDF, HTML, JPG & PNG'ye GroupDocs.Viewer Java ile Dönüştür](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Belgeleri PDF'ye Dönüştür – Tam Kılavuz](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)