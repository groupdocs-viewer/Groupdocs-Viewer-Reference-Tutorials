---
date: '2026-04-10'
description: GroupDocs.Viewer for Java'da günlük kaydını nasıl yapılandıracağınızı,
  daha iyi belge render'ı için konsol günlüğü ve dosya günlüğü eklemeyi öğrenin.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: GroupDocs.Viewer for Java'da Günlük Kaydı Nasıl Yapılandırılır
type: docs
url: /tr/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# GroupDocs.Viewer for Java'da Günlük Kaydı Yapılandırma

Bu öğreticide, GroupDocs.Viewer for Java'da **günlük kaydını nasıl yapılandıracağınızı** öğrenecek, bu da belge renderleme hattına gerçek zamanlı bir bakış sağlar ve sorunları hızlı bir şekilde çözmenize yardımcı olur.

## Hızlı Yanıtlar
- **Günlük kaydı ne sağlar?** Renderleme işlemleri ve hata detayları hakkında gerçek zamanlı geri bildirim.  
- **Hangi logger konsola yazdırır?** `ConsoleLogger` (konsol logger'ı ekleyin).  
- **Hangi logger bir dosyaya yazar?** `FileLogger` (dosya logger'ı ekleyin).  
- **Günlük kaydını etkinleştirmek için lisansa ihtiyacım var mı?** Hayır, günlük kaydı deneme ve lisanslı sürümlerde de çalışır.  
- **Günlük formatını özelleştirebilir miyim?** Evet, logger sınıflarını genişleterek.

## Giriş
Java uygulamalarında belge renderleme sürecinizi **GroupDocs.Viewer for Java** kullanarak geliştirin. Bu kılavuz, günlük kaydını konsola veya bir dosyaya yapılandırmanızı adım adım gösterir ve belge renderlemenizin nasıl çalıştığına dair kritik içgörüler sunar.

![GroupDocs.Viewer for Java ile Konsol ve Dosya Günlük Kaydı](/viewer/getting-started/console-and-file-logging-java.png)

**Ana Öğrenme Noktaları:**
- GroupDocs.Viewer for Java'da günlük kaydını yapılandırma.  
- Hem konsol hem de dosya tabanlı günlük sistemlerini uygulama.  
- GroupDocs.Viewer kullanarak gömülü kaynaklarla HTML'ye belge renderleme.

## Önkoşullar
Ensure you have:

1. **Gerekli Kütüphaneler:**  
   - GroupDocs.Viewer for Java kütüphanesi (sürüm 25.2 veya daha yeni).  

2. **Ortam Kurulum Gereksinimleri:**  
   - Sisteminizde yüklü bir Java Development Kit (JDK).  
   - IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE).  

3. **Bilgi Önkoşulları:**  
   - Java programlamaya temel bir anlayış.  
   - Bağımlılık yönetimi için Maven'e aşinalık.

Bu önkoşulları tamamladıktan sonra, GroupDocs.Viewer for Java'ı kurmaya hazırsınız!

## GroupDocs.Viewer for Java'ı Kurma
GroupDocs.Viewer'ı kullanmak için, Maven aracılığıyla projenize bir bağımlılık olarak ekleyin. İşte nasıl yapılacağı:

### Maven Kurulumu
Add the following configuration in your `pom.xml` file:
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
- **Ücretsiz Deneme:** [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) adresinden ücretsiz deneme indirin.  
- **Geçici Lisans:** Değerlendirme sınırlamalarını kaldırmak için [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) adresinden geçici lisans edinin.  
- **Satın Alma:** Tam erişim için [GroupDocs Purchase](https://purchase.groupdocs.com/buy) adresinden lisans satın almayı düşünün.

### Temel Başlatma
Initialize GroupDocs.Viewer with the following pattern:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

Bu kurulum, daha karmaşık günlük yapılandırmaları için temeli oluşturur.

## Günlük Kaydını Nasıl Yapılandırılır
GroupDocs.Viewer ile **konsol logger'ı eklemeyi** ve **dosya logger'ı eklemeyi** keşfedin.

### Özellik 1: Konsola Günlük Kaydı
#### Genel Bakış
Konsola günlük kaydı, terminalinizde anlık geri bildirim sağlar; geliştirme veya hata ayıklama aşamalarında faydalıdır.

#### Adımlar
##### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Adım 2: Günlük Yapılandırmasını Ayarlayın
ConsoleLogger'ı kullanarak günlükleri konsola yönlendirin.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Açıklama**  
- **ConsoleLogger:** Bu sınıf günlükleri konsola yönlendirir ve işlemlerin gerçek zamanlı görünümünü sağlar.  
- **HtmlViewOptions.forEmbeddedResources:** Her sayfa için gömülü kaynaklarla HTML üretir; **html view options**'ı etkili bir şekilde kullanmanın bir örneğidir.

#### Sorun Giderme İpuçları
Belge yolunuzun doğru ve erişilebilir olduğundan emin olun. Günlük ifadelerinin konsol ayarlarınızda uygun şekilde yapılandırıldığını doğrulayın.

### Özellik 2: Dosyaya Günlük Kaydı
#### Genel Bakış
Dosyaya günlük kaydı, işlemlerin kalıcı bir kaydını tutmaya yardımcı olur; denetim veya ölüm sonrası analiz için faydalıdır.

#### Adımlar
##### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Adım 2: Dosya Tabanlı Günlük Yapılandırmasını Ayarlayın
`FileLogger`'ı kullanarak günlükleri belirli bir dosyaya yazın.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Açıklama**  
- **FileLogger:** Bu sınıf günlükleri `output.log` adlı bir dosyaya yönlendirir.  
- **ViewerSettings with FileLogger:** GroupDocs.Viewer'ı belirtilen günlük dosyasında **viewer loglarını yakalamak** için yapılandırır.

#### Sorun Giderme İpuçları
Çıktı dosyası için dizinin yazılabilir olduğundan emin olun. Günlük kaydı başarısız olursa dosya izinlerini kontrol edin.

## Pratik Uygulamalar
GroupDocs.Viewer, belge yönetimi ve renderleme yeteneklerini artırabilir:

1. **Web Portalları:** Web kullanıcıları için doğrudan indirme yapmadan belgeleri anında renderleyin.  
2. **Kurumsal Sistemler:** Sözleşme veya anlaşmaları göstermek için CRM araçlarıyla entegre edin.  
3. **İç Panolar:** Raporların ve sunumların intranet içinde erişilebilir görünümlerini sağlayın.

## Performans Düşünceleri ve Java Günlük Kaydı En İyi Uygulamaları
Java'da GroupDocs.Viewer kullanırken şu noktalara dikkat edin:

- **Kaynak Kullanımını Optimize Edin:** Büyük belgeleri renderlerken bellek tüketimini izleyin.  
- **Java Bellek Yönetimi:** Otomatik kaynak temizliği için try‑with‑resources kullanın.  
- **Günlük Ayrıntısı:** Detay ve performans etkisini dengelemek için logger seviyelerini (ör. INFO, DEBUG) ayarlayın—bu, **java logging best practices**'in temel bir parçasıdır.

## Sonuç
GroupDocs.Viewer for Java'da **günlük kaydını nasıl yapılandıracağınızı** öğrendiniz; hızlı bir konsol görünümü ya da kalıcı bir dosya kaydı ihtiyacınız olsun. Bu yetenek, uygulamalarınızı hata ayıklama, izleme ve denetleme açısından çok değerlidir. Daha fazla yapılandırmayı keşfedin, özel logger'larla deney yapın ve GroupDocs.Viewer'ı diğer sistemlerle entegre ederek dayanıklılığı artırın.

Uygulama becerilerinizi bir sonraki seviyeye taşımaya hazır mısınız? Farklı ortamlarda günlük kaydı kurmayı deneyin ve bunun uygulamanızın güvenilirliğini nasıl artırdığını gözlemleyin!

## Kaynaklar
- [Dokümantasyon](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [İndirme](https://downloads.groupdocs.com/viewer/java/)

---

**Son Güncelleme:** 2026-04-10  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs