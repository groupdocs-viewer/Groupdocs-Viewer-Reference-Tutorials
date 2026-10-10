---
date: '2026-10-10'
description: GroupDocs.Viewer Java kullanarak zip'i html'ye nasıl dönüştüreceğinizi,
  sayfa başına öğe sayısını nasıl ayarlayacağınızı, embed resources html ve arşivleri
  verimli bir şekilde toplu olarak nasıl dönüştüreceğinizi öğrenin.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: GroupDocs.Viewer Java ile zip'i html'ye nasıl dönüştüreceğinizi, embed
  resources, sayfa başına öğe sayısını nasıl ayarlayacağınızı ve fast, portable web
  previews için arşivleri batch‑process nasıl yapacağınızı öğrenin.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: GroupDocs.Viewer Java ile sayfalama özelliğiyle zip'i HTML'ye dönüştürün
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: GroupDocs.Viewer Java ile zip'i html'ye dönüştürün ve sayfa başına öğe sayısını
  ayarlayın
type: docs
url: /tr/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ZIP'i HTML'e dönüştür ve sayfa başına öğe sayısını GroupDocs.Viewer Java ile ayarla

Birçok web uygulamasında bir ZIP veya RAR arşivinin içeriğini doğrudan tarayıcıda göstermeniz gerekir. **ZIP dosyalarını** HTML'e dönüştürmek için GroupDocs.Viewer for Java kullanmak yaygın bir gereksinimdir ve kütüphane, görüntüleri, CSS'i ve yazı tiplerini gömmenize olanak tanır, böylece sonuç tek, taşınabilir bir sayfa olur. Bu öğretici, Maven kurulumundan çok sayfalı render’a kadar her şeyi adım adım anlatırken, her seçeneğin performans ve kullanılabilirlik açısından neden önemli olduğunu açıklar.

![GroupDocs.Viewer for Java ile Arşivleri HTML'e Dönüştür](/viewer/export-conversion/convert-archives-to-html-java.png)

## Hızlı cevaplar
- **“Sayfa başına öğe sayısı” kontrolü ne işe yarar?** Bir arşivdeki kaç dosya veya klasörün her oluşturulan HTML sayfasında görüneceğini belirler.  
- **Görüntüleri ve CSS'i doğrudan HTML içinde gömebilir miyim?** Evet – kaynakları gömmek için `forEmbeddedResources` seçeneğini kullanın.  
- **Toplu dönüşüm mümkün mü?** Kesinlikle; bir arşiv koleksiyonunu döngüye alabilir ve aynı ayarlarla her birini render edebilirsiniz.  
- **GroupDocs.Viewer kullanmak için Maven gerekli mi?** Evet, aşağıda gösterildiği gibi `groupdocs-viewer` Maven bağımlılığını ekleyin.  
- **Hangi çıktı formatları destekleniyor?** Tek‑sayfa HTML ve çok‑sayfa HTML her ikisi de mevcuttur ve kütüphane 50+ giriş arşiv türünü destekler.

## GroupDocs.Viewer'da “sayfa başına öğe sayısı” nedir?
Bu ayar, çok‑sayfalı bir belge oluştururken her HTML sayfasında kaç arşiv girdisinin (dosya veya klasör) gösterileceğini belirler. Bu değeri ayarlamak, özellikle büyük arşivlerde sayfa boyutunu ve gezinme hızını dengelemeye yardımcı olur; sayfa başına yüklenen veri miktarını sınırlayarak son kullanıcıların render süresini azaltır.

## Neden kaynakları HTML içinde gömülür?
Kaynakları (görüntüler, CSS, yazı tipleri) doğrudan HTML dosyasına gömmek, harici dosyalar olmadan açılabilen tek bir taşınabilir belge oluşturur. Bu, e‑posta ekleri, çevrim dışı görüntüleme veya çıktıyı diğer web sayfalarına gömme senaryoları için idealdir. Ayrıca harici varlık yollarını yönetme ihtiyacını ortadan kaldırır.

## Önkoşullar

- **Gerekli kütüphaneler:** GroupDocs.Viewer sürüm 25.2 veya daha yenisi.  
- **Ortam:** Java Development Kit (JDK) kurulu ve yapılandırılmış.  
- **Bilgi:** Temel Java ve Maven bağımlılık yönetimi bilgisi.  

## Maven GroupDocs Viewer kurulumu

`pom.xml` dosyanıza GroupDocs deposunu ve görüntüleyici bağımlılığını ekleyin:

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
GroupDocs.Viewer bir **ücretsiz deneme bağlantısı**, geçici lisans veya tam satın alma seçeneği sunar. Proje zaman çizelgenize uygun olanı seçin.

## Temel başlatma
`Viewer` sınıfı, belgeleri ve arşivleri render etmek için giriş noktasıdır. Maven kurulumu tamamlandıktan sonra görüntüleyiciyi kodunuza dahil edin:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Arşivleri tek sayfalı HTML'e nasıl render ederiz
`HtmlViewOptions` sınıfı, HTML çıktısı için gömme kaynaklar gibi ayarları tanımlar. Arşivi yükleyin, HTML seçeneklerini kaynakları gömmek üzere yapılandırın ve her şeyi tek bir kendi içinde barındıran sayfaya render edin. Bu, tüm dosyaları, görüntüleri, CSS'i ve yazı tiplerini içeren tek bir HTML dosyası üretir; çevrim dışı kullanım veya e‑posta eki için hazırdır.

**Doğrudan cevap:** ZIP dosyası için bir `Viewer` örneği oluşturun, `HtmlViewOptions.forEmbeddedResources()` çağırın ve `viewer.view(documentPath, options)` metodunu çalıştırın. Bu, tüm dosyaları, görüntüleri, CSS'i ve yazı tiplerini içeren tek bir HTML dosyası üretir; çevrim dışı kullanım veya e‑posta eki için hazırdır.

### Adım 1: Çıktı dizinini tanımla
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Adım 2: Tek sayfalı çıktı için dosya adını ayarla
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Adım 3: Görüntüleyiciyi başlat
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Adım 4: Render seçeneklerini yapılandır (kaynakları HTML içinde göm)
`HtmlViewOptions` sınıfı, HTML çıktısı için gömme kaynaklar gibi ayarları tanımlar. Her şeyi tek bir dosyada birleştirmek için `forEmbeddedResources()` kullanın.

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Adım 5: Tek sayfa olarak render et
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Arşivleri çok sayfalı HTML'e nasıl render eder ve sayfa başına öğe sayısını ayarlar
`HtmlViewOptions` sınıfı aynı zamanda sayfalama desteği sunar. `options.setItemsPerPage(N)` çağrısıyla, arşivi birkaç HTML dosyasına bölerek her birinin **N** girişe kadar göstermesini sağlarsınız. Bu yaklaşım, büyük arşivlerde gezinme hızını artırırken her sayfayı hafif tutar.

**Doğrudan cevap:** `HtmlViewOptions.forEmbeddedResources()` kullanın, `options.setItemsPerPage(N)` çağırın ve arşivi render edin. Görüntüleyici, her biri **N** girişe kadar içeren ayrı HTML dosyaları (sayfa başına bir dosya) oluşturur; bu da büyük arşivlerde gezinmeyi hızlandırır.

### Adım 1: Çıktı dizinini yeniden kullan
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Adım 2: Çoklu sayfalar için dosya adı formatını tanımla
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Adım 3: Görüntüleyiciyi tekrar başlat
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Adım 4: Çok sayfalı seçenekleri yapılandır (kaynakları HTML içinde göm)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Adım 5: Sayfa başına öğe sayısını ayarla (eylemdeki anahtar kelime)
`options.setItemsPerPage(20); // how to convert zip archives with 20 entries per page`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Pratik uygulamalar

- **Belge yönetim sistemleri:** Ek görüntüleyiciler kurmadan arşiv önizleme işlevi ekleyin.  
- **Web portalları:** Kullanıcılara paketlenmiş belgeleri indirmeden hızlı bir şekilde keşfetme imkanı sunun.  
- **İş birliği araçları:** Takımların paylaşılan arşivleri doğrudan tarayıcıda incelemesini sağlayın.

## Performans değerlendirmeleri

- **Kaynak yönetimi:** Arşivleri akış olarak işleyerek bellek kullanımını düşük tutun; görüntüleyici, tüm dosyayı belleğe yüklemeden 500 MB’a kadar arşivleri işleyebilir.  
- **Toplu arşiv dönüştürme:** Bir dizi arşiv dosyasını döngüye alıp aynı render mantığını çağırarak verimliliği maksimize edin.  
- **Önbellek stratejisi:** Aynı arşiv sık erişiliyorsa render edilmiş HTML’i önbellekte saklayın; bu, tekrar işleme süresini %70’e kadar azaltabilir.

## Sıkça sorulan sorular

**S: GroupDocs.Viewer Java nedir?**  
C: GroupDocs.Viewer Java, ZIP ve RAR dahil 50’den fazla belge ve arşiv formatını HTML, PDF veya görüntü dosyalarına dış uygulamalara ihtiyaç duymadan render eden bir sunucu‑tarafı kütüphanedir.

**S: GroupDocs.Viewer'ın ücretsiz deneme sürümünü nasıl elde edebilirim?**  
C: [ücretsiz deneme bağlantısı](https://releases.groupdocs.com/viewer/java/) üzerinden indirip test edin.

**S: Arşivlerin dışında başka belge türlerini dönüştürebilir miyim?**  
C: Evet, görüntüleyici PDF, Word, Excel, PowerPoint ve 35+ ek formatı destekler.

**S: Render yavaşsa ne yapmalıyım?**  
C: Sayfa başına öğe sayısını azaltın, akışı etkinleştirin veya arşivleri daha küçük partiler halinde işleyerek hızı artırın.

**S: Yardım veya destek nereden alınabilir?**  
C: [destek forumu](https://forum.groupdocs.com/c/viewer/9) üzerinden iletişime geçin.

**S: CSS ve görüntüleri doğrudan HTML içinde gömmek mümkün mü?**  
C: Kesinlikle—örneklerde gösterildiği gibi `HtmlViewOptions.forEmbeddedResources` kullanın.

**S: Bir klasördeki arşivleri toplu olarak nasıl dönüştürebilirim?**  
C: `for` döngüsüyle her dosyayı yineleyin, aynı `Viewer` ve `HtmlViewOptions` yapılandırmasını her yinelemede uygulayın.

**S: Diğer kullanıcılarla sorunları nerede tartışabilirim?**  
C: [GroupDocs forumu](https://forum.groupdocs.com/c/viewer/9) üzerinden topluluk tartışmalarına katılın.

## Kaynaklar

- **Dokümantasyon:** İşlevselliği daha derinlemesine incelemek için [GroupDocs belgeleri](https://docs.groupdocs.com/viewer/java/) adresini ziyaret edin.  
- **API referansı:** Tam API’yı [GroupDocs API](https://reference.groupdocs.com/viewer/java/) üzerinden keşfedin.  
- **İndirme:** En yeni ikili dosyaları [indirme sayfası](https://releases.groupdocs.com/viewer/java/) üzerinden alın.  
- **Satın alma ve lisanslama:** Seçenekleri [satın alma sayfası](https://purchase.groupdocs.com/buy) üzerinden gözden geçirin.  
- **Destek ve topluluk:** Tartışmalara [destek forumu](https://forum.groupdocs.com/c/viewer/9) üzerinden katılın.  
- **GroupDocs forumu:** Topluluk yardımı için [GroupDocs forumu](https://forum.groupdocs.com/c/viewer/9) adresini kullanın.

---

**Son Güncelleme:** 2026-10-10  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs

## İlgili öğreticiler

- [Java ile GroupDocs.Viewer kullanarak zip'i HTML'e dönüştür ve zip klasörlerini render et](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java ile zip'i pdf'e dönüştür - Özel Dosya Adları](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [GroupDocs.Viewer for Java ile DOCX'i HTML'e Dönüştürme: Adım Adım Kılavuz](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}