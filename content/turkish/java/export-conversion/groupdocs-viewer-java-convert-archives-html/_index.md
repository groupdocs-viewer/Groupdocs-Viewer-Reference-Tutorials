---
date: '2026-02-23'
description: Sayfa başına öğe sayısını nasıl ayarlayacağınızı, kaynak HTML'yi nasıl
  gömeceğinizi ve GroupDocs.Viewer Java kullanarak arşivleri tek sayfalı veya çok
  sayfalı HTML'ye toplu olarak nasıl dönüştüreceğinizi öğrenin.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Sayfa Başına Öğeleri Ayarla: GroupDocs.Viewer Java ile Arşivleri HTML''ye
  Dönüştür'
type: docs
url: /tr/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Sayfa Başına Öğeleri Ayarlama: GroupDocs.Viewer Java ile Arşivleri HTML'ye Dönüştürme

ZIP veya RAR gibi arşiv dosyalarını web‑uyumlu HTML'ye dönüştürmek, belgeleri doğrudan tarayıcıda paylaşmak veya incelemek istediğinizde sık karşılaşılan bir ihtiyaçtır. Bu rehberde arşivleri işlerken **sayfa başına öğe sayısını nasıl ayarlayacağınızı**, kendi içinde bütünleşik bir çıktı için kaynak HTML'yi nasıl gömeceğinizi ve GroupDocs.Viewer Java ile arşivleri verimli bir şekilde toplu dönüştürmeyi öğreneceksiniz.

![GroupDocs.Viewer for Java ile Arşivleri HTML'ye Dönüştürme](/viewer/export-conversion/convert-archives-to-html-java.png)

## Hızlı Yanıtlar
- **“sayfa başına öğe sayısını” ne kontrol eder?** Bu, bir arşivden kaç dosya veya klasörün her oluşturulan HTML sayfasında görüneceğini belirler.  
- **Görselleri ve CSS'i doğrudan HTML içinde gömebilir miyim?** Evet – kaynak HTML'yi gömmek için `forEmbeddedResources` seçeneğini kullanın.  
- **Toplu dönüştürme mümkün mü?** Kesinlikle; arşiv koleksiyonunu döngüye alabilir ve her birini aynı ayarlarla işleyebilirsiniz.  
- **GroupDocs.Viewer kullanmak için Maven'e ihtiyacım var mı?** Evet, aşağıda gösterildiği gibi `maven groupdocs viewer` bağımlılığını ekleyin.  
- **Hangi çıktı formatları destekleniyor?** Tek sayfalı HTML Java ve çok sayfalı HTML Java her ikisi de mevcuttur.

## GroupDocs.Viewer'da “sayfa başına öğe sayısını” nedir?
**sayfa başına öğe sayısını** ayarı arşiv render seçeneklerine aittir. Görüntüleyiciye, çok sayfalı bir HTML belgesi oluştururken her HTML sayfasında kaç arşiv girdisinin (dosya veya klasör) gösterileceğini söyler. Bu değeri ayarlamak, özellikle büyük arşivlerde sayfa boyutu ve gezinme hızını dengelemenize yardımcı olur.

## Neden kaynak HTML'yi gömmek?
Kaynakları (görseller, CSS, fontlar) doğrudan HTML dosyasının içine gömmek, harici dosyalar olmadan açılabilen tek bir taşınabilir belge oluşturur. Bu, e‑posta ekleri, çevrim dışı görüntüleme veya çıktıyı diğer web sayfalarına gömmek için idealdir.

## Önkoşullar
- **Gerekli Kütüphaneler:** GroupDocs.Viewer sürüm 25.2 veya üzeri dahil edin.  
- **Ortam:** Java Development Kit (JDK) yüklü ve yapılandırılmış.  
- **Bilgi:** Temel Java ve Maven bağımlılık yönetimi.  

## Maven GroupDocs Viewer Kurulumu
GroupDocs deposunu ve görüntüleyici bağımlılığını `pom.xml` dosyanıza ekleyin:

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

### Lisans Edinme
GroupDocs.Viewer, **ücretsiz deneme bağlantısı**, geçici bir lisans veya tam satın alma seçeneği sunar. Proje zaman çizelgenize uyanı seçin.

### Temel Başlatma
Maven kurulumu sonrası, görüntüleyiciyi kodunuza ekleyin:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Arşivleri Tek‑Sayfa HTML'ye Nasıl Render'layabilirsiniz
### Adım 1: Çıktı Dizini Tanımlama
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Adım 2: Tek‑Sayfa Çıktısı için Dosya Adı Belirleme
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Adım 3: Görüntüleyiciyi Başlatma
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Adım 4: Render Seçeneklerini Yapılandırma (kaynak HTML'yi gömme)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Adım 5: Tek Sayfa Olarak Render'lama
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Arşivleri Çok‑Sayfalı HTML'ye Render'lama ve Sayfa Başına Öğeleri Ayarlama
### Adım 1: Çıktı Dizini Tekrar Kullanma
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Adım 2: Çoklu Sayfalar İçin Dosya Adı Formatı Tanımlama
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Adım 3: Görüntüleyiciyi Tekrar Başlatma
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Adım 4: Çok‑Sayfalı Seçenekleri Yapılandırma (kaynak HTML'yi gömme)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Adım 5: Sayfa Başına Öğeleri Ayarlama (eylemdeki anahtar kelime)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Pratik Uygulamalar
- **Belge Yönetim Sistemleri:** Ek görüntüleyiciler kurmadan arşiv önizleme işlevi ekleyin.  
- **Web Portalları:** Kullanıcılara paketlenmiş belgeleri hızlı, indirme gerektirmeyen bir şekilde keşfetme imkanı sunun.  
- **İşbirliği Araçları:** Takımlara paylaşılan arşivleri doğrudan tarayıcıda inceleme olanağı verin.

## Performans Düşünceleri
- **Kaynak Yönetimi:** Bellek kullanımını izleyin; büyük toplu işlemler için JVM çöp toplayıcısını ayarlamayı düşünün.  
- **Arşivleri Toplu Dönüştürme:** Arşiv dosyalarının bir listesini döngüye alıp aynı render mantığını çağırarak verimliliği maksimize edin.  
- **Önbellekleme Stratejisi:** Aynı arşive sık erişiliyorsa render edilmiş HTML'yi bir önbellekte saklayın.

## Sıkça Sorulan Sorular
**Q:** GroupDocs.Viewer Java nedir?  
**A:** HTML, PDF ve görseller gibi formatlara belgeleri—arşivler dahil—render etmek için çok yönlü bir kütüphanedir.

**Q:** GroupDocs.Viewer'ın ücretsiz deneme sürümünü nasıl edinebilirim?  
**A:** İndirmek ve denemek için [ücretsiz deneme bağlantısı](https://releases.groupdocs.com/viewer/java/) adresini ziyaret edin.

**Q:** Arşivlerin dışında diğer belge türlerini dönüştürebilir miyim?  
**A:** Evet, görüntüleyici PDF, Word, Excel ve daha birçok formatı destekler.

**Q:** Render işlemi yavaşsa ne yapmalıyım?  
**A:** Sayfa başına öğe sayısını azaltın, akışı etkinleştirin veya arşivleri daha küçük toplu işlemlerle işleyin.

**Q:** Yardım veya destek nereden alabilirim?  
**A:** [destek forumu](https://forum.groupdocs.com/c/viewer/9) üzerinden ulaşabilirsiniz.

**Q:** CSS ve görselleri doğrudan HTML içinde gömmek mümkün mü?  
**A:** Kesinlikle—örneklerde gösterildiği gibi `HtmlViewOptions.forEmbeddedResources` kullanın.

**Q:** Bir klasördeki arşivleri toplu olarak nasıl dönüştürebilirim?  
**A:** Her dosyayı bir `for` döngüsüyle yineleyerek, her yineleme için aynı `Viewer` ve `HtmlViewOptions` yapılandırmasını uygulayın.

## Kaynaklar
- **Documentation:** İşlevselliği daha derinlemesine incelemek için [GroupDocs belgeleri](https://docs.groupdocs.com/viewer/java/) adresine bakın.  
- **API Referansı:** Tam API'yi [GroupDocs API](https://reference.groupdocs.com/viewer/java/) üzerinden keşfedin.  
- **İndirme:** En son ikili dosyaları [indirme sayfasından](https://releases.groupdocs.com/viewer/java/) alın.  
- **Satın Alma ve Lisanslama:** Seçenekleri [satın alma sayfasında](https://purchase.groupdocs.com/buy) inceleyin.  
- **Destek ve Topluluk:** [GroupDocs forumunda](https://forum.groupdocs.com/c/viewer/9) tartışmalara katılın.

---

**Son Güncelleme:** 2026-02-23  
**Test Edilen:** GroupDocs.Viewer 25.2  
**Yazar:** GroupDocs