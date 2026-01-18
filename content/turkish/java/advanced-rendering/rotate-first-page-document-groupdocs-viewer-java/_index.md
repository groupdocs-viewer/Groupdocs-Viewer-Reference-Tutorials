---
date: '2026-01-18'
description: GroupDocs Viewer kullanarak Java’da sayfayı 90 derece döndürmeyi, kurulum,
  kod ve performans ipuçlarını içerecek şekilde öğrenin.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: GroupDocs Viewer for Java ile sayfayı 90 derece döndür
type: docs
url: /tr/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Sayfayı 90 derece döndürme - GroupDocs Viewer for Java ile

Bir belge içinde **sayfayı 90 derece döndürmeniz** gerektiğinde—PDF, Word dosyası ya da elektronik tablo olsun—programatik olarak yapmak zaman kazandırır ve manuel hataları ortadan kaldırır. Bu ileri düzey rehberde, **GroupDocs Viewer for Java** kullanarak herhangi bir desteklenen belgenin ilk sayfasını nasıl döndüreceğinizi adım adım göstereceğiz. Sonunda, kendi projelerinizde kullanabileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

![GroupDocs.Viewer for Java ile Bir Belgenin İlk Sayfasını Döndürme](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Hızlı Yanıtlar
- **“Sayfayı 90 derece döndürmek” ne anlama gelir?** Seçilen sayfayı saat yönünde çeyrek tur döndürür.  
- **Hangi kütüphane döndürmeyi gerçekleştirir?** GroupDocs Viewer for Java `rotatePage` metodunu sağlar.  
- **Java ile PDF sayfalarını döndürebilir miyim?** Evet—aynı `rotatePage` çağrısını kullanın; PDF, DOCX, XLSX ve daha fazlası için çalışır.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme çalışır; üretim için ücretli lisans gereklidir.  
- **İşlem bellek yoğun mu?** `Viewer` örneğini hızlıca kapattığınız sürece değil; aşağıdaki performans ipuçlarına bakın.

## “Sayfayı 90 derece döndürmek” nedir?
Sayfayı 90 derece döndürmek, sayfayı portre yönünden manzara yönüne (veya tersine) yeniden yönlendirir ve alttaki içeriği değiştirmez. Bu, sunumlar, yalnızca manzara grafiklerinin basılması veya yan yatmış taranmış belgelerin düzeltilmesi için özellikle kullanışlıdır.

## Neden GroupDocs Viewer for Java ile sayfaları döndürmelisiniz?
GroupDocs Viewer, onlarca dosya formatını yönetmenin karmaşıklığını soyutlar. Sayfa‑düzeyinde dönüşüm gibi işlemleri (ör. döndürme) uygulamanıza izin verirken orijinal dosyayı korur. API akıcı, çok iş parçacıklı güvenli ve herhangi bir Java 8+ çalışma ortamında çalışır.

## Önkoşullar

- **GroupDocs.Viewer for Java** (en son sürüm)
- **JDK 8** veya daha yenisi
- Bağımlılık yönetimi için **Maven** (veya Gradle)
- IntelliJ IDEA veya Eclipse gibi bir IDE
- Java I/O konusunda temel bilgi

## GroupDocs.Viewer for Java Kurulumu

`pom.xml` dosyanıza GroupDocs deposunu ve bağımlılığı ekleyin. Bu kod parçacığı orijinal öğreticiden değiştirilmemiştir:

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
Aşağıdaki kod, bir `Viewer` örneği oluşturmanın en minimal yolunu gösterir. Tam olarak gösterildiği gibi bırakın:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Adım Adım Uygulama: İlk Sayfayı 90 Derece Döndürme

### 1. Gerekli paketleri içe aktarın
Bu içe aktarmalar PDF render seçeneklerine ve döndürme enum’una erişmenizi sağlar.

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

### 3. PDF görüntüleme seçeneklerini yapılandırın ve döndürmeyi uygulayın
`rotatePage` metodu sayfa numarasını (1‑tabanlı) ve bir `Rotation` enum değerini alır.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Belgeyi render edin
Son olarak, döndürülmüş PDF’i oluşturmak için `view` metodunu çağırın.

```java
viewer.view(viewOptions);
```

#### Nasıl çalışır
- **PdfViewOptions**, Viewer'ın PDF dosyası üretmesini söyler.  
- **rotatePage(int, Rotation)** sadece belirttiğiniz sayfayı döndürür, diğerlerini dokunulmaz bırakır.  
- Metod `ON_90_DEGREE`, `ON_180_DEGREE` ve `ON_270_DEGREE` değerlerini destekler.

## Yaygın Sorunlar ve Çözümler
| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| **FileNotFoundException** | Yanlış yol veya eksik klasör | `YOUR_OUTPUT_DIRECTORY` ve `YOUR_DOCUMENT_DIRECTORY`'nin mevcut ve okunabilir olduğunu doğrulayın. |
| **Unsupported file format** | Viewer tarafından desteklenmeyen bir formatı döndürmeye çalışmak | [GroupDocs Viewer supported formats] sayfasını kontrol edin. |
| **No rotation visible** | Yanlış sayfa numarasını (0‑tabanlı) kullanmak | `rotatePage` metodunun **1‑tabanlı** indeksleme kullandığını unutmayın. |
| **Out‑of‑memory errors on large docs** | Birçok büyük dosyayı tek bir iş parçacığında render etmek | Belgeleri sıralı işleyin veya sınırlı eşzamanlılıkla bir iş parçacığı havuzu kullanın. |

## Pratik Uygulamalar

1. **Sunum ayarlamaları** – Portre slaytı anında manzaraya dönüştürün.  
2. **Toplu belge düzeltmesi** – Yana kaydırılmış taranmış PDF'leri otomatik olarak düzeltin.  
3. **Baskıya hazır çıktı** – Manzara grafiklerinin portre yönündeki kağıda doğru basıldığından emin olun.

## Performans İpuçları

- **Kaynakları hızlıca kapatın** – `try‑with‑resources` bloğu `Viewer`'ı otomatik olarak serbest bırakır.  
- **Toplu işleme** – Birçok dosya işlenirken, iş parçacığı başına tek bir `Viewer` örneği yeniden kullanarak yükü azaltın.  
- **Belleği izleyin** – 100 MB'den büyük belgeler için çıktıyı bellekte tutmak yerine diske akış olarak yazmayı düşünün.

## Sıkça Sorulan Sorular

**S: Birden fazla sayfayı aynı anda döndürebilir miyim?**  
Evet—döndürmek istediğiniz her sayfa numarası için `rotatePage()` metodunu çağırın.

**S: Render işleminden sonra döndürmeyi geri almanın bir yolu var mı?**  
Doğrudan değil. Rotasyon seçenekleri olmadan belgeyi tekrar render etmeniz gerekir.

**S: GroupDocs Viewer'da hangi dosya formatları sayfa döndürmeyi destekler?**  
DOCX, PDF, PPTX, XLSX ve resmi belgelerde listelenen birçok diğer format.

**S: Belgeler topluluğunda sayfaları otomatik olarak nasıl döndürebilirim?**  
Kodunuzu, dosya yolu koleksiyonunu dönen bir döngüye sarın ve her birine aynı `rotatePage` mantığını uygulayın.

**S: Döndürme sırasında hataları ele almak için en iyi uygulama nedir?**  
Viewer kullanımını bir `try‑catch` bloğuna alın, istisnayı kaydedin ve isteğe bağlı olarak bir sonraki dosyayı işlemeye devam edin.

## Kaynaklar

- **Dokümantasyon**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Referansı**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **İndirme**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Satın Alma**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Ücretsiz Deneme**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Geçici Lisans**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Destek**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-01-18  
**Test Edilen Sürüm:** GroupDocs Viewer 25.2 for Java  
**Yazar:** GroupDocs