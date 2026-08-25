---
date: '2026-08-25'
description: GroupDocs.Viewer for Java를 사용하여 Apple Numbers 파일을 PDF, HTML, JPG, 또는
  PNG로 변환하는 방법을 배웁니다. 설정, java 문서 변환 단계 및 웹 표시 팁이 포함됩니다.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: GroupDocs.Viewer for Java를 사용하여 Apple Numbers 파일을 PDF, HTML, JPG,
  또는 PNG로 변환하는 방법을 배웁니다. 설정, java 문서 변환 단계 및 웹 표시 팁이 포함됩니다.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: GroupDocs.Viewer for Java를 사용하여 Apple Numbers 파일을 변환하는 방법
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: GroupDocs.Viewer for Java를 사용하여 Apple Numbers 파일을 변환하는 방법
type: docs
url: /ko/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java로 Numbers 변환하는 방법

Displaying Apple Numbers spreadsheets on the web or inside a desktop client can feel like a puzzle, especially when you need to **convert numbers to PDF** or embed them as images for reports. In this tutorial you’ll learn exactly **how to convert numbers** to PDF, HTML, JPG, and PNG using **GroupDocs.Viewer for Java**. We’ll walk through project setup, code‑level rendering, and real‑world scenarios so you can build robust preview or archiving pipelines in minutes.

![GroupDocs.Viewer for Java로 Apple Numbers 문서 렌더링](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[GroupDocs.Viewer for Java로 Apple Numbers 문서 렌더링](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### 배우게 될 내용
- Maven 기반 Java 프로젝트에 GroupDocs.Viewer를 추가하는 방법.  
- 단계별 코드로 **convert numbers to pdf**, **convert numbers to html**, **convert numbers to jpg**, **convert numbers to png** 변환을 수행합니다.  
- 웹 포털, 이메일 워크플로, 문서 관리 시스템에 적합한 출력 형식을 선택하는 시점.  

## 빠른 답변
- **Java로 Numbers를 PDF로 변환할 수 있나요?** 예 – `Viewer`를 인스턴스화하고 `PdfViewOptions`를 호출하여 저장 준비가 된 PDF를 얻습니다.  
- **어떤 형식이 가장 풍부한 웹 미리보기를 제공하나요?** HTML은 테이블, 수식, 스타일을 인터랙티브하게 유지하기 때문에 가장 풍부한 웹 미리보기를 제공합니다.  
- **프로덕션에 라이선스가 필요합니까?** 비시험 배포에는 상용 라이선스가 필요합니다.  
- **이미지 변환이 지원되나요?** 물론입니다 – 고품질 스냅샷을 위해 `JpgViewOptions` 또는 `PngViewOptions`를 사용하십시오.  
- **필요한 Java 버전은 무엇인가요?** Java 8 이상 및 Maven이 필요합니다.  

## 전제 조건
- Java Development Kit (JDK) 8 또는 그 이후 버전이 머신에 설치되어 있어야 합니다.  
- 프로젝트 빌드와 의존성 관리를 위한 Maven.  
- Java 파일 I/O, 경로, 예외 처리에 대한 기본 지식.  

## GroupDocs.Viewer for Java 설정

### Maven을 사용한 설치
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`. This block must stay exactly as shown:

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
- **Free trial:** 전체 기능 제공, 신용카드 필요 없음.  
- **Temporary license:** 장기 테스트를 위한 기간 제한 키 요청.  
- **Full purchase:** 상업적 사용을 위한 영구 라이선스 획득.  

## Viewer 클래스란?
`Viewer` 클래스는 문서를 로드하고 요청된 출력 형식으로 렌더링하는 GroupDocs.Viewer의 핵심 엔진입니다. 파일 유형 처리를 추상화하여 스프레드시트 내부 파싱 대신 비즈니스 로직에 집중할 수 있습니다.

## GroupDocs.Viewer for Java로 Numbers를 HTML로 변환하는 방법?
`HtmlViewOptions`는 리소스 임베드 또는 외부 파일 링크와 같은 HTML 렌더링 설정을 지정합니다.  
Numbers 파일을 로드하고 HTML 옵션을 구성한 뒤 `viewer.view()`를 호출합니다. `HtmlViewOptions.forEmbeddedResources()` 메서드는 CSS와 이미지를 HTML에 직접 포함시켜 추가 자산 없이 웹 페이지에 삽입하기에 이상적인 결과를 제공합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **왜 중요한가:** 임베드된 리소스는 미리보기를 자체 포함하게 하여 깨진 이미지 링크를 방지하고 CDN 배포를 단순화합니다.

## GroupDocs.Viewer for Java로 Numbers를 JPG로 변환하는 방법?
`JpgViewOptions`는 JPEG 출력을 구성하며, 각 렌더링 페이지에 대해 품질 및 크기 조정을 허용합니다.  
각 스프레드시트 페이지를 JPEG 스냅샷으로 변환할 수 있습니다. `quality` 설정을 조정하여 파일 크기와 시각적 충실도 사이의 균형을 맞출 수 있으며, 이는 소셜 미디어나 이메일 뉴스레터에 가벼운 이미지를 필요로 할 때 유용합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **팁:** 대용량 워크북을 빠르게 처리하려면 품질을 70%로 낮추세요 – 시각적 영향은 최소이며 파일 크기가 크게 감소합니다.

## GroupDocs.Viewer for Java로 Numbers를 PNG로 변환하는 방법?
`PngViewOptions`는 PNG 출력을 구성하며, 무손실 압축 및 고품질 이미지를 위한 해상도 설정을 지원합니다.  
PNG는 무손실 압축을 제공하여 렌더링된 각 픽셀을 정확히 보존합니다. 보고서나 PDF용 인쇄 준비 그래픽이 필요할 때 DPI를 높이려면 `resolution` 속성을 사용하십시오.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **전문가 팁:** `options.setResolution(300)`을 설정하여 인쇄 페이지에서 선명하게 보이는 고해상도 출력을 얻으세요.

## GroupDocs.Viewer for Java로 Numbers를 PDF로 변환하는 방법?
`PdfViewOptions`는 폰트 임베드, 압축, 페이지 크기 제어 등을 포함한 PDF 렌더링 옵션을 정의합니다.  
`PdfViewOptions` 객체를 사용하면 폰트를 임베드하고 페이지 크기를 제어하며 Numbers 워크북의 원본 레이아웃을 보존할 수 있습니다. 변환은 한 번의 호출로 수행되어 검색 가능하고 편집 불가능한 PDF를 생성하며, 이는 아카이빙이나 규정 준수에 적합합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **핵심 설정:** `options.setCompress(true)`를 활성화하여 품질을 손상시키지 않고 PDF 크기를 줄일 수 있으며, 이는 대규모 문서 저장소에 필수적입니다.

## 왜 GroupDocs.Viewer for Java를 사용하나요?
GroupDocs.Viewer는 Apple Numbers를 포함해 **100개 이상의 파일 형식**을 지원하며, 전체 파일을 메모리에 로드하지 않고 수백 페이지 스프레드시트를 렌더링할 수 있습니다. 벤치마크에 따르면 250페이지 Numbers 파일이 표준 2.5 GHz CPU에서 8초 미만에 PDF로 변환되어 기업 파이프라인에 속도와 신뢰성을 제공합니다.

## 실제 적용 사례
- **Web integration:** 브라우저 플러그인 없이도 작동하는 인터랙티브 스프레드시트 뷰어를 위해 HTML로 렌더링합니다.  
- **Content sharing:** 뉴스레터, 채팅 앱, 소셜 피드에 빠르게 이미지를 삽입하기 위해 JPG/PNG로 변환합니다.  
- **Enterprise DMS:** **how to convert numbers**를 PDF로 사용하여 규정 준수 및 감사 추적을 위한 편집 불가능하고 검색 가능한 스프레드시트 버전을 저장합니다.  

## 성능 고려 사항
- **Resource management:** 항상 `Viewer`를 try‑with‑resources 블록 안에서 인스턴스화하여(예시와 같이) 네이티브 리소스가 즉시 해제되도록 합니다.  
- **Large workbooks:** 페이지별로 처리하고 출력을 스트리밍하여 500페이지 파일이라도 메모리 사용량을 100 MB 이하로 유지합니다.  
- **Thread safety:** 스레드당 별도의 `Viewer` 인스턴스를 생성하십시오; 이 클래스는 스레드 안전하지 않으므로 단일 인스턴스를 공유하면 경쟁 조건이 발생할 수 있습니다.  

## 일반적인 함정 및 문제 해결
- **Missing fonts:** 생성된 PDF가 다르게 보이면 서버에 필요한 폰트가 있는지 확인하거나 `PdfViewOptions.setEmbedFonts(true)`를 사용해 임베드하십시오.  
- **Blank pages:** Numbers 파일이 비밀번호로 보호되지 않았는지 확인하십시오; 현재 GroupDocs.Viewer는 보호된 워크북을 복호화하지 않습니다.  
- **Out‑of‑memory errors:** 매우 큰 파일의 경우 `options.setPageCount(1)`을 활성화하여 페이지당 하나씩 렌더링하고 나중에 결과를 결합하십시오.  

## 자주 묻는 질문
**Q: GroupDocs.Viewer가 지원하는 파일 형식은 무엇인가요?**  
A: DOCX, XLSX, PDF, HTML, Apple Numbers 등을 포함한 100개 이상의 형식을 지원하며 각 형식에 대해 완전한 렌더링 기능을 제공합니다.

**Q: 대용량 Numbers 파일을 효율적으로 처리하려면 어떻게 해야 하나요?**  
A: 변환을 페이지별로 스트리밍하고 `options.setPageCount()`를 사용해 메모리 사용량을 제한하며, 출력 PDF 압축을 고려하십시오.

**Q: GroupDocs.Viewer를 상업 프로젝트에 사용할 수 있나요?**  
A: 예—시험 제한을 해제하고 프로덕션 수준 지원을 받으려면 상용 라이선스를 구매하십시오.

**Q: 이미지 출력 품질을 맞춤 설정할 수 있나요?**  
A: 물론입니다. `JpgViewOptions.setQuality(int)` 또는 `PngViewOptions.setResolution(int)`를 조정하여 크기‑품질 요구 사항을 충족하십시오.

**Q: 더 고급 사용 예제를 어디서 찾을 수 있나요?**  
A: 자세한 가이드, 샘플 프로젝트, API 레퍼런스 정보를 위해 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)을 방문하십시오.

## 다음 단계
위에 보여진 옵션을 실험한 뒤 PDF 워터마크, 비밀번호 보호 추가, Spring Boot REST 서비스에 뷰어 통합 등 추가 커스터마이징을 탐색하십시오. [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)은 조합하여 사용할 수 있는 전체 기능 카탈로그를 제공합니다.

## 리소스
- **문서:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs 문서:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 레퍼런스:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **API 레퍼런스:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **다운로드:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **라이선스 구매:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **무료 체험:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **임시 라이선스:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **지원 포럼:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

**마지막 업데이트:** 2026-08-25  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs

## 관련 튜토리얼
- [GroupDocs.Viewer Java를 사용하여 Excel을 HTML, JPG, PNG, PDF로 변환하는 방법](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [GroupDocs.Viewer와 함께 Java에서 Excel을 HTML로 변환하고 숨겨진 행 및 열을 렌더링하는 방법](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Java 문서 렌더링 튜토리얼 - 파일을 HTML, PDF 및 이미지로 변환](/viewer/java/rendering-basics/)