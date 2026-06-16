---
date: '2026-03-29'
description: Java'da GroupDocs Viewer kullanarak HTML görünümü mpp oluşturmayı, proje
  belgelerini zaman aralıklarıyla adım adım kodla render etmeyi öğrenin.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: GroupDocs Viewer (Java) ile mpp HTML görünümü oluştur
type: docs
url: /tr/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer'ı Kullanarak Java'da Proje Belgelerini Zaman Aralıklarıyla Görüntüleme

Bu öğreticide, GroupDocs Viewer for Java ile **create html view mpp** oluşturmayı öğrenecek ve belirli bir zaman aralığına düşen Microsoft Project dosyasının yalnızca ilgili bölümlerini nasıl görüntüleyeceğinizi göreceksiniz. Maven kurulumu, kod yapılandırması ve gerçek dünya senaryolarını adım adım inceleyecek, böylece uygulamalarınıza kesin zaman çizelgesi görünümleri yerleştirebileceksiniz.

![GroupDocs.Viewer for Java ile Zaman Aralıklarına Göre Proje Belgelerini Görüntüleme](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Hızlı Yanıtlar
- **What does the feature do?** It renders only the portion of a Microsoft Project file that falls between a start and end date.  
- **Which output format is used?** HTML with embedded resources, perfect for web integration.  
- **Do I need a license?** A free trial works for evaluation; a full license is required for production.  
- **Can I change the date range at runtime?** Yes—adjust the `setStartDate` and `setEndDate` values in the rendering options.  
- **Is this supported on all Java versions?** Works with Java 8+ as long as you use GroupDocs.Viewer 25.2 or newer.

## Proje Belgeleri için html view mpp oluşturma
GroupDocs Viewer, Microsoft Project dosyalarını (`.mpp`, `.mpt`) HTML sayfalarına dönüştürebilir. Rendering seçeneklerinde başlangıç ve bitiş tarihlerini yapılandırarak çıktıyı ihtiyacınız olan zaman dilimiyle sınırlarsınız; bu da dosya boyutunu azaltır ve sayfa yüklemelerini hızlandırır.

## Bu Bağlamda “GroupDocs Nasıl Kullanılır” Nedir?
GroupDocs Viewer, 100'den fazla dosya formatını web‑uyumlu temsillere dönüştüren bir Java kütüphanesidir. Proje dosyaları için **how to use GroupDocs** yaptığınızda, Microsoft Project'e ihtiyaç duymadan takvim verilerini çıkarma, görselleştirme ve paylaşma yeteneği kazanırsınız.

## Neden Proje Belgelerini Zaman Aralıklarıyla Görüntüleyelim?
- **Focused analysis:** Show only the phase you care about (e.g., Q3 2024).  
- **Performance:** Smaller HTML output means faster page loads.  
- **Integration:** Embed timeline views into dashboards, reporting portals, or custom PM tools.  

## Önkoşullar
- **GroupDocs.Viewer for Java** version 25.2 or higher.  
- Java Development Kit (JDK) 8 or newer.  
- An IDE such as IntelliJ IDEA or Eclipse.  
- Basic Maven knowledge.  

## GroupDocs.Viewer for Java'ı Kurma

### Maven Bağımlılığı

Add the repository and dependency to your `pom.xml`:

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

1. **Free Trial** – Download a trial version from [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Obtain a temporary license for extended testing via [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – For unrestricted production use, buy a license at [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Temel Viewer Başlatma

The following snippet shows how to create a `Viewer` instance that points to a Microsoft Project file (`.mpp`):

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

### 1. Çıktı Dizinini Tanımlayın

Create a folder where the generated HTML pages will be saved:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Why?* Keeping rendered files organized makes it easier to serve them from a web server or embed them in a UI.

### 2. Viewer'ı Proje Dosyanızla Başlatın

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Why?* Loading the document prepares the internal parser and makes project‑specific metadata accessible.

### 3. Proje Dosyaları için Görünüm Bilgilerini Alın

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Why?* `ProjectManagementViewInfo` gives you the schedule’s start and end dates, which you’ll later use to limit the rendering scope.

### 4. HTML Rendering Seçeneklerini Yapılandırın (Projeden HTML Oluşturun)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Why?* Setting `StartDate` and `EndDate` tells GroupDocs to **generate html view mpp** data only within that window.

### 5. Rendering İşlemini Gerçekleştirin

```java
viewer.view(viewOptions);
```

*Why?* This call produces a series of self‑contained HTML pages that represent the selected time slice of your project schedule.

## Yaygın Tuzaklar ve Sorun Giderme
- **Incorrect file paths** – Double‑check that both the source `.mpp` file and the output directory exist.  
- **Unsupported file type** – Ensure the document is a supported Project format (e.g., `.mpp`, `.mpt`).  
- **License errors** – A trial license may impose rendering limits; switch to a full license for unrestricted use.  

## Pratik Uygulamalar
1. **Project Timeline Analysis** – Show stakeholders only the current phase.  
2. **Automated Reporting** – Generate time‑bound HTML reports for weekly status updates.  
3. **Integration with Dashboards** – Embed the rendered pages into BI tools or custom portals.  
4. **Archival** – Store a web‑friendly snapshot of a project’s schedule for future reference.  

## Performans İpuçları
- Use the *embedded resources* option to keep each HTML page self‑contained, reducing HTTP requests.  
- For very large projects, consider rendering in smaller date chunks to keep memory usage low.  
- Clean up temporary files after serving them to avoid disk bloat.  

## Sonuç
You now know **how to use GroupDocs** Viewer to render project documents within a specific time interval and **generate HTML from project** data in Java. This capability streamlines timeline visualizations, improves reporting efficiency, and integrates smoothly with modern web applications.

### Sonraki Adımlar
- Explore additional Viewer features such as watermarking, password protection, or custom CSS styling.  
- Combine this rendering pipeline with a REST API to serve on‑demand timeline views.  

## Sıkça Sorulan Sorular

**Q: What file formats does GroupDocs.Viewer support?**  
A: GroupDocs.Viewer supports a wide range of formats including Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, and many more.

**Q: How do I get started with a free trial of GroupDocs.Viewer?**  
A: You can download the trial version from [here](https://releases.groupdocs.com/viewer/java/).

**Q: Can I render documents without embedding resources?**  
A: Yes, you can choose a different HTML view option that references external resources instead of embedding them.

**Q: What if my document is too large for rendering?**  
A: Consider splitting the document into smaller sections or rendering only the required date range, as demonstrated above.

**Q: How do I handle rendering errors?**  
A: Verify all configuration settings, ensure you have a valid license, and consult the GroupDocs documentation for detailed error codes.

## Kaynaklar
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-03-29  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

---