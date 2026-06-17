---
date: '2026-05-26'
description: GroupDocs.Viewer for Java kullanarak nsf'yi pdf ve diğer formatlara (HTML,
  JPG, PNG) nasıl dönüştüreceğinizi öğrenin. En iyi uygulama ipuçlarıyla adım adım
  rehber.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: GroupDocs.Viewer for Java ile nsf'yi pdf'ye dönüştürün
type: docs
url: /tr/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java Kullanarak NSF Dosyalarını Birden Çok Formata Dönüştürme

Bu kapsamlı rehberde **nsf'yi pdf'ye nasıl dönüştüreceğinizi** öğrenecek ve ayrıca NSF dosyalarını GroupDocs.Viewer for Java ile HTML, JPG ve PNG olarak render edeceksiniz. Lotus Notes veritabanlarını arşivlemeniz, tarayıcıda görüntülemeniz veya görüntü önizlemeleri oluşturmanız gerekirse, bu öğretici ortam kurulumundan kod‑seviyesi detaylara kadar her şeyi adım adım anlatır—böylece dönüşümü dakikalar içinde uygulayabilirsiniz.

![GroupDocs.Viewer for Java ile NSF Dosyalarını HTML, JPG, PNG ve PDF'ye Dönüştürme](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[GroupDocs.Viewer for Java ile NSF Dosyalarını HTML, JPG, PNG ve PDF'ye Dönüştürme](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## Hızlı Yanıtlar
- **Birincil kullanım durumu nedir?** NSF dosyalarını PDF, HTML, JPG veya PNG olarak web, arşivleme veya paylaşım için render etmek.  
- **Dönüşümü hangi kütüphane gerçekleştiriyor?** GroupDocs.Viewer for Java.  
- **Lisans gerekir mi?** Ücretsiz deneme mevcuttur; üretim için tam lisans gereklidir.  
- **Hangi Java sürümü gereklidir?** JDK 8 veya daha yenisi.  
- **Birden çok NSF dosyasını toplu işleyebilir miyim?** Evet – render mantığını bir döngü içinde sarın ve kaynakları try‑with‑resources ile yönetin.

## “convert nsf to pdf” nedir?

NSF (Lotus Notes veritabanı) dosyasını PDF'ye dönüştürmek, orijinal düzeni, yazı tiplerini ve grafikleri koruyan, Notes istemcisine ihtiyaç duymadan okunabilen statik bir belge üretir. Bu format, PDF dosyaları herhangi bir işletim sistemi veya cihazda açılabildiği için yasal arşivleme, güvenli dağıtım ve uzun vadeli depolama için idealdir.

## Neden NSF'yi PDF ve Diğer Formatlara Dönüştürmeliyiz?

NSF dosyalarını PDF, HTML, JPG veya PNG'ye dönüştürmek evrensel erişilebilirlik sağlar, görsel bütünlüğü korur ve modern web ve mobil uygulamalarla sorunsuz entegrasyonu mümkün kılar. PDF kesin sayfa düzenini korur, HTML tarayıcıda anlık görüntüleme sunar, JPG/PNG ise küçük resimler veya gömme için yüksek çözünürlüklü görüntü anlık görüntüleri sağlar.

## Önkoşullar

Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK) 8+** – Daha iyi çöp toplama performansı için JDK 11 veya daha yenisi önerilir.  
- **Maven** – bağımlılık yönetimi için.  
- **GroupDocs.Viewer for Java** – deneme veya lisanslı sürüm.  
- Java dosya I/O ve Maven proje yapısına temel aşinalık.

## GroupDocs.Viewer for Java'ı Kurma

### Maven Yapılandırması

`pom.xml` dosyanıza GroupDocs.Viewer bağımlılığını ekleyin. Bu, tüm gerekli ikili dosyaları ve geçişli kütüphaneleri çeker.

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

Tam işlevselliği açmak için şunları yapabilirsiniz:

- **Ücretsiz Deneme:** Lisans anahtarı olmadan temel özellikleri değerlendirin.  
- **Geçici Lisans:** Test için zaman sınırlı bir anahtar isteyin.  
- **Tam Satın Alma:** Sınırsız kullanım için üretim lisansı edinin.

### Temel Başlatma

`Viewer` istenen çıktı formatına belgeleri render eden temel sınıftır. Lisansınızı ve dosya yolunuzu bir try‑with‑resources bloğu içinde başlatarak doğru şekilde serbest bırakılmasını sağlayın.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## NSF'yi PDF'ye Dönüştürme

Bir NSF belgesini PDF'ye dönüştürmek için önce kaynak dosyayı gösteren bir `Viewer` örneği oluşturun. Ardından sayfa boyutu, sıkıştırma seviyesi ve yazı tiplerinin gömülüp gömülmeyeceği gibi çıktı özelliklerini tanımlamak için `PdfViewOptions` yapılandırın. Son olarak `viewer.view(pdfOptions)` çağrısını yaparak tüm belgeyi dağıtıma hazır tek bir PDF dosyasına render edin.

`PdfViewOptions` PDF'ye özgü ayarları (sayfa boyutu, sıkıştırma vb.) belirtir.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## NSF'yi HTML'ye Render Etme

### Genel Bakış

NSF belgelerini, doğru ekran temsili için resimler ve CSS gömülü, kendi içinde tutarlı HTML sayfalarına dönüştürün.

### Adım‑Adım Kılavuz

#### 1. Çıktı Dizini ve Dosya Yolunu Ayarlama

HTML dosyalarının kaydedileceği klasörü tanımlayın.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. Yükleme Seçeneklerini Yapılandırma

`LoadOptions`, dış kaynaklar için zaman aşımı gibi kaynak yüklemeyi ince ayar yapmanıza olanak tanır.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. Viewer'ı Başlat ve Render Et

`Viewer`, NSF'yi işler ve HTML dosyalarını hedef dizine yazar.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## NSF'yi JPG'ye Render Etme

### Genel Bakış

NSF belgesinin her sayfasından yüksek kaliteli JPG görüntüleri üretin; ön izlemeler veya görüntü‑ağırlıklı iş akışları için kullanışlıdır.

#### 1. Çıktı Yolunu Tanımlama

`output_page_{0}.jpg` gibi bir adlandırma deseni belirtin; `{0}` sayfa numarasıdır.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. Yapılandır ve Render Et

`JpgViewOptions`, çözünürlük ve kalite gibi JPEG çıkışı ayarlarını tanımlar. `JpgViewOptions` oluşturun, istenen DPI'yi ayarlayın ve `viewer.view(options)` çağrısını yapın.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## NSF'yi PNG'ye Render Etme

### Genel Bakış

Orijinal NSF sayfalarının her ayrıntısını koruyan kayıpsız PNG görüntüleri üretin.

#### 1. Çıktı Yolunu Ayarlama

Otomatik sayfalama için `nsf_page_{0}.png` gibi bir şablon kullanın.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. Belgeyi Render Et

`PngViewOptions`, çözünürlük ve renk derinliği gibi PNG çıkış parametrelerini yapılandırır. `PngViewOptions` (ör. `setResolution(300)`) ayarlayın ve render edin.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## Pratik Uygulamalar

1. **Web‑Tabanlı Belge Paylaşımı:** NSF'yi HTML'ye dönüştürerek Notes kurmadan tarayıcıda anlık görüntüleme sağlayın.  
2. **Görüntü Arşivleme:** Sayfa‑sayfa JPG/PNG anlık görüntülerini küçük resim galerileri veya OCR boru hatları için saklayın.  
3. **Evrensel Erişim:** PDF dönüşümünü kullanarak herhangi bir cihazda açılabilen tek bir güvenli dosya sunun; uyumluluk gereksinimlerini karşılayın.

## Performans Düşünceleri

- **Kaynak Yükleme:** Ağ gecikmesine göre `setResourceLoadingTimeout` ayarlayarak duraklamaları önleyin.  
- **Bellek Yönetimi:** `Viewer` örnekleri için try‑with‑resources kullanın; bu, yerel kaynakları otomatik olarak serbest bırakır.  
- **Toplu İşleme:** Büyük toplular için dosyaları ardışık ya da paralel akışlarla işleyin, JVM bellek sınırlarının altında kalmak için yığın kullanımını izleyin.

## SSS Bölümü

**En iyi format nedir?**  
- Kullanım senaryosuna bağlıdır: Web portalları için HTML, evrensel dağıtım için PDF, görüntü‑ağırlıklı iş akışları için JPG/PNG.

**Büyük NSF dosyalarını verimli nasıl işlerim?**  
- `LoadOptions` ayarlarını (ör. `setResourceLoadingTimeout` artırma) yapın, dosyaları daha küçük partiler halinde işleyin ve mümkün olduğunda tek bir `Viewer` örneğini yeniden kullanın.

**Görüntü formatlarında çıktı kalitesini özelleştirebilir miyim?**  
- Evet. Render etmeden önce `JpgViewOptions` veya `PngViewOptions` ile DPI, sıkıştırma seviyesi ve renk derinliğini ayarlayın.

**Dönüşüm başarısız olursa ne yapmalıyım?**  
- Dosya yollarını doğrulayın, NSF dosyasının bozuk olmadığından emin olun ve ayrıntılı hata kodları için GroupDocs.Viewer günlüklerini inceleyin. En son kütüphane sürümüne geçmek genellikle uyumluluk sorunlarını çözer.

**Toplu dönüşüm destekleniyor mu?**  
- Kesinlikle. Render mantığını bir `for` döngüsü veya Java Stream içinde sararak birden çok NSF dosyasını otomatik olarak işleyebilirsiniz.

## Sıkça Sorulan Sorular

**S: NSF dosyasını notlar kaybolmadan PDF'ye nasıl dönüştürürüm?**  
C: `PdfViewOptions` çoğu notu otomatik olarak korur; bu seçeneklerle belgeyi render ettiğinizde ortaya çıkan PDF orijinal düzeni yansıtır.

**S: Şifre korumalı NSF dosyalarını dönüştürebilir miyim?**  
C: Evet. `Viewer` örneğini oluşturmadan önce `LoadOptions` aracılığıyla kimlik bilgilerini sağlayın.

**S: Hangi Java sürümü en iyi performansı verir?**  
C: JDK 11 veya daha yenisi, geliştirilmiş çöp toplama ve eşzamanlılık sunarak toplu dönüşümlerde hızı artırır.

**S: JPG/PNG çıktısı için özel DPI ayarlamak mümkün mü?**  
C: `JpgViewOptions.setResolution(int dpi)` veya `PngViewOptions.setResolution(int dpi)` metodlarını `viewer.view(options)` çağrısından önce yapılandırın.

**S: GroupDocs.Viewer çıktıyı doğrudan bir HTTP yanıtına akıtmayı destekliyor mu?**  
C: Evet. Görünüm seçeneklerinin `Stream` aşırı yüklemesini kullanarak sonucu doğrudan `HttpServletResponse.getOutputStream()`'a yazabilirsiniz.

## Sonuç

Artık **nsf'yi pdf'ye dönüştürme** ve NSF dosyalarını HTML, JPG ve PNG olarak render etme konusunda eksiksiz bir yol haritasına sahipsiniz. Yukarıdaki adımları izleyerek herhangi bir Java uygulamasına sağlam belge dönüşümünü entegre edebilir, toplu işleri otomatikleştirebilir ve içeriği kullanıcılarınızın ihtiyaçlarına en uygun formatta sunabilirsiniz. Çözümünüzü daha da zenginleştirmek için su işareti ekleme, özel yazı tipleri ve çok sayfalı işleme gibi ek Viewer özelliklerini keşfedin.

---

**Son Güncelleme:** 2026-05-26  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs

## İlgili Öğreticiler

- [groupdocs viewer java: Belgeleri PDF'ye Dönüştür – Tam Kılavuz](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – ODF'yi HTML, JPG, PNG, PDF'ye GroupDocs.Viewer for Java Kullanarak Dönüştür](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)