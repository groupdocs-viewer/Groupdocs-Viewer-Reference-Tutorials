---
"date": "2025-04-24"
"description": "GroupDocs.Viewer Java를 사용하여 Excel 파일을 HTML, JPG, PNG, PDF로 변환하는 방법을 알아보세요. 이 가이드에서는 설정, 렌더링 옵션 및 실제 활용 방법을 다룹니다."
"title": "GroupDocs.Viewer Java를 사용하여 Excel을 HTML/JPG/PNG/PDF로 변환하는 방법&#58; 단계별 가이드"
"url": "/ko/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
---

# GroupDocs.Viewer Java를 사용하여 Excel을 HTML/JPG/PNG/PDF로 변환하는 방법: 단계별 가이드

## 소개

스프레드시트 데이터를 행 및 열 머리글과 같은 중요한 세부 정보를 유지하면서 HTML, JPG, PNG 또는 PDF와 같은 다양한 형식으로 변환하는 것은 많은 경우에 필수적입니다. 보고서 생성, 이해관계자와의 정보 공유, 스프레드시트를 웹 애플리케이션에 통합 등 어떤 작업을 하든 Excel 시트 변환은 핵심적인 요구 사항이 될 수 있습니다. 이 가이드에서는 GroupDocs.Viewer Java를 사용하여 이러한 작업을 쉽고 정확하게 수행하는 방법을 안내합니다.

**배울 내용:**
- Java용 GroupDocs.Viewer 설정 및 사용
- Excel 파일을 HTML, JPG, PNG 및 PDF 형식으로 렌더링
- 출력에 행 및 열 제목을 포함하도록 옵션 구성
- 렌더링된 문서의 실제 응용 프로그램

구현에 들어가기 전에 필요한 전제 조건부터 살펴보겠습니다.

## 필수 조건

GroupDocs.Viewer Java로 스프레드시트를 렌더링하기 전에 다음 사항을 확인하세요.

### 필수 라이브러리 및 종속성

Maven을 사용하여 Java용 GroupDocs.Viewer를 설정하세요. 프로젝트에 포함하는 방법은 다음과 같습니다.

**Maven 설정:**
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

### 환경 설정
- Java Development Kit(JDK)가 설치되어 있는지 확인하세요.
- 개발의 편의성을 위해 IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하세요.

### 지식 전제 조건
- Java 프로그래밍에 대한 지식
- 종속성 관리를 위한 Maven의 기본 이해

이러한 전제 조건을 충족한 상태에서 Java용 GroupDocs.Viewer를 설정하고 기능 구현을 시작해 보겠습니다.

## Java용 GroupDocs.Viewer 설정

GroupDocs.Viewer for Java는 다양한 형식의 문서를 렌더링할 수 있는 다재다능한 라이브러리입니다. 시작하는 방법은 다음과 같습니다.

### 설치 정보
언급된 대로 Maven을 사용하여 프로젝트의 종속성으로 GroupDocs.Viewer를 추가합니다. `pom.xml` 파일.

### 라이센스 취득 단계
1. **무료 체험:** 체험판을 다운로드하세요 [GroupDocs 무료 평가판](https://releases.groupdocs.com/viewer/java/).
2. **임시 면허:** 더 많은 기능을 사용하려면 임시 라이센스를 취득하세요. [GroupDocs 임시 라이센스](https://purchase.groupdocs.com/temporary-license/).
3. **구입:** 전체 액세스 및 지원을 받으려면 라이선스를 구매하세요. [GroupDocs 구매](https://purchase.groupdocs.com/buy).

### 기본 초기화
설치가 완료되면 다음을 사용하여 GroupDocs.Viewer를 초기화할 수 있습니다.
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // 뷰어를 사용하려면 여기에 코드가 있습니다.
        }
    }
}
```
이렇게 하면 환경이 초기화되어 문서 렌더링을 위한 준비가 완료됩니다.

## 구현 가이드

각 기능을 분석하고 이를 세부적으로 구현하는 방법을 살펴보겠습니다.

### 스프레드시트를 HTML로 렌더링
**개요:** 웹 프레젠테이션이나 보고서를 위해 행과 열 제목을 보존하면서 Excel 시트를 HTML 형식으로 변환합니다.

#### 단계별 구현:
##### 1. 필요한 라이브러리 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2. 출력 디렉토리 설정
렌더링된 파일이 저장될 위치를 정의합니다.
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3. 뷰어 초기화 및 옵션 구성
GroupDocs.Viewer를 사용하여 문서를 렌더링합니다.
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // 스프레드시트에서 행과 열 머리글의 렌더링을 활성화합니다.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 1~3페이지를 렌더링합니다.
}
```
**설명:** 그만큼 `HtmlViewOptions` 클래스는 HTML 출력을 구성하는 데 사용됩니다. 설정 `setRenderHeadings(true)` 렌더링된 HTML에서 행과 열 제목이 표시되도록 합니다.

### 스프레드시트를 JPG로 렌더링
**개요:** 행과 열 머리글을 포함하여 Excel 시트를 고품질 이미지 파일(JPG)로 변환합니다. 시각적 프레젠테이션이나 인쇄물에 이상적입니다.

#### 단계별 구현:
##### 1. 필요한 라이브러리 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2. 출력 디렉토리 설정
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3. 뷰어 초기화 및 옵션 구성
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // 스프레드시트에서 행과 열 머리글의 렌더링을 활성화합니다.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 1~3페이지를 렌더링합니다.
}
```
**설명:** `JpgViewOptions` 이미지 설정을 처리합니다. `setRenderHeadings(true)` 이 옵션을 사용하면 헤더가 JPG 출력에 포함됩니다.

### 스프레드시트를 PNG로 렌더링
**개요:** 행과 열 제목을 유지하면서 Excel 시트를 PNG 형식으로 변환하여 고품질 이미지 출력에 적합합니다.

#### 단계별 구현:
##### 1. 필요한 라이브러리 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2. 출력 디렉토리 설정
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3. 뷰어 초기화 및 옵션 구성
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // 스프레드시트에서 행과 열 머리글의 렌더링을 활성화합니다.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 1~3페이지를 렌더링합니다.
}
```
**설명:** `PngViewOptions` PNG 설정에 사용됩니다. `setRenderHeadings(true)`, 헤더는 출력 이미지에 포함됩니다.

### 스프레드시트를 PDF로 렌더링
**개요:** 행과 열 제목이 표시되도록 하면서 Excel 시트를 PDF 형식으로 변환할 수 있어 문서 보관이나 공유에 적합합니다.

#### 단계별 구현:
##### 1. 필요한 라이브러리 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2. 출력 디렉토리 설정
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3. 뷰어 초기화 및 옵션 구성
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // 스프레드시트에서 행과 열 머리글의 렌더링을 활성화합니다.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 1~3페이지를 렌더링합니다.
}
```
**설명:** `PdfViewOptions` PDF 출력 설정을 구성합니다. `setRenderHeadings(true)` 이 옵션을 사용하면 최종 PDF에서 머리글이 표시됩니다.

## 실제 응용 프로그램
이러한 기능을 적용할 수 있는 실제 시나리오는 다음과 같습니다.

1. **사업 보고:** Excel 데이터를 HTML이나 PDF 형식으로 변환하여 자세한 보고서를 이해관계자와 공유하고, 손쉽게 배포하고 볼 수 있습니다.
2. **데이터 시각화:** 프레젠테이션을 위해 스프레드시트를 JPG나 PNG와 같은 이미지 포맷으로 변환하고, 헤더가 시각화된 데이터에 대한 맥락을 제공하도록 합니다.
3. **문서 보관:** PDF 변환을 사용하면 제목과 같은 모든 필수 세부 정보를 보존하면서 누구나 쉽게 접근할 수 있는 형식으로 문서를 보관할 수 있습니다.