---
date: '2026-07-19'
description: GroupDocs.Viewer for Java kullanarak pst'yi html'ye ve JPG, PNG, PDF
  gibi diğer formatlara nasıl dönüştüreceğinizi öğrenin. Bu rehber, gerekli tüm adımları
  ve yapılandırmaları kapsar.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: GroupDocs.Viewer for Java kullanarak PST'yi HTML'ye hızlı bir şekilde
  dönüştürün. Üretim ortamına hazır bir rehberde JPG, PNG ve PDF'ye nasıl dışa aktarılacağını
  adım adım öğrenin.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: GroupDocs.Viewer for Java ile PST'yi HTML'ye Dönüştür – Hızlı E-posta Dışa
  Aktarma
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: GroupDocs.Viewer for Java Kullanarak PST'yi HTML, JPG, PNG, PDF'ye Dönüştür
type: docs
url: /tr/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST'yi HTML, JPG, PNG, PDF'ye Dönüştürme GroupDocs.Viewer for Java Kullanarak

PST'yi **pst'yi html'ye dönüştür** veya JPG, PNG ya da PDF gibi diğer formatlara dönüştürmek mi istiyorsunuz? Güçlü GroupDocs.Viewer for Java kütüphanesi ile bu görev basit ve verimlidir. Bu öğreticide Outlook PST/OST dosyalarını web‑dostu HTML, görüntü dosyaları veya tek bir PDF olarak nasıl render edeceğinizi öğrenecek, böylece e‑posta arşivlerinizi paylaşması ve arşivlemesi kolay olacaktır.

![GroupDocs.Viewer for Java ile PST/OST'yi HTML, JPG, PNG, PDF'ye Dönüştür](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[GroupDocs.Viewer for Java ile PST/OST'yi HTML, JPG, PNG, PDF'ye Dönüştür](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

## Öğrenecekleriniz
- GroupDocs.Viewer for Java'ı bir Maven projesinde nasıl kuracağınızı.  
- HTML, JPG, PNG ve PDF'ye **java pst'yi dönüştür** dosyalarını dönüştürmek için adım‑adım talimatlar.  
- En iyi performans için yapılandırma ipuçları ve yaygın tuzaklar.

## Hızlı Yanıtlar
- **PST dönüşümünü hangi kütüphane yönetir?** GroupDocs.Viewer for Java.  
- **PST'yi doğrudan PDF'ye dönüştürebilir miyim?** Evet, `PdfViewOptions` kullanarak.  
- **Üretim için lisans gerekli mi?** Geçerli bir GroupDocs lisansı gereklidir.  
- **Hangi Java sürümü destekleniyor?** JDK 8 veya üzeri.  
- **Ekleri manuel olarak çıkarmam gerekiyor mu?** Hayır, görüntüleyici otomatik olarak render eder.

## GroupDocs.Viewer for Java Nedir?
GroupDocs.Viewer for Java, dış yazılım gerektirmeden 100'den fazla belge ve e‑posta formatını yükleyen ve bunları HTML, görüntü veya PDF çıktısına render eden bir sunucu‑tarafı API'dir. PST dosyalarını 2 GB'a kadar işleyebilir ve bellek kullanımını 200 MB'ın altında tutar.

## GroupDocs.Viewer for Java Kullanarak pst'yi html'ye Nasıl Dönüştürülür?
`new Viewer("source.pst")` ile PST dosyasını yükleyin, `HtmlViewOptions`'ı bir çıktı klasörüne işaret edecek şekilde yapılandırın ve `viewer.view(htmlOptions)`'ı çağırın. API her e‑postayı çıkarır, biçimlendirmeyi, ekleri ve meta verileri korur ve her mesaj için ayrı bir HTML sayfası yazar—tüm bunlar tek bir metod çağrısında gerçekleşir.

### Neden GroupDocs.Viewer'ı Seçmelisiniz?
- **Yüksek‑doğruluklu renderleme** – Zengin‑metin gövdeleri, tablolar ve gömülü görüntüler dahil olmak üzere e‑posta içeriğinin %99,9'u doğru bir şekilde yeniden üretilir.  
- **Çoklu çıktı formatları** – Tek bir API çağrısı HTML, JPG, PNG veya PDF üretebilir, 50'den fazla dışa aktarma seçeneğini kapsar.  
- **Sıfır dış bağımlılık** – Outlook, Exchange Server veya üçüncü‑taraf dönüştürücülere ihtiyaç yok; her şey Java çalışma zamanınız içinde çalışır.

## Önkoşullar
- **GroupDocs.Viewer for Java** – sürüm 25.2 veya üzeri.  
- **Java Development Kit (JDK)** – 8 veya daha yeni.  
- Bağımlılık yönetimi için Maven.  
- Temel Java bilgisi ve Maven'e aşinalık.

## GroupDocs.Viewer for Java'ı Kurma
`Viewer`, GroupDocs.Viewer for Java'da bir belgeyi yükleyen ve seçilen formata render eden temel sınıftır. GroupDocs deposunu ve bağımlılığı `pom.xml` dosyanıza ekleyin:

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
- **Ücretsiz deneme** – tüm özellikleri ücretsiz keşfedin.  
- **Geçici lisans** – gerekirse değerlendirme süresini uzatın.  
- **Tam lisans** – üretim dağıtımları için gereklidir.

### Temel Başlatma
`Viewer` örnekleri hafiftir; nesne oluşturma yükünü azaltmak için tek bir örneği birden çok dosya için yeniden kullanabilirsiniz.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Uygulama Kılavuzu
Aşağıdaki bölümler PST/OST dosyalarını her desteklenen formata render etmenizi adım adım gösterir.

### PST/OST Belgelerini HTML'ye Render Etme
#### Adım 1: Çıktı Dizini Oluşturma
HTML sayfalarının yazılacağı bir klasör tanımlayın. GroupDocs, her e‑posta için varlıkları düzenli tutmak amacıyla bir alt klasör oluşturur.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Adım 2: Load Options'ı Yapılandırma
`LoadOptions`, şifre yönetimi, kaynak yükleme zaman aşımı ve seçmeli sayfa render'ı belirlemenizi sağlar. Çoğu sunucu ortamı için 30 saniyelik bir zaman aşımı ayarlamak iyi çalışır.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 3: HTML View Options'ı Tanımlama
`HtmlViewOptions`, çıktı klasörünü, kaynak yönetimini ve HTML dönüşümü için isteğe bağlı CSS ayarlarını belirler.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Adım 4: Viewer'ı Başlat ve HTML'yi Render Et
Bir `Viewer` nesnesi oluşturun, PST dosya yolunu geçin ve `HtmlViewOptions` ile `view` metodunu çağırın. API, PST içindeki tüm mesajlar üzerinde otomatik olarak döner ve düzenli bir HTML hiyerarşisi üretir.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### PST/OST Belgelerini JPG'ye Render Etme
#### Adım 1: Çıktı Dizini Oluşturma
JPG anlık görüntüleri için özel bir klasör oluşturun; her e‑posta uzunluğuna bağlı olarak bir veya daha fazla görüntü dosyasına dönüşür.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 2: Load Options'ı Yapılandırma
HTML için kullanılan aynı `LoadOptions` burada da yeniden kullanılabilir, formatlar arasında tutarlı şifre yönetimi sağlar.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Adım 3: JPG View Options'ı Tanımlama
`JpgViewOptions`, JPEG dönüşümü için görüntü çözünürlüğünü, kalitesini ve çıktı klasörünü kontrol eder.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Adım 4: Viewer'ı Başlat ve JPG'yi Render Et
Web önizlemesi için yüksek kalite JPEG dosyaları üretmek üzere `viewer.view(jpgOptions)` kullanın.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### PST/OST Belgelerini PNG'ye Render Etme
#### Adım 1: Çıktı Dizini Oluşturma
Arşivleme veya OCR işleme için kayıpsız kalite gerektiğinde PNG çıktısı faydalıdır.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Adım 2: Load Options'ı Yapılandırma
Şifre ve zaman aşımı yapılandırmasının ötesinde ek bir ayar gerekmez.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Adım 3: PNG View Options'ı Tanımlama
`PngViewOptions`, kayıpsız PNG görüntüleri için şeffaf arka plan ve çıktı klasörü ayarlamanıza olanak tanır.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Adım 4: Viewer'ı Başlat ve PNG'yi Render Et
Her e‑posta için PNG anlık görüntüleri üretmek üzere `viewer.view(pngOptions)` örnekleyin.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST Belgelerini PDF'ye Render Etme
#### Adım 1: Çıktı Dizini Oluşturma
PST başına tek bir PDF dosyası, yasal inceleme iş akışlarını basitleştirir ve depolama yükünü azaltır.

CODE_BLOCK_PLACEHOLDER_14_END

#### Adım 2: Load Options'ı Yapılandırma
PDF'ye dönüştürürken, herhangi bir makinede görsel tutarlılığı sağlamak için `setEmbedFonts(true)`'ı etkinleştirmek isteyebilirsiniz.

CODE_BLOCK_PLACEHOLDER_15_END

#### Adım 3: PDF View Options'ı Tanımlama
`PdfViewOptions`, sıkıştırma seviyesini seçmenize, yazı tiplerini gömmesine ve PDF dönüşümü için çıktı dosya adını ayarlamanıza olanak tanır.

CODE_BLOCK_PLACEHOLDER_16_END

#### Adım 4: Viewer'ı Başlat ve PDF'yi Render Et
`PdfViewOptions` oluşturun, isteğe bağlı olarak bir sıkıştırma seviyesi seçin ve `viewer.view(pdfOptions)`'ı çağırın. API, tüm e‑postaları tek bir aranabilir PDF belgesinde birleştirir.

CODE_BLOCK_PLACEHOLDER_17_END

## Pratik Uygulamalar
- **E‑posta Arşivleme:** Büyük PST arşivlerini uyumluluk için aranabilir HTML veya PDF'ye dönüştürün.  
- **Belge Yönetim Sistemleri:** Dönüştürülmüş dosyaları yalnızca PDF, PNG veya JPG kabul eden sistemlerde saklayın.  
- **İşbirliği Platformları:** Dönüştürülmüş e‑postaları Slack veya Teams'te görüntü olarak paylaşın.  
- **Yasal İnceleme:** Mahkemelere e‑posta delillerinin PDF sürümlerini sağlayın.  
- **Yedekleme Stratejileri:** Kritik mesajların hafif PNG veya JPG anlık görüntülerini saklayın.

## Performans Düşünceleri
- **Kaynak Yönetimi:** Birden çok dosya işlenirken `Viewer` örneklerini yeniden kullanarak yükü azaltın.  
- **Bellek Ayarı:** Sunucu kapasitesine göre `loadOptions.setResourceLoadingTimeout`'ı ayarlayın.  
- **Asenkron İşleme:** Dönüşümü arka plan iş parçacıklarına devrederek duyarlı kullanıcı arayüzleri sağlayın.  

## Sıkça Sorulan Sorular
**S: Aynı kod tabanıyla **pst'yi pdf'ye** nasıl dönüştürürüm?**  
C: PDF renderleme bölümünde gösterildiği gibi `PdfViewOptions` kullanın; kodun geri kalanı aynı kalır.

**S: GroupDocs.Viewer şifreli PST dosyalarını işleyebilir mi?**  
E: Evet, render etmeden önce `LoadOptions.setPassword("yourPassword")` ile şifreyi sağlayın.

**S: **java pst'yi** PNG ile JPG'ye dönüştürme arasındaki fark nedir?**  
C: PNG kayıpsız kaliteyi korur, ekran görüntüleri için idealdir; JPG ise e‑posta önizlemeleri için daha küçük dosya boyutları sunar.

**S: **pst'yi toplu olarak nasıl dönüştürürüm**?**  
C: Renderleme mantığını bir klasördeki PST dosyaları üzerinde dönen bir döngüye sarın; her dosya için aynı `Viewer` yapılandırmasını yeniden kullanın.

**S: API 1 GB'den büyük PST dosyalarını dönüştürmeyi destekliyor mu?**  
C: Evet, GroupDocs.Viewer verileri akış olarak işler ve tüm arşivi belleğe yüklemeden 2 GB'a kadar dosyaları işleyebilir.

## Sonuç
Artık GroupDocs.Viewer for Java kullanarak **pst'yi html'ye**, JPG, PNG ve PDF'ye dönüştürmek için eksiksiz, üretim‑hazır bir kılavuza sahipsiniz. Yukarıdaki adımları izleyerek e‑posta dönüşümünü herhangi bir Java‑tabanlı iş akışına entegre edebilir, erişilebilirliği artırabilir ve uyumluluk gereksinimlerini karşılayabilirsiniz.

---

**Son Güncelleme:** 2026-07-19  
**Test Edilen Versiyon:** GroupDocs.Viewer for Java 25.2  
**Yazar:** GroupDocs

## İlgili Öğreticiler
- [GroupDocs.Viewer for Java Kullanarak NSF'yi PDF, HTML, JPG, PNG'ye Dönüştür](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – ODF'yi HTML, JPG, PNG, PDF'ye Dönüştürmek için GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [GroupDocs.Viewer for Java Kullanarak DOCX'i HTML'ye Dönüştürme: Adım‑Adım Kılavuz](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)