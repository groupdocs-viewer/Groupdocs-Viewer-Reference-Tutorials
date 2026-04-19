---
date: '2026-02-02'
description: Java dosya çıkış akışı ve güçlü GroupDocs.Viewer API'sini kullanarak
  Java uygulamalarında belge eklerini verimli bir şekilde almayı ve kaydetmeyi öğrenin.
keywords:
- GroupDocs.Viewer Java
- retrieve document attachments Java
- save document attachments GroupDocs
title: Java dosya çıkış akışı kullanarak GroupDocs.Viewer for Java ile Belge Eklerini
  Alma ve Kaydetme
type: docs
url: /tr/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# java file output stream kullanarak GroupDocs.Viewer for Java ile Belge Eklerini Alma ve Kaydetme

## Giriş

Java uygulamalarınızda **java file output stream** kullanarak belge eklerini programlı bir şekilde çıkarmak ve yönetmek mi istiyorsunuz? Dijital belge yönetiminin yükselişiyle, bu süreçleri verimli bir şekilde sadeleştiren araçlara sahip olmak çok—belge eklerini sorunsuz bir şekilde alıp kaydetmenizi sağlayan ideal çözümünüz.

![GroupDocs.Viewer for Java ile Belge Eklerini Al ve Kaydet](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

Bu öğreticide, GroupDocs.Viewer’ın gücünden yararlanarak belgelerden ekleri nasıl alıp istediğiniz dizine kaydedebileceğinizi inceleyeceğiz. Adımları izleyerek, Java ortamında belge verilerini etkili bir şekilde yönetme konusunda pratik beceriler kazanacaksınız.

## Hızlı Yanıtlar
- **java file output stream ne işe yarar?** Byte akışlarını doğrudan dosyalara yazar, ekler gibi ikili verilerin diske kaydedilmesini sağlar.  
- **Ekleri hangi API getirir?** `Viewer.getAttachments()` ek meta verilerinin bir listesini döndürür.  
- **Çıktı klasörünü belirtebilir miyim?** Evet—`Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");` ifadesini kullanın.  
- **Lisans gerekir mi?** Değerlendirme için ücretsiz deneme yaklaşım çoklu iş parçac Her iş parçacığı## java Java sınıfıdır. E-posta ekleri, görüntüler veya bir belgeden java file output stream neden kullanılmalı?
- **Doğrudan ikili işleme** – Ara dönüşümlere gerek yok; ek baytları kaynak dosyada göründüğü gibi tam olarak yazar.  
- **Performans** – Ak kullanımını minimuma indirir.asyondır.

## Önkoşullar
- **Gerekli Kütüphaneler ve Bağımlılıklar**: Projenize GroupDocs.Viewer kütüphanesini ekleyin (aşağıdaki Maven snippet’ine bakın).  
- **Ortam Kurulumu**: JDK 8+ yüklü bir Java IDE (IntelliJ IDEA, Eclipse vb.).  
- **Bilgi Gereksinimleri**: `FileOutputStream` başta olmak üzere Java I/O konularına ve temel Maven kullanımına aşina olun.

## GroupDocs.Viewer for Java Kurulumu
Projenizde GroupDocs.Viewer API’sını kullanmaya başlamak için Maven üzerinden kurulum yapmanız gerekir. `pom.xml` dosyanıza aşağıdaki yapılandırmayı ekleyin:

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

**Lisans Edinme Adımları:**
- **Ücretsiz Deneme**: Özellikleri keşfetmek için ücretsiz deneme sürümüyle başlayın.  
- **Geçici Lisans**: Uzatılmış değerlendirme süresi için geçici bir lisans alın.  
- **Satın Alma**: Üretim ortamı için satın alınmış bir lisansa ihtiyacınız olacak.

### Temel Başlatma ve Kurulum
GroupDocs.Viewer projenize bağımlılık olarak eklendikten sonra, Java uygulamanızda başlatın. İşte temel örnek:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Bu temel kurulum, GroupDocs.Viewer’ı başlatır ve ekleri alabilmek için hazır hâle getirir.

## Uygulama Kılavuzu

### java file output stream ile Ekleri Almak
GroupDocs.Viewer kullanarak ekleri nasıl alabileceğinizi adım adım inceleyelim. Bu özellik, belgenizde bulunan her ek hakkında meta veri çıkarmanızı sağlar.

#### Genel Bakış
Ekleri almak, `getAttachments` metoduna erişmeyi içerir; bu metod `Attachment` nesnelerinin bir listesini döndürür ve dosya adı, boyut gibi detayları içerir.

#### Uygulama Adımları
1. **Viewer Örneği Oluşturun**  
   Belgenizin yolunu belirterek `Viewer` sınıfını başlatın:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Ekleri Alın**  
   `getAttachments` metodunu kullanın:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Parametre ve Metodları Anlamak**  
   - `Viewer`: Belgeye dosya yolu ya da akış (stream) ile erişir.  
   - `getAttachments()`: Ek dosyalarının bir listesini getirir; isim gibi detayları sağlar.

### Belge Eklerini Bir Dizin’e Kaydetmek
Ekleri nasıl alacağınızı öğrendikten sonra, GroupDocs.Viewer API’sı ve **java file output stream** kullanarak istediğiniz dizine kaydedelim.

#### Genel Bakış
Bu özellik, alınan her ek dosyasını belirttiğiniz çıktı dizinine kaydetmeyi kapsar.

#### Uygulama Adımları
1. **Çıktı Dizinini Tanımlayın**  
   Dosyaların kaydedileceği `outputDirectory` yolunu ayarlayın:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Ekleri Kaydedin**  
   `saveAttachment` metodunu kullanarak bir döngü içinde her eki kaydedin:

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Parametre ve Metodları Açıklama**  
   - `saveAttachment`: Bir `Attachment` nesnesi ve dosya çıkış akışı alarak eki kaydeder.  
   - `FileOutputStream`: **java file output stream** mantığıyla dosyalara veri yazmayı yönetir.

### Sorun Giderme İpuçları
- **Eksik Bağımlılıklar**: Tüm Maven bağımlılıklarının doğru eklendiğinden emin olun.  
- **Dosya Yolu Hataları**: Belgeler ve çıktı dizinleri için yolları iki kez kontrol edin.  
- **Erişim İzinleri**: Uygulamanızın gerekli okuma/yazma izinlerine sahip olduğundan emin olun.

## Pratik Uygulamalar
GroupDocs.Viewer’ı Java’da kullanmak, çeşitli senaryolarda son derece değerli olabilir:

1. **E‑posta İstemcileri** – E‑posta arşivlerinden ekleri otomatik olarak çıkarıp işleyin veya arşivleyin.  
2. **Belge Yönetim Sistemleri (DMS)** – DMS’yi, ek dosyaları alıp düzenleyerek güçlendirin.  
3. **Hukuk Departmanları** – Hukuki belgelerden kanıt niteliğindeki ekleri güvenli bir şekilde çıkarın.

CRM, ERP veya özel iş akışı motorlarıyla entegrasyon, iş süreçlerini daha da akıcı hâle getirerek ek yönetimini departmanlar arasında sorunsuz bir şekilde sağlayabilir.

## Performans Düşünceleri
GroupDocs.Viewer kullanırken performansı artırmak için:

- **Dosya İşleme Optimizasyonu** – Büyük dosyalar için tamponlu (buffered) akışlar kullanın ve kaynakları zamanında kapatın.  
- **Bellek Yönetimi** – `Viewer` örneklerini hızlı bir şekilde serbest bırakın (try‑with‑resources) ve bellek sızıntılarını önleyin.  

Java en iyi uygulamalarını takip etmek, ek işleme hattınızın verimliliğini önemli ölçüde artıracaktır.

## Sonuç
Artık **java file output stream** ile GroupDocs.Viewer for Java kullanarak belge eklerini nasıl alıp kaydedeceğinizi keşfettiniz. Bu güçlü API, belge verilerini yönetmeyi basitleştirir ve dijital belgelerle çalışan geliştiriciler için vazgeçilmez bir araçtır.

GroupDocs.Viewer’ın diğer özelliklerini—sayfa render’ı, format dönüştürme veya metin çıkarma gibi—deneyerek keşfetmeye devam edin. Sorularınız veya desteğe ihtiyacınız olursa, resmi kaynakime geçmekten çekinmeyin.

## Sıkça Sorulan Java projemde nasıl kurarım?**  
C: Daha önce gösterilen Maven bağımlılığını ekleyin; depo URL’si ve sürüm bilgisi hızlı bir başlang?**  
C: PDF, DOCX, MSG vb. geniş bir formatleri kayd ne yapmalıyım? uygul Ayrıca `FileOutputStream` kullanımının örnekte gösterildiği gibi olduğuna dikkat edin.

**S: Üretim ortamı için lisans gerekli mi?**  
C: Evet, üretim dağıtımları için geçerli bir GroupDocs.Viewer lisansı zorunludur. Değerlendirme**  
C: `java file output stream` ve tamponlu I/O kullanımı, büyük ikili dosyaların ver gerektiSon Güncelleme:** 2026-02-02  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs