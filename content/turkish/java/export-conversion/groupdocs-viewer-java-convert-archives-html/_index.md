---
date: '2026-08-03'
description: GroupDocs.Viewer Java kullanarak zip'i html'ye nasıl dönüştüreceğinizi,
  sayfa başına öğe sayısını nasıl ayarlayacağınızı, html kaynaklarını nasıl gömeceğinizi
  ve arşivleri verimli bir şekilde toplu olarak nasıl dönüştüreceğinizi öğrenin.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: GroupDocs.Viewer Java kullanarak zip'i html'ye nasıl dönüştüreceğinizi,
  sayfa başına öğe sayısını nasıl ayarlayacağınızı, html kaynaklarını nasıl gömeceğinizi
  ve arşivleri verimli bir şekilde toplu olarak nasıl dönüştüreceğinizi öğrenin. Adım
  adım kod ve performans ipuçlarını izleyin.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: GroupDocs.Viewer Java ile zip'i html'ye dönüştürün ve sayfa başına öğe sayısını
  ayarlayın
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
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

# ZIP'i HTML'ye dönüştürün ve sayfa başına öğe sayısını GroupDocs.Viewer Java ile ayarlayın

Birçok web uygulamasında ZIP veya RAR arşivinin içeriğini doğrudan tarayıcıda göstermeniz gerekir. GroupDocs.Viewer for Java ile **zip'i html'ye dönüştür** tek bir adımda, her sayfada kaç arşiv girdisinin görüneceğini kontrol edebilir, tüm destekleyici resimleri ve CSS'yi gömebilir ve hatta onlarca arşivi toplu olarak işleyebilirsiniz. Bu öğretici, Maven kurulumundan çok sayfalı renderlamaya kadar tam iş akışını adım adım gösterir ve her ayarın performans ve kullanılabilirlik açısından neden önemli olduğunu açıklar.

![GroupDocs.Viewer for Java ile Arşivleri HTML'ye Dönüştür](/viewer/export-conversion/convert-archives-to-html-java.png)

## Hızlı cevaplar
- **“set items per page” neyi kontrol eder?** Arşivden kaç dosya veya klasörün her oluşturulan HTML sayfasında görüneceğini belirler.  
- **HTML içinde doğrudan resim ve CSS gömebilir miyim?** Evet – kaynakları HTML içinde gömmek için `forEmbeddedResources` seçeneğini kullanın.  
- **Toplu dönüşüm mümkün mü?** Kesinlikle; arşiv koleksiyonunu döngüye alabilir ve her birini aynı ayarlarla renderlayabilirsiniz.  
- **GroupDocs.Viewer kullanmak için Maven'e ihtiyacım var mı?** Evet, aşağıda gösterildiği gibi `groupdocs-viewer` Maven bağımlılığını ekleyin.  
- **Hangi çıktı formatları destekleniyor?** Tek sayfalık HTML ve çok sayfalı HTML her ikisi de mevcuttur ve kütüphane 50+ giriş arşiv türünü destekler.

## GroupDocs.Viewer'da “set items per page” nedir?
**set items per page** ayarı arşiv renderleme seçeneklerine aittir. Çok sayfalı bir HTML belgesi oluşturduğunuzda, görüntüleyiciye her HTML sayfasında kaç arşiv girdisinin (dosya veya klasör) gösterileceğini söyler. Bu değeri ayarlamak, özellikle büyük arşivlerde sayfa boyutu ve gezinme hızını dengelemenize yardımcı olur.

## Neden kaynakları HTML içinde gömüyoruz?
Kaynakları (resimler, CSS, fontlar) doğrudan HTML dosyasının içine gömmek, harici dosyalar olmadan açılabilen tek bir taşınabilir belge oluşturur. Bu, e-posta ekleri, çevrim dışı görüntüleme veya çıktıyı diğer web sayfalarına gömmek için idealdir. Bu yaklaşım ayrıca dağıtımı basitleştirir çünkü harici varlık yollarını yönetmek gerekmez.

## Önkoşullar
- **Gerekli kütüphaneler:** GroupDocs.Viewer sürüm 25.2 veya üzeri dahil edin.  
- **Ortam:** Java Development Kit (JDK) yüklü ve yapılandırılmış.  
- **Bilgi:** Temel Java ve Maven bağımlılık yönetimi.  

## Maven GroupDocs Viewer kurulumu

`pom.xml` dosyanıza GroupDocs deposunu ve viewer bağımlılığını ekleyin:

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

### Lisans edinme
GroupDocs.Viewer bir **ücretsiz deneme bağlantısı**, geçici bir lisans veya tam satın alma seçeneği sunar. Proje zaman çizelgenize uyanı seçin.

### Temel başlatma
Maven kurulumu sonrası, viewer'ı kodunuza ekleyin:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Arşivleri tek sayfalık HTML'ye nasıl renderlayabilirsiniz
Viewer, bir belgeyi veya arşivi renderlamak için yükleyen temel sınıftır.

Tüm arşivi içeren tek bir HTML dosyası oluşturmak için ZIP dosyası için bir `Viewer` örneği oluşturun ve tüm resimleri, CSS'i ve fontları gömmek için `HtmlViewOptions.forEmbeddedResources()` kullanın. Bu seçeneklerle arşivi renderlamak, e-posta veya çevrim dışı kullanım için uygun tek bir bağımsız sayfa üretir.

### Adım 1: Çıktı dizinini tanımlayın
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Adım 2: Tek sayfalık çıktı için dosya adını ayarlayın
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Adım 3: Viewer'ı başlatın
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Adım 4: Render seçeneklerini yapılandırın (kaynakları HTML içinde gömün)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Adım 5: Tek sayfa olarak renderlayın
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Arşivleri çok sayfalı HTML'ye nasıl renderlayıp sayfa başına öğe sayısını ayarlarsınız
`HtmlViewOptions`, görüntüleyicinin HTML çıktısını nasıl renderlayacağını yapılandırır; sayfalama ve kaynak gömme dahil.

Bir arşivi birden fazla sayfaya bölmek için `HtmlViewOptions.forEmbeddedResources()` oluşturun ve istenen sayfa boyutunu `options.setItemsPerPage(20)` ile ayarlayın. Viewer, her biri belirtilen giriş sayısına kadar gösteren ayrı HTML dosyaları oluşturacak; bu, büyük arşivlerde gezinmeyi iyileştirir ve daha hızlı yükleme sağlar.

### Adım 1: Çıktı dizinini yeniden kullanın
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Adım 2: Çoklu sayfalar için dosya adı formatını tanımlayın
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Adım 3: Viewer'ı tekrar başlatın
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Adım 4: Çok sayfalı seçenekleri yapılandırın (kaynakları HTML içinde gömün)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Adım 5: Sayfa başına öğe sayısını ayarlayın (eylemdeki anahtar kelime)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Pratik uygulamalar
- **Belge yönetim sistemleri:** Ek görüntüleyiciler kurmadan arşiv önizleme işlevi ekleyin.  
- **Web portalları:** Kullanıcılara paketlenmiş belgeleri hızlı ve indirme gerektirmeden keşfetme imkanı sunun.  
- **İş birliği araçları:** Takımların paylaşılan arşivleri doğrudan tarayıcıda incelemesine izin verin.

## Performans değerlendirmeleri
- **Kaynak yönetimi:** Arşivleri akış olarak işleyerek bellek kullanımını düşük tutun; viewer, tüm dosyayı belleğe yüklemeden 500 MB'a kadar arşivleri işleyebilir.  
- **Arşivleri toplu dönüştürme:** Arşiv dosyaları listesini döngüye alıp aynı render mantığını çağırarak verimliliği maksimize edin.  
- **Önbellekleme stratejisi:** Aynı arşive sık erişiliyorsa renderlanmış HTML'i önbellekte saklayın, tekrar işleme süresini %70'e kadar azaltın.

## Sıkça Sorulan Sorular
**S: GroupDocs.Viewer Java nedir?**  
C: GroupDocs.Viewer Java, ZIP ve RAR dahil 50'den fazla belge ve arşiv formatını HTML, PDF veya görüntü dosyalarına dış uygulamalara ihtiyaç duymadan renderlayan bir sunucu‑tarafı kütüphanedir.

**S: GroupDocs.Viewer'ın ücretsiz deneme sürümünü nasıl elde edebilirim?**  
C: İndirmek ve denemek için [ücretsiz deneme bağlantısını](https://releases.groupdocs.com/viewer/java/) ziyaret edin.

**S: Arşivlerin dışında başka belge türlerini dönüştürebilir miyim?**  
C: Evet, viewer PDF'ler, Word, Excel, PowerPoint ve 35+ ek formatı destekler.

**S: Renderlama yavaşsa ne yapmalıyım?**  
C: Sayfa başına öğe sayısını azaltın, akışı etkinleştirin veya hızı artırmak için arşivleri daha küçük partilerde işleyin.

**S: Yardım veya destek nereden alabilirim?**  
C: [destek forumu](https://forum.groupdocs.com/c/viewer/9) üzerinden ulaşabilirsiniz.

**S: CSS ve resimleri doğrudan HTML içinde gömmek mümkün mü?**  
C: Kesinlikle—örneklerde gösterildiği gibi `HtmlViewOptions.forEmbeddedResources` kullanın.

**S: Bir klasördeki arşivleri toplu olarak nasıl dönüştürürüm?**  
C: Her dosyayı bir `for` döngüsüyle yineleyin ve her yineleme için aynı `Viewer` ve `HtmlViewOptions` yapılandırmasını uygulayın.

## Kaynaklar
- **Dokümantasyon:** [GroupDocs dokümantasyonu](https://docs.groupdocs.com/viewer/java/) ile işlevselliği daha derinlemesine inceleyin.  
- **API referansı:** Tam API'yi [GroupDocs API](https://reference.groupdocs.com/viewer/java/) adresinde keşfedin.  
- **İndirme:** En son ikili dosyaları [indirme sayfasından](https://releases.groupdocs.com/viewer/java/) alın.  
- **Satın alma ve lisanslama:** [satın alma sayfasında](https://purchase.groupdocs.com/buy) seçenekleri inceleyin.  
- **Destek ve topluluk:** [GroupDocs forumunda](https://forum.groupdocs.com/c/viewer/9) tartışmalara katılın.

---

**Son Güncelleme:** 2026-08-03  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs

## İlgili Öğreticiler
- [ZIP'i HTML'ye dönüştürme ve ZIP klasörlerini Java'da GroupDocs.Viewer ile renderleme](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java ile ZIP'i PDF'ye dönüştürme - Özel Dosya Adları](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [GroupDocs.Viewer for Java kullanarak DOCX'i HTML'ye dönüştürme: Adım Adım Kılavuz](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)