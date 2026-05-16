---
date: '2026-02-18'
description: GroupDocs Viewer for Java kullanarak WMZ ve WMF dosyalarını PDF, HTML,
  JPG ve PNG formatına nasıl dönüştüreceğinizi öğrenin. Bu rehber, groupdocs viewer
  java ve java vektörel grafik dönüştürmeyi kapsar.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: GroupDocs Viewer for Java ile WMZ'yi PDF ve Diğer Formatlara Nasıl Dönüştürürsünüz
type: docs
url: /tr/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 answer.# WMZ'yi PDF ve Diğer Formatlara GroupDocs Viewer for Java Kullanarak Nasıl Dönüştürülür

WMZ (Web Metafile) ve WMF (Windows Metafile) dosyalarını daha erişilebilir formatlara—özellikle **convert WMZ to PDF**—dönüştürmek zor olabilir çünkü bu vektör grafik formatları piksel verisi yerine çizim talimatları depolar. **GroupDocs Viewer for Java** ile WMZ/WMF belgelerini HTML, JPG, PNG, **PDF** ve diğer popüler formatlara sadece birkaç satır kodla işleyebilirsiniz.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

Bu öğreticide kütüphaneyi nasıl kuracağınızı, WMZ/WMF dosyalarını istenen çıktıya nasıl işleyeceğinizi ve yaygın sorunları nasıl ele alacağınızı öğreneceksiniz. Sonunda **groupdocs viewer java**'yu Java uygulamalarınıza **java convert vector graphics** hızlı ve güvenilir bir şekilde entegre edebileceksiniz.

## Hızlı Yanıtlar
- **WMZ/WMF hangi formatlara dönüştürülebilir?** HTML, JPG, PNG ve PDF tam olarak desteklenir.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme testi için çalışır; ticari lisans değerlendirme sınırlamalarını kaldırır.  
- **Hangi Java sürümü gereklidir?** Java 8 veya daha yenisi önerilir.  
- **Sadece belirli sayfaları işleyebilir miyim?** Evet, görünüm seçeneklerinde sayfa aralıklarını belirtebilirsiniz.  
- **Büyük dosyalar için bellek kullanımı bir sorun mu?** Belleği düşük tutmak için try‑with‑resources kullanın ve yalnızca gerekli sayfaları işleyin.

## “convert WMZ to PDF” nedir?
WMZ'yi PDF'ye dönüştürmek, vektör tabanlı WMZ dosyasını bir PDF konteyneri içinde rasterleştirmek (veya vektör verisini korumak) anlamına gelir. PDF evrensel olarak görüntülenebilir, aranabilir ve yazdırılabilir, bu da WMZ grafiklerini arşivlemek ve paylaşmak için idealdir.

## Vektör grafiklerini dönüştürmek için GroupDocs Viewer for Java neden kullanılmalı?
- **Yüksek doğruluk**: Kütüphane, PDF ya da PNG'ye çıktı alırken orijinal çizim kalitesini korur.  
- **Sıfır dış bağımlılık**: Yerel Windows kütüphanelerine gerek yok; her şey JDK'lı herhangi bir platformda çalışır.  
- **Basit API**: Tek bir `Viewer` örneği ve tek bir `view` çağrısı tüm dönüşümü yönetir.  
- **Ölçeklenebilir**: Tek sayfalı ikonlar ve çok sayfalı teknik çizimler için aynı derecede iyi çalışır.

## Önkoşullar

### Gerekli Kütüphaneler
- **GroupDocs.Viewer for Java** – çekirdek render motoru.  
- Java Development Kit (JDK) 8+.

### Ortam Kurulumu
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Bağımlılık yönetimi için Maven (veya tercih ederseniz Gradle).

### Bilgi Önkoşulları
- Java dosya I/O (`java.nio.file.Path`) konusunda aşinalık.  
- Belge görüntüleyicilerin içeriği nasıl işlediğine dair temel anlayış.

## GroupDocs.Viewer for Java Kurulumu

Depoyu ve bağımlılığı `pom.xml` dosyanıza ekleyin:

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

> **Lisans ipucu:** Değerlendirme için ücretsiz deneme sürümünü kullanın, ardından tam işlevselliği açmak için geçici ya da satın alınmış bir lisans uygulayın.

Bağımlılık çözüldükten sonra, her dönüşüm adımında yeniden kullanılacak bir `Viewer` örneği oluşturabilirsiniz.

## Uygulama Rehberi

Dört dönüşüm senaryosunu ele alacağız: HTML, JPG, PNG ve PDF. Her örnek aynı deseni izler—çıkış yolunu tanımlayın, kaynak WMZ dosyasıyla `Viewer` örneği oluşturun, uygun görünüm seçeneklerini yapılandırın ve `view` çağrısı yapın.

### WMZ/WMF'yi HTML'ye İşleme

#### Genel Bakış
HTML çıktısı, grafiği doğrudan web sayfalarına yerleştirmenizi sağlar; tüm kaynaklar (görseller, CSS) tek bir dosyada bulunur.

**Adım 1: Çıktı Dizini Yolunu Tanımlayın**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Adım 2: Viewer'ı Başlatın ve HTML'ye İşleyin**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF'yi JPG'ye İşleme

#### Genel Bakış
JPG, hızlı ön izlemeler veya e-posta ekleri için mükemmel, yaygın olarak desteklenen bir raster formattır.

**Adım 1: Çıktı Dizini Yolunu Tanımlayın**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Adım 2: Viewer'ı Başlatın ve JPG'ye İşleyin**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF'yi PNG'ye İşleme

#### Genel Bakış
PNG şeffaflığı destekler, farklı arka planlarla harmanlanması gereken grafikler için idealdir.

**Adım 1: Çıktı Dizini Yolunu Tanımlayın**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Adım 2: Viewer'ı Başlatın ve PNG'ye İşleyin**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF'yi PDF'ye İşleme

#### Genel Bakış
PDF, platform bağımsız, aranabilir bir belge sunar ve orijinal düzeni korur.

**Adım 1: Çıktı Dizini Yolunu Tanımlayın**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Adım 2: Viewer'ı Başlatın ve PDF'ye İşleyin**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|----------|
| **OutOfMemoryError** büyük WMZ dosyalarında | Viewer tüm belgeyi belleğe yüklüyor | `PageStreamViewOptions` kullanarak bir sayfayı bir seferde işleyin veya JVM yığınını (`-Xmx`) artırın. |
| **Missing fonts** PDF'de | Kaynak WMZ'de font gömülü değil | Gerekli fontları ana makineye kurun veya özel font sağlamak için `FontSettings` kullanın. |
| **Blank PNG output** | Yanlış çıktı yolu veya yetersiz yazma izinleri | `outputDirectory`'nin var olduğunu ve uygulamanın yazma erişimine sahip olduğunu doğrulayın. |
| **HTML resources not loading** | `forExternalResources` kullanırken dosyaları kopyalamamak | Kendine ait bir HTML dosyası için `forEmbeddedResources` kullanın. |

## Sıkça Sorulan Sorular

**S: WMF'yi aynı kodla PNG'ye dönüştürebilir miyim?**  
C: Evet. PNG örneği hem WMZ hem de WMF dosyaları için çalışır; sadece `TestFiles.SAMPLE_WMZ`'yi WMF kaynağınızla değiştirin.

**S: Sadece bir sayfa alt kümesini dönüştürmek mümkün mü?**  
C: Kesinlikle. `PdfViewOptions` (veya diğer formatlar için ilgili seçenekler) kullanın ve render etmeden önce `setPageNumbers(List<Integer>)` çağırın.

**S: Her çıktı formatı için ayrı bir lisansa ihtiyacım var mı?**  
C: Hayır. Tek bir GroupDocs Viewer lisansı, HTML, JPG, PNG ve PDF dahil tüm desteklenen formatları kapsar.

**S: “java convert vector graphics” performansı nasıl etkiler?**  
C: Vektör‑to‑raster dönüşümü CPU‑yoğunludur. Büyük toplular için çoklu iş parçacığı kullanmayı ve dosyalar arasında tek bir `Viewer` örneğini yeniden kullanmayı düşünün.

**S: PDF vektör kalitesini korur mu, yoksa rasterleştirilecek mi?**  
C: WMZ/WMF'yi PDF'ye dönüştürürken, GroupDocs Viewer mümkün olduğunda vektör talimatlarını korur ve ölçeklenebilir bir PDF oluşturur.

## Sonuç

Artık **convert WMZ to PDF** ve diğer yaygın formatları **GroupDocs Viewer for Java** kullanarak dönüştürmek için eksiksiz, üretim‑hazır bir rehbere sahipsiniz. Grafikleri anlık olarak sunan bir web servisi ya da belgeleri PDF olarak saklayan bir arşiv aracı oluşturuyor olun, yukarıdaki adımlar size hızlı bir şekilde ulaşmanızı sağlayacak.

---

**Last Updated:** 2026-02-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs