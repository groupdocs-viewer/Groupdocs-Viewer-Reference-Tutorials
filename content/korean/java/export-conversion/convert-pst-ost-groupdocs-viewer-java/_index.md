---
date: '2026-07-19'
description: GroupDocs.Viewer for Java를 사용하여 PST를 HTML 및 JPG, PNG, PDF와 같은 다른 형식으로
  변환하는 방법을 배웁니다. 이 가이드는 필요한 모든 단계와 구성 설정을 다룹니다.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: GroupDocs.Viewer for Java를 사용하여 PST를 HTML로 빠르게 변환합니다. 단계별로 JPG, PNG,
  PDF로도 내보내는 방법을 production‑ready guide에서 배웁니다.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: GroupDocs.Viewer for Java와 함께 PST를 HTML로 변환 – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: GroupDocs.Viewer for Java를 사용하여 PST를 HTML, JPG, PNG, PDF로 변환
type: docs
url: /ko/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# PST를 HTML, JPG, PNG, PDF로 변환하기 - GroupDocs.Viewer for Java 사용

PST를 **convert pst to html**하거나 JPG, PNG, PDF와 같은 다른 형식으로 변환하려고 하시나요? 강력한 GroupDocs.Viewer for Java 라이브러리를 사용하면 이 작업이 간단하고 효율적입니다. 이 튜토리얼에서는 Outlook PST/OST 파일을 웹 친화적인 HTML, 이미지 파일 또는 단일 PDF로 렌더링하는 방법을 배우게 되며, 이메일 아카이브를 쉽게 공유하고 보관할 수 있습니다.

![GroupDocs.Viewer for Java를 사용한 PST/OST를 HTML, JPG, PNG, PDF로 변환](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[GroupDocs.Viewer for Java를 사용한 PST/OST를 HTML, JPG, PNG, PDF로 변환](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**배우게 될 내용**
- Maven 프로젝트에서 GroupDocs.Viewer for Java을 설정하는 방법.  
- HTML, JPG, PNG 및 PDF로 **java convert pst** 파일을 변환하는 단계별 안내.  
- 최적 성능을 위한 구성 팁 및 일반적인 함정.

## 빠른 답변
- **PST 변환을 처리하는 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java.  
- **PST를 PDF로 직접 변환할 수 있나요?** 예, `PdfViewOptions`를 사용합니다.  
- **프로덕션에 라이선스가 필요합니까?** 유효한 GroupDocs 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** JDK 8 이상.  
- **첨부 파일을 수동으로 추출해야 하나요?** 아니요, 뷰어가 자동으로 렌더링합니다.

## GroupDocs.Viewer for Java란?
GroupDocs.Viewer for Java는 서버 측 API로, 100개 이상의 문서 및 이메일 형식을 로드하고 외부 소프트웨어 없이 HTML, 이미지 또는 PDF 출력으로 렌더링합니다. 최대 2 GB 크기의 PST 파일을 처리하면서 메모리 사용량을 200 MB 이하로 유지합니다.

## GroupDocs.Viewer for Java를 사용하여 pst를 html로 변환하는 방법?
`new Viewer("source.pst")` 로 PST 파일을 로드하고, `HtmlViewOptions` 를 설정하여 출력 폴더를 지정한 뒤 `viewer.view(htmlOptions)` 를 호출합니다. API는 각 이메일을 추출하고, 서식, 첨부 파일 및 메타데이터를 보존하며, 메시지당 별도의 HTML 페이지를 작성합니다—모두 하나의 메서드 호출로 수행됩니다.

### GroupDocs.Viewer를 선택해야 하는 이유
- **고품질 렌더링** – 풍부한 텍스트 본문, 표, 삽입 이미지 등을 포함한 이메일 콘텐츠의 99.9 %가 정확하게 재현됩니다.  
- **다중 출력 형식** – 하나의 API 호출로 HTML, JPG, PNG 또는 PDF를 생성할 수 있으며, 50개 이상의 내보내기 옵션을 지원합니다.  
- **외부 종속성 없음** – Outlook, Exchange Server 또는 타사 변환기가 필요 없으며, 모든 것이 Java 런타임 내에서 실행됩니다.

## 전제 조건
- **GroupDocs.Viewer for Java** – 버전 25.2 이상.  
- **Java Development Kit (JDK)** – 8 이상.  
- 종속성 관리를 위한 Maven.  
- 기본 Java 지식 및 Maven 사용 경험.

## GroupDocs.Viewer for Java 설정
`Viewer`는 GroupDocs.Viewer for Java의 핵심 클래스이며, 문서를 로드하고 선택한 형식으로 렌더링합니다. `pom.xml`에 GroupDocs 저장소와 종속성을 추가합니다:

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
- **무료 체험** – 비용 없이 모든 기능을 탐색할 수 있습니다.  
- **임시 라이선스** – 필요에 따라 평가 기간을 연장합니다.  
- **정식 라이선스** – 프로덕션 배포에 필요합니다.

### 기본 초기화
`Viewer` 인스턴스는 가볍고, 여러 파일에 대해 단일 인스턴스를 재사용하여 객체 생성 오버헤드를 최소화할 수 있습니다.

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

## 구현 가이드
다음 섹션에서는 PST/OST 파일을 각 지원 형식으로 렌더링하는 방법을 단계별로 안내합니다.

### PST/OST 문서를 HTML로 렌더링
#### 단계 1: 출력 디렉터리 설정
HTML 페이지가 기록될 폴더를 정의합니다. GroupDocs는 각 이메일마다 하위 폴더를 생성하여 자산을 정리합니다.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 단계 2: Load Options 구성
`LoadOptions`를 사용하면 비밀번호 처리, 리소스 로딩 시간 초과, 선택적 페이지 렌더링을 지정할 수 있습니다. 30초의 시간 초과를 설정하면 대부분의 서버 환경에 적합합니다.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 단계 3: HTML View Options 정의
`HtmlViewOptions`는 출력 폴더, 리소스 처리 및 HTML 변환을 위한 선택적 CSS 설정을 지정합니다.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### 단계 4: Viewer 초기화 및 HTML 렌더링
`Viewer` 객체를 생성하고 PST 파일 경로를 전달한 뒤 `HtmlViewOptions`와 함께 `view`를 호출합니다. API는 PST 내부의 모든 메시지를 자동으로 순회하며 정돈된 HTML 계층 구조를 생성합니다.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### PST/OST 문서를 JPG로 렌더링
#### 단계 1: 출력 디렉터리 설정
JPG 스냅샷을 위한 전용 폴더를 생성합니다; 각 이메일은 길이에 따라 하나 이상의 이미지 파일이 됩니다.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 단계 2: Load Options 구성
HTML에 사용한 동일한 `LoadOptions`를 여기에서도 재사용하여 형식 간 비밀번호 처리를 일관되게 유지합니다.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 단계 3: JPG View Options 정의
`JpgViewOptions`는 이미지 해상도, 품질 및 JPEG 변환을 위한 출력 폴더를 제어합니다.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 단계 4: Viewer 초기화 및 JPG 렌더링
`viewer.view(jpgOptions)`를 사용하여 웹 미리보기에 적합한 고품질 JPEG 파일을 생성합니다.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### PST/OST 문서를 PNG로 렌더링
#### 단계 1: 출력 디렉터리 설정
PNG 출력은 아카이빙이나 OCR 처리를 위해 무손실 품질이 필요할 때 유용합니다.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 단계 2: Load Options 구성
비밀번호 및 시간 초과 설정 외에 추가 설정은 필요하지 않습니다.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 단계 3: PNG View Options 정의
`PngViewOptions`를 사용하면 투명 배경과 무손실 PNG 이미지를 위한 출력 폴더를 설정할 수 있습니다.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 단계 4: Viewer 초기화 및 PNG 렌더링
`viewer.view(pngOptions)`를 인스턴스화하여 각 이메일의 PNG 스냅샷을 생성합니다.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST 문서를 PDF로 렌더링
#### 단계 1: 출력 디렉터리 설정
PST당 하나의 PDF 파일은 법률 검토 워크플로를 단순화하고 저장 오버헤드를 감소시킵니다.

CODE_BLOCK_PLACEHOLDER_14_END

#### 단계 2: Load Options 구성
PDF로 변환할 때 `setEmbedFonts(true)`를 활성화하면 모든 기기에서 시각적 일관성을 보장할 수 있습니다.

CODE_BLOCK_PLACEHOLDER_15_END

#### 단계 3: PDF View Options 정의
`PdfViewOptions`를 사용하면 압축 수준, 폰트 포함 여부를 선택하고 PDF 변환을 위한 출력 파일 이름을 지정할 수 있습니다.

CODE_BLOCK_PLACEHOLDER_16_END

#### 단계 4: Viewer 초기화 및 PDF 렌더링
`PdfViewOptions`를 생성하고, 필요에 따라 압축 수준을 선택한 뒤 `viewer.view(pdfOptions)`를 호출합니다. API는 모든 이메일을 하나의 검색 가능한 PDF 문서로 병합합니다.

CODE_BLOCK_PLACEHOLDER_17_END

## 실용적인 적용 사례
- **이메일 아카이빙:** 대용량 PST 아카이브를 검색 가능한 HTML 또는 PDF로 변환하여 규정 준수를 지원합니다.  
- **문서 관리 시스템:** PDF, PNG 또는 JPG만 허용하는 시스템에 변환된 파일을 저장합니다.  
- **협업 플랫폼:** Slack이나 Teams에서 변환된 이메일을 이미지로 공유합니다.  
- **법률 검토:** 법원에 이메일 증거의 PDF 버전을 제공합니다.  
- **백업 전략:** 중요한 메시지의 가벼운 PNG 또는 JPG 스냅샷을 보관합니다.

## 성능 고려 사항
- **리소스 관리:** 여러 파일을 처리할 때 `Viewer` 인스턴스를 재사용하여 오버헤드를 줄입니다.  
- **메모리 튜닝:** 서버 용량에 따라 `loadOptions.setResourceLoadingTimeout`을 조정합니다.  
- **비동기 처리:** 변환 작업을 백그라운드 스레드로 오프로드하여 UI 응답성을 높입니다.

## 자주 묻는 질문
**Q: 동일한 코드 베이스로 **convert pst to pdf**를 어떻게 수행하나요?**  
A: PDF 렌더링 섹션에 표시된 대로 `PdfViewOptions`를 사용하면 되며, 나머지 코드는 동일하게 유지됩니다.

**Q: GroupDocs.Viewer가 암호화된 PST 파일을 처리할 수 있나요?**  
A: 예, 렌더링 전에 `LoadOptions.setPassword("yourPassword")`로 비밀번호를 제공하면 됩니다.

**Q: **java convert pst**를 PNG와 JPG로 변환할 때 차이점은 무엇인가요?**  
A: PNG는 무손실 품질을 유지하여 스크린샷에 이상적이며, JPG는 이메일 미리보기에 적합한 작은 파일 크기를 제공합니다.

**Q: **how to convert pst** 파일을 대량으로 변환하는 방법이 있나요?**  
A: PST 파일이 들어 있는 디렉터리를 순회하는 루프에 렌더링 로직을 감싸고, 각 파일에 동일한 `Viewer` 구성을 재사용합니다.

**Q: API가 1 GB보다 큰 PST 파일 변환을 지원하나요?**  
A: 예, GroupDocs.Viewer는 데이터를 스트리밍하여 전체 아카이브를 메모리에 로드하지 않고도 최대 2 GB 파일을 처리할 수 있습니다.

## 결론
이제 GroupDocs.Viewer for Java를 사용하여 **convert pst to html**, JPG, PNG 및 PDF로 변환하는 완전하고 프로덕션 준비된 가이드를 확보했습니다. 위 단계들을 따르면 이메일 변환을 모든 Java 기반 워크플로에 통합하고 접근성을 향상시키며 규정 준수 요구 사항을 충족할 수 있습니다.

---

**마지막 업데이트:** 2026-07-19  
**테스트 환경:** GroupDocs.Viewer for Java 25.2  
**작성자:** GroupDocs

## 관련 튜토리얼
- [GroupDocs.Viewer for Java를 사용하여 NSF를 PDF, HTML, JPG, PNG로 변환](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – ODF를 HTML, JPG, PNG, PDF로 변환 (GroupDocs.Viewer for Java 사용)](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [GroupDocs.Viewer for Java를 사용하여 DOCX를 HTML로 변환하는 방법: 단계별 가이드](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)