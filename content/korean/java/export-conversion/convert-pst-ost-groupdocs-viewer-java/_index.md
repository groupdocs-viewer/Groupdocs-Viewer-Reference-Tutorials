---
date: '2026-02-15'
description: GroupDocs.Viewer for Java를 사용하여 pst를 html 및 JPG, PNG, PDF와 같은 다른 형식으로
  변환하는 방법을 배웁니다. 이 가이드는 필요한 모든 단계와 구성을 다룹니다.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: GroupDocs.Viewer for Java를 사용하여 PST를 HTML, JPG, PNG, PDF로 변환
type: docs
url: /ko/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java를 사용하여 PST를 HTML, JPG, PNG, PDF로 변환하기

Are you looking to **convert pst to html** or other formats like JPG, PNG, or PDF? With the powerful GroupDocs.Viewer for Java library, this task is straightforward and efficient. In this tutorial you’ll learn how to render Outlook PST/OST files into web‑friendly HTML, image files, or a single PDF, making your email archives easy to share and archive.

![GroupDocs.Viewer for Java를 사용한 PST/OST를 HTML, JPG, PNG, PDF로 변환](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**배우게 될 내용**
- Maven 프로젝트에서 GroupDocs.Viewer for Java를 설정하는 방법.  
- **java convert pst** 파일을 HTML, JPG, PNG, PDF로 변환하는 단계별 안내.  
- 최적의 성능을 위한 구성 팁 및 일반적인 함정.

## Quick Answers
- **PST 변환을 처리하는 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java.  
- **PST를 PDF로 직접 변환할 수 있나요?** 예, `PdfViewOptions`를 사용합니다.  
- **프로덕션에 라이선스가 필요합니까?** 유효한 GroupDocs 라이선스가 필요합니다.  
- **지원되는 Java 버전은 어느 것인가요?** JDK 8 이상.  
- **첨부 파일을 수동으로 추출해야 하나요?** 아니요, 뷰어가 자동으로 렌더링합니다.

## How to convert pst to html using GroupDocs.Viewer for Java
Below you’ll find a concise overview of the conversion process before diving into the detailed code examples.

### Why choose GroupDocs.Viewer?
- **High fidelity** rendering of email bodies, attachments, and formatting.  
- **Multiple output formats** (HTML, JPG, PNG, PDF) from a single API.  
- **No external dependencies** – everything runs inside your Java application.

## Prerequisites

- **GroupDocs.Viewer for Java** – version 25.2 or later.  
- **Java Development Kit (JDK)** – 8 or newer.  
- Maven for dependency management.  
- Basic Java knowledge and familiarity with Maven.

## Setting Up GroupDocs.Viewer for Java

Add the GroupDocs repository and dependency to your `pom.xml`:

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

### License Acquisition
- **Free trial** – explore all features without cost.  
- **Temporary license** – extend evaluation time if needed.  
- **Full license** – required for production deployments.

### Basic Initialization

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Implementation Guide

The following sections walk you through rendering PST/OST files into each supported format.

### Rendering PST/OST Documents to HTML

#### Step 1: Set Up Output Directory

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Step 2: Configure Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 3: Initialize Viewer and Render HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering PST/OST Documents to JPG

#### Step 1: Set Up Output Directory

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Step 2: Configure Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 3: Initialize Viewer and Render JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering PST/OST Documents to PNG

#### Step 1: Set Up Output Directory

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Step 2: Configure Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 3: Initialize Viewer and Render PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering PST/OST Documents to PDF

#### Step 1: Set Up Output Directory

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Step 2: Configure Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 3: Initialize Viewer and Render PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Practical Applications

- **Email Archiving:** Turn large PST archives into searchable HTML or PDF for compliance.  
- **Document Management Systems:** Store converted files in systems that only accept PDF, PNG, or JPG.  
- **Collaboration Platforms:** Share converted emails as images in Slack or Teams.  
- **Legal Review:** Provide courts with PDF versions of email evidence.  
- **Backup Strategies:** Keep lightweight PNG or JPG snapshots of critical messages.

## Performance Considerations

- **Resource Management:** Reuse `Viewer` instances when processing multiple files to reduce overhead.  
- **Memory Tuning:** Adjust `loadOptions.setResourceLoadingTimeout` based on server capacity.  
- **Asynchronous Processing:** Offload conversion to background threads for responsive UIs.  

## Frequently Asked Questions

**Q: How do I **convert pst to pdf** with the same code base?**  
A: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of the code remains identical.

**Q: Can GroupDocs.Viewer handle encrypted PST files?**  
A: Yes, provide the password via `LoadOptions.setPassword("yourPassword")` before rendering.

**Q: What is the difference between **java convert pst** to PNG vs JPG?**  
A: PNG preserves lossless quality, ideal for screenshots, while JPG offers smaller file sizes for email previews.

**Q: Is there a way to **how to convert pst** files in bulk?**  
A: Wrap the rendering logic in a loop that iterates over a directory of PST files; reuse the same `Viewer` configuration for each file.

## Conclusion

You now have a complete, production‑ready guide to **convert pst to html**, JPG, PNG, and PDF using GroupDocs.Viewer for Java. By following the steps above you can integrate email conversion into any Java‑based workflow, improve accessibility, and meet compliance requirements.

---

**마지막 업데이트:** 2026-02-15  
**테스트 환경:** GroupDocs.Viewer for Java 25.2  
**작성자:** GroupDocs