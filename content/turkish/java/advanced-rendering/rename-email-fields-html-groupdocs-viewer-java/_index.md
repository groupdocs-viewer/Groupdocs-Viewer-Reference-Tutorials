---
date: '2026-03-24'
description: GroupDocs Viewer for Java kullanarak e-postayı HTML'ye dönüştürmeyi ve
  e-posta alanlarını yeniden adlandırmayı öğrenin. Bu kılavuz, e-postayı özel başlıklarla
  HTML olarak render etmeyi gösterir.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: E-postayı HTML'ye Dönüştür ve Alanları Yeniden Adlandır – GroupDocs Viewer
  Java
type: docs
url: /tr/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# E-postayı HTML'ye Dönüştürme ve Alanları Yeniden Adlandırma – GroupDocs Viewer Java

Eğer **e-postayı HTML'ye dönüştürmek** ve e-posta başlıklarına özel bir görünüm vermek istiyorsanız doğru yerdesiniz. Bu öğreticide, e-posta alanlarını yeniden adlandırma, **e-postayı HTML'ye dönüştürme** ve GroupDocs.Viewer for Java kullanarak e-posta başlıklarını özelleştirme adımlarını ayrıntılı olarak göstereceğiz. Sonunda, tercih ettiğiniz başlık adlarıyla temiz bir HTML temsiline sahip olacak, çıktıyı uygulamalarınıza daha kolay entegre edebileceksiniz.

![E-posta Alanlarını Yeniden Adlandırma ve HTML'ye Dönüştürme – GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Neler Öğreneceksiniz
- GroupDocs.Viewer for Java kullanarak **e-postayı HTML'ye dönüştürme**.  
- “From”, “To”, “Sent” ve “Subject” gibi **e-posta alanlarını yeniden adlandırma** teknikleri.  
- Maven ve lisanslama ayarları için en iyi uygulamalar.  
- **E-posta başlıklarını özelleştirmenin** değer kattığı gerçek dünya senaryoları.

## Hızlı Yanıtlar
- **“E-postayı HTML'ye dönüştürmek” ne anlama geliyor?** Bir e-posta dosyasını (MSG/EML) web‑hazır bir HTML belgesi olarak render etmek demektir.  
- **Dönüşümü hangi kütüphane yapıyor?** GroupDocs.Viewer for Java (v25.2+).  
- **Lisans gerekli mi?** Değerlendirme için bir deneme sürümü yeterlidir; üretim ortamı için tam lisans gerekir.  
- **Herhangi bir başlık adını değiştirebilir miyim?** Evet, standart bir e-posta başlığı `fieldTextMap` aracılığıyla yeniden eşlenebilir.  
- **Çıktı HTML mi yoksa gömülü kaynaklar mı?** Tek bir kendine yeten dosya için gömülü kaynakları seçebilirsiniz.

## GroupDocs.Viewer Bağlamında “e-postayı HTML'ye dönüştürmek” ne demektir?
E-postayı HTML'ye dönüştürmek, ham bir e-posta dosyasını alıp mesaj gövdesi ve meta verilerini gösteren bir HTML sayfası üretmek anlamına gelir. **E-posta alanlarını yeniden adlandırdığınızda** varsayılan etiketler (ör. “From”) özel metinle (ör. “Gönderen”) değiştirilir; bu, kurumsal terminolojiye uyum sağlamanıza veya UI tutarlılığını artırmanıza yardımcı olur.

## Neden E-postayı HTML'ye Dönüştürüp Alanları Yeniden Adlandırmalısınız?
- **Tutarlı marka kimliği:** Çıktıyı kuruluşunuzun diline göre uyarlayın.  
- **Arama kolaylığı:** Özelleştirilmiş başlıklar arşiv sistemlerinde daha etkili indekslenebilir.  
- **Daha iyi UI entegrasyonu:** HTML parçacığını web portalları veya destek panellerine sorunsuz yerleştirin.

## Ön Koşullar

### Gerekli Kütüphaneler, Sürümler ve Bağımlılıklar
- **GroupDocs.Viewer for Java** – sürüm 25.2 veya üzeri.  
- **Java Development Kit (JDK)** – sürüm 8+.

### Ortam Kurulum Gereksinimleri
- Bağımlılık yönetimi için **Maven**.  
- IntelliJ IDEA, Eclipse veya VS Code gibi bir IDE.

### Bilgi Ön Koşulları
Temel Java ve Maven bilgisi, içeriği hızlı takip etmenizi sağlar.

## GroupDocs.Viewer for Java Kurulumu

### Maven Yapılandırması
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

### Lisans Edinme Adımları
- **Ücretsiz Deneme:** [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) adresinden ücretsiz deneme sürümünü indirin.  
- **Geçici Lisans:** Sınırlama olmadan tam özellikleri keşfetmek için [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) adresinden geçici lisans alın.  
- **Satın Alım:** Sürekli kullanım için [GroupDocs Purchase](https://purchase.groupdocs.com/buy) üzerinden lisans satın almayı düşünün.

### Temel Başlatma ve Kurulum
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
`.msg` dosyanıza işaret edecek şekilde dosya yolunu ayarlayın.

## E-postayı HTML'ye Dönüştürme ve Alanları Yeniden Adlandırma – Adım‑Adım

### 1. Çıktı Dizini Yolunu Ayarlayın
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*`"YOUR_OUTPUT_DIRECTORY"` ifadesini HTML dosyalarının kaydedileceği klasörle değiştirin.*

### 2. Sayfa Dosya Yolu Formatını Tanımlayın
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*Render sırasında `{0}` sayfa numarasıyla değiştirilecektir.*

### 3. E-posta Alanlarını Yeni İsimlerle Eşleyecek Haritayı Oluşturun
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Burada varsayılan etiketleri özel olanlarla değiştiriyoruz.*

### 4. HTML Görünüm Seçeneklerini Yapılandırın
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` CSS/JS dosyalarını HTML içinde paketler, `setFieldTextMap` ise özel başlık adlarını uygular.*

### 5. E-postayı HTML'ye Render Edin
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*`"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` ifadesini gerçek MSG dosyanızın yolu ile değiştirin.*

#### Sorun Giderme İpuçları
- Çıktı dizininin yazılabilir olduğundan emin olun.  
- Giriş MSG dosyasının varlığını ve yolunun doğru olduğunu kontrol edin.  
- Maven'da belirtilen GroupDocs.Viewer sürümünün (25.2) aynı olduğundan emin olun.

## Pratik Uygulamalar
1. **Özel E-posta Raporları:** E-posta başlıklarını kurumsal terminolojiyle eşleştirerek daha net raporlar oluşturun.  
2. **E-posta Arşivleme Sistemleri:** Standartlaştırılmış başlık adlarıyla arama yeteneğini artırın.  
3. **Müşteri Destek Platformları:** Biletlerde kişiselleştirilmiş başlık etiketleri göstererek ajan deneyimini iyileştirin.

## Performans Düşünceleri
- `Viewer` nesnelerini `try‑with‑resources` ile serbest bırakarak belleği hızlıca temizleyin.  
- Büyük toplulukları profilleyin ve gerekirse e-postaları paralel akışlarla işleyin.

## Sonuç
Artık **e-postayı HTML'ye dönüştürürken** **e-posta alanlarını yeniden adlandırma** ve **e-posta başlıklarını özelleştirme** konusunda GroupDocs.Viewer for Java ile tam kontrole sahipsiniz. Bu teknik, e-posta meta verilerinin HTML çıktılarında nasıl sunulacağını tamamen yönetmenizi sağlar.

### Sonraki Adımlar
- Ek alan eşlemeleri deneyin (ör. CC, BCC).  
- PDF veya PNG gibi diğer render formatlarını keşfedin.  
- Daha derin API bilgileri için [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) sayfasını ziyaret edin.

## Sık Sorulan Sorular

**S: Bu yöntem EML gibi diğer e-posta formatlarıyla da çalışır mı?**  
C: Evet, GroupDocs.Viewer hem MSG hem de EML dosyalarını destekler; aynı alan‑eşleme mantığı geçerlidir.

**S: HTML'yi gömülü kaynaklar olmadan çıktı alabilir miyim?**  
C: Ayrı CSS/JS dosyalarını tercih ediyorsanız `HtmlViewOptions.forExternalResources(...)` kullanabilirsiniz.

**S: Hangi GroupDocs.Viewer sürümü test edildi?**  
C: Kod, GroupDocs.Viewer **25.2** sürümüyle test edilmiştir.

**S: Özel başlıkların fontunu veya stilini değiştirmek mümkün mü?**  
C: Render sonrası CSS ile stil ekleyebilir veya `HtmlViewOptions.getResourcesPath()` aracılığıyla özel CSS enjekte edebilirsiniz.

**S: Oluşturulan HTML dosya yolunu programatik olarak nasıl alırım?**  
C: Dosya yolu, `pageFilePathFormat` içinde tanımlanan modele göre `String.format` ile sayfa numarası eklenerek oluşturulur.

## Kaynaklar
- **Dokümantasyon:** Kapsamlı kılavuzlar için [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) adresini ziyaret edin.  
- **API Referansı:** Ayrıntılı API bilgileri [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/) sayfasında bulunabilir.  
- **GroupDocs.Viewer İndirme:** En yeni sürüme [Downloads Page](https://releases.groupdocs.com/viewer/java/) üzerinden ulaşabilirsiniz.

---

**Son Güncelleme:** 2026-03-24  
**Test Edilen Sürüm:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs