---
"date": "2025-04-24"
"description": "Belge oluşturma sürecinizi geliştirmek için konsol ve dosya tabanlı günlük kaydı dahil olmak üzere GroupDocs.Viewer for Java ile günlük kaydının nasıl ayarlanacağını öğrenin."
"title": "GroupDocs.Viewer for Java&#58;da Günlük Kaydını Yapılandırma&#58; Konsol ve Dosya Günlük Kaydı Kılavuzu"
"url": "/tr/java/getting-started/groupdocs-viewer-java-logging-setup/"
"weight": 1
type: docs
---
# Java için GroupDocs.Viewer'da Günlük Kaydını Yapılandırma

## giriiş
Java uygulamalarında belge oluşturma sürecinizi geliştirin **Java için GroupDocs.Viewer**Bu eğitim, günlük kaydının konsola veya bir dosyaya yapılandırılması konusunda size rehberlik ederek, belge oluşturma işleminizin nasıl çalıştığına dair önemli bilgiler sağlar.

**Önemli Öğrenme Noktaları:**
- Java için GroupDocs.Viewer'da günlük kaydını yapılandırın.
- Hem konsol hem de dosya tabanlı günlükleme sistemlerini uygulayın.
- GroupDocs.Viewer kullanarak belgeleri gömülü kaynaklarla HTML'ye dönüştürün.

Ortamımızı kurmaya başlamadan önce ön koşulları gözden geçirelim.

## Ön koşullar
Şunlara sahip olduğunuzdan emin olun:
1. **Gerekli Kütüphaneler:**
   - GroupDocs.Viewer for Java kütüphanesi (sürüm 25.2 veya üzeri).

2. **Çevre Kurulum Gereksinimleri:**
   - Sisteminizde yüklü bir Java Geliştirme Kiti (JDK).
   - IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE).

3. **Bilgi Ön Koşulları:**
   - Java programlamanın temel bilgisi.
   - Bağımlılık yönetimi için Maven'a aşinalık.

Bu ön koşullar sağlandığında, Java için GroupDocs.Viewer'ı kurmaya hazırsınız!

## Java için GroupDocs.Viewer Kurulumu
GroupDocs.Viewer'ı kullanmak için Maven kullanarak projenize bir bağımlılık olarak ekleyin. İşte nasıl:

### Maven Kurulumu
Aşağıdaki yapılandırmayı ekleyin `pom.xml` dosya:
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

### Lisans Edinimi
- **Ücretsiz Deneme:** Ücretsiz deneme sürümünü indirin [GroupDocs Sürümleri](https://releases.groupdocs.com/viewer/java/).
- **Geçici Lisans:** Değerlendirme sınırlamalarını kaldırmak için geçici bir lisans edinin [GroupDocs Geçici Lisansı](https://purchase.groupdocs.com/temporary-license/).
- **Satın almak:** Tam erişim için, şu adresten bir lisans satın almayı düşünün: [GroupDocs Satın Alma](https://purchase.groupdocs.com/buy).

### Temel Başlatma
GroupDocs.Viewer'ı aşağıdaki desenle başlatın:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Örnek PDF dosyası ve ayarlarıyla başlatın
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

Bu kurulum, daha karmaşık günlük kaydı yapılandırmalarının temelini oluşturur.

## Uygulama Kılavuzu
GroupDocs.Viewer ile konsol ve dosya tabanlı günlük kaydının nasıl uygulanacağını keşfedin.

### Özellik 1: Konsola Kayıt
#### Genel bakış
Konsola giriş yapmak, geliştirme veya hata ayıklama aşamalarında kullanışlı olacak şekilde terminalinize anında geri bildirim sağlar.

#### Adımlar:
##### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### Adım 2: Günlük Kaydı Yapılandırmasını Ayarlayın
Kullanmak `ConsoleLogger` günlükleri konsola yönlendirmek için.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
##### Açıklama
- **KonsolKaydedici:** Bu sınıf günlükleri konsola yönlendirerek işlemlerin gerçek zamanlı görünümünü sağlar.
- **HtmlViewOptions.forEmbeddedResources:** Her sayfa için gömülü kaynaklara sahip HTML üretir.

#### Sorun Giderme İpuçları
Belge yolunuzun doğru ve erişilebilir olduğundan emin olun. Günlük ifadelerinin konsol ayarlarınızda uygun şekilde yapılandırıldığını doğrulayın.

### Özellik 2: Dosyaya Kayıt
#### Genel bakış
Bir dosyaya kayıt tutmak, işlemlerin kalıcı bir kaydının tutulmasına yardımcı olur ve denetim veya ölüm sonrası analiz için faydalıdır.

#### Adımlar:
##### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### Adım 2: Dosya Tabanlı Günlük Kaydı Yapılandırmasını Ayarlayın
Kullanmak `FileLogger` günlükleri belirtilen bir dosyaya yazmak için.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
##### Açıklama
- **Dosya Kaydedici:** Bu sınıf günlükleri adlı bir dosyaya yönlendirir `output.log`.
- **FileLogger ile ViewerSettings:** GroupDocs.Viewer'ı belirtilen günlük dosyasındaki etkinlikleri günlüğe kaydedecek şekilde yapılandırır.

#### Sorun Giderme İpuçları
Çıktı dosyası için dizinin yazılabilir olduğundan emin olun. Günlüğe kaydetme başarısız olursa dosya izinlerini kontrol edin.

## Pratik Uygulamalar
GroupDocs.Viewer belge yönetimi ve işleme yeteneklerini geliştirebilir:
1. **Web Portalları:** Doğrudan indirmeye gerek kalmadan, belgeleri anında web kullanıcıları için oluşturun.
2. **Kurumsal Sistemler:** Sözleşmeleri veya anlaşmaları görüntülemek için CRM araçlarıyla entegre edin.
3. **Dahili Gösterge Panoları:** İntranetlerdeki rapor ve sunumların erişilebilir görünümlerini sağlayın.

## Performans Hususları
Java'da GroupDocs.Viewer kullanırken şunları göz önünde bulundurun:
- **Kaynak Kullanımını Optimize Edin:** Büyük belgeler işlenirken bellek tüketimini izleyin.
- **Java Bellek Yönetimi En İyi Uygulamaları:** Otomatik kaynak yönetimi için try-with-resources'ı kullanın.
- **Performans Ayarı:** Ayrıntı ve performans etkisini dengelemek için günlük kaydı ayrıntı düzeyini ayarlayın.

## Çözüm
GroupDocs.Viewer Java'yı belge işleme etkinliklerini konsola veya bir dosyaya kaydedecek şekilde nasıl yapılandıracağınızı öğrendiniz. Bu yetenek, uygulamalarınızı hata ayıklamak, izlemek ve denetlemek için paha biçilmezdir. Daha fazla yapılandırmayı keşfedin ve GroupDocs.Viewer'ı projelerinizdeki kullanımını artırmak için diğer sistemlerle entegre edin.

Uygulama becerilerinizi bir üst seviyeye taşımaya hazır mısınız? Farklı ortamlarda günlük kaydı kurmayı deneyin ve uygulamanızın sağlamlığını nasıl artırdığını gözlemleyin!

## SSS Bölümü
1. **GroupDocs.Viewer Java ile büyük belgeleri yönetmenin en iyi yolu nedir?**
   - Verimli bellek yönetimi uygulamalarını kullanın ve tüm belgeleri işlemek yerine belirli sayfaları işlemeyi düşünün.
2. **Konsol ve dosya çıktılarının ötesinde ek bilgileri günlüğe kaydedebilir miyim?**
   - Evet, veritabanları veya izleme araçları gibi diğer sistemlerle entegre olabilen özel günlük kaydı sınıflarını uygulayarak günlük kaydı işlevselliğini genişletin.
3. **Günlüklerimin güvenli olduğundan nasıl emin olabilirim?**
   - Günlük dosyalarını güvenli dizinlerde saklayın ve yetkisiz erişimi önlemek için uygun erişim kontrollerini uygulayın.
4. **FileLogger kullanırken log formatını değiştirmek mümkün müdür?**
   - Evet, günlük kaydı davranışınızı genişleterek özelleştirin `FileLogger` sınıfını ve gerektiğinde yöntemlerini geçersiz kılma.
5. **GroupDocs.Viewer PDF olmayan belgeleri işleyebilir mi?**
   - Kesinlikle! GroupDocs.Viewer Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere çeşitli belge biçimlerini destekler.

## Kaynaklar
- [Belgeleme](https://docs.groupdocs.com/viewer/java/)
- [API Referansı](https://reference.groupdocs.com/viewer/java/)
- [İndirmek](https://downloads.groupdocs.com/viewer/java/)