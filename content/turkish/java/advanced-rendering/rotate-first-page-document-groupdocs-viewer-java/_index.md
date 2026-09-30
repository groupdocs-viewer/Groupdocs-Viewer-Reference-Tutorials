---
date: '2026-09-30'
description: GroupDocs Viewer kullanarak Java’da sayfayı 90 derece nasıl döndüreceğinizi,
  kurulum, kod ve performans ipuçlarını öğrenin.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: GroupDocs Viewer kullanarak Java’da sayfayı 90 derece döndürün. Adım
  adım rehber, performans ipuçları ve geliştiriciler için gerçek dünya kullanım örnekleri.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Java için GroupDocs Viewer ile sayfayı 90 derece döndürün
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Java için GroupDocs Viewer ile sayfayı 90 derece döndürün
type: docs
url: /tr/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sayfayı 90 derece döndürme GroupDocs Viewer for Java ile

Eğer bir belgede **sayfayı 90 derece döndürmeniz** gerekiyorsa—PDF, Word dosyası ya da elektronik tablo olsun—Java’da programatik olarak yapmak zamanı tasarruf ettirir, manuel hataları ortadan kaldırır ve işlemi otomatikleştirilmiş akışlara entegre etmenizi sağlar. Bu ileri düzey rehberde, **GroupDocs Viewer for Java** kullanarak herhangi bir desteklenen belgenin ilk sayfasını nasıl döndüreceğinizi, bu yeteneğin gerçek dünya projelerinde neden önemli olduğunu ve süreci nasıl hafif ve bellek‑verimli tutacağınızı öğreneceksiniz.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Hızlı yanıtlar
- **“Sayfayı 90 derece döndürmek” ne anlama geliyor?** Seçilen sayfayı saat yönünde çeyrek tur döndürür.  
- **Döndürmeyi hangi kütüphane gerçekleştiriyor?** GroupDocs Viewer for Java `rotatePage` metodunu sağlar.  
- **PDF sayfalarını Java ile döndürebilir miyim?** Evet—aynı `rotatePage` çağrısını kullanın; PDF, DOCX, XLSX ve daha fazlası için çalışır.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ücretli lisans gerekir.  
- **İşlem bellek‑ağır mı?** `Viewer` örneğini hemen kapatırsanız değil; aşağıdaki performans ipuçlarına bakın.

## “Sayfayı 90 derece döndürmek” nedir?
Bir sayfayı 90 derece döndürmek, sayfayı portre konumundan manzara konumuna (veya tersine) yeniden yönlendirir, içerik değişmeden kalır. Sunumlar, yalnızca manzara grafiklerinin yazdırılması veya yan yatmış taranmış belgelerin düzeltilmesi için kullanışlıdır. Döndürme, render zamanında uygulanır ve orijinal dosya değişmez.

## Neden GroupDocs Viewer for Java ile programatik olarak sayfaları döndürmeliyiz?
GroupDocs Viewer **50+ giriş ve çıkış formatını** destekler—PDF, DOCX, PPTX, XLSX ve birçok görüntü türü dahil—bu sayede dış dönüştürücülere ihtiyaç duymadan herhangi bir belgeyi render edebilirsiniz. API akıcı, çok‑thread‑güvenli ve Java 8+ ortamında çalışır, bu da kurumsal‑düzey otomasyon için tutarlı dosya tipi işleme imkanı verir.

## Önkoşullar

- GroupDocs Viewer for Java (en son sürüm)
- JDK 8 veya üzeri
- Maven (veya Gradle) bağımlılık yönetimi için
- IntelliJ IDEA veya Eclipse gibi bir IDE
- Java I/O konusunda temel bilgi

## GroupDocs.Viewer for Java kurulumu

`pom.xml` dosyanıza GroupDocs deposunu ve bağımlılığı ekleyin. Bu snippet orijinal öğreticideki gibi değişmeden kalır:

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
- **Ücretsiz deneme** – GroupDocs sitesinden indirin.  
- **Geçici lisans** – daha uzun bir değerlendirme süresi gerekiyorsa talep edin.  
- **Tam lisans** – üretim dağıtımları için satın alın.

### Temel Viewer başlatma
`Viewer` sınıfı, bir belgeyi yükleyen ve render ve dönüşüm metodlarını sunan giriş noktasıdır. Kodu tam olarak gösterildiği gibi tutun:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## PDF sayfasını Java ile nasıl döndürürüz
Hedef dosyayı `Viewer` ile yükleyin, sayfa numarasını belirtin ve `rotatePage` metodunu çağırın. Metod PDF, DOCX, PPTX, XLSX ve kütüphanenin desteklediği diğer formatlar için çalışır. Döndürmeden sonra belgeyi yeni bir PDF olarak render edebilir ya da doğrudan istemciye akıtabilirsiniz; böylece orijinal dosya dokunulmaz kalır.

## Adım‑adım uygulama: ilk sayfayı 90 derece döndürme

### 1. Gerekli paketleri içe aktarın
`PdfViewOptions` Viewer’ın PDF dosyası üretmesini söyler, `Rotation` enum’u ise açıyı tanımlar. Her iki sınıf da `com.groupdocs.viewer.options` paketindedir.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Çıktı konumlarını tanımlayın ve Viewer’ı oluşturun
Yer tutucu yolları gerçek dizinlerinizle değiştirin. `Viewer` yapıcı, kaynak belgeye işaret eden bir `File` nesnesi alır.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF görüntü seçeneklerini yapılandırın ve döndürmeyi uygulayın
`rotatePage(int, Rotation)` metodu **1‑tabanlı** sayfa indeksi ve bir `Rotation` enum değeri alır. Bu örnekte ilk sayfayı saat yönünde döndürmek için `Rotation.ON_90_DEGREE` kullanıyoruz.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Belgeyi render edin
Yapılandırılmış seçeneklerle `view` metodunu çağırmak, döndürülmüş PDF’i çıktı klasörüne yazar.

```java
viewer.view(viewOptions);
```

#### Nasıl çalışır
- **PdfViewOptions** Viewer’ın PDF çıktı dosyası üretmesini sağlar.  
- **rotatePage(int, Rotation)** yalnızca belirtilen sayfayı döndürür, diğer sayfalar değişmez.  
- Metod üç döndürme sabitini destekler: `ON_90_DEGREE`, `ON_180_DEGREE` ve `ON_270_DEGREE`.

## Yaygın sorunlar ve çözümler
| Belirti | Muhtemel neden | Çözüm |
|---------|----------------|------|
| **FileNotFoundException** | Yanlış yol veya eksik klasör | `YOUR_OUTPUT_DIRECTORY` ve `YOUR_DOCUMENT_DIRECTORY` var ve okunabilir olduğundan emin olun. |
| **Unsupported file format** | Viewer’ın desteklemediği bir formatı döndürmeye çalışmak | [GroupDocs Viewer supported formats] sayfasını kontrol edin. |
| **No rotation visible** | Yanlış sayfa numarası (0‑tabanlı) kullanmak | `rotatePage` metodunun **1‑tabanlı** indeksleme kullandığını unutmayın. |
| **Out‑of‑memory errors on large docs** | Tek bir iş parçacığında çok sayıda büyük dosya render edilmesi | Belgeleri sıralı işleyin veya sınırlı eşzamanlılıkla bir iş parçacığı havuzu kullanın. |

## Pratik uygulamalar

1. **Sunum ayarlamaları** – Portre slaytı, görsel etkiyi artırmak için anında manzaraya çevirin.  
2. **Toplu belge düzeltmesi** – Yan yatmış taranmış PDF’leri otomatik olarak düzeltin, saatlerce süren manuel işi ortadan kaldırın.  
3. **Baskıya hazır çıktı** – Manzara grafikleri, portre yönündeki kağıda manuel sürükleme yapmadan doğru şekilde basılsın.

## Performans ipuçları

- **Kaynakları hemen kapatın** – `try‑with‑resources` bloğu `Viewer`’ı otomatik olarak serbest bırakır, belleği boşaltır.  
- **Toplu işleme** – Her iş parçacığı için tek bir `Viewer` örneği yeniden kullanarak başlatma maliyetini azaltın.  
- **Belleği izleyin** – 100 MB’dan büyük belgeler için çıktıyı bellekte tutmak yerine diske akıtın; GroupDocs Viewer 200 MB dosyaları 250 MB’dan az RAM kullanarak işleyebilir.

## Sıkça sorulan sorular

**S: Birden fazla sayfayı aynı anda döndürebilir miyim?**  
C: Evet—döndürmek istediğiniz her sayfa için `rotatePage()` metodunu bir döngü içinde ya da zincirleme çağırabilirsiniz.

**S: Render sonrası döndürmeyi geri almanın bir yolu var mı?**  
C: Doğrudan yok. Döndürme seçenekleri olmadan belgeyi yeniden render etmeniz gerekir.

**S: GroupDocs Viewer’da hangi dosya formatları sayfa döndürmeyi destekliyor?**  
C: DOCX, PDF, PPTX, XLSX ve resmi dokümantasyonda listelenen birçok diğer format.

**S: Belgeler topluluğunda sayfaları otomatik olarak nasıl döndürürüm?**  
C: Dosya yolu koleksiyonunu dolaşan bir döngüye döndürme mantığını yerleştirerek aynı `rotatePage` yapılandırmasını her dosyaya uygulayın.

**S: Döndürme sırasında hataları yönetmenin en iyi yolu nedir?**  
C: Viewer kullanımını bir `try‑catch` bloğuna alın, istisna detaylarını kaydedin ve isteğe bağlı olarak sonraki dosyaya geçerek tek bir hatanın tüm toplu işlemi durdurmasını önleyin.

## Kaynaklar

- **Dokümantasyon**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API referansı**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **İndirme**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Satın alma**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Ücretsiz deneme**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Geçici lisans**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Destek**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-09-30  
**Test Edilen Versiyon:** GroupDocs Viewer 25.2 for Java  
**Yazar:** GroupDocs

## İlgili Öğreticiler

- [How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Load Document from URL in Java – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)
- [Groupdocs Viewer Java Document Views](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}