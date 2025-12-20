---
date: '2025-12-20'
description: GroupDocs.Viewer for Java'da klasör başına maksimum öğe sayısını yapılandırarak
  Outlook klasöründeki öğeleri sınırlamayı öğrenin, büyük PST/OST dosyalarını işlerken
  performansı artırın.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: GroupDocs.Viewer for Java ile Outlook Görüntülemede Klasör Başına Maksimum
  Öğe Sayısını Nasıl Ayarlarsınız
type: docs
url: /tr/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Java'da GroupDocs.Viewer Kullanarak Outlook Öğesi İşlemeyi Sınırlama

Devasa Outlook veri dosyalarını (PST veya OST) yönetmek hızla bir performans darboğazına dönüşebilir. Bu rehberde, GroupDocs.Viewer for Java ile render ederken **max items per folder** nasıl ayarlanacağını keşfedecek, böylece yalnızca gerçekten ihtiyacınız olan verileri işleyebileceksiniz. **limit items outlook folder** tekniğini uygulayarak, uygulamanız gigabaytlarca e-posta verisiyle bile yanıt verir durumda kalır.

![GroupDocs.Viewer for Java ile Outlook Öğesi İşlemeyi Sınırlama](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Öğrenecekleriniz
- GroupDocs.Viewer for Java'ı kurma
- Kütüphaneyi Outlook dosyalarında **max items per folder** olarak yapılandırma
- Öğeleri klasöre sınırlamanın hızı artırdığı ve bellek kullanımını azalttığı gerçek dünya senaryoları

Kurulum ve uygulamayı adım adım inceleyelim.

## Hızlı Yanıtlar
- **“max items per folder” ne yapar?** Her Outlook klasöründeki belirli bir sayıda e-posta öğesinin render edilmesini sınırlar.  
- **Neden items outlook folder sınırlanmalı?** Büyük posta kutularında işleme süresini ve bellek tüketimini azaltmak için.  
- **Hangi sürüm bu özelliği destekliyor?** GroupDocs.Viewer 25.2 ve sonrası.  
- **Lisans gerekiyor mu?** Evet, üretim kullanım için bir deneme veya satın alınmış lisans gereklidir.  
- **Sınırı çalışma zamanında değiştirebilir miyim?** Kesinlikle – render etmeden önce `setMaxItemsInFolder` değerini değiştirmeniz yeterlidir.

## Genel Bakış
PST veya OST gibi büyük Outlook veri dosyalarını yönetmekte zorlanıyor musunuz? Bu rehber, bu dosyaları GroupDocs.Viewer for Java ile render ederken işlenen öğe sayısını nasıl sınırlayacağınızı gösterir, uygulamanızın verimliliğini ve yanıt verebilirliğini artırır.

### “max items per folder” nedir?
**max items per folder** ayarı, görüntüleyicinin her klasörde belirli bir öğe sayısını render ettikten sonra durmasını söyler. Bu, yalnızca son e-postaların önizlemesine ihtiyaç duyduğunuzda veya tüm posta kutusunu gerektirmeyen raporlar oluştururken özellikle faydalıdır.

### Neden limit items outlook folder yaklaşımını kullanmalı?
- **Performans:** Daha hızlı render süreleri ve daha düşük CPU kullanımı.  
- **Ölçeklenebilirlik:** JVM belleğini tüketmeden daha büyük posta kutularını yönetme.  
- **Esneklik:** Kullanıcı tercihleri veya cihaz yeteneklerine göre sınırı ayarlama.

## Önkoşullar
Başlamadan önce aşağıdakilerin olduğundan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar:
1. **Java Development Kit (JDK)**: JDK 8 veya daha yeni bir sürüm kurun.  
2. **GroupDocs.Viewer for Java**: Projenize bağımlılık olarak ekleyin.

### Ortam Kurulum Gereksinimleri:
- IntelliJ IDEA, Eclipse veya NetBeans gibi uygun bir IDE.  
- Bağımlılıkları Maven ile yönetiyorsanız Maven kurulu olmalı.

### Bilgi Önkoşulları:
- Java programlama ve dosya işlemleri hakkında temel bilgi.  
- Maven projelerine aşina olmak faydalı ancak zorunlu değil.

## GroupDocs.Viewer for Java'ı Kurma
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
- **Ücretsiz Deneme**: Kütüphanenin özelliklerini keşfetmek için [GroupDocs](https://releases.groupdocs.com/viewer/java/) adresinden ücretsiz deneme indirin.  
- **Geçici Lisans**: Değerlendirme sınırlamaları olmadan tam erişim için [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) adresinden geçici lisans alın.  
- **Satın Alma**: Uzun vadeli kullanım için [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) adresinden lisans satın almayı düşünün.

### Temel Başlatma ve Kurulum
Maven yapılandırıldıktan sonra, Java uygulamanızda viewer nesnesini ayarlayarak GroupDocs.Viewer'ı başlatın. Bu, belgeleri yüklemenizi ve render etmenizi sağlar.

## Uygulama Kılavuzu

### Outlook Dosyalarından Render Edilen Öğeleri Sınırlama
Bu bölüm, GroupDocs.Viewer for Java kullanarak Outlook veri dosyalarından render edilen öğeleri nasıl sınırlayacağınızı ayrıntılı olarak açıklar.

#### Genel Bakış
Belirli seçenekleri yapılandırarak, render işlemini klasör başına belirli bir öğe sayısıyla sınırlayabilirsiniz. Bu özellik, büyük e-posta veri setleriyle çalışırken performans ve verimliliği artırır.

**Adım 1: Çıktı Dizin Yolu Ayarlama**  
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```

**Adım 2: HTML Sayfaları için Dosya Yolu Formatı Tanımlama**  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Adım 3: Gömülü Kaynaklarla HtmlViewOptions'ı Yapılandırma**  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Adım 4: Outlook Seçeneklerini Klasör Başına Öğeleri Sınırlayacak Şekilde Ayarlama**  
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```

Burada, **max items per folder** değerini üç olarak ayarlıyoruz. **limit items outlook folder** senaryonuza göre sayıyı ayarlayın.

**Adım 5: Belgeyi Yükleyin ve Render Edin**  
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```

`Viewer` sınıfını kullanarak bir OST dosyasını yükleyin ve tanımlı görüntü seçeneklerine göre render edin. try‑with‑resources ifadesi, kaynakların kullanım sonrası düzgün bir şekilde kapatılmasını sağlar.

### Sorun Giderme İpuçları
- Kodunuzu çalıştırmadan önce tüm yol ve dizinlerin mevcut olduğundan emin olun.  
- GroupDocs.Viewer bağımlılıklarının Maven tarafından doğru şekilde çözüldüğünü doğrulayın.  
- Render sırasında oluşabilecek istisnaları kontrol edin; bu, dosya formatları veya izinlerle ilgili sorunları gösterebilir.

## Pratik Uygulamalar
1. **E-posta Arşivleme** – Öğeleri sınırlamak, tüm veri seti yerine belirli e-postaların arşivlenmesine odaklanan uygulamalar için idealdir.  
2. **Veri Göçü** – Sistemler arasında veri aktarırken, performansı optimize etmek ve işlem süresini azaltmak için yalnızca gerekli öğeleri render edin.  
3. **Özel Raporlama** – Tüm klasörleri yüklemeden, gereken e-posta içeriğini seçerek raporlar oluşturun.

## Performans Düşünceleri
### Performansı Optimize Etmek İçin İpuçları
- Bellek kullanımını azaltmak için klasör başına öğe sayısını sınırlayın.  
- Render sırasında ek ağ çağrılarını önlemek için gömülü kaynakları verimli kullanın.

### Kaynak Kullanım Kılavuzları
- İşlenen Outlook dosyalarının boyutuna göre JVM belleğini izleyin ve ayarları buna göre düzenleyin.

### Java Bellek Yönetimi için En İyi Uygulamalar
- Otomatik kaynak yönetimi için try‑with‑resources kullanın.  
- Büyük dosya işlemleriyle ilgili darboğazları belirlemek için uygulamanızı profilleyin.

## Sonuç
Bu öğreticide, GroupDocs.Viewer for Java kullanarak Outlook veri dosyalarında **max items per folder** özelliğini etkili bir şekilde nasıl uygulayacağınızı öğrendiniz. Bu adımları izleyerek ve performans ipuçlarını göz önünde bulundurarak, belirli ihtiyaçlara uygun verimli uygulamalar oluşturabilirsiniz.

### Sonraki Adımlar
- [Resmi dokümantasyona](https://docs.groupdocs.com/viewer/java/) bakarak GroupDocs.Viewer'ın ek özelliklerini keşfedin.  
- Uygulamanızın gereksinimlerine en uygun ayarı bulmak için farklı render seçenekleriyle deneyler yapın.

Denemeye hazır mısınız? Bu çözümü bugün projelerinizde uygulamaya başlayın ve geliştirilmiş verimliliği ilk elden görün.

## Sıkça Sorulan Sorular

**S: GroupDocs.Viewer Java ne için kullanılır?**  
C: Outlook veri dosyaları da dahil olmak üzere çeşitli belge formatlarını HTML veya görüntü formatlarına render etmek için tasarlanmış çok yönlü bir kütüphanedir.

**S: GroupDocs.Viewer'ın ücretsiz denemesini nasıl alabilirim?**  
C: Erişim ve indirme seçenekleri için [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin.

**S: PST dosyalarında da öğe render'ını sınırlayabilir miyim?**  
C: Evet, aynı yapılandırma OST ve PST dosya formatları için geçerlidir.

**S: Render sırasında uygulamam yavaş çalışıyorsa ne yapmalıyım?**  
C: Öğe sınırlarını ve kaynak ayarlarını gözden geçirin; bellek yönetimi uygulamalarını optimize etmeyi düşünün.

**S: GroupDocs.Viewer sorunları için desteği nereden bulabilirim?**  
C: Yardım için [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9) adresine bakabilirsiniz.

## Ek Kaynaklar
- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer for Java'ı İndir](https://releases.groupdocs.com/viewer/java/)
- [Lisans Satın Al](https://purchase.groupdocs.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.groupdocs.com/viewer/java/)
- [Geçici Lisans Başvurusu](https://purchase.groupdocs.com/temporary-license/)
- [Destek Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs