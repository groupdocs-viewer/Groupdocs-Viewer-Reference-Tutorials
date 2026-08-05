---
date: '2026-04-04'
description: GroupDocs.Viewer for Java ile belirli PDF sayfalarını nasıl döndüreceğinizi
  öğrenin. Bu adım adım kılavuz, Maven kurulumu, PDF'yi 90 derece döndürme ve sorun
  giderme konularını kapsar.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: GroupDocs.Viewer for Java ile Belirli PDF Sayfalarını Döndürme
type: docs
url: /tr/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java ile Belirli PDF Sayfalarını Döndürme

PDF içinde belirli sayfaları döndürmek, belgeleri hizalamak, taranmış görüntüleri düzeltmek veya sunum slaytlarını ayarlamak için gerekli olabilir. **Bu rehberde GroupDocs.Viewer ile programlı olarak belirli pdf sayfalarını nasıl döndüreceğinizi öğreneceksiniz**, ister pdf'i 90 derece döndürmeniz, tüm bir bölümü ters çevirmeniz veya tek bir çağrıda birden fazla sayfayı işlemeniz gerekse.

![GroupDocs.Viewer for Java ile Belirli PDF Sayfalarını Döndürme](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Öğrenecekleriniz**
- Java projenizde GroupDocs.Viewer'ı kurma (Maven GroupDocs Viewer yapılandırması dahil)
- Belirli PDF sayfalarını programlı olarak döndürme (pdf'i 90 derece, 180 derece vb. döndürme)
- Optimum kullanım için ana yapılandırmalar
- Uygulama sırasında yaygın sorunların giderilmesi

## Hızlı Yanıtlar
- **Java'da PDF sayfalarını döndürebilen kütüphane hangisidir?** GroupDocs.Viewer for Java.  
- **Tek bir sayfayı 90 derece döndürebilir miyim?** Evet, `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` kullanın.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme için geçici bir lisans mevcuttur.  
- **Maven gerekli mi?** Maven, GroupDocs bağımlılıklarını yönetmenin önerilen yoludur.  
- **Döndürülmüş sayfaları nasıl render ederim?** `HtmlViewOptions` kullanın ve `viewer.view(...)` çağırın.

## Önkoşullar

### Gerekli Kütüphaneler ve Bağımlılıklar
- Java Development Kit (JDK) 8 ve üzeri.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Bağımlılık yönetimi için Maven.

### Ortam Kurulum Gereksinimleri
1. **Maven Yapılandırması** – `pom.xml` dosyanıza GroupDocs.Viewer ekleyin.  
2. **Lisans Edinme** – GroupDocs'tan geçici bir lisans alın. [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin veya [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) üzerinden geçici lisans başvurusu yapın.

## GroupDocs.Viewer for Java Kurulumu

Maven kullanarak GroupDocs.Viewer'ı Java projenize entegre etmek için `pom.xml` dosyanızı güncelleyin:

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

### Temel Başlatma ve Kurulum
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## GroupDocs.Viewer ile Belirli PDF Sayfalarını Döndürme
### Genel Bakış
Belirli PDF sayfalarını döndürmek, orijinal dosyayı değiştirmeden belge sunumunu ince ayarlarla kontrol etmenizi sağlar.

### Adım 1: Sayfa Döndürmeyi Yapılandırma
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Adım 2: Viewer'ı Başlat ve Render Et
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parametreler ve Yapılandırma
- **Rotation** – `rotatePage(pageNumber, Rotation.*)`; döndürme seçenekleri `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – PDF‑to‑HTML dönüşümünü, düzeni ve gömülü kaynakları koruyarak yönetir.  
- **pdf to html java** – Aynı API'nin bir parçası olan sınıf, doğru bir görsel temsil sağlar.

## Neden Belirli PDF Sayfalarını Döndürmeliyiz?
- **Belge Hizalama** – Taranan sözleşme veya faturaların doğru yönlendirilmesi.  
- **Sunum Ayarlamaları** – PDF olarak dışa aktarılan slaytları ayarlama.  
- **Arşiv Tutarlılığı** – Toplu dijitalleştirme sırasında sayfa yönlendirmesini standartlaştırma.

## Yaygın Sorunlar ve Çözümler (pdf döndürme sorunlarını giderme)

- **Yanlış Yollar** – `YOUR_DOCUMENT_DIRECTORY` ve `YOUR_OUTPUT_DIRECTORY`'nin mevcut ve erişilebilir olduğunu doğrulayın.  
- **Eksik Bağımlılıklar** – Maven koordinatlarının en son GroupDocs.Viewer sürümüyle eşleştiğinden emin olun.  
- **Lisans Kısıtlamaları** – Geçici lisansı doğru şekilde uygulayın; aksi takdirde bazı özellikler devre dışı kalabilir.  
- **Bellek Dalgalanmaları** – Büyük PDF'leri daha küçük partilerde render edin veya JVM yığın boyutunu artırın.

## Pratik Uygulamalar

### Gerçek Dünya Kullanım Durumları
1. **Belge Hizalama** – Tarama belgelerini doğru dijital yönlendirme için döndürün.  
2. **Sunum Ayarlamaları** – Paylaşmadan önce PDF içindeki sunum slaytlarını değiştirin.  
3. **Arşiv İş Akışları** – Dijitalleştirme sırasında tarihsel belgelerin yönlendirmesini otomatik olarak ayarlayın.

### Entegrasyon Olanakları
GroupDocs.Viewer'ı Java tabanlı içerik yönetim sistemleri, kurumsal portal'lar veya PDF'lerin anlık görüntülenmesi gereken özel API'lerle birleştirin.

## Performans Düşünceleri
- **Kaynak Yönetimi** – Dosya tanıtıcılarını ve belleği serbest bırakmak için `Viewer` örneğini her zaman kapatın.  
- **Java Bellek Yönetimi** – Büyük PDF'leri işlerken yığın kullanımını izleyin; tüm dosyayı yüklemek yerine sayfaları akış olarak işlemeyi düşünün.  
- **En İyi Uygulamalar** – İşlem süresini azaltmak için sık erişilen belgeler için render edilmiş HTML'yi önbelleğe alın.

## Sonuç
Bu öğreticide **Java'da GroupDocs.Viewer kullanarak belirli pdf sayfalarını nasıl döndüreceğinizi** Maven kurulumu, döndürülmüş sayfaların render edilmesi ve yaygın sorunların ele alınmasıyla açıkladık. Belge iş akışınızı daha da genişletmek için filigran ekleme, format dönüşümü veya toplu işleme gibi ek özelliklerle deneyler yapın.

**Sonraki Adımlar:** PDF'leri PNG'ye dönüştürme, filigran ekleme veya bulut depolama sağlayıcılarıyla entegrasyon gibi diğer GroupDocs.Viewer yeteneklerine göz atın.

## SSS Bölümü
- **Döndürme Sorunlarını Giderme** – Sayfa numaralarının ve döndürme parametrelerinin doğru olduğunu doğrulayın.  
- **Büyük PDF Dosyalarını İşleme** – Sayfaları partiler halinde işleyin ve bellek kullanımını izleyin.  
- **Lisans Gereksinimleri** – Geliştirme için geçici lisans kullanın; üretim için tam lisans satın alın.  
- **Birden Çok Sayfayı Döndürme** – Farklı sayfa numaraları ve açılarıyla `rotatePage`'i tekrarlayarak çağırın.  
- **Java Kütüphaneleriyle Entegrasyon** – GroupDocs.Viewer, Spring Boot, Jakarta EE ve diğer Java çerçeveleriyle sorunsuz çalışır.

## Sıkça Sorulan Sorular

**S: Bir PDF'in tüm sayfalarını bir kerede döndürebilir miyim?**  
C: Evet. Sayfa numaraları üzerinde döngü kurarak her sayfa için `rotatePage(page, Rotation.ON_90_DEGREE)` çağırın.

**S: Döndürme orijinal PDF dosyasını etkiler mi?**  
C: Hayır. Döndürme yalnızca renderleme sürecinde uygulanır; kaynak PDF değişmeden kalır.

**S: PDF şifre korumalıysa ne olur?**  
C: `Viewer` örneğini oluştururken şifreyi sağlayın: `new Viewer(path, password)`.

**S: HtmlViewOptions ayarlarken “null pointer” hatasını nasıl ayıklayabilirim?**  
C: Çıktı dizininin mevcut olduğundan ve `pageFilePathFormat`'in doğru çözüldüğünden emin olun.

**S: Sayfaları diğer formatlara (ör. PNG) dönüştürürken döndürmek mümkün mü?**  
C: Evet. Hedef format için uygun view seçenekleriyle aynı `rotatePage` yapılandırmasını kullanın.

## Kaynaklar
- **Dokümantasyon**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-04-04  
**Test Edilen:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs