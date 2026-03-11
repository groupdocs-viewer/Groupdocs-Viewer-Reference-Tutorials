---
date: '2026-01-10'
description: GroupDocs.Viewer kullanarak Java'da özel tarih‑saat formatı ile EML'yi
  HTML'ye dönüştürmeyi ve zaman dilimi offset'ini ayarlamayı öğrenin. E-posta arşivleme
  ve destek sistemleri için idealdir.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Java'da GroupDocs.Viewer Kullanarak Özel Tarih/Saat ile EML'yi HTML'ye Dönüştür
type: docs
url: /tr/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Java'da GroupDocs.Viewer Kullanarak Özel TarihSaat ile EML'yi HTML'ye Dönüştürme

## Giriş

Günümüzün hızlı dijital dünyasında, **EML'yi HTML'ye dönüştürmek** ve doğru tarih‑saat sunumunu sağlamak, arşivleme, destek portalları ve yasal uyumluluk için hayati öneme sahiptir. Bu öğretici, GroupDocs.Viewer for Java kullanarak e‑posta mesajlarını HTML'ye render ederken **özel bir tarih‑saat formatı** ve **zaman dilimi kayması** uygulamanızı adım adım gösterir. Sonunda, zaman damgalarını doğru ve okunabilir tutan yeniden kullanılabilir bir çözüm elde edeceksiniz.

![GroupDocs.Viewer for Java ile Özel TarihSaat Kullanarak E-postaları Görüntüleme](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Öğrenecekleriniz**
- Java projesinde GroupDocs.Viewer'ı nasıl kuracağınız  
- E‑postaları gömülü kaynaklarla HTML'ye nasıl render edeceğiniz  
- E‑posta mesajlarınızın **tarih‑saat formatını** nasıl özelleştireceğiniz (custom datetime format java)  
- Doğru zaman damgaları için **zaman dilimi kaymasını** nasıl ayarlayacağınız (set timezone offset java)  

## Hızlı Yanıtlar
- **GroupDocs.Viewer EML'yi HTML'ye dönüştürebilir mi?** Evet, EML dosyalarını doğrudan HTML'ye render eder.  
- **Lisans gerekir mi?** Ücretsiz deneme sürümü test için yeterlidir; üretim için ücretli lisans gereklidir.  
- **Hangi Java sürümü gerekiyor?** Java 8 veya daha yenisi.  
- **Görüntülenen tarih formatını nasıl değiştiririm?** `options.getEmailOptions().setDateTimeFormat(...)` kullanın.  
- **Zaman dilimini ayarlayabilir miyim?** Evet, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))` ile.  

## “EML'yi HTML'ye dönüştürmek” nedir?
EML dosyasını HTML'ye dönüştürmek, ham e‑postayı (başlıklar, gövde ve ekler dahil) tarayıcıların ek eklentilere ihtiyaç duymadan görüntüleyebileceği web‑dostu bir formata çevirir. Bu sayede e‑postaları web uygulamalarına, arşivlere veya destek panellerine kolayca yerleştirebilirsiniz.

## Bu Görev İçin Neden GroupDocs.Viewer Kullanılmalı?
- **Sıfır bağımlılık render** – Outlook veya harici mail ayrıştırıcılarına gerek yok.  
- **Gömülü kaynaklar için yerleşik destek** (görseller, ekler).  
- **Tarih‑saat formatı ve zaman dilimi yönetimi üzerinde ince ayar** imkanı.  

## Önkoşullar

- **GroupDocs.Viewer for Java** sürüm 25.2 veya üzeri.  
- **Java Development Kit (JDK)** 8+ ve bir IDE (IntelliJ IDEA, Eclipse vb.).  
- Temel Java bilgisi ve Maven deneyimi.  

## Java için GroupDocs.Viewer Kurulumu

### Maven Yapılandırması
`pom.xml` dosyanıza GroupDocs deposunu ve bağımlılığı ekleyin:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### Lisans Edinme
Ücretsiz deneme ile başlayın veya genişletilmiş test için geçici bir lisans isteyin. Üretim kullanımı için tam lisans satın alın.

### Temel Başlatma
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Java'da Özel TarihSaat ile EML'yi HTML'ye Dönüştürme

Aşağıdaki adım‑adım kılavuz, **EML'yi HTML'ye dönüştürürken** özel bir tarih‑saat formatı ve zaman dilimi kayması uygulamanızı gösterir.

### Adım 1: Çıktı Dizini ve Dosya Yolunu Ayarlama
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Açıklama:* `Path.of()` HTML'nin kaydedileceği klasöre referans oluşturur. `resolve()` dosya adını ekler.

### Adım 2: E‑posta Dosyasıyla Viewer'ı Başlatma
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Açıklama:* `Viewer` örneği dönüştürmek istediğiniz EML dosyasına işaret eder.

### Adım 3: HtmlViewOptions'ı Yapılandırma
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Açıklama:* `forEmbeddedResources()` görselleri ve diğer kaynakları doğrudan HTML çıktısına gömer.

### Adım 4: Özel TarihSaat Formatını Ayarlama *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Açıklama:* Bu desen ay, gün, yıl, saat, dakika, AM/PM işareti ve zaman dilimi kaymasını (`zzz`) gösterir.

### Adım 5: Zaman Dilimi Kaymasını Ayarlama *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Açıklama:* Render edilen zaman damgalarını istenen saat dilimine ayarlar. `"GMT+1"` ifadesini geçerli bir bölge tanımlayıcısı ile değiştirin.

### Adım 6: Belgeyi Render Etme
```java
viewer.view(options);
```
*Açıklama:* Dönüştürmeyi yürütür ve özel tarih‑saat ayarlarınızla bir HTML dosyası üretir.

## Sorun Giderme İpuçları
- **FileNotFoundException:** `Viewer` ve `Path.of()` içinde kullanılan yolları iki kez kontrol edin.  
- **Yanlış zaman damgaları:** `TimeZone` kimliğinin hedef bölgenizle eşleştiğinden emin olun.  
- **Görseller eksik:** `HtmlViewOptions.forEmbeddedResources()` kullandığınızdan emin olun; aksi takdirde dış kaynaklar dahil edilmeyebilir.  

## Pratik Uygulamalar
1. **E‑posta Arşivleme:** Uyumluluk için aranabilir HTML anlık görüntülerini saklayın.  
2. **Müşteri Destek Portalları:** Gelen biletleri doğru yerel saatlerle gösterin.  
3. **Yasal Dokümantasyon:** Standartlaştırılmış zaman damgalarıyla mahkeme‑hazır e‑posta kayıtları üretin.  

## Performans Düşünceleri
- Toplu dönüşümler için ayrı bir sunucuya dağıtın.  
- Java yığın kullanımını izleyin; `OutOfMemoryError` alırsanız `-Xmx` değerini artırın.  
- Aynı e‑posta tekrar tekrar isteniyorsa render edilmiş HTML'yi önbelleğe alın.  

## Sonuç
Artık GroupDocs.Viewer for Java kullanarak **özel bir tarih‑saat formatı ve zaman dilimi kayması** ile **EML'yi HTML'ye dönüştürmek** için tam üretim‑hazır bir yönteme sahipsiniz. Bu, okunabilirliği artırır, zaman damgalarının doğruluğunu sağlar ve arşivleme ya da destek iş akışlarına sorunsuz bir şekilde entegre olur.

**Sonraki Adımlar:** CSS stillendirme, sayfalama veya PDF dönüşümü gibi ek Viewer seçeneklerini keşfederek çıktıyı ihtiyaçlarınıza göre daha da özelleştirin.

## Sık Sorulan Sorular

**S: EML dosyaları eklerle birlikte nasıl işlenir?**  
C: `HtmlViewOptions.forEmbeddedResources()` kullandığınızda ekler otomatik olarak gömülür. İsterseniz Viewer API'si aracılığıyla da çıkarabilirsiniz.

**S: HTML şablonunu değiştirebilir veya özel CSS ekleyebilir miyim?**  
C: Evet, render işleminden sonra oluşturulan HTML dosyasını düzenleyebilir veya kaydetmeden önce programatik olarak CSS enjekte edebilirsiniz.

**S: Birden fazla EML dosyasını toplu olarak render etmek mümkün mü?**  
C: Render mantığını bir döngü içinde sarın ve her dosya için aynı `HtmlViewOptions` örneğini yeniden kullanın.

**S: MSG gibi diğer e‑posta formatlarını da desteklemek istersem?**  
C: GroupDocs.Viewer ayrıca MSG, PST ve diğer e‑posta konteynerlerini destekler—sadece `Viewer` yapıcısındaki dosya uzantısını değiştirmeniz yeterlidir.

**S: Her sunucu için ayrı bir lisans almam gerekiyor mu?**  
C: Lisans dağıtım başına yapılır; çok‑sunucu senaryoları için GroupDocs lisans rehberine bakın.

## Kaynaklar

- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)  
- [API Referansı](https://reference.groupdocs.com/viewer/java/)  
- [İndirme](https://releases.groupdocs.com/viewer/java/)  
- [Satın Al](https://purchase.groupdocs.com/buy)  
- [Ücretsiz Deneme](https://releases.groupdocs.com/viewer/java/)  
- [Geçici Lisans](https://purchase.groupdocs.com/temporary-license/)  
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)  

---

**Son Güncelleme:** 2026-01-10  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 (Java)  
**Yazar:** GroupDocs