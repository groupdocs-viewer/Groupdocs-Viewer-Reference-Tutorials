---
date: '2026-03-24'
description: GroupDocs.Viewer kullanarak Java’da özel tarih‑saat formatı ile EML’yi
  HTML’ye dönüştürmeyi ve saat dilimi ofsetini ayarlamayı öğrenin. E‑posta arşivleme
  ve destek sistemleri için idealdir.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Java'da GroupDocs.Viewer Kullanarak Özel Tarih/Saat ile EML'yi HTML'ye Dönüştürme
type: docs
url: /tr/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# EML'yi Java'da GroupDocs.Viewer Kullanarak Özel TarihSaat ile HTML'ye Dönüştür

Günümüzün hızlı tempolu dijital dünyasında, **EML'yi HTML'ye dönüştürmek** hızlı ve doğru tarih‑saat sunumu ile arşivleme, destek portalları ve yasal uyumluluk için hayati öneme sahiptir. Bu öğretici, GroupDocs.Viewer for Java kullanarak **custom datetime format** ve **timezone offset** uygularken e‑posta mesajlarını HTML'ye render etmenizi adım adım gösterir. Sonunda, zaman damgalarını doğru ve okunabilir tutan, herhangi bir **email to HTML Java** iş akışı için mükemmel, yeniden kullanılabilir bir çözüm elde edeceksiniz.

![GroupDocs.Viewer for Java ile Özel TarihSaat Kullanarak E-postaları Render Et](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Neler Öğreneceksiniz**
- Java projesinde GroupDocs.Viewer'ı nasıl kuracağınız  
- E‑postaları gömülü kaynaklarla HTML'ye nasıl render edeceğiniz  
- E‑posta mesajlarınızın **custom datetime format**ını nasıl özelleştireceğiniz (custom datetime java)  
- Doğru zaman damgaları için **timezone offset**i nasıl ayarlayacağınız (timezone offset java)  

## Hızlı Yanıtlar
- **GroupDocs.Viewer EML'yi HTML'ye dönüştürebilir mi?** Evet, EML dosyalarını doğrudan HTML'ye render eder.  
- **Lisans gerekli mi?** Ücretsiz deneme testi için yeterlidir; üretim ortamı için ücretli lisans gerekir.  
- **Hangi Java sürümü gerekiyor?** Java 8 veya daha yenisi.  
- **Görüntülenen tarih formatını nasıl değiştiririm?** `options.getEmailOptions().setDateTimeFormat(...)` kullanın.  
- **Saat dilimini ayarlayabilir miyim?** Evet, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))` ile ayarlayabilirsiniz.

## “EML'yi HTML'ye dönüştürmek” ne demektir?
Bir EML dosyasını HTML'ye dönüştürmek, ham e‑postayı (başlıklar, gövde ve ekler dahil) tarayıcıların ek bir eklenti olmadan görüntüleyebileceği web‑dostu bir formata çevirir. Bu sayede e‑postalar web uygulamalarına, arşivlere veya destek panellerine kolayca gömülebilir.

## Bu Görev İçin GroupDocs.Viewer Neden Kullanılmalı?
- **Sıfır bağımlılık render** – Outlook veya dış mail ayrıştırıcılarına gerek yok.  
- **Gömülü kaynaklar için yerleşik destek** (görseller, ekler).  
- **Tarih‑saat formatlaması ve saat dilimi yönetimi üzerinde ince ayar** imkanı.  

## Ön Koşullar

- **GroupDocs.Viewer for Java** sürüm 25.2 veya üzeri.  
- **Java Development Kit (JDK)** 8+ ve bir IDE (IntelliJ IDEA, Eclipse vb.).  
- Temel Java bilgisi ve Maven deneyimi.

## GroupDocs.Viewer for Java Kurulumu

### Maven Yapılandırması
`pom.xml` dosyanıza GroupDocs deposunu ve bağımlılığını ekleyin:

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

Aşağıdaki adım‑adım kılavuz, **EML'yi HTML'ye dönüştürürken** özel bir datetime formatı ve saat dilimi offseti uygulamanızı gösterir.

### Adım 1: Çıktı Dizini ve Dosya Yolunu Ayarlama
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Açıklama:* `Path.of()` HTML'nin kaydedileceği klasöre bir referans oluşturur. `resolve()` dosya adını ekler.

### Adım 2: Viewer'ı E‑posta Dosyasıyla Başlatma
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

### Adım 4: Özel DateTime Formatını Ayarlama *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Açıklama:* Bu desen ay, gün, yıl, saat, dakika, AM/PM işareti ve saat dilimi offsetini (`zzz`) gösterir.

### Adım 5: Saat Dilimi Offsetini Ayarlama *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Açıklama:* Render edilen zaman damgalarını istediğiniz saat dilimine ayarlar. `"GMT+1"` ifadesini geçerli bir bölge tanımlayıcısı ile değiştirin.

### Java'da E‑posta Saat Dilimini Nasıl Ayarlarsınız
Basit offsetlerin ötesinde **e‑posta saat dilimini ayarlamanız** gerektiğinde—örneğin yaz‑kış saat değişikliklerini yönetmek—`java.util.TimeZone` API'sinden `"Europe/Paris"` veya `"America/New_York"` gibi bölge kimliklerini kullanarak uygun `TimeZone` nesnesini alabilir ve `setTimeZoneOffset` metoduna geçirebilirsiniz. Bu sayede e‑posta zaman damgaları her zaman doğru yerel zamanı yansıtır.

### Adım 6: Belgeyi Render Etme
```java
viewer.view(options);
```
*Açıklama:* Dönüştürmeyi yürütür ve özel tarih‑saat ayarlarınızla bir HTML dosyası üretir.

## Sorun Giderme İpuçları
- **FileNotFoundException:** `Viewer` ve `Path.of()` içinde kullanılan yolları kontrol edin.  
- **Yanlış zaman damgaları:** `TimeZone` kimliğinin hedef bölgenizle eşleştiğinden emin olun.  
- **Görseller eksik:** `HtmlViewOptions.forEmbeddedResources()` kullandığınızdan emin olun; aksi takdirde dış kaynaklar dahil edilmeyebilir.  

## Pratik Uygulamalar
1. **E‑posta Arşivleme:** Uyumluluk için aranabilir HTML anlık görüntülerini saklayın.  
2. **Müşteri Destek Portalları:** Gelen biletleri doğru yerel saatlerle gösterin.  
3. **Hukuki Belgeler:** Standart zaman damgalarıyla mahkeme‑hazır e‑posta kayıtları üretin.  

## Performans Düşünceleri
- Toplu dönüşümler için ayrı bir sunucu üzerinde dağıtın.  
- Java yığın kullanımını izleyin; `OutOfMemoryError` alırsanız `-Xmx` değerini artırın.  
- Aynı e‑posta tekrar tekrar isteniyorsa render edilmiş HTML'yi önbelleğe alın.  

## Sonuç
GroupDocs.Viewer for Java kullanarak **EML'yi HTML'ye dönüştürmek**, özel datetime formatı ve saat dilimi offsetiyle üretim‑hazır bir yöntem elde ettiniz. Bu, okunabilirliği artırır, zaman damgalarının doğruluğunu sağlar ve arşivleme ya da destek iş akışlarına sorunsuz bir şekilde entegre olur.

**Sonraki Adımlar:** CSS stil verme, sayfalama veya PDF dönüşümü gibi ek Viewer seçeneklerini keşfederek çıktıyı ihtiyaçlarınıza göre daha da özelleştirin.

## Sık Sorulan Sorular

**S: EML dosyaları eklerle nasıl işlenir?**  
C: `HtmlViewOptions.forEmbeddedResources()` kullandığınızda ekler otomatik olarak gömülür. İsterseniz Viewer API'siyle ekleri ayrıca çıkarabilirsiniz.

**S: HTML şablonunu değiştirebilir veya özel CSS ekleyebilir miyim?**  
C: Evet, render sonrası oluşturulan HTML dosyasını düzenleyebilir veya kaydetmeden önce programatik olarak CSS enjekte edebilirsiniz.

**S: Birden fazla EML dosyasını toplu olarak render edebilir miyim?**  
C: Render mantığını bir döngü içinde sarın ve her dosya için aynı `HtmlViewOptions` örneğini yeniden kullanın.

**S: MSG gibi diğer e‑posta formatlarını desteklemek istersem ne yapmalıyım?**  
C: GroupDocs.Viewer MSG, PST ve diğer e‑posta konteynerlerini de destekler—sadece `Viewer` yapıcısındaki dosya uzantısını değiştirmeniz yeterlidir.

**S: Her sunucu için ayrı bir lisans gerekir mi?**  
C: Lisans dağıtıma göre verilir; çok‑sunucu senaryoları için GroupDocs lisans rehberine bakın.

## Kaynaklar

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-03-24  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 (Java)  
**Yazar:** GroupDocs