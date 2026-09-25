---
date: '2026-09-25'
description: GroupDocs Viewer for Java ile html view mpp oluşturmayı öğrenin, proje
  belgelerini zaman aralıklarıyla adım adım kod kullanarak render edin.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: GroupDocs Viewer for Java ile html view mpp oluşturarak Microsoft
  Project dosyalarını belirli zaman aralıklarıyla render edin. Kesin zaman çizelgesi
  görselleştirmesi için adım adım kurulum, lisanslama ve kod parçacıklarını izleyin.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: GroupDocs Viewer for Java ile html view mpp oluşturun
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: GroupDocs Viewer (Java) ile html view mpp oluşturun
type: docs
url: /tr/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer'ı Java'da zaman aralıklarıyla proje belgelerini render etmek için nasıl kullanılır

Bu öğreticide, GroupDocs Viewer for Java ile **create html view mpp** nasıl oluşturulacağını öğrenecek, belirli bir başlangıç ve bitiş tarih aralığına düşen Microsoft Project dosyasının yalnızca belirli bölümlerini render etmenizi sağlayacaksınız. Maven kurulumu, lisanslama ve uygulamalarınıza doğrudan kesin zaman çizelgesi görünümleri yerleştirmeniz için gereken tam API çağrılarını adım adım inceleyeceğiz.

![Zaman Aralıklarıyla Proje Belgelerini Render Etme - GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Ön izleme için, [Zaman Aralıklarıyla Proje Belgelerini Render Etme - GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png) adresine bakın.

## Hızlı Yanıtlar
- **Bu özellik ne yapar?** Başlangıç ve bitiş tarihleri arasında kalan Microsoft Project dosyasının yalnızca o kısmını render eder.  
- **Hangi çıktı formatı kullanılır?** Gömülü kaynaklarla HTML, web entegrasyonu için mükemmeldir.  
- **Lisans gerekir mi?** Değerlendirme için ücretsiz deneme çalışır; üretim için tam lisans gereklidir.  
- **Tarih aralığını çalışma zamanında değiştirebilir miyim?** Evet—render seçeneklerinde `setStartDate` ve `setEndDate` değerlerini ayarlayın.  
- **Bu tüm Java sürümlerinde destekleniyor mu?** GroupDocs.Viewer 25.2 veya daha yenisini kullandığınız sürece Java 8+ ile çalışır.

## create html view mpp nedir?
`create html view mpp`, bir Microsoft Project dosyasını (`.mpp` veya `.mpt`) zaman çizelgesini temsil eden bir dizi HTML sayfasına dönüştürme sürecidir. GroupDocs Viewer dönüşümü sunucu tarafında gerçekleştirir, böylece Microsoft Project yüklemeden zaman çizelgesini herhangi bir tarayıcıda görüntüleyebilirsiniz.

## Neden proje belgelerini zaman aralıklarıyla render edelim?
Yalnızca gerekli zaman aralığını render etmek, oluşturulan HTML'in boyutunu azaltır, sayfa yüklemesini hızlandırır ve analiz etmeniz gereken belirli proje aşamasına odaklanmanızı sağlar. Bu hedeflenmiş görünüm, gösterge panoları, durum raporları veya tam proje verilerinin bunaltıcı olacağı özelleştirilmiş PM araçlarına gömme için idealdir.

## Önkoşullar
- **GroupDocs.Viewer for Java** sürüm 25.2 ve üzeri.  
- Java Development Kit (JDK) 8 ve üzeri.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Temel Maven bilgisi.  

## GroupDocs.Viewer for Java Kurulumu

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

### Lisans edinme adımları
1. **Ücretsiz deneme** – [GroupDocs indirme sayfasından](https://releases.groupdocs.com/viewer/java/) bir deneme sürümü indirin.  
2. **Geçici lisans** – Uzatılmış test için [geçici‑lisans sayfası](https://purchase.groupdocs.com/temporary-license/) üzerinden geçici bir lisans edinin.  
3. **Satın Alma** – Sınırsız üretim kullanımı için [GroupDocs Satın Alma Sayfası](https://purchase.groupdocs.com/buy) üzerinden bir lisans satın alın.

## Temel görüntüleyici başlatma

`Viewer`, GroupDocs.Viewer for Java'da bir belgeyi yükleyen ve render yetenekleri sağlayan ana sınıftır.

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

## Proje dosyaları için görünüm bilgilerini alın

`ProjectManagementViewInfo`, bir Microsoft Project dosyasının genel zaman çizelgesi başlangıç ve bitiş tarihleri dahil olmak üzere meta verilerini sağlar.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## HTML render seçeneklerini yapılandırma (projeden HTML oluşturma)

`HtmlViewOptions`, GroupDocs'un HTML'yi nasıl render edeceğini yapılandırır; tarih aralığını ayarlamanıza, kaynakları gömmeye ve görünümü özelleştirmenize olanak tanır.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Render sürecini çalıştırma

`viewer.render`, sağlanan seçeneklere göre dönüşümü gerçekleştirir ve ortaya çıkan HTML dosyalarını hedef klasöre yazar.

```java
viewer.view(viewOptions);
```

## Yaygın tuzaklar ve sorun giderme
- **Yanlış dosya yolları** – Kaynak `.mpp` dosyasının ve çıktı dizininin mevcut olduğundan emin olun.  
- **Desteklenmeyen dosya türü** – Belgenin desteklenen bir Project formatı (örn., `.mpp`, `.mpt`) olduğundan emin olun.  
- **Lisans hataları** – Deneme lisansı render sınırlamaları getirebilir; sınırsız kullanım için tam lisansa geçin.  

## Pratik uygulamalar
1. **Proje zaman çizelgesi analizi** – Paydaşlara yalnızca mevcut aşamayı gösterin.  
2. **Otomatik raporlama** – Haftalık durum güncellemeleri için zaman sınırlı HTML raporları oluşturun.  
3. **Gösterge panelleriyle entegrasyon** – Render edilen sayfaları BI araçlarına veya özelleştirilmiş portallara gömün.  
4. **Arşivleme** – Projenin zaman çizelgesinin web‑dostu bir anlık görüntüsünü gelecekte referans için saklayın.  

## Performans ipuçları
- *Gömülü kaynaklar* seçeneğini kullanarak her HTML sayfasını kendi içinde tutun, HTTP isteklerini azaltın.  
- Çok büyük projeler için, bellek kullanımını düşük tutmak amacıyla daha küçük tarih dilimlerinde render etmeyi düşünün. Bir yıllık dilimi render etmek, tam proje dışa aktarımına göre HTML boyutunu %80'e kadar küçültebilir ve tipik sunucularda yükleme süresini birkaç saniyeden bir saniyenin altına indirebilir.  
- Disk şişmesini önlemek için dosyaları hizmet ettikten sonra geçici dosyaları temizleyin.  

## Sonuç
Artık **GroupDocs** Viewer'ı belirli bir zaman aralığında proje belgelerini render etmek ve Java'da **projeden HTML üretmek** için nasıl kullanacağınızı biliyorsunuz. Bu yetenek, zaman çizelgesi görselleştirmelerini basitleştirir, raporlama verimliliğini artırır ve modern web uygulamalarıyla sorunsuz bir şekilde bütünleşir.

### Sonraki adımlar
- Su işareti ekleme, şifre koruması veya özel CSS stil gibi ek Viewer özelliklerini keşfedin.  
- Bu render pipeline'ını bir REST API ile birleştirerek isteğe bağlı zaman çizelgesi görünümleri sunun.  

## Sıkça Sorulan Sorular
**Q: GroupDocs.Viewer hangi dosya formatlarını destekliyor?**  
**A:** GroupDocs.Viewer, PDF, DOCX, XLSX, PPTX ve Microsoft Project dosyaları dahil olmak üzere 100'den fazla giriş formatını destekler, evrensel belge görselleştirmesini sağlar.

**Q: GroupDocs.Viewer'ın ücretsiz denemesine nasıl başlayabilirim?**  
**A:** Deneme sürümünü [GroupDocs Viewer Java indirme sayfasından](https://releases.groupdocs.com/viewer/java/) indirebilirsiniz.

**Q: Belgeleri kaynakları gömmeden render edebilir miyim?**  
**A:** Evet, gömmek yerine harici kaynaklara referans veren farklı bir HTML görünüm seçeneği seçebilirsiniz.

**Q: Belgem render için çok büyük olursa ne yapmalıyım?**  
**A:** Belgeyi daha küçük bölümlere ayırmayı veya yukarıda gösterildiği gibi yalnızca gerekli tarih aralığını render etmeyi düşünün.

**Q: Render hatalarını nasıl ele alırım?**  
**A:** Tüm yapılandırma ayarlarını doğrulayın, geçerli bir lisansa sahip olduğunuzdan emin olun ve ayrıntılı hata kodları için GroupDocs belgelerine başvurun.

## Kaynaklar
- **Dokümantasyon**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API referansı**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **İndirme**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Satın Alma**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Ücretsiz deneme**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Geçici lisans**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Destek**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Son Güncelleme:** 2026-09-25  
**Test Edilen Versiyon:** GroupDocs.Viewer 25.2 for Java  
**Yazar:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## İlgili Öğreticiler
- [GroupDocs.Viewer for Java Kullanarak Notlarla MS Project Dosyalarını HTML, JPG, PNG ve PDF Olarak Nasıl Render Edilir](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [MS Project HTML Dışa Aktarma: GroupDocs Java ile Zaman Birimlerini Ayarlama](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Groupdocs Viewer Java Duyarlı Html Renderleme](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)