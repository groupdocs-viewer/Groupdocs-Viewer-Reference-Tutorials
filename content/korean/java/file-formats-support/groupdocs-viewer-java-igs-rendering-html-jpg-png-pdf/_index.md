---
date: '2026-08-08'
description: GroupDocs.Viewer for Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환하는 방법을 배웁니다.
  단계별 가이드, 전제 조건 및 Java 개발자를 위한 문제 해결.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: GroupDocs.Viewer for Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환합니다.
  자세한 설정, 코드 스니펫 및 Java 개발자를 위한 문제 해결.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: GroupDocs.Viewer Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: GroupDocs.Viewer Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환
type: docs
url: /ko/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# GroupDocs.Viewer Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환

Java 애플리케이션에서 직접 **IGS를 PDF**(또는 HTML, JPG, PNG)로 변환해야 한다면, 여기가 바로 정답입니다. 이 튜토리얼에서는 라이브러리 설치부터 프로젝트에 맞는 형식으로 3‑D 모델을 렌더링하는 방법까지 모든 과정을 안내합니다. GroupDocs.Viewer가 빠르고 신뢰할 수 있는 변환을 위한 견고한 선택인 이유를 이해하고, 자체 솔루션에 바로 적용할 수 있는 실행 가능한 코드 스니펫을 제공받게 됩니다.

![GroupDocs.Viewer for Java를 사용하여 IGS 파일을 HTML, JPG, PNG 및 PDF로 변환](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 빠른 답변
- **Java로 IGS를 PDF로 변환할 수 있나요?** 예, `PdfViewOptions`와 `Viewer` API를 함께 사용하십시오.  
- **지원되는 출력 형식은 무엇인가요?** HTML, JPG, PNG, 및 PDF는 모두 기본적으로 처리됩니다.  
- **프로덕션에 라이선스가 필요합니까?** 상업용 라이선스가 필요합니다; 무료 체험을 통해 핵심 기능을 테스트할 수 있습니다.  
- **필요한 Java 버전은 무엇인가요?** JDK 8 이상; 라이브러리는 Java 11, 17 및 이후 버전에서도 실행됩니다.  
- **라이브러리를 추가하는 방법이 Maven만인가요?** 아니요, Gradle를 사용하거나 JAR 파일을 수동으로 클래스패스에 추가할 수도 있습니다.

## IGS를 PDF로 변환한다는 것은 무엇인가요?
IGS를 PDF로 변환한다는 것은 중립적인 3‑D CAD 파일을 정적이며 보편적으로 볼 수 있는 문서로 바꾸는 것을 의미합니다. 이를 통해 CAD 도구가 없는 이해관계자와 디자인 시각 자료를 공유하거나, 보고서에 렌더링을 삽입하거나, 규정 준수를 위해 모델을 보관할 수 있습니다.

## IGS 변환에 GroupDocs.Viewer를 사용하는 이유는 무엇인가요?
GroupDocs.Viewer는 외부 CAD 소프트웨어 없이 IGS 파일을 처리합니다. **50개 이상의 입력 및 출력 형식**을 지원하고, **수백 개의 부품**을 포함한 어셈블리를 렌더링하면서 메모리 사용량을 **200 MB** 이하로 유지하며, 일반적인 모델을 표준 서버에서 **2 초** 미만에 결과를 제공합니다. 이러한 정량적인 이점은 엔터프라이즈 파이프라인에 고성능·비용 효율적인 선택이 됩니다.

## 필수 조건
- **GroupDocs.Viewer for Java** ≥ 25.2 (최신 안정 릴리스).  
- **JDK 8+**가 설치되고 IDE(IntelliJ IDEA, Eclipse, NetBeans 등)에서 구성되어 있어야 합니다.  
- 기본적인 Maven 지식(선택 사항이지만 의존성 관리에 권장).

## GroupDocs.Viewer for Java 설정

### Maven 의존성
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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

### 라이선스 획득
GroupDocs.Viewer offers three licensing options:
- **Free trial** – 제한된 사용량, 빠른 개념 증명 테스트에 적합합니다.  
- **Temporary license** – 짧은 평가 기간 동안 전체 기능을 제공하며 파일럿 프로젝트에 이상적입니다.  
- **Commercial license** – 무제한 프로덕션 사용이 가능하고, 우선 지원 및 업데이트가 포함됩니다.

### 기본 Viewer 초기화
The `Viewer` class is the entry point for all rendering operations. It loads the source file, parses the format, and exposes methods to produce the desired output.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## IGS를 HTML로 렌더링

### IGS를 HTML로 변환하는 방법은?
`Viewer` 인스턴스로 IGS 파일을 로드하고 모든 필요한 자산을 포함하는 `HtmlViewOptions` 객체를 전달합니다. 호출은 전체 3‑D 뷰를 포함하는 단일 HTML 파일을 반환하므로 웹 페이지에 쉽게 삽입할 수 있습니다. 페이지 크기, 배경 색상, 인터랙티브 컨트롤 포함 여부와 같은 옵션을 설정하여 렌더링을 맞춤화할 수도 있습니다.  
`HtmlViewOptions`는 리소스 임베딩 및 페이지 레이아웃을 포함한 HTML 출력 생성 방식을 구성합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## IGS를 JPG로 렌더링

### IGS를 JPG로 변환하는 방법은?
`JpgViewOptions` 객체를 생성하고 원하는 해상도와 압축 품질을 설정한 뒤 `Viewer`가 모델의 각 페이지에 대한 래스터 이미지를 생성하도록 합니다. 생성된 JPG 파일은 지정된 디렉터리에 저장할 수 있으며, 파일 크기와 시각적 품질 사이의 균형을 맞추기 위해 품질 매개변수를 조정할 수 있습니다. 이는 썸네일이나 고해상도 인쇄에 유용합니다.  
`JpgViewOptions`는 해상도, 품질 및 출력 디렉터리와 같은 JPG 이미지 생성 설정을 지정합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## IGS를 PNG로 렌더링

### IGS를 PNG로 변환하는 방법은?
`PngViewOptions` 클래스를 사용하면 선택적 투명성을 포함한 무손실 이미지를 생성할 수 있습니다. 이 형식은 마케팅 자료에서 컬러 배경 위에 모델을 오버레이하는 데 이상적입니다. 해상도와 배경 색상을 브랜드 가이드라인에 맞게 정의하여 모든 생성된 자산에서 일관된 외관을 보장할 수 있습니다.  
`PngViewOptions`는 해상도, 투명성 및 배경 색상을 포함한 PNG 렌더링 매개변수를 정의합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## IGS를 PDF로 렌더링

### IGS를 PDF로 변환하는 방법은?
`PdfViewOptions`를 사용하여 3‑D 모델의 시각적 레이아웃을 유지하는 페이지가 있는 PDF를 생성합니다. 기업 브랜드 가이드라인에 맞게 글꼴을 포함하고 페이지 크기를 제어할 수도 있습니다. 추가 설정을 통해 이미지 품질, 압축 수준 및 다중 페이지 어셈블리의 목차 포함 여부를 지정할 수 있습니다.  
`PdfViewOptions`는 페이지 크기, 이미지 품질 및 글꼴 포함 구성을 허용하여 PDF 생성을 제어합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 실제 적용 사례
- **Web portals** – HTML로 렌더링된 모델을 제품 구성기에 직접 삽입하여 고객이 플러그인을 설치하지 않고도 회전 및 확대/축소할 수 있게 합니다.  
- **Marketing assets** – 브로셔, 슬라이드덱, 소셜 미디어 게시물을 위한 고해상도 JPG/PNG 이미지를 생성합니다.  
- **Technical documentation** – 사용자 매뉴얼에 CAD 모델의 PDF 렌더링을 포함하여 엔지니어가 오프라인에서도 설계를 볼 수 있도록 합니다.  
- **Quality assurance** – 수천 개의 IGS 파일에 대한 썸네일 생성을 자동화하여 시각적 검사 워크플로를 가속화합니다.

## 일반적인 문제 및 해결책

| Issue | Solution |
|-------|----------|
| **출력 폴더를 찾을 수 없음** | `Path outputDirectory`에 전달된 경로를 확인하고 Java 프로세스가 대상 디렉터리에 대한 쓰기 권한을 가지고 있는지 확인하십시오. |
| **PDF에서 빈 페이지** | 원본 IGS 파일이 손상되지 않았는지 확인하고, 먼저 기본 CAD 뷰어에서 열어 보십시오. |
| **대형 어셈블리 렌더링이 느림** | JVM 힙을 (`-Xmx2g` 이상) 늘리고 `viewer.getPageCount()`를 사용하여 페이지별로 렌더링하는 방식을 고려하여 청크를 처리하십시오. |
| **PDF에서 글꼴 누락** | `PdfViewOptions`를 사용해 필요한 글꼴을 포함하거나, 변환 서비스를 제공하는 서버에 누락된 글꼴을 설치하십시오. |

## 자주 묻는 질문

**Q: 단일 실행에서 여러 IGS 파일을 변환할 수 있나요?**  
A: 예. 파일 경로 컬렉션을 반복하면서 동일한 `Viewer` 인스턴스 내에서 각 파일에 대해 적절한 `view` 메서드를 호출하면 됩니다.

**Q: PDF 페이지 크기를 사용자 정의할 수 있나요?**  
A: 물론입니다. `PdfViewOptions`는 `setPageSize(PageSize.A4)`, `PageSize.Letter` 및 `setCustomSize(width, height)`를 통해 사용자 정의 치수를 제공합니다.

**Q: 각 출력 형식마다 별도의 라이선스가 필요합니까?**  
A: 아닙니다. 단일 GroupDocs.Viewer 라이선스로 HTML, JPG, PNG 및 PDF를 포함한 모든 지원 형식을 커버합니다.

**Q: 성능이 저하되기 전에 IGS 파일 크기는 얼마나 커야 하나요?**  
A: 이 라이브러리는 **500 MB**까지의 파일을 안정적으로 처리합니다; 200 MB보다 큰 모델의 경우 추가 JVM 메모리를 할당하고 배치 렌더링을 고려하십시오.

**Q: 특정 뷰나 방향만 렌더링할 수 있나요?**  
A: GroupDocs.Viewer는 IGS 파일에 정의된 기본 방향을 렌더링합니다. 사용자 정의 뷰가 필요하면 CAD 도구로 파일을 사전 처리하거나 변환 전에 모델을 조정하십시오.

---

**마지막 업데이트:** 2026-08-08  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs

## 관련 튜토리얼

- [GroupDocs.Viewer Java로 cdr을 html, jpg, png, pdf로 변환](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Java에서 GroupDocs.Viewer를 사용하여 pdf를 html로 변환하고 이미지 품질을 최적화하는 방법](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)