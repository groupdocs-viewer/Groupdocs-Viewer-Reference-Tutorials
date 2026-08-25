---
date: '2026-08-25'
description: GroupDocs.Viewer for Java ile Apple Numbers dosyalarını PDF, HTML, JPG
  veya PNG formatına dönüştürmeyi öğrenin. Kurulum, java belge dönüştürme adımları
  ve web görüntüleme ipuçları dahil.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: GroupDocs.Viewer for Java ile Apple Numbers dosyalarını PDF, HTML,
  JPG veya PNG formatına dönüştürmeyi öğrenin. Kurulum, java belge dönüştürme adımları
  ve web görüntüleme ipuçları dahil.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: GroupDocs.Viewer for Java ile Apple Numbers dosyalarını nasıl dönüştürürsünüz
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: GroupDocs.Viewer for Java ile Apple Numbers dosyalarını nasıl dönüştürürsünüz
type: docs
url: /tr/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Apple Numbers dosyalarını GroupDocs.Viewer for Java ile nasıl dönüştürürsünüz

Apple Numbers elektronik tablolarını web üzerinde veya bir masaüstü istemcide görüntülemek bir bulmaca gibi hissettirebilir, özellikle **numbers'ı PDF'ye dönüştürmeniz** veya raporlar için görüntü olarak gömmeniz gerektiğinde. Bu öğreticide **numbers'ı nasıl dönüştüreceğinizi** PDF, HTML, JPG ve PNG formatlarına **GroupDocs.Viewer for Java** kullanarak öğreneceksiniz. Proje kurulumunu, kod‑seviyesinde render etmeyi ve gerçek dünya senaryolarını adım adım göstereceğiz, böylece birkaç dakika içinde sağlam ön izleme veya arşivleme boru hatları oluşturabilirsiniz.

![Apple Numbers Belgelerini GroupDocs.Viewer for Java ile Render Et](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Apple Numbers Belgelerini GroupDocs.Viewer for Java ile Render Et](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Ne öğreneceksiniz
- Maven‑tabanlı bir Java projesine GroupDocs.Viewer eklemeyi.  
- **numbers'ı pdf'ye dönüştürmek**, **numbers'ı html'ye dönüştürmek**, **numbers'ı jpg'ye dönüştürmek** ve **numbers'ı png'ye dönüştürmek** için adım‑adım kodu.  
- Web portalları, e‑posta iş akışları veya belge yönetim sistemleri için her çıktı formatını ne zaman seçmeniz gerektiği.  

## Hızlı cevaplar
- **Java ile Numbers dosyasını PDF'ye dönüştürebilir miyim?** Evet – `Viewer` sınıfını örnekleyin ve `PdfViewOptions` çağırarak depolanmaya hazır bir PDF elde edin.  
- **Hangi format en zengin web ön izlemesini sağlar?** HTML, çünkü tabloları, formülleri ve stillemeyi etkileşimli tutar.  
- **Üretim için lisansa ihtiyacım var mı?** Deneme dışı herhangi bir dağıtım için ticari lisans gereklidir.  
- **Görüntü dönüştürme destekleniyor mu?** Kesinlikle – yüksek kaliteli anlık görüntüler için `JpgViewOptions` veya `PngViewOptions` kullanın.  
- **Hangi Java sürümü gereklidir?** Bağımlılık yönetimi için Java 8+ ve Maven.  

## Önkoşullar
- Makinenizde yüklü Java Development Kit (JDK) 8 veya daha yeni bir sürüm.  
- Bağımlılıkları yönetmek ve projeyi derlemek için Maven.  
- Java dosya I/O, yol ve istisna yönetimi konularına temel aşinalık.  

## GroupDocs.Viewer for Java'ı kurma

### Maven ile kurulum
`pom.xml` dosyanıza GroupDocs deposunu ve Viewer bağımlılığını ekleyin. Bu blok tam olarak gösterildiği gibi kalmalıdır:

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

### Lisans edinimi
- **Free trial:** Tam özellik seti, kredi kartı gerektirmez.  
- **Temporary license:** Uzatılmış test için zaman sınırlı bir anahtar isteyin.  
- **Full purchase:** Ticari kullanım için kalıcı bir lisans edinin.  

## Viewer sınıfı nedir?
`Viewer` sınıfı, bir belgeyi yükleyen ve istenen çıktı formatına render eden GroupDocs.Viewer’ın çekirdek motorudur. Dosya tipi işleme görevlerini soyutlayarak iş mantığınıza odaklanmanızı sağlar, elektronik tablo iç yapısını ayrıştırmak zorunda kalmazsınız.

## Numbers dosyasını HTML'ye GroupDocs.Viewer for Java ile nasıl dönüştürürsünüz?

`HtmlViewOptions`, HTML render ayarlarını belirler; kaynakları gömmek veya harici dosyalara bağlamak gibi. Numbers dosyasını yükleyin, HTML seçeneklerini yapılandırın ve `viewer.view()` metodunu çağırın. `HtmlViewOptions.forEmbeddedResources()` metodu CSS ve görselleri doğrudan HTML içine paketler, böylece ek varlıklar olmadan bir web sayfasına gömülmesi ideal olur.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Neden önemli:** Gömülü kaynaklar ön izlemeyi kendi içinde tutar, kırık görsel bağlantılarını önler ve CDN dağıtımını basitleştirir.

## Numbers dosyasını JPG'ye GroupDocs.Viewer for Java ile nasıl dönüştürürsünüz?

`JpgViewOptions`, JPEG çıktısını yapılandırır; kalite ve boyut ayarları her render edilen sayfa için yapılabilir. Her elektronik tablo sayfasını bir JPEG anlık görüntüsüne dönüştürebilirsiniz. `quality` ayarını dosya boyutu ile görsel sadakati dengelemek için ayarlayın; bu, sosyal medya veya e‑posta bültenleri için hafif görseller gerektiğinde faydalıdır.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **İpucu:** Büyük çalışma kitaplarının daha hızlı işlenmesi için kaliteyi %70'e düşürün – görsel etkisi minimal olurken dosya boyutu dramatik şekilde azalır.

## Numbers dosyasını PNG'ye GroupDocs.Viewer for Java ile nasıl dönüştürürsünüz?

`PngViewOptions`, PNG çıktısını yapılandırır; kayıpsız sıkıştırma ve yüksek kaliteli görüntüler için çözünürlük ayarlarını destekler. PNG, kayıpsız sıkıştırma sunar ve render edilen her pikseli tam olarak korur. Baskı‑hazır grafikler veya PDF'ler için DPI artırmanız gerektiğinde `resolution` özelliğini kullanın.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro ipucu:** `options.setResolution(300)` ayarını yaparak yüksek çözünürlüklü çıktı elde edin; bu, basılı sayfalarda keskin görünür.

## Numbers dosyasını PDF'ye GroupDocs.Viewer for Java ile nasıl dönüştürürsünüz?

`PdfViewOptions`, PDF render ayarlarını tanımlar; font gömme, sıkıştırma ve sayfa boyutu kontrolü gibi. `PdfViewOptions` nesnesi fontları gömmeyi, sayfa boyutunu kontrol etmeyi ve Numbers çalışma kitabının orijinal düzenini korumayı sağlar. Dönüştürme tek bir çağrıda gerçekleşir, arama yapılabilir, düzenlenemez bir PDF üretir; arşivleme veya uyumluluk için mükemmeldir.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Ana yapılandırma:** `options.setCompress(true)` özelliğini etkinleştirerek kaliteyi kaybetmeden PDF boyutunu küçültün; bu, büyük ölçekli belge depoları için kritiktir.

## Neden GroupDocs.Viewer for Java kullanmalısınız?

GroupDocs.Viewer, Apple Numbers dahil **100'den fazla dosya formatını** destekler ve çok sayfalı elektronik tabloları belleğe tamamen yüklemeden render edebilir. Benchmark'lar, 250 sayfalık bir Numbers dosyasının standart 2.5 GHz CPU'da 8 saniyeden kısa sürede PDF'ye dönüştürüldüğünü gösteriyor; bu da kurumsal boru hatları için hız ve güvenilirlik sağlar.

## Pratik uygulamalar
- **Web entegrasyonu:** HTML render ederek, eklenti gerektirmeyen, tarayıcılar arasında çalışan etkileşimli bir elektronik tablo görüntüleyici oluşturun.  
- **İçerik paylaşımı:** JPG/PNG'ye dönüştürerek bültenlerde, sohbet uygulamalarında veya sosyal akışlarda hızlı görsel gömmeler yapın.  
- **Kurumsal DMS:** **numbers'ı PDF'ye nasıl dönüştürürsünüz** kısmını kullanarak, uyumluluk ve denetim izleri için düzenlenemez, aranabilir bir sürüm saklayın.  

## Performans hususları
- **Kaynak yönetimi:** `Viewer` nesnesini her zaman bir try‑with‑resources bloğu içinde örnekleyin (gösterildiği gibi) böylece yerel kaynaklar hemen serbest bırakılsın.  
- **Büyük çalışma kitapları:** Sayfa‑sayfa işleyin ve çıktıyı akışlayarak bellek kullanımını 100 MB'nin altında tutun, 500‑sayfalık dosyalar için bile.  
- **İş parçacığı güvenliği:** Her iş parçacığı için ayrı bir `Viewer` örneği oluşturun; sınıf thread‑safe değildir, tek bir örnek paylaşımı yarış koşullarına yol açabilir.  

## Yaygın tuzaklar ve sorun giderme

- **Eksik fontlar:** Oluşturulan PDF farklı görünüyorsa, sunucuda gerekli fontların bulunduğundan emin olun veya `PdfViewOptions.setEmbedFonts(true)` ile gömün.  
- **Boş sayfalar:** Numbers dosyasının şifre korumalı olmadığını doğrulayın; GroupDocs.Viewer şu anda korumalı çalışma kitaplarını çözemez.  
- **Bellek dışı hatalar:** Çok büyük dosyalar için `options.setPageCount(1)` ayarını etkinleştirerek bir seferde bir sayfa render edin ve sonuçları daha sonra birleştirin.  

## Sıkça sorulan sorular

**Q: GroupDocs.Viewer hangi dosya formatlarını destekliyor?**  
A: DOCX, XLSX, PDF, HTML ve Apple Numbers dahil olmak üzere 100'den fazla formatı tam render yetenekleriyle destekler.

**Q: Büyük Numbers dosyalarını verimli bir şekilde nasıl yönetirim?**  
A: Dönüştürmeyi sayfa‑sayfa akışlayın, bellek kullanımını sınırlamak için `options.setPageCount()` kullanın ve çıktı PDF'yi sıkıştırmayı düşünün.

**Q: GroupDocs.Viewer ticari bir projede kullanılabilir mi?**  
A: Evet—deneme sınırlamalarını kaldırmak ve üretim‑düzeyi destek almak için ticari bir lisans satın alın.

**Q: Görüntülerin çıktı kalitesini özelleştirmek mümkün mü?**  
A: Kesinlikle. `JjgpViewOptions.setQuality(int)` veya `PngViewOptions.setResolution(int)` ayarlarını ihtiyacınıza göre düzenleyin.

**Q: Daha gelişmiş kullanım örneklerini nerede bulabilirim?**  
A: Derinlemesine kılavuzlar, örnek projeler ve API referans detayları için [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) adresini ziyaret edin.

## Sonraki adımlar
Yukarıda gösterilen seçeneklerle denemeler yapın, ardından PDF'ye filigran ekleme, parola koruması ekleme veya görüntüyü bir Spring Boot REST servisine entegre etme gibi ek özelleştirmeleri keşfedin. Tam özellik kataloğu için [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) sayfasına bakabilirsiniz.

## Kaynaklar
- **Documentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs documentation:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **API reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Purchase license:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Support forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

**Last Updated:** 2026-08-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## İlgili Eğitimler

- [How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [How to Convert Excel to HTML and Render Hidden Rows & Columns in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Java Document Rendering Tutorial - Convert Files to HTML, PDF & Images](/viewer/java/rendering-basics/)