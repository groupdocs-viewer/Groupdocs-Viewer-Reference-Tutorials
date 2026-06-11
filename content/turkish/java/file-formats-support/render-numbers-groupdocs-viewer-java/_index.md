---
date: '2026-03-05'
description: GroupDocs.Viewer for Java kullanarak sayıları PDF ve HTML, JPG, PNG gibi
  diğer formatlara nasıl dönüştüreceğinizi öğrenin. Bu kılavuz, kurulum, render teknikleri
  ve pratik uygulamaları kapsar.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: GroupDocs.Viewer for Java ile Numbers'ı PDF'ye Dönüştür
type: docs
url: /tr/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Numbers'ı PDF'ye (ve Diğer Formatlara) GroupDocs.Viewer for Java ile Dönüştürme

Apple Numbers belgelerini web'de veya masaüstü uygulamalarda görüntülemek zor olabilir, özellikle **convert numbers to pdf** yapmanız veya görüntü olarak gömmeniz gerektiğinde. Bu öğreticide, **GroupDocs.Viewer for Java** kullanarak Numbers dosyalarını HTML, JPG, PNG ve **PDF**'ye nasıl dönüştüreceğinizi adım adım göstereceğiz—bu sayede elektronik tablolarınızı paylaşmak, ön izlemek veya arşivlemek için esnek seçenekler elde edersiniz.

![Apple Numbers Belgelerini GroupDocs.Viewer for Java ile Görüntüleme](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Öğrenecekleriniz
- Maven tabanlı bir Java projesinde GroupDocs.Viewer'ı nasıl kuracağınız  
- Adım adım kod ile **convert numbers to pdf**, **convert numbers to html**, ve **convert numbers to jpg**  
- Belge dönüşümünün web portallarına, e-posta iş akışlarına ve DMS entegrasyonlarına değer kattığı gerçek dünya senaryoları  

## Hızlı Yanıtlar
- **Numbers'ı Java ile PDF'ye dönüştürebilir miyim?** Evet, GroupDocs.Viewer'da `PdfViewOptions` kullanarak.  
- **Web ön izleme için en iyi format hangisidir?** HTML en etkileşimli deneyimi sunar.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Deneme dışı dağıtımlar için ticari bir lisans gereklidir.  
- **Görüntü dönüşümü destekleniyor mu?** Kesinlikle—yüksek kaliteli görüntüler için `JpgViewOptions` veya `PngViewOptions` kullanın.  
- **Hangi Java sürümü gereklidir?** Bağımlılık yönetimi için Java 8+ ve Maven.  

## Önkoşullar
- Java Development Kit (JDK) 8 veya daha yüksek bir sürüm yüklü.  
- Bağımlılıkları yönetmek için Maven.  
- Java dosya I/O ve yol yapıları hakkında temel bilgi.  

## GroupDocs.Viewer for Java'ı Kurma

### Maven ile Kurulum
Depoyu ve bağımlılığı `pom.xml` dosyanıza ekleyin. Bu blok tam olarak gösterildiği gibi kalmalıdır:

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

### Lisans Alımı
- **Free Trial:** Ücretsiz deneme, tüm özellikleri maliyetsiz değerlendirin.  
- **Temporary License:** Uzun süreli test için zaman sınırlı bir anahtar isteyin.  
- **Purchase:** Ticari projeler için tam lisans edinin.  

## Numbers Belgesini HTML Olarak Render Etme  
*Kullanım durumu: bir elektronik tabloyu doğrudan bir web sayfasına gömmek.*

### Adım 1: Viewer'ı Başlat ve HTML Seçeneklerini Yapılandır
Aşağıda çalıştıracağınız tam kod bulunmaktadır. Yorumlar her satırı açıklar, ancak **kod bloğunu değiştirmeyin**.

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

- **Neden önemli:** `HtmlViewOptions.forEmbeddedResources()` CSS ve görüntüleri HTML içinde paketler, bu da hızlı web ön izlemeleri için mükemmeldir.

## Numbers Belgesini JPG Olarak Render Etme  
*Sosyal medyada veya e-postada bir elektronik tablonun anlık görüntüsünü paylaşmak için harika.*

### Adım 1: Viewer'ı Kur ve JPG Seçeneklerini Ayarla
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

- **İpucu:** Daha küçük dosyalar için `options.setQuality(int)` ile görüntü kalitesini ayarlayın.

## Numbers Belgesini PNG Olarak Render Etme  
*Raporlar için kayıpsız, yüksek çözünürlüklü bir görüntü gerektiğinde idealdir.*

### Adım 1: PNG Seçeneklerini Başlat ve Yapılandır
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

- **Profesyonel ipucu:** Baskıya hazır görüntüler için DPI'yi kontrol etmek amacıyla `options.setResolution(int)` kullanın.

## Numbers Belgesini PDF Olarak Render Etme  
*Birçok geliştirici için temel hedef: **convert numbers to pdf** arşivleme veya dağıtım için.*

### Adım 1: PDF Dönüşümü için Viewer'ı Kur
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

- **Ana yapılandırma:** `PdfViewOptions` yazı tiplerini gömmenize ve sayfa boyutunu kontrol etmenize olanak tanır, böylece çıktı marka gereksinimlerinize uyar.

## Pratik Uygulamalar
- **Web Entegrasyonu:** Sitenizde etkileşimli bir elektronik tablo görüntüleyici için HTML olarak render edin.  
- **İçerik Paylaşımı:** Bültenlerde veya sohbetlerde hızlı görüntü gömmeleri için JPG/PNG'ye dönüştürün.  
- **Kurumsal DMS:** **convert numbers to pdf** kullanarak elektronik tablonun düzenlenemez, aranabilir bir sürümünü saklayın.  

## Performans Düşünceleri
- **Kaynak Yönetimi:** Yerel kaynakları hızlıca serbest bırakmak için `Viewer`'ı her zaman bir try‑with‑resources bloğunda (gösterildiği gibi) kapatın.  
- **Büyük Dosyalar:** Çok büyük Numbers dosyaları için sayfa sayfa işleme ve sonuçları akış olarak gönderme yöntemini düşünün; böylece yüksek bellek tüketiminden kaçınılır.  
- **İş Parçacığı Güvenliği:** Her iş parçacığı için ayrı bir `Viewer` örneği oluşturun; sınıf iş parçacığı güvenli değildir.  

## Sonuç
Artık GroupDocs.Viewer for Java kullanarak **convert numbers to pdf**, HTML, JPG ve PNG için eksiksiz bir araç setine sahipsiniz. Bu yetenekler, bir web portalına veri sağlama, rapor oluşturma veya elektronik tabloları arşivleme gibi esnek belge iş akışları oluşturmanıza olanak tanır.

### Sonraki Adımlar
Daha fazla özelleştirme seçeneğini [GroupDocs belgelerinde](https://docs.groupdocs.com/viewer/java/) keşfedin ve bu özellikleri kendi uygulamalarınıza entegre ederek deneyin.

## SSS Bölümü

**Q1: GroupDocs.Viewer hangi dosya formatlarını destekliyor?**  
A1: DOCX, XLSX, PDF ve daha fazlası dahil olmak üzere geniş bir belge formatı yelpazesini destekler.

**Q2: Büyük Numbers dosyalarını verimli bir şekilde nasıl yönetebilirim?**  
A2: Java'nın bellek yönetimi tekniklerini kullanın ve büyük dosya boyutlarını etkili bir şekilde işlemek için kodunuzu optimize edin.

**Q3: GroupDocs.Viewer ticari bir projede kullanılabilir mi?**  
A4: Evet, ancak ticari kullanım için bir lisans satın almanız gerekir.

**Q4: Görüntülerin çıktı kalitesini özelleştirmek mümkün mü?**  
A5: Kesinlikle. `JpgViewOptions` ve `PngViewOptions` içindeki ayarları değiştirebilirsiniz.

**Q5: Daha gelişmiş kullanım örneklerini nerede bulabilirim?**  
A5: Ayrıntılı dokümantasyon için [API referansına](https://reference.groupdocs.com/viewer/java/) göz atın.

## Sıkça Sorulan Sorular

**Q: Numbers dosyasını biçimlendirmeyi kaybetmeden PDF'ye nasıl dönüştürürüm?**  
A: Yukarıda gösterildiği gibi `PdfViewOptions` kullanın; görüntüleyici düzeni, yazı tiplerini ve hücre stillerini otomatik olarak korur.

**Q: Bir elektronik tabloyu tek bir çağrıyla görüntüye dönüştürebilir miyim?**  
A: Evet, `JpgViewOptions` veya `PngViewOptions` dönüşümü tek adımda gerçekleştirir, çözünürlük ve kaliteyi belirlemenize olanak tanır.

**Q: Birden fazla Numbers dosyasını toplu işleme yapmanın bir yolu var mı?**  
A: Görüntüleyici mantığını bir döngü içinde sarın, her dosya için `Viewer`'ı yeniden başlatın ve her çıktıyı ayrı bir klasöre yazın.

**Q: Her çıktı formatı için ayrı bir lisansa ihtiyacım var mı?**  
A: Hayır, tek bir GroupDocs.Viewer lisansı tüm desteklenen formatları kapsar.

**Q: Bu özellikler için hangi GroupDocs.Viewer sürümü gereklidir?**  
A: Örnekler 25.2 sürümünü hedeflemektedir; bu sürüm Numbers'tan PDF/HTML/Görüntü dönüşümünü tam olarak destekler.

## Kaynaklar
- **Dokümantasyon:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **API Referansı:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **İndirme:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Lisans Satın Al:** [Buy a License](https://purchase.groupdocs.com/buy)
- **Ücretsiz Deneme:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Geçici Lisans:** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **Destek Forumu:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-03-05  
**Test Edilen Sürüm:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs