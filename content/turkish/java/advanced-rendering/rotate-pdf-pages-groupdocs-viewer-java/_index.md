---
date: '2026-01-18'
description: GroupDocs.Viewer for Java ile PDF sayfalarını nasıl döndüreceğinizi öğrenin.
  Bu adım adım öğretici, Maven kurulumunu, sayfa döndürmeyi (90 derece PDF döndürme
  dahil) ve sorun giderme konularını kapsar.
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: Java'da GroupDocs.Viewer Kullanarak PDF Sayfalarını Döndürme – Kapsamlı Bir
  Rehber
type: docs
url: /tr/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer ile Java'da PDF Sayfalarını Döndürme

Bir PDF içinde belirli sayfaları döndürmek, belgeleri hizalamak veya sunum slaytlarını ayarlamak için gerekli olabilir. **Bu rehberde GroupDocs.Viewer ile programlı olarak pdf** sayfalarını nasıl döndüreceğinizi öğreneceksiniz; pdf'yi 90 derece döndürmeniz, bir bölümü ters çevirmeniz veya tek bir çağrıda birden fazla sayfayı işlemeniz gerekebilir.

![GroupDocs.Viewer for Java ile Belirli PDF Sayfalarını Döndürme](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Öğrenecekleriniz:**
- Java projenizde GroupDocs.Viewer'ı kurma (Maven GroupDocs Viewer yapılandırması dahil)
- Belirli PDF sayfalarını programlı olarak döndürme (pdf'yi 90 derece, 180 derece vb. döndürme)
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

Başlamak için aşağıdakilere sahip olduğunuzdan emin olun:
- Makinenizde yüklü Java Development Kit (JDK) sürüm 8 veya üzeri.
- IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE).
- Proje bağımlılıklarını yönetmek için Maven.

### Ortam Kurulum Gereksinimleri

1. **Maven Yapılandırması**: `pom.xml` dosyanıza gerekli depoları ve bağımlılıkları ekleyerek GroupDocs.Viewer'ı Maven projenize ekleyin.
2. **Lisans Edinme**: Geliştirme sırasında sınırlama olmadan tüm özellikleri keşfetmenizi sağlayan geçici bir lisansı GroupDocs'tan alın. [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin veya [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) üzerinden geçici lisans başvurusunda bulunun.

## GroupDocs.Viewer for Java Kurulumu

Maven kullanarak GroupDocs.Viewer'ı Java projenize entegre etmek için `pom.xml` dosyanızı güncelleyin:

**Maven Yapılandırması**
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

Belge dizininizi ve çıktı yollarınızı belirterek GroupDocs.Viewer'ı başlatın:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Uygulama Kılavuzu

### GroupDocs.Viewer ile Belirli Sayfaları Döndürme

**Genel Bakış:** Daha iyi belge sunumu için belirli PDF sayfalarını döndürün.

#### Adım 1: Sayfa Döndürmeyi Yapılandırma

`HtmlViewOptions` kullanarak ilk sayfayı 90 derece, ikinci sayfayı 180 derece döndürün:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### Adım 2: Viewer'ı Başlat ve Render Et

Belgenizle bir `Viewer` örneği oluşturun ve belirtilen sayfaları render edin:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### Parametreler ve Yapılandırma

- **Rotation**: Sayfa numaraları ve döndürme açılarıyla `rotatePage` kullanın. Mevcut döndürmeler: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.
- **HtmlViewOptions**: PDF sayfa dönüşümünü HTML'e yapılandırır, gömülü kaynakların dahil edilmesini sağlar.
- **pdf to html java**: `HtmlViewOptions` sınıfı, düzeni koruyarak PDF‑to‑HTML dönüşümünü yönetir.

#### Sorun Giderme İpuçları (troubleshoot pdf rotation)

- Belge ve çıktı dizinlerinin yollarını doğrulayın.
- Eksik bağımlılıkları veya yanlış kütüphane sürümlerini kontrol edin.
- Deneme sırasında özellik kısıtlamaları oluşursa lisansın doğru uygulandığından emin olun.
- Bellek dalgalanmaları yaşıyorsanız, sayfaları daha küçük partiler halinde render etmeyi düşünün (birden fazla pdf sayfasını kademeli olarak döndürün).

## Pratik Uygulamalar

### Gerçek Dünya Kullanım Senaryoları
1. **Belge Hizalama** – Tarama belgelerini doğru dijital yönlendirme için döndürün.
2. **Sunum Ayarlamaları** – Paylaşmadan önce PDF içindeki sunum slaytlarını değiştirin.
3. **Arşiv İş Akışları** – Dijitalleştirme sırasında tarihi belgelerin yönünü otomatik olarak ayarlayın.

### Entegrasyon Olanakları
Dinamik görüntüleme yetenekleri gerektiren Java tabanlı belge yönetim sistemleri, içerik platformları veya özel kurumsal çözümlerle GroupDocs.Viewer'ı entegre edin.

## Performans Düşünceleri

- **Kaynak Yönetimi**: Kaynakları serbest bırakmak için `Viewer` örneğini kapatın.
- **Java Bellek Yönetimi**: Büyük belgeleri render ederken bellek kullanımını izleyin ve verimli veri yapıları kullanın.
- **En İyi Uygulamalar**: Sık erişilen belgeler veya sayfalar için önbellekleme kullanın.

## Sonuç

Bu öğreticide Java'da GroupDocs.Viewer kullanarak **pdf sayfalarını nasıl döndüreceğinizi** ortam kurulumundan pratik uygulamalara kadar ele aldık. Filigran ekleme veya belgeleri farklı formatlara dönüştürme gibi ek işlevlerle deneyler yapın.

**Sonraki Adımlar:** Belge işleme yeteneklerinizi geliştirmek için daha fazla GroupDocs.Viewer özelliğini keşfedin.

## SSS Bölümü

### Yaygın Sorular
1. **Döndürme Sorunlarını Giderme**: Sayfa numaraları ve döndürme parametrelerinin doğru olduğunu doğrulayın.
2. **Büyük PDF Dosyalarını İşleme**: Uygun kaynak yönetimiyle büyük belgeleri verimli bir şekilde işleyin.
3. **Lisans Gereksinimleri**: Geliştirme için geçici lisans kullanın; üretim için tam lisans satın alın.
4. **Birden Fazla Sayfayı Döndürme**: Farklı sayfa numaraları ve açılarla `rotatePage`'i birden çok kez çağırın.
5. **Java Kütüphaneleriyle Entegrasyon**: GroupDocs.Viewer'ı daha büyük uygulamalara veya çerçevelere sorunsuz bir şekilde entegre edin.

## Sık Sorulan Sorular

**S: Bir PDF'nin tüm sayfalarını bir kerede döndürebilir miyim?**  
C: Evet. Sayfa numaraları üzerinden döngü kurarak her sayfa için `rotatePage(page, Rotation.ON_90_DEGREE)` çağırın.

**S: Döndürme orijinal PDF dosyasını etkiler mi?**  
C: Hayır. Döndürme yalnızca render sürecinde uygulanır; kaynak PDF değişmeden kalır.

**S: PDF şifre korumalıysa ne olur?**  
C: `Viewer` örneğini oluştururken şifreyi sağlayın: `new Viewer(path, password)`.

**S: HtmlViewOptions ayarlarken “null pointer” hatasını nasıl ayıklayabilirim?**  
C: Çıktı dizininin mevcut olduğundan ve `pageFilePathFormat`'in doğru çözüldüğünden emin olun.

**S: Sayfaları diğer formatlara (ör. PNG) dönüştürürken döndürmenin bir yolu var mı?**  
C: Hedef format için uygun view seçenekleriyle aynı `rotatePage` yapılandırmasını kullanın.

## Kaynaklar
- **Documentation**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-01-18  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs