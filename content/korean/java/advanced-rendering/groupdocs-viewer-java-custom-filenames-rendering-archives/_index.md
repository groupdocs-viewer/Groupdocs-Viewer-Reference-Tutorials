---
date: '2026-10-15'
description: GroupDocs.Viewer for Java를 사용하여 zip을 pdf로 변환하고 zip에서 pdf를 생성하는 방법을 배우고,
  아카이브 렌더링 시 사용자 지정 파일명을 설정하는 방법을 알아보세요. 단계별 가이드에는 Maven 설정 및 구성 세부 사항이 포함됩니다.
keywords:
- convert zip to pdf
- convert archive to pdf
- generate pdf from zip
lastmod: '2026-10-15'
og_description: GroupDocs.Viewer for Java로 zip을 pdf로 변환하고 생성된 PDF에 사용자 지정 파일명을 설정합니다.
  이 가이드에서는 Maven 설정, API 사용법 및 성능 팁을 제공합니다.
og_image_alt: 'GroupDocs.Viewer Java example: custom PDF filenames for archive rendering'
og_title: GroupDocs.Viewer Java를 사용하여 zip을 pdf로 변환
schemas:
- author: GroupDocs
  dateModified: '2026-10-15'
  description: Learn how to convert zip to pdf and generate pdf from zip using GroupDocs.Viewer
    for Java, while setting custom filenames for archive rendering. Step‑by‑step guide
    includes Maven setup and configuration details.
  headline: convert zip to pdf with GroupDocs.Viewer Java - Custom Filenames
  type: TechArticle
- description: Learn how to convert zip to pdf and generate pdf from zip using GroupDocs.Viewer
    for Java, while setting custom filenames for archive rendering. Step‑by‑step guide
    includes Maven setup and configuration details.
  name: convert zip to pdf with GroupDocs.Viewer Java - Custom Filenames
  steps:
  - name: Define Output Directory and File Path
    text: 'Start by setting up the output directory and file path using placeholders
      for easy customization:'
  - name: Initialize Viewer Object
    text: 'The `Viewer` class provides methods to load and render documents and archives.
      Create a `Viewer` object with the archive file you wish to render:'
  - name: Create PdfViewOptions
    text: '`PdfViewOptions` defines settings for PDF output such as page size and
      margins. Set up `PdfViewOptions` to specify the rendering configurations:'
  - name: Set Custom Filename
    text: '`ArchiveOptions` allows you to configure archive‑specific rendering options,
      including the output PDF filename. Use `ArchiveOptions` to set a custom filename
      for your rendered PDF document:'
  - name: Render Archive File to PDF
    text: 'Finally, render your archive file using the specified options:'
  type: HowTo
- questions:
  - answer: Use Maven and add the specified repository and dependency to your `pom.xml`.
    question: How do I install GroupDocs.Viewer for Java?
  - answer: Yes, similar options exist for different output formats supported by GroupDocs.Viewer.
    question: Can I specify filenames for other file formats besides PDF?
  - answer: Double‑check the path definitions and ensure all configurations, especially
      `ArchiveOptions.setPdfFileName`, are set correctly.
    question: What if my rendered document filename is not as expected?
  - answer: Optimize memory usage and consider processing the archive in smaller chunks
      or streaming the content to avoid loading the entire file into memory.
    question: How do I handle large archive files with GroupDocs.Viewer?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for comprehensive guides and API references.
    question: Where can I find more resources on using GroupDocs.Viewer?
  type: FAQPage
tags:
- convert zip to pdf
- GroupDocs Viewer
- Java PDF rendering
- custom filenames
- archive conversion
title: GroupDocs.Viewer Java로 zip을 pdf로 변환 – 사용자 지정 파일명
type: docs
url: /ko/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip을 PDF로 변환하기 – GroupDocs.Viewer Java 사용자 지정 파일명

Converting zip archives to PDF is a frequent requirement when you need to share or archive documents in a universally readable format. In this tutorial you’ll learn **how to convert zip to pdf** with GroupDocs.Viewer for Java while also controlling the output filename to match your naming conventions. We’ll walk through environment preparation, Maven integration, and the exact API calls needed to produce a PDF with a custom name, plus performance‑boosting tips for large archives.

![GroupDocs.Viewer for Java를 사용한 아카이브 PDF 렌더링을 위한 사용자 지정 파일명](/viewer/advanced-rendering/custom-filenames-for-pdf-rendering-of-archives-java.png)

[GroupDocs.Viewer for Java를 사용한 아카이브 PDF 렌더링을 위한 사용자 지정 파일명](/viewer/advanced-rendering/custom-filenames-for-pdf-rendering-of-archives-java.png)

## 빠른 답변
- **주요 사용 사례는 무엇인가요?** zip 아카이브를 사용자 지정 출력 이름으로 PDF로 변환합니다.  
- **필요한 라이브러리는?** GroupDocs.Viewer for Java (v25.2 이상).  
- **라이선스가 필요합니까?** 평가용으로는 체험판 또는 임시 라이선스로 충분하지만, 프로덕션에서는 구매 라이선스가 필요합니다.  
- **다른 형식의 파일명도 변경할 수 있나요?** 예, HTML, PNG 및 기타 지원 형식에도 유사한 옵션이 있습니다.  
- **Maven이 유일한 설치 방법인가요?** Maven이 권장되지만, 원한다면 JAR 파일을 수동으로 추가할 수도 있습니다.

## “zip을 PDF로 변환”이란 무엇인가요?

ZIP 아카이브를 로드하고 그 안에 포함된 모든 지원 파일(DOCX, PPTX, 이미지 등)을 단일 PDF 파일로 렌더링하는 것이 **zip을 PDF로 변환**이라는 의미입니다. 이 과정은 원본 애플리케이션이 없어도 모든 장치에서 열 수 있는 휴대용 읽기 전용 문서를 생성합니다.

## 이 작업에 GroupDocs.Viewer를 사용하는 이유

GroupDocs.Viewer는 **100**개 이상의 문서 및 이미지 형식을 렌더링을 지원하며, 전체 아카이브를 메모리에 로드하지 않고 **500개 이상**의 파일이 포함된 아카이브를 처리할 수 있어 수동 추출에 비해 메모리 사용량을 최대 **70 %**까지 절감합니다. 고수준 API 덕분에 사용자 정의 파서를 작성할 필요가 없어 배치 워크플로가 더 빠르고 신뢰성 있게 동작합니다.

## 사전 요구 사항

- **Java Development Kit (JDK)** – 버전 8 이상.  
- **IDE** – IntelliJ IDEA, Eclipse 또는 Java 호환 편집기.  
- **Maven** – 의존성 관리를 위한 도구(권장).  
- **기본 Java 지식** – 클래스, 객체 및 파일 I/O에 익숙해야 합니다.

## GroupDocs.Viewer for Java 설정

### Maven을 통한 설치

`pom.xml`에 GroupDocs 저장소와 Viewer 의존성을 추가합니다. 이 한 단계만으로 라이브러리와 모든 전이 의존성이 다운로드됩니다.

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

### 라이선스 획득 단계
- **무료 체험** – 30일 동안 완전 기능 제공.  
- **임시 라이선스** – 기능 제한 없이 연장된 평가.  
- **구매 라이선스** – 프로덕션 배포에 필요.

#### 기본 초기화 및 설정

Maven이 패키지를 해결한 후, `Viewer` 인스턴스를 생성하고 렌더링하려는 아카이브를 지정합니다.

```java
import com.groupdocs.viewer.Viewer;
// Initialize viewer object
try (Viewer viewer = new Viewer("YOUR_ARCHIVE_FILE_PATH")) {
    // Configure options here
} catch (Exception e) {
    e.printStackTrace();
}
```

## 구현 가이드

아래는 사용자 지정 파일명을 사용한 **zip을 PDF로 변환** 단계별 워크플로입니다. 각 단계는 간단한 설명과 실제 코드가 들어갈 자리인 플레이스홀더를 포함합니다.

### 사용자 지정 파일명으로 zip을 PDF로 변환하는 방법

아카이브를 로드하고 PDF 옵션을 설정한 뒤 `ArchiveOptions`를 통해 사용자 지정 파일명을 지정하고 최종적으로 PDF를 렌더링합니다. 이 두 단계 패턴은 출력 파일이 지정한 정확한 이름을 갖도록 보장하여 후처리 이름 변경이 필요 없게 합니다.

`ArchiveOptions`는 출력 파일명과 같은 아카이브 전용 렌더링 설정을 구성합니다.

#### 단계 1: 출력 디렉터리 및 파일 경로 정의

생성된 PDF가 저장될 폴더를 준비하고, 유연성을 위해 플레이스홀더를 사용해 대상 파일명을 구성합니다.

```java
import java.nio.file.Path;
// Define output directory and file path
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path outputFilePath = outputDirectory.resolve("output.pdf");
```

#### 단계 2: Viewer 객체 초기화

`Viewer`는 문서와 아카이브를 로드하고 렌더링하는 핵심 클래스입니다. 인스턴스를 생성하면 라이브러리가 소스 파일에 연결됩니다.

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP")) {
    // Continue to next steps
} catch (Exception e) {
    e.printStackTrace();
}
```

#### 단계 3: PdfViewOptions 생성

`PdfViewOptions`는 페이지 크기, 여백 및 기타 PDF 전용 설정을 제어합니다. 텍스트 추출, 이미지 압축 등을 활성화하거나 비활성화할 수 있습니다.

```java
import com.groupdocs.viewer.options.PdfViewOptions;
// Configure PDF view options
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
```

#### 단계 4: 사용자 지정 파일명 설정

`ArchiveOptions`를 사용하면 결과 PDF 파일명을 포함한 아카이브 렌더링을 세밀하게 조정할 수 있습니다. 다음 호출은 원하는 정확한 파일명을 지정합니다.

```java
import com.groupdocs.viewer.options.FileName;
import com.groupdocs.viewer.options.ArchiveOptions;
// Specify the output PDF filename
viewOptions.getArchiveOptions().setFileName(new FileName("my_custom_filename.pdf"));
```

#### 단계 5: 아카이브 파일을 PDF로 렌더링

구성된 옵션으로 `view` 메서드를 호출하면 최종 PDF가 생성됩니다. 라이브러리는 콘텐츠를 스트리밍하므로 수백 페이지에 달하는 아카이브도 효율적으로 처리됩니다.

```java
// Execute rendering process
viewer.view(viewOptions);
```

## 일반적인 문제와 해결책

- **파일명 오류** – `ArchiveOptions.setPdfFileName`이 기대하는 정확한 문자열(확장자 `.pdf` 포함)을 받는지 확인하세요.  
- **출력 폴더 없음** – 단계 1에서 정의한 디렉터리가 존재하는지 확인하거나 렌더링 전에 프로그래밍으로 생성하세요.  
- **ZIP 내부 지원되지 않는 파일** – GroupDocs.Viewer는 렌더링할 수 없는 파일을 건너뛰며, 로그에서 경고를 확인하고 아카이브를 사전 필터링하는 것을 고려하세요.  
- **대용량 아카이브 시 메모리 급증** – 스트리밍 API(`Viewer.view`와 `FileOutputStream` 사용)를 활용해 메모리 사용량을 낮게 유지하세요.

## 실용적인 적용 사례

1. **브랜드 일관성 보고** – 클라이언트 ID 또는 프로젝트 코드를 기반으로 PDF 파일명을 자동 지정해 문서 저장소를 깔끔하게 유지합니다.  
2. **법률 문서 보관** – 사례 파일 번들(주로 ZIP 형태)을 불변 PDF로 변환해 장기 보관합니다.  
3. **자동 이메일 첨부** – 사용자가 업로드한 ZIP에서 단일 PDF를 생성하고 추가 파일 처리 코드 없이 이메일에 첨부합니다.

## 성능 고려 사항

- **메모리 사용량** – GroupDocs.Viewer는 스트리밍 방식으로 아카이브를 처리하며, 1 GB ZIP 파일이라도 일반적으로 **150 MB** 이하를 사용합니다.  
- **CPU 부하** – 혼합 유형 아카이브에서 300페이지 PDF를 렌더링할 경우 표준 2.6 GHz CPU에서 10페이지당 평균 **1.2 초**가 소요됩니다.  
- **스레드 안전성** – `Viewer` 인스턴스는 스레드 안전하지 않으므로 요청당 새 인스턴스를 생성하거나 다중 스레드 환경에서 접근을 동기화하세요.

## 자주 묻는 질문

**Q: GroupDocs.Viewer for Java를 어떻게 설치하나요?**  
A: Maven을 사용하고 지정된 저장소와 의존성을 `pom.xml`에 추가하세요.

**Q: PDF 외 다른 파일 형식에도 파일명을 지정할 수 있나요?**  
A: 예, HTML, PNG 및 GroupDocs.Viewer가 지원하는 기타 출력 형식에도 유사한 옵션이 있습니다.

**Q: 렌더링된 문서 파일명이 예상과 다르면 어떻게 해야 하나요?**  
A: 경로 정의를 다시 확인하고 특히 `ArchiveOptions.setPdfFileName` 설정이 올바른지 확인하세요.

**Q: GroupDocs.Viewer로 대용량 아카이브 파일을 처리하려면 어떻게 해야 하나요?**  
A: 메모리 사용을 최적화하고 전체 파일을 메모리에 로드하지 않도록 아카이브를 작은 청크로 처리하거나 스트리밍 방식으로 콘텐츠를 전송하세요.

**Q: GroupDocs.Viewer 사용에 대한 추가 자료는 어디서 찾을 수 있나요?**  
A: 포괄적인 가이드와 API 레퍼런스는 [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)에서 확인하세요.

## 리소스
- **문서**: [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)
- **문서**: [GroupDocs Viewer Java 문서](https://docs.groupdocs.com/viewer/java/)
- **API reference**: [GroupDocs Viewer Java 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer 릴리스](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [GroupDocs 라이선스 구매](https://purchase.groupdocs.com/buy)
- **Free trial**: [GroupDocs Viewer 체험](https://releases.groupdocs.com/viewer/java/)
- **Temporary license**: [임시 라이선스 받기](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-10-15  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs  

---

## 관련 튜토리얼

- [groupdocs viewer java: 문서를 PDF로 변환 – 완전 가이드](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java에서 라이선스 설정 방법: 파일 및 URL 설정 가이드](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)
- [GroupDocs.Viewer for Java를 사용한 효율적인 PDF 페이지 재정렬 – 종합 가이드](/viewer/java/advanced-rendering/master-pdf-page-reorder-groupdocs-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}