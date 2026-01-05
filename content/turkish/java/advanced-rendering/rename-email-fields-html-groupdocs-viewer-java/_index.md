---
date: '2026-01-05'
description: GroupDocs.Viewer for Java kullanarak e-posta alanlarını yeniden adlandırmayı,
  e-postayı HTML'ye dönüştürmeyi ve e-posta başlıklarını özelleştirmeyi öğrenin.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: GroupDocs.Viewer Java ile E-postaları HTML'ye Render ederken E-posta alanlarını
  nasıl yeniden adlandırılır?
type: docs
url: /tr/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer Java ile E-postaları HTML'ye Render Ederken E-posta Alanlarını Nasıl Yeniden Adlandırılır

Bir e-postayı HTML'ye dönüştürürken **e-posta alanlarını nasıl yeniden adlandıracağınızı** merak ediyor musunuz? Bu rehberde, e-posta alanlarını yeniden adlandırma, **e-postayı HTML'ye dönüştürme** ve GroupDocs.Viewer for Java kullanarak **e-posta başlıklarını özelleştirme** adımlarını ayrıntılı olarak göstereceğiz. Sonunda, tercih ettiğiniz başlık adlarıyla temiz bir HTML temsiline sahip olacaksınız, bu da çıktıyı okumayı ve uygulamalarınıza entegre etmeyi kolaylaştırır.

![E-postaları HTML'ye Dönüştürürken E-posta Alanlarını Yeniden Adlandırma - GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Öğrenecekleriniz
- GroupDocs.Viewer for Java'yı **e-postayı HTML'ye dönüştürmek** için nasıl kullanacağınızı.  
- “From”, “To”, “Sent” ve “Subject” gibi **e-posta alanlarını yeniden adlandırma** teknikleri.  
- Maven ve lisanslamayı kurma konusunda en iyi uygulamalar.  
- **E-posta başlıklarını özelleştirme**'nin değer kattığı gerçek dünya senaryoları.

## Hızlı Yanıtlar
- **“how to rename email” ne anlama geliyor?** Varsayılan e-posta başlığı adlarını render sırasında özel etiketlere eşlemeyi ifade eder.  
- **Dönüşümü hangi kütüphane yönetiyor?** GroupDocs.Viewer for Java (v25.2+).  
- **Lisans gerekli mi?** Değerlendirme için bir deneme sürümü çalışır; üretim için tam lisans gerekir.  
- **Herhangi bir başlık adını değiştirebilir miyim?** Evet, `fieldTextMap` aracılığıyla herhangi bir standart e-posta başlığı yeniden eşlenebilir.  
- **Çıktı HTML mi yoksa gömülü kaynaklar mı?** Tek bir bağımsız dosya için gömülü kaynakları seçebilirsiniz.

## “How to Rename Email” GroupDocs.Viewer Bağlamında Ne Anlama Geliyor?
E-posta alanlarını yeniden adlandırmak, e-posta HTML'ye render edildiğinde varsayılan etiketleri (ör. “From”) özel metinle (ör. “Sender”) değiştirmek anlamına gelir. Bu, çıktıyı kurumsal terminolojiyle uyumlu hale getirmek veya son kullanıcı okunabilirliğini artırmak için faydalıdır.

## Neden E-postayı HTML'ye Dönüştürmek ve E-posta Başlıklarını Özelleştirmek?
- **Tutarlı marka:** Tüm iletişimlerde kuruluşunuzun diline uyum sağlamak.  
- **Gelişmiş aranabilirlik:** Özelleştirilmiş başlıklar arşivleme sistemlerinde daha etkili indekslenebilir.  
- **Daha iyi UI entegrasyonu:** HTML snippet'ini web portallarına veya destek panellerine sorunsuz uyacak şekilde özelleştirin.

## Ön Koşullar

### Gerekli Kütüphaneler, Sürümler ve Bağımlılıklar
- **GroupDocs.Viewer for Java** – sürüm 25.2 veya üzeri.  
- **Java Development Kit (JDK)** – sürüm 8+.

### Ortam Kurulum Gereksinimleri
- **Maven** bağımlılık yönetimi için.  
- IntelliJ IDEA, Eclipse veya VS Code gibi bir IDE.

### Bilgi Ön Koşulları
Temel Java ve Maven bilgisi, konuyu hızlıca takip etmenize yardımcı olacaktır.

## GroupDocs.Viewer for Java'ı Kurma

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
- **Satın Alma:** Sürekli kullanım için [GroupDocs Purchase](https://purchase.groupdocs.com/buy) üzerinden lisans satın almayı düşünün.

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
Dosya yolunu `.msg` dosyanıza işaret edecek şekilde ayarlayın.

## Uygulama Kılavuzu

### E-posta Alanlarını Yeniden Adlandırma – Adım Adım

#### 1. Çıktı Dizin Yolunu Ayarlama
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*`"YOUR_OUTPUT_DIRECTORY"` ifadesini HTML dosyalarının kaydedileceği klasörle değiştirin.*

#### 2. Sayfa Dosya Yolu Formatını Tanımlama
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` render sırasında sayfa numarasıyla değiştirilecektir.*

#### 3. E-posta Alanlarını Yeni İsimlerle Eşleştirme Oluşturma
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
*Burada varsayılan etiketleri özelleştirilmiş olanlarla değiştiriyoruz.*

#### 4. HTML Görünüm Seçeneklerini Yapılandırma
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` CSS/JS'yi HTML içine paketler, `setFieldTextMap` ise özelleştirilmiş başlık adlarını uygular.*

#### 5. E-postayı HTML'ye Render Etme
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*`"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` ifadesini MSG dosyanızın gerçek yolu ile değiştirin.*

#### Sorun Giderme İpuçları
- Çıktı dizininin yazılabilir olduğunu doğrulayın.  
- Giriş MSG dosyasının mevcut ve yolunun doğru olduğundan emin olun.  
- Maven'de bildirildiği gibi aynı GroupDocs.Viewer sürümünü (25.2) kullanın.

## Pratik Uygulamalar
1. **Özel E-posta Raporları:** Daha net raporlar için e-posta başlıklarını kurumsal terminolojiyle uyumlu hale getirin.  
2. **E-posta Arşivleme Sistemleri:** Standartlaştırılmış başlık adlarıyla aranabilirliği artırın.  
3. **Müşteri Destek Platformları:** Biletleri, ajan deneyimini iyileştirmek için kişiselleştirilmiş başlık etiketleriyle sunun.

## Performans Düşünceleri
- `Viewer` nesnelerini try‑with‑resources ile serbest bırakarak belleği hızlıca temizleyin.  
- Büyük partileri profilleyin ve gerekirse e-postaları paralel akışlarda işlemeyi düşünün.

## Sonuç
Artık GroupDocs.Viewer for Java ile **e-posta alanlarını nasıl yeniden adlandıracağınızı**, **e-postayı HTML'ye dönüştürürken** ve **e-posta başlıklarını özelleştirirken** biliyorsunuz. Bu teknik, e-posta meta verilerinin HTML çıktılarındaki sunumunu tam kontrol etmenizi sağlar.

### Sonraki Adımlar
- Ek alan eşlemeleri (ör. CC, BCC) ile denemeler yapın.  
- PDF veya PNG gibi diğer render formatlarını keşfedin.  
- Daha derin API bilgileri için [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) adresini ziyaret edin.

## SSS Bölümü
1. **Bu yöntemle tüm e-posta başlıklarını yeniden adlandırabilir miyim?**  
   - Evet, gereksinimlerinize göre herhangi bir standart e-posta başlığını yeni bir isimle eşleyebilirsiniz.  
2. **GroupDocs.Viewer'ı lisans olmadan kullanmak mümkün mü?**  
   - Test için bir deneme sürümü mevcuttur, ancak tam özellikli sürüm geçerli bir lisans gerektirir.  
3. **GroupDocs.Viewer ile büyük miktarda e-postayı verimli bir şekilde nasıl yönetebilirim?**  
   - Toplu işleme yapmayı ve sistem kaynaklarını optimize etmeyi düşünerek büyük veri setlerini etkili bir şekilde yönetin.  
4. **Bu çözümü mevcut bir Java uygulamasına entegre edebilir miyim?**  
   - Kesinlikle, Maven bağımlılıklarıyla entegrasyon oldukça basittir.  
5. **Sorunlarla karşılaşırsam nereden destek alabilirim?**  
   - Topluluk ve resmi yardım için [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) adresini ziyaret edin.

## Sıkça Sorulan Sorular

**S: Bu yaklaşım EML gibi diğer e-posta formatlarıyla çalışır mı?**  
C: Evet, GroupDocs.Viewer hem MSG hem de EML dosyalarını destekler; aynı alan eşleme mantığı uygulanır.

**S: HTML'yi gömülü kaynaklar olmadan çıktı alabilir miyim?**  
C: Ayrı CSS/JS dosyalarını tercih ediyorsanız `HtmlViewOptions.forExternalResources(...)` kullanabilirsiniz.

**S: Hangi GroupDocs.Viewer sürümü test edildi?**  
C: Kod, GroupDocs.Viewer **25.2** ile test edilmiştir.

**S: Özelleştirilmiş başlıkların fontunu veya stilini değiştirmek mümkün mü?**  
C: Stil, render sonrası CSS ile uygulanabilir veya `HtmlViewOptions.getResourcesPath()` kullanarak özel CSS enjekte edebilirsiniz.

**S: Oluşturulan HTML dosya yolunu programlı olarak nasıl alabilirim?**  
C: Dosya yolu, `pageFilePathFormat` içinde tanımlanan desene göre olur; sayfa numarasıyla `String.format` kullanarak oluşturabilirsiniz.

## Kaynaklar
- **Dokümantasyon:** Kapsamlı rehberler [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) adresinde mevcuttur.  
- **API Referansı:** Ayrıntılı API bilgileri [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/) adresinde bulunabilir.  
- **GroupDocs.Viewer'ı İndir:** En son sürüme [Downloads Page](https://releases.groupdocs.com/viewer/java/) üzerinden ulaşabilirsiniz.

---

**Son Güncelleme:** 2026-01-05  
**Test Edilen Sürüm:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs