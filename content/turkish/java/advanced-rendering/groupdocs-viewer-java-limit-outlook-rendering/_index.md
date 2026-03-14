---
date: '2026-02-21'
description: GroupDocs.Viewer for Java ile Outlook dosyalarını render ederken klasör
  başına maksimum öğe sayısını nasıl ayarlayacağınızı öğrenin; bu, büyük PST/OST dosyalarında
  performansı artırır.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: GroupDocs.Viewer for Java ile Outlook Görüntülemede Klasör Başına Azami Öğe
  Sayısını Nasıl Ayarlarsınız
type: docs
url: /tr/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

GroupDocs stays)

Now ensure we preserve markdown formatting, code block placeholders unchanged.

Also ensure we keep any bold formatting.

Now produce final output with all translated content.# Java'da GroupDocs.Viewer Kullanarak Outlook Öğesi Oluşturmayı Sınırlama

Büyük Outlook veri dosyalarını (PST veya OST) yönetmek hızla bir performans darboğazına dönüşebilir. Bu rehberde, GroupDocs.Viewer for Java ile oluşturma sırasında klasör başına **set max items** nasıl ayarlanacağını keşfedeceksiniz, böylece yalnızca gerçekten ihtiyacınız olan verileri işlersiniz. **limit items per folder** tekniğini uygulayarak, uygulamanız gigabaytlarca e-posta verisiyle bile yanıt verir durumda kalır.

![Limit Outlook Item Rendering with GroupDocs.Viewer for Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Öğrenecekleriniz
- GroupDocs.Viewer for Java'ı kurma  
- Kütüphaneyi Outlook dosyalarında klasör başına **set max items** ayarlamak için yapılandırma  
- Klasör başına öğe sınırlamanın hızı artırdığı ve bellek kullanımını azalttığı gerçek dünya senaryoları  

## Hızlı Yanıtlar
- **What does “set max items per folder” do?** Oluşturmayı, her Outlook klasöründeki tanımlı sayıda e-posta öğesiyle sınırlar.  
- **Why limit Outlook items?** Büyük posta kutuları için işleme süresini ve bellek tüketimini azaltmak.  
- **Which version supports this feature?** GroupDocs.Viewer 25.2 ve sonrası.  
- **Do I need a license?** Evet, üretim kullanımı için bir deneme veya satın alınmış lisans gereklidir.  
- **Can I change the limit at runtime?** Kesinlikle – oluşturma öncesinde `setMaxItemsInFolder` değerini değiştirmeniz yeterlidir.  

## Outlook Oluşturmasında klasör başına maksimum öğe ayarlama
Aşağıda, Outlook öğelerini sınırlamak isteyebileceğiniz **neden**, ayarın **ne** işe yaradığını ve Java projenizde **nasıl** yapılandırılacağını adım adım açıklayan bir rehber bulacaksınız.

### “set max items per folder” nedir?
**set max items** seçeneği, görüntüleyicinin her klasörde belirli bir öğe sayısını oluşturduktan sonra durmasını söyler. Bu, yalnızca son e-postaların bir önizlemesine ihtiyacınız olduğunda veya tüm posta kutusunu gerektirmeyen raporlar oluştururken özellikle faydalıdır.

### Neden klasör başına öğe sınırlama yaklaşımını kullanmalısınız?
- **Performance:** Daha hızlı oluşturma süreleri ve daha düşük CPU kullanımı.  
- **Scalability:** JVM belleğini tüketmeden daha büyük posta kutularını yönetme.  
- **Flexibility:** Kullanıcı tercihleri veya cihaz yeteneklerine göre sınırı ayarlama.  

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürümünü kurun.  
2. **GroupDocs.Viewer for Java** – Projenize bağımlılık olarak ekleyin.

### Ortam Kurulum Gereksinimleri
- IntelliJ IDEA, Eclipse veya NetBeans gibi uygun bir IDE.  
- Bağımlılıkları Maven ile yönetiyorsanız Maven kurulu olmalı.

### Bilgi Önkoşulları
- Java programlama ve dosya işleme konusunda temel bilgi.  
- Maven projelerine aşina olmak faydalıdır, ancak zorunlu değildir.

## GroupDocs.Viewer for Java Kurulumu
Maven kullanarak projenizde GroupDocs.Viewer'ı kurun:

**Maven Yapılandırması:**
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
- **Free Trial**: Kütüphanenin özelliklerini keşfetmek için [GroupDocs](https://releases.groupdocs.com/viewer/java/) adresinden ücretsiz deneme sürümünü indirin.  
- **Temporary License**: Değerlendirme sınırlamaları olmadan tam erişim için [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) adresinden geçici bir lisans alın.  
- **Purchase**: Uzun vadeli kullanım için [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) adresinden lisans satın almayı düşünün.

### Temel Başlatma ve Kurulum
Maven yapılandırıldıktan sonra, Java uygulamanızda viewer nesnesini ayarlayarak GroupDocs.Viewer'ı başlatın. Bu, belgeleri yükleyip oluşturmanızı sağlar.

## Uygulama Kılavuzu

### Outlook Dosyalarından Oluşturulan Öğeleri Sınırlama
Bu bölüm, GroupDocs.Viewer for Java kullanarak Outlook veri dosyalarından oluşturulan öğeleri nasıl sınırlayacağınızı ayrıntılı olarak açıklar.

#### Genel Bakış
Belirli seçenekleri yapılandırarak, oluşturmayı klasör başına belirli bir öğe sayısıyla sınırlayabilirsiniz. Bu özellik, büyük e-posta veri setleriyle çalışırken performans ve verimliliği artırır.

**Adım 1: Çıktı Dizin Yolunu Ayarlama**
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```
Bu kod, oluşturulan HTML dosyalarının saklanacağı dizini ayarlar. `"LimitCountOfItemsToRender"` ifadesini istediğiniz yol adıyla değiştirin.

**Adım 2: HTML Sayfaları için Dosya Yolu Biçimini Tanımlama**
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
Oluşturma sırasında üretilen HTML sayfaları için tutarlı bir adlandırma biçimi oluşturun, böylece erişim ve yönetim kolaylaşır.

**Adım 3: HtmlViewOptions'ı Gömülü Kaynaklarla Yapılandırma**
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
Bu seçenek, belgelerin gömülü kaynaklarla nasıl oluşturulacağını belirler; bu sayede görüntüler ve stiller daha iyi bütünleşir.

**Adım 4: Outlook Seçeneklerini Klasör Başına Öğeleri Sınırlamak İçin Ayarlama**
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```
Burada, **set max items** değerini üç olarak belirliyoruz. **limit items per folder** senaryonuza göre sayıyı ayarlayın.

**Adım 5: Belgeyi Yükleyip Oluşturma**
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```
`Viewer` sınıfını kullanarak bir OST dosyasını yükleyin ve tanımlı görünüm seçeneklerine göre oluşturun. try‑with‑resources ifadesi, kaynakların kullanım sonrası düzgün bir şekilde kapatılmasını sağlar.

### Sorun Giderme İpuçları
- Kodunuzu çalıştırmadan önce tüm yol ve dizinlerin mevcut olduğundan emin olun.  
- GroupDocs.Viewer bağımlılıklarının Maven tarafından doğru bir şekilde çözüldüğünü doğrulayın.  
- Oluşturma sırasında oluşabilecek istisnaları kontrol edin; bu, dosya biçimleri veya izinlerle ilgili sorunları gösterebilir.

## Pratik Uygulamalar
1. **Email Archiving** – Öğeleri sınırlamak, tüm veri setleri yerine belirli e-postaların arşivlenmesine odaklanan uygulamalar için idealdir.  
2. **Data Migration** – Sistemler arasında veri aktarırken, performansı optimize etmek ve işleme süresini azaltmak için yalnızca gerekli öğeleri oluşturun.  
3. **Custom Reporting** – Tüm klasörleri yüklemeden, gereken e-posta içeriğini seçerek raporlar oluşturun.

## Performans Düşünceleri
### Performansı Optimize Etme İpuçları
- Bellek kullanımını azaltmak için klasör başına öğe sayısını sınırlayın.  
- Oluşturma sırasında ek ağ çağrılarını önlemek için gömülü kaynakları verimli kullanın.

### Kaynak Kullanım Kılavuzları
- İşlenen Outlook dosyalarının boyutuna göre JVM belleğini izleyin ve ayarları buna göre düzenleyin.

### Java Bellek Yönetimi için En İyi Uygulamalar
- Otomatik kaynak yönetimi için try‑with‑resources kullanın.  
- Büyük dosya işlemleriyle ilgili darboğazları belirlemek için uygulamanızı profilleyin.

## Yaygın Tuzaklar ve Nasıl Kaçınılır
| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| Çıktı dosyaları oluşturulmadı | Çıktı dizini yolu yanlış veya izinler eksik | `outputDirectory`'nin mevcut ve yazılabilir olduğunu doğrulayın |
| Birkaç öğeden sonra oluşturma durdu | `setMaxItemsInFolder` çok düşük ayarlandı | Sınırı artırın veya yapılandırılabilir hale getirin |
| Büyük PST'de OutOfMemoryError | Varsayılan bellek ayarları yetersiz | JVM yığınını artırın (`-Xmx`) ve sınırı düşük tutun |

## Sonuç
Bu öğreticide, GroupDocs.Viewer for Java kullanarak Outlook veri dosyalarında **set max items per folder** nasıl ayarlanacağını öğrendiniz. Adımları izleyip performans ipuçlarını uygulayarak, ihtiyaçlarınıza özel verimli uygulamalar oluşturabilirsiniz.

### Sonraki Adımlar
- [Resmi belgeler](https://docs.groupdocs.com/viewer/java/) üzerinden GroupDocs.Viewer'ın ek özelliklerini keşfedin.  
- Uygulamanızın gereksinimlerine en uygun ayarı bulmak için farklı oluşturma seçenekleriyle deneyler yapın.

Denemeye hazır mısınız? Bu çözümü bugün projelerinizde uygulamaya başlayın ve geliştirilmiş verimliliği ilk elden görün.

## Sıkça Sorulan Sorular

**S: GroupDocs.Viewer Java ne için kullanılır?**  
C: Outlook veri dosyaları da dahil olmak üzere çeşitli belge formatlarını HTML veya görüntü formatlarına dönüştürmek için tasarlanmış çok yönlü bir kütüphanedir.

**S: GroupDocs.Viewer'ın ücretsiz denemesini nasıl alabilirim?**  
C: Erişim ve indirme seçenekleri için [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin.

**S: PST dosyalarında da öğe oluşturmayı sınırlayabilir miyim?**  
C: Evet, aynı yapılandırma OST ve PST dosya formatları için geçerlidir.

**S: Oluşturma sırasında uygulamam yavaş çalışıyorsa ne yapmalıyım?**  
C: Öğe sınırlarını ve kaynak ayarlarını gözden geçirin; bellek yönetimi uygulamalarını optimize etmeyi düşünün.

**S: GroupDocs.Viewer sorunları için destek nereden bulunur?**  
C: Yardım için [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9) adresine bakın.

## Ek Kaynaklar
- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer for Java'ı İndir](https://releases.groupdocs.com/viewer/java/)
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans Başvurusu](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forumu](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-02-21  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs