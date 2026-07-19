---
date: '2026-07-19'
description: GroupDocs Viewer for Java를 사용하여 WMZ를 PDF, HTML, JPG 및 PNG로 변환하는 방법을 배웁니다.
  java convert vector graphics에 대한 단계별 가이드.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: GroupDocs Viewer for Java를 사용하여 WMZ를 PDF, HTML, JPG 및 PNG로 변환합니다.
  이 튜토리얼은 고충실도로 step‑by‑step java convert vector graphics를 보여줍니다.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: GroupDocs Viewer for Java와 함께 WMZ를 PDF로 변환 – Quick Guide
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: GroupDocs Viewer for Java를 사용하여 WMZ를 PDF 및 기타 형식으로 변환
type: docs
url: /ko/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Java를 사용하여 WMZ를 PDF 및 기타 형식으로 변환

WMZ(Web Metafile) 및 WMF(Windows Metafile) 파일을 보다 접근하기 쉬운 형식—특히 **convert WMZ to PDF**—으로 변환하는 것은 이러한 벡터 그래픽 형식이 픽셀 데이터가 아니라 그리기 명령을 저장하기 때문에 까다로울 수 있습니다. **GroupDocs Viewer for Java**를 사용하면 몇 줄의 코드만으로 WMZ/WMF 문서를 HTML, JPG, PNG, **PDF** 및 기타 인기 형식으로 렌더링하면서 원본 시각적 충실도를 유지할 수 있습니다.

![GroupDocs.Viewer for Java를 사용한 WMZ/WMF 문서 변환](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[GroupDocs.Viewer for Java를 사용한 WMZ/WMF 문서 변환](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## 빠른 답변
- **WMZ/WMF를 어떤 형식으로 변환할 수 있나요?** HTML, JPG, PNG 및 PDF가 완전히 지원됩니다.  
- **개발에 라이선스가 필요합니까?** 무료 체험판으로 테스트가 가능하며, 상업용 라이선스로 평가 제한을 해제할 수 있습니다.  
- **필요한 Java 버전은 무엇인가요?** Java 8 이상을 권장합니다.  
- **특정 페이지만 렌더링할 수 있나요?** 예, 보기 옵션에서 페이지 범위를 지정할 수 있습니다.  
- **대용량 파일에서 메모리 사용이 문제인가요?** try‑with‑resources를 사용하고 필요한 페이지만 렌더링하여 메모리 사용량을 낮게 유지하세요.

## “convert WMZ to PDF”란 무엇인가요?
**Convert WMZ to PDF**는 WMZ 벡터 파일을 가져와 그리기 명령을 PDF 컨테이너에 삽입하여 보편적으로 볼 수 있고, 검색 가능하며, 인쇄 가능한 문서를 만드는 것을 의미합니다. 변환은 선 품질과 형태를 보존하므로 결과 PDF는 어떤 장치에서도 원본 그래픽과 동일하게 보입니다.

## 벡터 그래픽 변환에 GroupDocs Viewer for Java를 사용하는 이유는?
GroupDocs Viewer for Java는 **고충실도**로 WMZ 및 WMF 렌더링을 처리하여 PDF, PNG 또는 HTML로 출력하더라도 벡터 세부 정보를 보존합니다. 이 라이브러리는 JDK가 설치된 모든 플랫폼에서 실행되며, 네이티브 Windows 구성 요소가 필요 없고, 단일 호출 API를 제공하여 단일 아이콘 파일부터 다중 페이지 기술 도면까지 확장됩니다. 벤치마크 테스트에서 표준 4코어 서버에서 **200페이지가 넘는 WMZ 파일을 12초 미만**에 처리했습니다.

## 전제 조건

- **GroupDocs.Viewer for Java** – 핵심 렌더링 엔진.  
- Java Development Kit (JDK) 8 또는 최신 버전.  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(선택 사항이지만 권장).  
- 의존성 관리를 위한 Maven(또는 Gradle).

Java NIO(`java.nio.file.Path`)와 기본 파일 I/O에 익숙하면 예제를 원활히 따라갈 수 있습니다.

## GroupDocs.Viewer for Java 설정

`Viewer` 클래스는 모든 렌더링 작업의 진입점입니다. 이는 여러 변환에 걸쳐 재사용할 수 있는 스레드 안전 엔진을 나타냅니다.

`pom.xml`(또는 Gradle 등가 파일)에 리포지토리와 의존성을 추가하세요. Maven이 아티팩트를 해결한 후, 각 변환 단계에서 재사용할 `Viewer` 인스턴스를 생성할 수 있습니다.

> **라이선스 팁:** 평가를 위해 무료 체험판을 사용하고, 전체 기능을 사용하려면 임시 또는 구매한 라이선스를 적용하세요.

## 구현 가이드

아래에서는 HTML, JPG, PNG 및 PDF 네 가지 변환 시나리오를 단계별로 살펴봅니다. 각 시나리오는 동일한 3단계 패턴을 따릅니다:

1. **렌더링된 파일이 저장될 출력 디렉터리**를 정의합니다.  
2. 소스 WMZ/WMF 파일을 가리키는 **`Viewer` 인스턴스**를 생성합니다.  
3. **형식별 보기 옵션**을 구성하고 `view` 메서드를 호출합니다.

`view` 메서드는 제공된 옵션을 기반으로 렌더링을 수행합니다.

### WMZ/WMF를 HTML로 렌더링

#### 개요
HTML 출력은 그래픽을 웹 페이지에 직접 삽입할 수 있게 하며, 모든 리소스(이미지, CSS)가 단일 파일에 포함됩니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Step 2: Viewer 초기화 및 HTML로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF를 JPG로 렌더링

#### 개요
JPG는 널리 지원되는 래스터 형식으로, 빠른 미리보기나 이메일 첨부에 적합합니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Step 2: Viewer 초기화 및 JPG로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF를 PNG로 렌더링

#### 개요
PNG는 투명성을 지원하여 다양한 배경과 혼합해야 하는 그래픽에 이상적입니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Step 2: Viewer 초기화 및 PNG로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF를 PDF로 렌더링

#### 개요
PDF는 플랫폼에 독립적이며 검색 가능한 문서를 제공하고 원본 레이아웃을 유지합니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Step 2: Viewer 초기화 및 PDF로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## 일반적인 문제 및 해결책

`PageStreamViewOptions`는 특정 페이지를 스트림으로 렌더링할 수 있게 합니다.  
`PdfViewOptions`는 페이지 범위 및 DPI와 같은 PDF 출력 설정을 구성합니다.  
`FontSettings`를 사용하면 소스 문서가 누락된 글꼴을 참조할 때 사용자 정의 글꼴을 제공할 수 있습니다.

| 문제 | 원인 | 해결책 |
|-------|-------|----------|
| **OutOfMemoryError** 대용량 WMZ 파일 | Viewer가 전체 문서를 메모리에 로드함 | `PageStreamViewOptions`를 사용해 페이지당 하나씩 렌더링하거나 JVM 힙(`-Xmx`)을 늘리세요. |
| **Missing fonts** PDF에서 누락된 글꼴 | 소스 WMZ에 글꼴이 포함되지 않음 | 필요한 글꼴을 호스트 머신에 설치하거나 `FontSettings`를 사용해 사용자 정의 글꼴을 제공하세요. |
| **Blank PNG output** 빈 PNG 출력 | 잘못된 출력 경로나 쓰기 권한 부족 | `outputDirectory`가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하세요. |
| **HTML resources not loading** HTML 리소스 로드 실패 | `forExternalResources`를 사용했지만 파일을 복사하지 않음 | 자체 포함형 HTML 파일을 위해 `forEmbeddedResources`를 사용하세요. |

## 자주 묻는 질문

**Q: 동일한 코드를 사용해 WMF를 PNG로 변환할 수 있나요?**  
A: 예. PNG 예제는 WMZ와 WMF 파일 모두에 적용되며, `TestFiles.SAMPLE_WMZ`를 WMF 소스로 교체하면 됩니다.

**Q: 페이지의 일부만 변환할 수 있나요?**  
A: 물론입니다. `PdfViewOptions`(또는 다른 형식에 해당하는 옵션)를 사용하고 렌더링 전에 `setPageNumbers(List<Integer>)`를 호출하세요.

**Q: 각 출력 형식마다 별도의 라이선스가 필요합니까?**  
A: 아닙니다. 단일 GroupDocs Viewer 라이선스로 HTML, JPG, PNG, PDF 등 모든 지원 형식을 포함합니다.

**Q: “java convert vector graphics”가 성능에 어떤 영향을 미치나요?**  
A: 벡터‑래스터 변환은 CPU 집약적입니다. 대량 배치의 경우 멀티스레딩을 고려하고 파일마다 단일 `Viewer` 인스턴스를 재사용하세요.

**Q: PDF가 벡터 품질을 유지하나요, 아니면 래스터화되나요?**  
A: WMZ/WMF를 PDF로 변환할 때 GroupDocs Viewer는 가능한 경우 벡터 명령을 보존하여 확장 가능한 PDF를 생성합니다.

## 결론

이제 **GroupDocs Viewer for Java**를 사용하여 **convert WMZ to PDF** 및 기타 일반 형식으로 변환하는 완전하고 프로덕션 준비된 가이드를 보유하게 되었습니다. 실시간으로 그래픽을 제공하는 웹 서비스든, 문서를 PDF로 저장하는 아카이브 도구든, 위 단계들을 통해 빠르고 안정적으로 구현할 수 있습니다. 프로젝트 요구에 맞게 페이지 범위, DPI 설정 또는 워터마킹을 맞춤화하려면 API를 더 탐색해 보세요.

---

**마지막 업데이트:** 2026-07-19  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs

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

## 관련 튜토리얼

- [Java에서 GroupDocs.Viewer를 사용해 OBJ를 HTML, JPG, PNG 및 PDF로 변환하는 방법](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [GroupDocs.Viewer Java를 사용해 IGS를 PDF, HTML, JPG 및 PNG로 변환](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: 문서를 PDF로 변환 – 완전 가이드](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)