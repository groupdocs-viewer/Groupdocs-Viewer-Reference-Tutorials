---
date: '2026-02-28'
description: GroupDocs.Viewer for Java를 사용하여 CDR 파일을 HTML, JPG, PNG 및 PDF로 변환하는 방법을
  배웁니다. 설정, 코드 예제 및 성능 팁이 포함됩니다.
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: GroupDocs.Viewer Java를 사용하여 cdr을 html, jpg, png, pdf로 변환
type: docs
url: /ko/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# GroupDocs.Viewer Java로 CDR을 HTML, JPG, PNG, PDF로 변환

CDR을 **HTML**(또는 JPG, PNG, PDF) 로 빠르고 안정적으로 변환해야 한다면, 이 튜토리얼이 바로 정답입니다. 이 가이드에서는 GroupDocs.Viewer for Java를 설치하고 CorelDRAW(CDR) 파일을 웹 친화적인 HTML 페이지, 고품질 이미지, 그리고 범용 PDF로 렌더링하는 전체 과정을 단계별로 안내합니다. 마지막까지 따라 하면 몇 줄의 코드만으로 Java 애플리케이션에 변환 기능을 통합할 수 있습니다.

![Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## Quick Answers
- **CDR을 HTML로 변환하는 라이브러리는?** GroupDocs.Viewer for Java.  
- **CDR을 JPG, PNG, PDF 로도 변환할 수 있나요?** 네—같은 Viewer API에 다른 뷰 옵션을 지정하면 됩니다.  
- **라이선스가 필요합니까?** 테스트용으로는 무료 체험판이나 임시 라이선스로 충분하지만, 운영 환경에서는 정식 라이선스가 필요합니다.  
- **필요한 Java 버전은?** JDK 8 이상.  
- **배치 변환을 지원하나요?** 물론입니다—같은 Viewer 인스턴스를 사용해 파일을 반복 처리하면 됩니다.

## “convert CDR to HTML”이란?
CDR을 HTML로 변환한다는 것은 CorelDRAW 벡터 파일을 표준 HTML 마크업으로 바꾸고, 필요에 따라 이미지와 스타일을 포함시켜 원본 디자인 소프트웨어 없이도 웹 브라우저에서 바로 볼 수 있게 하는 작업을 의미합니다.

## 왜 CDR을 HTML, JPG, PNG, PDF 로 변환해야 할까요?
- **HTML** 은 웹 포털에 그래픽을 삽입하고 즉시 공유할 수 있게 해줍니다.  
- **JPG** 와 **PNG** 는 갤러리, 썸네일, 이메일 첨부 파일 등에서 사용할 수 있는 래스터 이미지입니다.  
- **PDF** 는 인쇄 가능하고 플랫폼에 구애받지 않는 버전으로, 아카이빙이나 문서 공유 시스템에 적합합니다.  

네 가지 포맷을 모두 갖추면 대상에 맞는 파일을 제공해 성능을 최적화하고, 향후 확장성을 확보할 수 있습니다.

## Prerequisites

시작하기 전에 다음을 준비하세요:

1. **라이브러리 및 종속성** – Maven 프로젝트에 GroupDocs.Viewer를 추가합니다.  
2. **Java Development Kit (JDK)** – 버전 8 이상 설치.  
3. **기본 Java 지식** – 코드 스니펫을 이해하기 위해 필요합니다.

### Required Libraries, Versions, and Dependencies

다음 Maven 설정을 `pom.xml`에 추가하세요(원본 튜토리얼과 동일하게 유지).

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

### License Acquisition Steps

GroupDocs.Viewer는 무료 체험판, 테스트용 임시 라이선스, 정식 구매 옵션을 제공합니다:

- **Free Trial** – [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/)에서 다운로드.  
- **Temporary License** – [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/)에서 요청.  
- **Purchase** – [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy)에서 영구 라이선스 구매.

## Setting Up GroupDocs.Viewer for Java

### Installation with Maven
위의 Maven 스니펫이 모든 필요한 JAR을 자동으로 가져옵니다. 파일을 저장한 뒤 `mvn clean install`을 실행하면 됩니다.

### License Initialization
문서를 렌더링하기 전에 라이선스를 초기화하세요:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

아래에서는 각 출력 포맷별 단계별 예제를 제공합니다. 코드 블록은 원본 튜토리얼과 동일하며, 설명만 추가했습니다.

### How to convert CDR to HTML with GroupDocs.Viewer

#### Rendering CDR Document to HTML
**Overview:** CDR 파일을 웹 친화적인 HTML로 변환해 손쉽게 공유합니다.

**Step 1 – Set Up File Paths**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### How to convert CDR to JPG with GroupDocs.Viewer

#### Rendering CDR Document to JPG
**Overview:** CDR 소스에서 고품질 JPEG 이미지를 생성합니다.

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### How to convert CDR to PNG with GroupDocs.Viewer

#### Rendering CDR Document to PNG
**Overview:** 보관용 또는 디자인 작업에 적합한 무손실 PNG 이미지를 생성합니다.

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### How to convert CDR to PDF with GroupDocs.Viewer

#### Rendering CDR Document to PDF
**Overview:** CDR 파일을 범용 PDF로 변환합니다.

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Practical Applications

- **Web Portals:** HTML 변환을 활용해 CDR 디자인을 사이트에 직접 삽입합니다.  
- **Image Galleries:** JPG/PNG 출력물을 사용해 빠르게 로드되는 이미지 갤러리를 구축합니다.  
- **Document Sharing:** 인쇄 가능하고 읽기 전용인 PDF를 고객에게 제공합니다.  
- **Archiving:** 여러 포맷을 저장해 향후 접근성을 보장합니다.  
- **Cross‑Platform Integration:** 생성된 파일을 OCR, 분석 등 다른 서비스와 연계합니다.

## Performance Considerations

- **Dispose of Viewer instances** promptly (as shown with try‑with‑resources) to free memory.  
- **Batch Processing:** Loop over a collection of CDR files using the same Viewer configuration to reduce overhead.  
- **Resource Allocation:** Allocate sufficient CPU/RAM for large or complex CDR files; monitoring tools can help you fine‑tune.

## Conclusion

우리는 GroupDocs.Viewer for Java를 사용해 **CDR을 HTML**, JPG, PNG, PDF 로 변환하는 방법을 모두 살펴보았습니다. 간결한 코드 스니펫과 모범 사례를 따라 하면 어떤 Java 기반 워크플로에도 손쉽게 이 변환 기능을 통합해 사용자에게 유연하고 고품질의 결과물을 제공할 수 있습니다.

### Next Steps
- 사용자 정의 페이지 크기나 워터마크와 같은 고급 렌더링 옵션을 실험해 보세요.  
- 변환 파이프라인을 REST API와 결합해 온‑디맨드 파일 변환 서비스를 제공하세요.  
- 커뮤니티에 참여하고 [GroupDocs Forum](https://forum.groupdocs.com/c/viewer)에서 질문해 보세요.

## Frequently Asked Questions

**Q: 비밀번호로 보호된 CDR 파일을 변환할 수 있나요?**  
A: 네. 비밀번호 매개변수를 받는 `Viewer` 인스턴스로 파일을 로드하면 됩니다(API 문서 참고).

**Q: 한 번에 변환할 수 있는 페이지 수에 제한이 있나요?**  
A: 명확한 제한은 없지만, 매우 큰 파일은 메모리를 많이 사용하므로 페이지별로 처리하는 것이 좋습니다.

**Q: HTML 출력에 폰트가 포함되나요?**  
A: `HtmlViewOptions.forEmbeddedResources`를 사용하면 폰트가 Base64 형태로 포함되어 일관된 렌더링을 보장합니다.

**Q: JPEG 품질을 어떻게 제어하나요?**  
A: `JpgViewOptions`의 `setQuality(int)` 메서드로 1‑100 사이 값을 지정하면 됩니다.

**Q: Linux 서버에서도 CDR 파일을 변환할 수 있나요?**  
A: 물론입니다—JDK만 설치되어 있으면 플랫폼에 구애받지 않고 GroupDocs.Viewer를 사용할 수 있습니다.

---

**Last Updated:** 2026-02-28  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs