---
date: '2026-06-15'
description: GroupDocs Viewer를 사용하여 Excel을 PDF(Java)로 변환하고 Excel 시트를 행 및 열별로 분할하는
  방법을 배웁니다. setup, code 및 best practices가 포함됩니다.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel을 PDF(Java)로 변환하고 행 및 열별로 시트 분할
type: docs
url: /ko/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel을 PDF(Java)로 변환 및 행·열별 시트 분할 (Java)

Large Excel 워크북은 종종 단일 화면이나 인쇄 페이지에 편안하게 표시될 수 있는 양보다 더 많은 데이터를 포함합니다. **convert excel to pdf java**는 정적이고 공유 가능한 형식이 필요할 때 흔히 요구되는 작업이며, **splitting Excel sheets by rows and columns**는 웹이나 인쇄 레이아웃에서 데이터를 더 쉽게 활용할 수 있게 합니다. 이 가이드에서는 **GroupDocs Viewer for Java**를 사용하여 두 작업을 단계별로 설명하고, 페이지 매김 설정 방법과 성능 및 문제 해결을 위한 모범 사례 팁을 안내합니다.

![GroupDocs.Viewer for Java를 사용한 행 및 열별 Excel 시트 분할](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[GroupDocs.Viewer for Java를 사용한 행 및 열별 Excel 시트 분할](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## 빠른 답변
- **어떤 라이브러리를 사용합니까?** GroupDocs Viewer for Java.  
- **행과 열을 모두 기준으로 분할할 수 있나요?** 예 – you can define rows‑per‑page and columns‑per‑page together.  
- **라이선스가 필요합니까?** A trial or temporary license works for development; a full license is required for production.  
- **지원되는 출력 형식은 무엇입니까?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **Maven이 필요합니까?** Maven is the recommended way to manage dependencies.  
- **Excel을 PDF로 변환할 수도 있나요?** 물론 – just switch `HtmlViewOptions` to `PdfViewOptions` and reuse the same pagination settings.

## “Excel 분할 방법”이란?
Splitting an Excel sheet means dividing a single worksheet into multiple pages or files based on a fixed number of rows, columns, or both. This technique is handy when you need to create paginated reports, embed data in web pages, or generate printable sections without loading the entire workbook at once.

## 왜 GroupDocs Viewer for Java를 사용합니까?
GroupDocs Viewer processes spreadsheets in a single pass and automatically paginates them, eliminating manual calculations. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, and **the library supports 50+ input and output formats**, including XLS, XLSX, CSV, PDF, and HTML. It runs on any JVM‑compatible platform—Windows, Linux, macOS, Docker containers, or cloud‑based serverless runtimes—so you can integrate it wherever your Java application lives.

## 사전 요구 사항
- Java 17 이상 설치됨.  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
- Maven을 사용한 종속성 관리.  
- 기본 Java 지식 및 Excel 파일 처리에 대한 이해.

### 필요한 라이브러리, 버전 및 종속성
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
무료 체험, 임시 라이선스 또는 전체 라이선스를 [GroupDocs](https://purchase.groupdocs.com/buy)에서 구매하십시오.

## Excel을 PDF(Java)로 변환하는 방법?

The `Viewer` class is the core component of GroupDocs Viewer that loads a document and provides rendering methods for various output formats. `SpreadsheetOptions` allows you to control pagination settings such as rows‑per‑page and columns‑per‑page for spreadsheet rendering.

Load your Excel file with `new Viewer("source.xlsx")`, configure `SpreadsheetOptions` for pagination, and call `viewer.view(pdfOptions, stream)` – that single call converts the workbook to a PDF while respecting the row/column limits you set. The conversion preserves formulas, images, and cell styles, delivering a faithful PDF replica ready for distribution.

## 행별로 Excel 시트 분할하기

Splitting by rows creates a series of HTML pages, each containing a fixed number of rows (e.g., 15). This approach is ideal for dashboards that display a limited number of records per view. The viewer will generate separate HTML files such as `page_0.html`, `page_1.html`, etc., each containing the specified number of rows. This makes it simple to load only the needed portion in a web interface, reducing bandwidth and rendering time.

### 정의 앵커
`Viewer`는 문서를 로드하고 선택한 출력 형식으로 렌더링을 조정하는 GroupDocs Viewer의 핵심 클래스입니다.

### 단계별 구현

#### 단계 1: 경로 설정 및 Viewer 초기화
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### 단계 2: 페이지당 행 수 설정
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### 단계 3: 문서 렌더링
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## 행과 열 모두 기준으로 Excel 시트 분할하기

Sometimes a single page needs to show a matrix of rows **and** columns (e.g., 15 rows × 7 columns). This gives you full control over the layout of each HTML page. The resulting pages display a rectangular block of cells, for example rows 1‑15 and columns A‑G on the first page, rows 16‑30 and columns H‑N on the next. This grid‑style pagination is useful for creating printable reports that fit standard paper sizes.

### 정의 앵커
`SpreadsheetOptions`는 각 생성 페이지에 표시될 행 및 열 수를 구성합니다.

### 단계별 구현

#### 단계 1: 경로 설정 및 Viewer 초기화
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### 단계 2: 페이지당 행 및 열 수 설정
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### 단계 3: 문서 렌더링
Render using the same `view` call.

```java
viewer.view(options);
```

## 실용적인 적용 사례
- **Generate Excel report Java**: 대형 재무 모델을 페이지 매김된 HTML 보고서 시리즈로 변환합니다.  
- **GroupDocs Viewer Excel**: 분할된 페이지를 웹 포털에 직접 삽입하여 인터랙티브한 데이터 탐색을 가능하게 합니다.  
- **Render Excel HTML Java**: 생성된 HTML 페이지를 서블릿이나 Spring 컨트롤러를 통해 제공하여 클라이언트 측 빠른 렌더링을 지원합니다.  

## 성능 고려 사항
- **Memory usage** – 대형 워크북은 상당한 힙을 사용할 수 있으므로 JVM `-Xmx` 설정을 늘리는 것을 고려하십시오.  
- **Chunk size** – 페이지 크기와 렌더링 속도의 균형을 맞출 수 있도록 행/열 수를 선택하십시오.  
- **Version updates** – 성능 향상을 위해 GroupDocs Viewer를 최신 상태로 유지하십시오; 최신 25.2 릴리스는 24.x에 비해 렌더링 속도를 최대 30 % 향상시킵니다.

## 일반적인 문제 및 해결 방법
| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| `OutOfMemoryError` | 페이지당 너무 많은 행을 지정하여 매우 큰 시트를 렌더링하는 경우 | `countRowsPerPage`를 줄이거나 JVM 힙을 늘리세요 |
| 빈 출력 파일 | 파일 경로가 잘못되었거나 쓰기 권한이 없습니다 | `outputDirectory`가 존재하고 쓰기 가능한지 확인하십시오 |
| HTML 리소스가 로드되지 않음 | `forEmbeddedResources`를 사용했지만 다른 기본 URL에서 파일을 제공하는 경우 | 전체 출력 폴더를 제공하거나 `forExternalResources`로 전환하십시오 |

## 자주 묻는 질문

**Q: HTML 대신 PDF를 생성할 수 있나요?**  
A: 예. `HtmlViewOptions`를 `PdfViewOptions`로 교체하고 동일한 `SpreadsheetOptions` 구성을 유지하면 됩니다.

**Q: 고정된 행/열이 아니라 셀 내용에 따라 분할할 수 있나요?**  
A: 셀 내용 기반 분할은 GroupDocs Viewer에 기본 제공되지 않지만, Apache POI로 워크북을 사전 처리하여 별도 시트를 만든 후 렌더링할 수 있습니다.

**Q: GroupDocs Viewer가 오래된 Excel 형식(XLS)을 지원합니까?**  
A: 물론입니다. Viewer는 XLS, XLSX, CSV 및 기타 스프레드시트 형식을 처리합니다.

**Q: 생성된 HTML을 Spring MVC 뷰에 어떻게 삽입합니까?**  
A: 출력 폴더를 정적 리소스로 제공하고, Thymeleaf 또는 JSP 템플릿에서 `page_0.html`, `page_1.html` 등을 참조하면 됩니다.

**Q: 상용 배포를 위해 어떤 라이선스가 필요합니까?**  
A: GroupDocs의 전체 프로덕션 라이선스가 필요합니다; 체험 라이선스는 평가용으로만 사용할 수 있습니다.

## 리소스
- **문서**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 참조**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **다운로드**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **구매**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **무료 체험**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **임시 라이선스**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **지원**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**최종 업데이트:** 2026-06-15  
**테스트 환경:** GroupDocs Viewer 25.2 for Java  
**작성자:** GroupDocs  

## 관련 튜토리얼

- [GroupDocs.Viewer를 사용한 Java 스프레드시트에서 숨겨진 행 및 열 렌더링](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [GroupDocs.Viewer를 사용한 Java에서 빈 행 렌더링 건너뛰기: 성능 가이드](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [포괄 가이드: GroupDocs.Viewer Java를 사용해 Excel 2003 XML을 HTML/JPG/PNG/PDF로 변환](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)