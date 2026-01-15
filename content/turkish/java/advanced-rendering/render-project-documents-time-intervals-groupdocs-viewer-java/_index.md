---
date: '2026-01-15'
description: GroupDocs Viewer'ı kullanarak proje belgelerinden belirli zaman aralıklarında
  HTML oluşturmayı öğrenin. Bu rehber kurulum, kod ve gerçek dünya kullanım örneklerini
  kapsar.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Java'da GroupDocs Viewer ile Proje Belgelerini Zaman Aralıklarına Göre Görüntüleme
type: docs
url: /tr/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer'ı Kullanarak Java'da Zaman Aralıklarıyla Proje Belgelerini Görüntüleme

Eğer **GroupDocs'ı nasıl kullanacağınızı** odaklanmış bir zaman penceresinde proje takvimlerini görüntülemek için arıyorsanız, doğru yerdesiniz. Bu öğreticide, Maven kurulumundan proje belgelerinden HTML üretimine kadar tüm süreci adım adım anlatacağız; böylece kesin zaman çizelgesi görünümlerini doğrudan uygulamalarınıza yerleştirebileceksiniz.

![GroupDocs.Viewer for Java ile Zaman Aralıklarıyla Proje Belgelerini Görüntüleme](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Hızlı Yanıtlar
- **Bu özellik ne yapar?** Microsoft Project dosyasının yalnızca başlangıç ve bitiş tarihleri arasındaki kısmını görüntüler.  
- **Hangi çıktı formatı kullanılır?** Web entegrasyonu için mükemmel, gömülü kaynaklarla HTML.  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme yeterlidir; üretim için tam lisans gerekir.  
- **Tarih aralığını çalışma zamanında değiştirebilir miyim?** Evet—render seçeneklerinde `setStartDate` ve `setEndDate` değerlerini ayarlayın.  
- **Tüm Java sürümlerinde destekleniyor mu?** Java 8+ ile, GroupDocs.Viewer 25.2 veya daha yeni bir sürüm kullanıldıkça çalışır.

## Bu Bağlamda “GroupDocs'ı Nasıl Kullanılır” Ne Anlama Geliyor?
GroupDocs Viewer, 100'den fazla dosya formatını web‑dostu temsillere dönüştüren bir Java kütüphanesidir. Proje dosyaları için **GroupDocs'ı nasıl kullanacağınızı** öğrenerek, Microsoft Project'e ihtiyaç duymadan takvim verilerini çıkarabilir, görselleştirebilir ve paylaşabilirsiniz.

## Neden Proje Belgelerini Zaman Aralıklarıyla Görüntülemek?
- **Odaklanmış analiz:** İlgilendiğiniz aşamayı (ör. 2024 Q3) sadece gösterin.  
- **Performans:** Daha küçük HTML çıktısı, sayfa yüklemelerinin daha hızlı olmasını sağlar.  
- **Entegrasyon:** Zaman çizelgesi görünümlerini panolara, raporlama portallarına veya özel PM araçlarına yerleştirin.  

## Önkoşullar

- **GroupDocs.Viewer for Java** sürüm 25.2 veya üzeri.  
- Java Development Kit (JDK) 8 veya daha yeni bir sürüm.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Temel Maven bilgisi.  

## GroupDocs.Viewer for Java'ı Kurma

### Maven Bağımlılığı

`pom.xml` dosyanıza depo ve bağımlılığı ekleyin:

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

1. **Ücretsiz Deneme** – [GroupDocs indirme sayfasından](https://releases.groupdocs.com/viewer/java/) deneme sürümünü indirin.  
2. **Geçici Lisans** – [bu linkten](https://purchase.groupdocs.com/temporary-license/) uzatılmış test için geçici bir lisans alın.  
3. **Satın Alma** – Sınırsız üretim kullanımı için lisansı [GroupDocs Satın Alma Sayfası](https://purchase.groupdocs.com/buy) üzerinden satın alın.  

### Temel Viewer Başlatma

Aşağıdaki kod parçacığı, bir Microsoft Project dosyasına (`.mpp`) işaret eden bir `Viewer` örneği oluşturmayı gösterir:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Adım‑Adım Uygulama Kılavuzu

### 1. Çıktı Dizini Tanımlama

Oluşturulan HTML sayfalarının kaydedileceği bir klasör oluşturun:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Why?* Render edilen dosyaların düzenli tutulması, bir web sunucusundan hizmet vermeyi veya bir UI içinde gömmeyi kolaylaştırır.

### 2. Viewer'ı Proje Dosyanızla Başlatma

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Why?* Belgeyi yüklemek, iç parser'ı hazırlar ve proje‑özel meta verilerine erişim sağlar.

### 3. Proje Dosyaları İçin Görünüm Bilgilerini Alın

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Why?* `ProjectManagementViewInfo`, takvimin başlangıç ve bitiş tarihlerini verir; bu tarihleri daha sonra render kapsamını sınırlamak için kullanacaksınız.

### 4. HTML Görüntüleme Seçeneklerini Yapılandırma (Projeden HTML Oluşturma)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Why?* `StartDate` ve `EndDate` ayarları, GroupDocs'a **projeden HTML** oluşturmasını yalnızca bu pencere içinde yapmasını söyler.

### 5. Görüntüleme İşlemini Çalıştırma

```java
viewer.view(viewOptions);
```

*Why?* Bu çağrı, proje takviminizin seçilen zaman dilimini temsil eden, kendi içinde bağımsız HTML sayfaları üretir.

## Yaygın Tuzaklar ve Sorun Giderme
- **Yanlış dosya yolları** – Hem kaynak `.mpp` dosyasının hem de çıktı dizininin mevcut olduğundan emin olun.  
- **Desteklenmeyen dosya türü** – Belgenin desteklenen bir Project formatı (ör. `.mpp`, `.mpt`) olduğundan emin olun.  
- **Lisans hataları** – Deneme lisansı render sınırlamaları getirebilir; sınırsız kullanım için tam lisansa geçin.  

## Pratik Uygulamalar
1. **Proje Zaman Çizelgesi Analizi** – Paydaşlara yalnızca mevcut aşamayı gösterin.  
2. **Otomatik Raporlama** – Haftalık durum güncellemeleri için zaman‑sınırlı HTML raporları oluşturun.  
3. **Panolarla Entegrasyon** – Render edilen sayfaları BI araçlarına veya özel portalara yerleştirin.  
4. **Arşivleme** – Proje takviminin web‑dostu bir anlık görüntüsünü gelecekte referans almak üzere saklayın.  

## Performans İpuçları
- Her HTML sayfasını kendi içinde bağımsız tutan *gömülü kaynaklar* seçeneğini kullanarak HTTP isteklerini azaltın.  
- Çok büyük projeler için, bellek kullanımını düşük tutmak amacıyla daha küçük tarih dilimlerinde render etmeyi düşünün.  
- Sunulduktan sonra geçici dosyaları temizleyerek disk şişmesini önleyin.  

## Sonuç

Artık **GroupDocs'ı nasıl kullanacağınızı** biliyorsunuz; Java'da belirli bir zaman aralığında proje belgelerini render edip **projeden HTML** oluşturabilirsiniz. Bu yetenek, zaman çizelgesi görselleştirmelerini basitleştirir, raporlama verimliliğini artırır ve modern web uygulamalarıyla sorunsuz entegrasyon sağlar.

### Sonraki Adımlar
- Filigran ekleme, şifre koruması veya özel CSS stillendirme gibi ek Viewer özelliklerini keşfedin.  
- Bu render hattını bir REST API ile birleştirerek isteğe bağlı zaman çizelgesi görünümleri sunun.  

## Sıkça Sorulan Sorular

**S: GroupDocs.Viewer hangi dosya formatlarını destekliyor?**  
C: GroupDocs.Viewer, Microsoft Project (MPP), PDF, Word, Excel, PowerPoint ve daha birçok format dahil olmak üzere geniş bir format yelpazesini destekler.

**S: GroupDocs.Viewer'ın ücretsiz denemesine nasıl başlayabilirim?**  
C: Deneme sürümünü [buradan](https://releases.groupdocs.com/viewer/java/) indirebilirsiniz.

**S: Belgeleri kaynakları gömmeden render edebilir miyim?**  
C: Evet, dış kaynaklara referans veren farklı bir HTML görüntüleme seçeneğini tercih edebilirsiniz.

**S: Belgem render için çok büyükse ne yapmalıyım?**  
C: Belgeyi daha küçük bölümlere ayırmayı veya yukarıda gösterildiği gibi yalnızca gerekli tarih aralığını render etmeyi düşünün.

**S: Render hatalarını nasıl ele alırım?**  
C: Tüm yapılandırma ayarlarını doğrulayın, geçerli bir lisansınız olduğundan emin olun ve ayrıntılı hata kodları için GroupDocs belgelerine bakın.

## Kaynaklar
- **Dokümantasyon**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Referansı**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **İndirme**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Satın Alma**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Ücretsiz Deneme**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Geçici Lisans**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Destek**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-15  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs