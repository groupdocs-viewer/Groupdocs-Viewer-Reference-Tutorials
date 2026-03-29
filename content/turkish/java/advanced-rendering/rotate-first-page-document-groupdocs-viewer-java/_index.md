---
date: '2026-03-29'
description: GroupDocs Viewer kullanarak Java’da sayfayı 90 derece döndürmeyi, kurulum,
  kod ve performans ipuçları dahil olmak üzere öğrenin.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: GroupDocs Viewer for Java ile sayfayı 90 derece döndür
type: docs
url: /tr/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Java ile sayfayı 90 derece döndürme

Bir belgede **sayfayı 90 derece döndürmeniz** gerektiğinde—PDF, Word dosyası ya da elektronik tablo olsun—programlı olarak yapmak zaman kazandırır ve manuel hataları ortadan kaldırır. Bu ileri düzey rehberde, **GroupDocs Viewer for Java** kullanarak desteklenen herhangi bir belgenin ilk sayfasını döndürmek için tam adımları göstereceğiz. Sonunda, kendi projelerinize ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.  
Ayrıca, Java'da sayfaları döndürmenin neden önemli olduğunu, bu tekniğin öne çıktığı yaygın senaryoları ve işlemi hafif tutmanın yollarını da tartışacağız.

![GroupDocs.Viewer for Java ile bir belgenin ilk sayfasını döndürme](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Hızlı Yanıtlar
- **“rotate page 90 degrees” ne anlama geliyor?** Seçilen sayfayı saat yönünde çeyrek dönüş döndürür.  
- **Döndürmeyi hangi kütüphane yönetir?** GroupDocs Viewer for Java `rotatePage` metodunu sağlar.  
- **Java ile PDF sayfalarını döndürebilir miyim?** Evet—aynı `rotatePage` çağrısını kullanın; PDF, DOCX, XLSX ve daha fazlası için çalışır.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ücretli lisans gereklidir.  
- **İşlem bellek yoğun mu?** `Viewer` örneğini hemen kapattığınızda değil; aşağıdaki performans ipuçlarına bakın.

## “rotate page 90 degrees” nedir?
Bir sayfayı 90 derece döndürmek, sayfayı dikeyden yataya (veya tersine) yeniden yönlendirir, alttaki içeriği değiştirmeden. Bu, özellikle sunumlar, yalnızca yatay grafiklerin basımı veya yan yana taranan belgelerin düzeltilmesi için kullanışlıdır.

## GroupDocs Viewer for Java ile sayfaları programlı olarak neden döndürmeliyiz?
GroupDocs Viewer, onlarca dosya formatını yönetmenin karmaşıklığını soyutlar. Sayfa‑düzeyinde dönüşüm—döndürme gibi—uygulamanıza izin verirken orijinal dosyayı bozulmadan tutar. API akıcı, çok iş parçacıklı güvenli ve herhangi bir Java 8+ çalışma zamanında çalışır, bu da onu kurumsal‑düzey otomasyon için güvenilir bir seçim yapar.

## Önkoşullar

- **GroupDocs.Viewer for Java** (en son sürüm)
- **JDK 8** veya daha yeni
- **Maven** (veya Gradle) bağımlılık yönetimi için
- IntelliJ IDEA veya Eclipse gibi bir IDE
- Java I/O konusunda temel bilgi

## GroupDocs.Viewer for Java Kurulumu

`pom.xml` dosyanıza GroupDocs deposunu ve bağımlılığı ekleyin. Bu kod parçacığı orijinal öğreticiden değişmemiştir:

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
- **Free trial** – GroupDocs sitesinden indirin.  
- **Temporary license** – uzatılmış bir değerlendirme süresine ihtiyacınız varsa isteyin.  
- **Full license** – üretim dağıtımları için satın alın.

### Temel Viewer başlatma
Aşağıdaki kod, bir `Viewer` örneği oluşturmanın en minimal yolunu gösterir. Tam olarak gösterildiği gibi tutun:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer ile Java’da PDF sayfası nasıl döndürülür
API birçok formatta çalışsa da, PDF sayfa döndürme için en yaygın kullanım senaryosudur. Aynı `rotatePage` metodu kullanılır, bu yüzden sadece viewer'ı bir PDF dosyasına yönlendirip sayfa numarasını belirtmeniz yeterlidir.

## Adım‑Adım Uygulama: İlk Sayfayı 90 Derece Döndürme

### 1. Gerekli paketleri içe aktarın
Bu importlar, PDF render seçeneklerine ve döndürme enum'ına erişim sağlar.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Çıktı konumlarını tanımlayın ve Viewer'ı oluşturun
Yer tutucu yolları gerçek dizinlerinizle değiştirin.

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
`rotatePage` metodu sayfa numarasını (1‑tabanlı) ve bir `Rotation` enum değerini alır.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Belgeyi render edin
Son olarak, döndürülmüş PDF'i oluşturmak için `view` metodunu çağırın.

```java
viewer.view(viewOptions);
```

#### Nasıl çalışır
- **PdfViewOptions** Viewer'a bir PDF dosyası çıkışı vermesini söyler.  
- **rotatePage(int, Rotation)** sadece belirttiğiniz sayfayı döndürür, geri kalanını dokunulmaz bırakır.  
- Metod `ON_90_DEGREE`, `ON_180_DEGREE` ve `ON_270_DEGREE` değerlerini destekler.

## Yaygın Sorunlar ve Çözümler

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| **FileNotFoundException** | Yanlış yol veya eksik klasör | `YOUR_OUTPUT_DIRECTORY` ve `YOUR_DOCUMENT_DIRECTORY`'nin mevcut ve okunabilir olduğunu doğrulayın. |
| **Unsupported file format** | Viewer tarafından desteklenmeyen bir formatı döndürmeye çalışmak | [GroupDocs Viewer supported formats] sayfasını kontrol edin. |
| **No rotation visible** | Yanlış sayfa numarası (0‑tabanlı) kullanmak | `rotatePage` metodunun **1‑tabanlı** indeksleme kullandığını unutmayın. |
| **Out‑of‑memory errors on large docs** | Tek bir iş parçacığında birçok büyük dosyayı render etmek | Belgeleri sıralı işleyin veya sınırlı eşzamanlılıkla bir iş parçacığı havuzu kullanın. |

## Pratik Uygulamalar

1. **Presentation adjustments** – Anlık olarak dikey bir slaytı yataya dönüştürün.  
2. **Bulk document correction** – Yan yana taranan PDF'lerin otomatik olarak düzeltilmesini sağlayın.  
3. **Print‑ready output** – Yatay grafiklerin dikey yönlendirilmiş kağıda doğru şekilde basılmasını garantileyin.

## Performans İpuçları

- **Close resources promptly** – `try‑with‑resources` bloğu `Viewer`'ı otomatik olarak serbest bırakır.  
- **Batch processing** – Birçok dosya işlenirken, yükü azaltmak için her iş parçacığı başına tek bir `Viewer` örneği yeniden kullanın.  
- **Monitor memory** – 100 MB'den büyük belgeler için çıktıyı bellekte tutmak yerine diske akıtmayı düşünün.

## Sıkça Sorulan Sorular

**Q: Birden fazla sayfayı aynı anda döndürebilir miyim?**  
A: Evet—döndürmek istediğiniz her sayfa numarası için `rotatePage()` çağırın.

**Q: Render sonrası döndürmeyi geri almanın bir yolu var mı?**  
A: Doğrudan değil. Döndürme seçenekleri olmadan belgeyi tekrar render etmeniz gerekir.

**Q: GroupDocs Viewer’da hangi dosya formatları sayfa döndürmeyi destekler?**  
A: DOCX, PDF, PPTX, XLSX ve resmi belgelerde listelenen birçok diğer format.

**Q: Belgeler topluluğunda sayfaları otomatik olarak nasıl döndürebilirim?**  
A: Dosya yolu koleksiyonunu dolaşan bir döngü içinde kodu sarın ve her birine aynı `rotatePage` mantığını uygulayın.

**Q: Döndürme sırasında hataları ele almak için en iyi uygulama nedir?**  
A: Viewer kullanımını bir `try‑catch` bloğuna alın, istisnayı kaydedin ve isteğe bağlı olarak bir sonraki dosyayı işlemeye devam edin.

## Kaynaklar

- **Dokümantasyon**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Referansı**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **İndir**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Satın Al**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Ücretsiz Deneme**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Geçici Lisans İste**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Destek**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen:** GroupDocs Viewer 25.2 for Java  
**Yazar:** GroupDocs