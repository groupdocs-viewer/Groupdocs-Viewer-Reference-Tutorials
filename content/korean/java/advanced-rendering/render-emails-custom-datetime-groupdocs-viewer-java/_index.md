---
date: '2026-03-24'
description: GroupDocs.Viewer를 사용하여 Java에서 사용자 정의 날짜·시간 형식과 시간대 오프셋을 설정해 EML을 HTML로
  변환하는 방법을 배워보세요. 이메일 아카이빙 및 지원 시스템에 이상적입니다.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Java와 GroupDocs.Viewer를 사용하여 사용자 정의 날짜/시간으로 EML을 HTML로 변환
type: docs
url: /ko/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Java에서 GroupDocs.Viewer를 사용하여 사용자 정의 DateTime으로 EML을 HTML로 변환

오늘날 빠르게 변화하는 디지털 환경에서 **EML을 HTML로 변환**하고 올바른 날짜‑시간 표시를 적용하는 것은 아카이빙, 지원 포털 및 법적 준수를 위해 필수적입니다. 이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 이메일 메시지를 HTML로 렌더링하면서 **사용자 정의 datetime 형식**과 **시간대 오프셋**을 적용하는 방법을 단계별로 안내합니다. 끝까지 따라오시면 타임스탬프를 정확하고 읽기 쉽게 유지하는 재사용 가능한 솔루션을 얻을 수 있으며, 모든 **email to HTML Java** 워크플로에 완벽히 맞습니다.

![GroupDocs.Viewer for Java를 사용한 사용자 정의 DateTime으로 이메일 렌더링](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**배우게 될 내용**
- Java 프로젝트에 GroupDocs.Viewer를 설정하는 방법  
- 이메일을 HTML로 렌더링하고 리소스를 포함하는 방법  
- 이메일 메시지의 **날짜‑시간 형식**을 사용자 정의하는 방법 (custom datetime java)  
- 정확한 타임스탬프를 위해 **시간대 오프셋**을 설정하는 방법 (timezone offset java)  

## Quick Answers
- **GroupDocs.Viewer가 EML을 HTML로 변환할 수 있나요?** 예, EML 파일을 직접 HTML로 렌더링합니다.  
- **라이선스가 필요합니까?** 무료 체험판으로 테스트할 수 있으며, 프로덕션 환경에서는 유료 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상.  
- **표시되는 날짜 형식을 어떻게 변경하나요?** `options.getEmailOptions().setDateTimeFormat(...)`를 사용합니다.  
- **시간대를 조정할 수 있나요?** 예, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`를 사용합니다.

## “EML을 HTML로 변환”이란?
EML 파일을 HTML로 변환하면 원시 이메일(헤더, 본문, 첨부 파일 포함)을 브라우저가 추가 플러그인 없이 표시할 수 있는 웹 친화적인 형식으로 바꿉니다. 이를 통해 웹 애플리케이션, 아카이브 또는 지원 대시보드에 이메일을 쉽게 삽입할 수 있습니다.

## 이 작업에 GroupDocs.Viewer를 사용하는 이유
- **Zero‑dependency 렌더링** – Outlook이나 외부 메일 파서가 필요 없습니다.  
- **임베디드 리소스 지원** (이미지, 첨부 파일) 내장.  
- **날짜‑시간 형식 및 시간대 처리**에 대한 세밀한 제어 가능.  

## Prerequisites

- **GroupDocs.Viewer for Java** 버전 25.2 이상.  
- **Java Development Kit (JDK)** 8+ 및 IDE (IntelliJ IDEA, Eclipse 등).  
- 기본 Java 지식 및 Maven 사용 경험.

## Setting Up GroupDocs.Viewer for Java

### Maven Configuration
Add the GroupDocs repository and dependency to your `pom.xml`:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### License Acquisition
Start with a free trial or request a temporary license for extended testing. Purchase a full license for production use.

### Basic Initialization
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Convert EML to HTML with Custom DateTime in Java

The following step‑by‑step guide shows how to **convert EML to HTML** while applying a custom datetime format and timezone offset.

### Step 1: Set Up Output Directory and File Path
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Explanation:* `Path.of()` creates a reference to the folder where the HTML will be saved. `resolve()` appends the file name.

### Step 2: Initialize Viewer with Email File
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Explanation:* The `Viewer` instance points to the EML file you want to convert.

### Step 3: Configure HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Explanation:* `forEmbeddedResources()` bundles images and other resources directly into the HTML output.

### Step 4: Set Custom DateTime Format *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Explanation:* This pattern displays the month, day, year, hour, minute, AM/PM marker, and the timezone offset (`zzz`).

### Step 5: Set TimeZone Offset *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Explanation:* Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"` with any valid zone identifier.

### How to Adjust Email Timezone in Java
If you need to **adjust email timezone** beyond simple offsets—such as handling daylight‑saving changes—you can retrieve the appropriate `TimeZone` object from the `java.util.TimeZone` API using region IDs like `"Europe/Paris"` or `"America/New_York"` and pass it to `setTimeZoneOffset`. This ensures the email timestamps always reflect the correct local time.

### Step 6: Render Document
```java
viewer.view(options);
```
*Explanation:* Executes the conversion, producing an HTML file with your custom date‑time settings.

## Troubleshooting Tips
- **FileNotFoundException:** Double‑check the paths used in `Viewer` and `Path.of()`.  
- **Incorrect timestamps:** Verify that the `TimeZone` ID matches your target region.  
- **Missing images:** Ensure you used `HtmlViewOptions.forEmbeddedResources()`; otherwise, external resources may not be included.  

## Practical Applications
1. **Email Archiving:** Store searchable HTML snapshots of emails for compliance.  
2. **Customer Support Portals:** Show incoming tickets with accurate local times.  
3. **Legal Documentation:** Produce court‑ready email records with standardized timestamps.  

## Performance Considerations
- Deploy on a dedicated server for bulk conversions.  
- Monitor Java heap usage; increase `-Xmx` if you encounter `OutOfMemoryError`.  
- Cache rendered HTML when the same email is requested repeatedly.  

## Conclusion
You now have a complete, production‑ready method to **convert EML to HTML** with a custom datetime format and timezone offset using GroupDocs.Viewer for Java. This enhances readability, ensures timestamp accuracy, and fits seamlessly into archiving or support workflows.

**Next Steps:** Explore additional Viewer options such as CSS styling, pagination, or PDF conversion to further tailor the output to your needs.

## Frequently Asked Questions

**Q: How do I handle EML files with attachments?**  
A: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`. You can also extract them via the Viewer API if needed.

**Q: Can I change the HTML template or add custom CSS?**  
A: Yes, after rendering you can edit the generated HTML file or inject CSS programmatically before saving.

**Q: Is it possible to render multiple EML files in a batch?**  
A: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions` instance for each file.

**Q: What if I need to support other email formats like MSG?**  
A: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply change the file extension in the `Viewer` constructor.

**Q: Do I need a separate license for each server?**  
A: Licensing is per deployment; consult the GroupDocs licensing guide for multi‑server scenarios.

## Resources

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-03-24  
**Tested With:** GroupDocs.Viewer 25.2 (Java)  
**Author:** GroupDocs