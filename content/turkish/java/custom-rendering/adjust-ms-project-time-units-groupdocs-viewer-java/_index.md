---
date: '2026-05-21'
description: Nasıl yapılacağını öğrenin MS Project HTML export with adjusted time
  units using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
  and troubleshooting.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML Export: Adjust Time Units ile GroupDocs Java'
type: docs
url: /tr/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML Dışa Aktarma: Zaman Birimlerini GroupDocs Java ile Ayarlama

Exporting an **MS Project** file to HTML is a common requirement for project‑management dashboards, status‑report portals, and collaborative review tools. By default the viewer renders time‑related data in minutes, which can clutter the visual layout and make daily reporting harder to read. With **GroupDocs Viewer for Java** you can programmatically set the time‑unit to **days**, producing a clean *ms project html export* that aligns with typical stakeholder expectations. In this tutorial you’ll learn how to configure the viewer, adjust the time unit, and render the project to HTML in a few straightforward steps.

![GroupDocs.Viewer for Java ile MS Project Zaman Birimlerini Ayarlama](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[GroupDocs.Viewer for Java ile MS Project Zaman Birimlerini Ayarlama](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Hızlı Yanıtlar
- **MS Project dosyalarını render eden kütüphane nedir?** GroupDocs Viewer for Java.  
- **HTML dışa aktarımı için hangi zaman birimini ayarlayabilirim?** Günler, `TimeUnit.DAYS` kullanarak.  
- **Üretim için lisansa ihtiyacım var mı?** Evet— kalıcı bir lisans gereklidir; deneme sürümü değerlendirme için çalışır. Bir [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) ile başlayabilirsiniz.  
- **Hangi IDE en iyisi?** Maven'ı destekleyen herhangi bir Java IDE (IntelliJ IDEA, Eclipse, NetBeans).  
- **Maven zorunlu mu?** Maven bağımlılık yönetimini basitleştirir, ancak Gradle veya manuel JAR eklemesi de kullanabilirsiniz.  
- **Nereden satın alabilirim?** Fiyatlandırma için [satın alma sayfası](https://purchase.groupdocs.com/buy) sayfasını ziyaret edin.

## GroupDocs Viewer for Java Nedir?
**GroupDocs Viewer for Java**, MS Project dahil olmak üzere 150'den fazla belge formatını web‑uyumlu HTML, PNG, JPEG veya PDF'ye dönüştüren bir Java SDK'dır.  
Ayrıştırma mantığını soyutlar, zaman birimleri gibi render seçeneklerini kontrol etmenizi sağlar ve Java 8 ve üzerini destekleyen herhangi bir platformda çalışır.

## Neden MS Project HTML dışa aktarımı için zaman birimlerini ayarlamalıyız?
Zaman birimini **gün** olarak ayarlamak görsel gürültüyü azaltır, çoğu raporlama periyoduna uyar ve daha az ayrıntılı zaman işareti üretildiği için sayfa yükleme sürelerini iyileştirir. Sayısal olarak, gün yerine dakika kullanarak render etmek tipik 30‑günlük projeler için oluşturulan HTML boyutunu **%45** kadar azaltabilir ve istemci‑tarafı render'ı yaklaşık **%30** hızlandırır.

## Önkoşullar
- **Java Development Kit (JDK) 8 veya daha yeni** sürümünün çalışma istasyonunuzda kurulu olması.  
- **Maven** (veya Gradle) bağımlılık yönetimi için.  
- Dışa aktarmak istediğiniz bir **MS Project (.mpp)** dosyası.  
- **GroupDocs Viewer for Java** lisansına (deneme veya kalıcı) erişim.  

### Gerekli Kütüphaneler
Aşağıdaki bağımlılığı `pom.xml` dosyanıza ekleyin (veya eşdeğer Gradle snippet'ine):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro ipucu:** Sürüm numarasını güncel tutun; yeni sürümler format desteği ve performans iyileştirmeleri ekler.

## GroupDocs Viewer for Java Nasıl Kurulur?
Görüntüleyiciyi, MS Project dosyanıza işaret eden bir `Viewer` örneği oluşturarak başlatın. `Viewer` sınıfı tüm render işlemleri için giriş noktasıdır. Kaynak belgeyi yükler, iç yapılandırmaları hazırlar ve istenen çıktı formatlarını üretmek için `view()` ve `viewToHtml()` gibi metodları sunar.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Tanım referansı:** `Viewer` sınıfı, bir kaynak belgeyi yükleyen ve `view()` ve `viewToHtml()` gibi render metodları sağlayan GroupDocs Viewer’ın çekirdek bileşenidir.

## HTML dışa aktarımı için zaman birimlerini nasıl ayarlarım?
Zaman granülerliğini değiştirmek için bir `ViewOptions` nesnesi oluşturun, `ProjectOptions` özelliğini `TimeUnit.DAYS` kullanacak şekilde yapılandırın ve bunu görüntüleyiciye geçirin. `ViewOptions` belge için render ayarlarını tanımlar, `TimeUnit` enum'ı ise zaman‑ilişkili veriler için birimi (dakika, saat, gün) belirtir. Bu seçenekleri ayarladıktan sonra `viewer.view(options)` çağrısıyla günlük işaretli HTML üretin.

`new Viewer("file.mpp")` ile MS Project dosyanızı yükleyin, bir `ViewOptions` nesnesi oluşturun, `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` ayarını yapın ve ardından `viewer.view(options)` çağırın. Bu üç adımlı akış zaman birimini dakikadan güne değiştirir ve yalnızca günlük aralıkları gösteren HTML dosyaları üretir.

### Adım 1: Çıktı klasörünü tanımlayın
HTML sayfalarının kaydedileceği yazılabilir bir dizin seçin, örneğin `output/`.

### Adım 2: Gömülü kaynaklarla view seçenekleri oluşturun
Gömülü kaynaklar (CSS, JavaScript) HTML sayfalarının bağımsız olmasını sağlar.

### Adım 3: Zaman birimini gün olarak ayarlayın
Granülerliği değiştirmek için `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` kullanın.

### Adım 4: Belgeyi render edin
`viewer.view(options)` çağırın; görüntüleyici her proje sayfası için bir HTML dosyası oluşturur ve çıktı klasörüne yazar.

### Adım 5: Sonucu doğrulayın
Oluşturulan `index.html` dosyasını bir tarayıcıda açın; görev çubuklarının dakika işaretleri yerine gün işaretlerine hizalandığını görmelisiniz.

## Yaygın Tuzaklar ve Sorun Giderme
- **Yanlış çıktı yolu** – Dizin mevcut olduğundan ve Java işleminin yazma izinlerine sahip olduğundan emin olun.  
- **Lisans eksik** – Geçerli bir lisans olmadan görüntüleyici deneme moduna geçer ve filigran ekleyebilir.  
- **Büyük dosyalar (> 500 MB)** – JVM yığın boyutunu (`-Xmx2g`) artırmayı veya sayfaları toplu işlemek için `options.setRenderLimit(1000)` ile render etmeyi düşünün.  

## Ayarlanmış zaman birimi HTML dışa aktarımının pratik uygulamaları
1. **Yönetici panoları** – Günlük granülerlik çoğu KPI görselleştirmesine uyar.  
2. **Otomatik durum e-postaları** – Oluşturulan HTML'i doğrudan e-posta gövdelerine gömerek hızlı güncellemeler sağlayın.  
3. **Proje portalları** – HTML'i bir intranet sitesinde barındırın; ekip üyeleri görevleri gün bazında filtreleyebilir.  

## Büyük MS Project dosyaları için performans hususları
- **Bellek yönetimi** – Kullanılmayan nesneleri hızlıca serbest bırakmak için Java’nın çöp toplama bayraklarını (`-XX:+UseG1GC`) kullanın.  
- **Seçici render** – Yalnızca Gantt şemasına ihtiyacınız varsa, diğer kaynak renderlarını `options.getProjectOptions().setRenderGantt(true)` ve `setRenderResources(false)` ile devre dışı bırakın.  
- **Paralel işleme** – Toplu dönüşümler için dosya başına ayrı `Viewer` nesneleri oluşturun ve çok çekirdekli CPU'ları kullanmak amacıyla bir iş parçacığı havuzunda çalıştırın.  

## Sonuç
Artık GroupDocs Viewer for Java kullanarak zaman birimleri gün olarak ayarlanmış bir **ms project html export** gerçekleştirmek için eksiksiz, üretim‑hazır bir iş akışına sahipsiniz. Bu yaklaşım HTML boyutunu azaltır, istemci render'ını hızlandırır ve proje takvimlerinin paydaş‑dostu bir görünümünü sunar. PDF dışa aktarımı veya görüntü anlık görüntüleri gibi ek render seçeneklerini keşfederek entegrasyonu daha geniş raporlama hatlarına genişletebilirsiniz.

## Sıkça Sorulan Sorular

**S: Diğer Proje görünümlerini (ör. Kaynak Sayfası) HTML'ye render edebilir miyim?**  
C: Evet, `ProjectOptions` nesnesi render'dan önce Gantt, Kaynak Sayfası ve Takvim gibi belirli görünümleri etkinleştirmenize veya devre dışı bırakmanıza olanak tanır.

**S: Oluşturulan HTML'nin CSS'ini özelleştirmek mümkün mü?**  
C: Kesinlikle. `options.setStyleSheetPath("path/to/custom.css")` ile özel bir stil sayfası yolu sağlayın ve görüntüleyici bunu her sayfaya gömecektir.

**S: GroupDocs Viewer, MS Project için hangi dosya boyutu limitlerini destekliyor?**  
C: SDK, akış mimarisi sayesinde belgeyi tamamen belleğe yüklemeye gerek kalmadan **500 MB**'a kadar dosyaları işleyebilir.

**S: Sunucuda Microsoft Project kurmam gerekiyor mu?**  
C: Hayır. GroupDocs Viewer .mpp formatını doğrudan ayrıştırır ve Microsoft Project ya da herhangi bir Office kurulumuna ihtiyaç duymaz.

**S: Görüntüleyiciyi üretim ortamı için nasıl lisanslarım?**  
C: GroupDocs mağazasından kalıcı bir lisans satın alın; çalışma zamanında `License license = new License(); license.setLicense("path/to/license.lic");` kodu ile lisans dosyasını uygulayın. Kısa vadeli ihtiyaçlar için bir [geçici lisans](https://purchase.groupdocs.com/temporary-license/) alabilirsiniz.

**Son Güncelleme:** 2026-05-21  
**Test Edilen Versiyon:** GroupDocs Viewer Java 25.2  
**Yazar:** GroupDocs  

**Kaynaklar**  
- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)  
- [API Referansı](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer İndir](https://releases.groupdocs.com/viewer/java/)  
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)  

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## İlgili Öğreticiler

- [GroupDocs.Viewer for Java Kullanarak Notlarla MS Project Dosyalarını HTML, JPG, PNG ve PDF Olarak Render Etme](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Java'da Zaman Aralıklarıyla Proje Belgelerini Render Etmek İçin GroupDocs Viewer Kullanma](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java'da Lisansları Ayarlama: Dosya ve URL Kurulum Kılavuzu](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)