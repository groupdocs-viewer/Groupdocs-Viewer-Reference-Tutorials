---
date: '2026-05-31'
description: GroupDocs.Viewer for Java를 사용하여 zip을 pdf로 변환하고 zip에서 pdf를 생성하는 방법을 배우고,
  아카이브 렌더링 시 사용자 지정 파일 이름을 설정하는 방법을 알아보세요. 단계별 가이드에는 Maven 설정 및 구성 세부 정보가 포함되어 있습니다.
keywords:
- convert zip to pdf
- generate pdf from zip
- custom filenames PDF rendering
schemas:
- author: GroupDocs
  dateModified: '2026-05-31'
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
title: GroupDocs.Viewer Java를 사용해 zip을 pdf로 변환 - 사용자 지정 파일 이름
type: docs
url: /ko/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/
weight: 1
---

# GroupDocs.Viewer Java 마스터하기: 아카이브를 PDF로 렌더링할 때 사용자 지정 파일 이름 지정

ZIP 아카이브를 PDF 파일로 변환하는 것은 문서를 보편적으로 읽을 수 있는 형식으로 공유하거나 보관해야 할 때 자주 요구되는 작업입니다. 이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 **zip을 pdf로 변환하는 방법**을 배우고, 출력 파일 이름을 명명 규칙에 맞게 제어하는 방법을 배웁니다. 이 가이드는 환경 준비, Maven 통합 및 사용자 지정 이름의 PDF를 생성하는 데 필요한 정확한 API 호출 과정을 안내합니다.

![GroupDocs.Viewer for Java를 사용한 아카이브 PDF 렌더링을 위한 사용자 지정 파일 이름](/viewer/advanced-rendering/custom-filenames-for-pdf-rendering-of-archives-java.png)

**배우게 될 내용**
- GroupDocs.Viewer for Java 설정
- 지정된 파일 이름으로 아카이브 파일을 PDF로 렌더링
- 사용자 지정 파일 이름 기능의 실용적인 적용 사례
- 성능 최적화를 위한 모범 사례

개발 환경을 준비하고 GroupDocs.Viewer를 문서 렌더링을 위한 강력한 도구로 만드는 핵심 기능을 살펴보면서 시작해 보겠습니다.

## 빠른 답변
- **주요 사용 사례는 무엇인가요?** 사용자 지정 출력 이름으로 ZIP 아카이브를 PDF로 변환합니다.  
- **필요한 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java (v25.2 이상).  
- **라이선스가 필요합니까?** 평가용으로는 체험판 또는 임시 라이선스를 사용할 수 있으며, 프로덕션에서는 구매한 라이선스가 필요합니다.  
- **다른 형식의 파일 이름도 변경할 수 있나요?** 예, HTML, PNG 등에 대한 유사한 옵션이 있습니다.  
- **Maven이 유일한 설치 방법인가요?** Maven이 권장되지만 JAR 파일을 직접 사용할 수도 있습니다.

## “zip을 pdf로 변환”이란 무엇인가요?

ZIP 아카이브를 단일 PDF 문서로 변환하면 아카이브 내부의 모든 지원 파일(DOCX, PPTX, 이미지 등)이 하나의 휴대용 파일로 병합됩니다. 이는 배포를 간소화하고, 플랫폼 간 일관된 렌더링을 보장하며, 조직의 명명 표준에 맞는 사용자 지정 파일 이름을 적용할 수 있게 합니다.

## 왜 이 작업에 GroupDocs.Viewer를 사용하나요?

GroupDocs.Viewer는 아카이브 내부의 다양한 파일 유형을 처리하는 복잡성을 추상화하는 고수준 API를 제공합니다. 100개 이상의 문서 및 이미지 형식을 렌더링을 지원하며, ArchiveOptions를 통해 정확한 PDF 파일 이름을 지정할 수 있어 배치 처리 및 자동화 워크플로우를 보다 깔끔하게 만들 수 있습니다. 또한 이 라이브러리는 전체 파일을 메모리에 로드하지 않고 대용량 아카이브를 처리하여 수동 추출에 비해 메모리 사용량을 최대 70 %까지 줄입니다.

## 전제 조건

시작하기 전에 다음 항목을 준비하십시오:

### 필요한 라이브러리 및 종속성
- **GroupDocs.Viewer for Java**: 버전 25.2 이상.

### 환경 설정 요구 사항
- JDK(Java Development Kit)가 머신에 설치되어 있어야 합니다.
- IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용하여 Java 애플리케이션을 개발합니다.

### 지식 전제 조건
- Java 프로그래밍에 대한 기본 이해
- 빌드 자동화 도구인 Maven에 대한 친숙함

이러한 전제 조건을 갖추었다면, GroupDocs.Viewer for Java 설정을 진행해 보겠습니다.

## GroupDocs.Viewer for Java 설정

### Maven을 통한 설치

Maven을 사용하여 프로젝트에 GroupDocs.Viewer를 통합하려면 `pom.xml` 파일에 다음 저장소와 의존성을 추가하십시오:

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
- **무료 체험**: 기능을 평가할 수 있는 완전한 기능의 체험 버전에 접근합니다.  
- **임시 라이선스**: 제한 없이 장기간 평가를 위해 획득합니다.  
- **구매**: 상업적 사용을 위한 라이선스를 획득합니다.

#### 기본 초기화 및 설정

Maven 설정 후, 다음 코드 스니펫으로 GroupDocs.Viewer를 초기화합니다:

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

이제 **zip을 pdf로 변환**하면서 사용자 지정 이름을 지정하는 파일 이름 지정에 집중해 보겠습니다.

### 사용자 지정 파일 이름으로 zip을 pdf로 변환하는 방법

`Viewer`로 아카이브를 로드하고, `PdfViewOptions`를 구성한 뒤 `ArchiveOptions`를 사용하여 렌더링 전에 원하는 PDF 파일 이름을 설정합니다. 이 두 단계 패턴은 출력 파일이 지정한 대로 정확히 이름이 지정되도록 하여 사후 처리 이름 변경이 필요 없게 합니다.

#### 단계 1: 출력 디렉터리 및 파일 경로 정의

쉽게 커스터마이징할 수 있도록 플레이스홀더를 사용해 출력 디렉터리와 파일 경로를 설정합니다:

```java
import java.nio.file.Path;
// Define output directory and file path
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path outputFilePath = outputDirectory.resolve("output.pdf");
```

#### 단계 2: Viewer 객체 초기화

`Viewer` 클래스는 문서 및 아카이브를 로드하고 렌더링하는 메서드를 제공합니다. 렌더링하려는 아카이브 파일로 `Viewer` 객체를 생성합니다:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP")) {
    // Continue to next steps
} catch (Exception e) {
    e.printStackTrace();
}
```

#### 단계 3: PdfViewOptions 생성

`PdfViewOptions`는 페이지 크기와 여백 등 PDF 출력 설정을 정의합니다. 렌더링 구성을 지정하도록 `PdfViewOptions`를 설정합니다:

```java
import com.groupdocs.viewer.options.PdfViewOptions;
// Configure PDF view options
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
```

#### 단계 4: 사용자 지정 파일 이름 설정

`ArchiveOptions`를 사용하면 아카이브 전용 렌더링 옵션을 구성할 수 있으며, 여기에는 출력 PDF 파일 이름도 포함됩니다. `ArchiveOptions`를 사용해 렌더링된 PDF 문서의 사용자 지정 파일 이름을 설정합니다:

```java
import com.groupdocs.viewer.options.FileName;
import com.groupdocs.viewer.options.ArchiveOptions;
// Specify the output PDF filename
viewOptions.getArchiveOptions().setFileName(new FileName("my_custom_filename.pdf"));
```

#### 단계 5: 아카이브 파일을 PDF로 렌더링

마지막으로, 지정된 옵션을 사용해 아카이브 파일을 렌더링합니다:

```java
// Execute rendering process
viewer.view(viewOptions);
```

### 문제 해결 팁
- 모든 경로가 올바르게 설정되고 디렉터리가 존재하는지 확인하십시오.  
- 설치된 GroupDocs.Viewer 버전이 올바른지 확인하십시오.  
- 생성된 PDF 파일 이름이 기대와 다르면 `ArchiveOptions`의 `setPdfFileName` 호출을 다시 확인하십시오.

## 실용적인 적용 사례

**zip을 pdf로 변환**하고 사용자 지정 파일 이름을 설정하는 방법을 이해하면 다양한 시나리오에서 유용합니다:

1. **브랜딩 일관성** – 여러 문서에 걸쳐 브랜딩 목적의 출력 파일 이름을 맞춤 설정합니다.  
2. **조직 효율성** – 문서 관리 및 검색을 용이하게 하기 위해 일관된 명명 규칙을 유지합니다.  
3. **자동 보고** – 예약 작업을 통해 특정 파일 이름으로 보고서를 자동으로 생성합니다.

## 성능 고려 사항

GroupDocs.Viewer를 사용할 때 성능을 최적화하기 위해 다음 사항을 고려하십시오:

- Java에서 효율적인 메모리 관리 방식을 활용합니다.  
- 렌더링 작업 중 리소스 사용량을 모니터링합니다.  
- 시스템 성능에 영향을 주지 않도록 대용량 문서 아카이브를 처리하기 위한 모범 사례를 적용합니다(예: 파일 스트리밍 읽기 및 가능한 경우 `Viewer` 인스턴스 재사용).

## 결론

이 튜토리얼을 통해 GroupDocs.Viewer for Java를 사용하여 **zip을 pdf로 변환**하면서 사용자 지정 파일 이름을 지정하는 방법을 배웠습니다. 이 단계를 따르면 문서 관리 프로세스를 간소화하고 생성된 PDF 전반에 걸쳐 일관성을 보장할 수 있습니다.

### 다음 단계
- GroupDocs.Viewer의 추가 기능(예: HTML, PNG 출력)을 탐색합니다.  
- TAR 또는 7z와 같은 다른 아카이브 유형을 렌더링해 봅니다.  

프로젝트에 이 솔루션을 적용할 준비가 되셨나요? 오늘 바로 시도해 보세요!

## 자주 묻는 질문

**Q: GroupDocs.Viewer for Java를 어떻게 설치하나요?**  
A: Maven을 사용하고 지정된 저장소와 의존성을 `pom.xml`에 추가하십시오.

**Q: PDF 외의 다른 파일 형식에 대한 파일 이름을 지정할 수 있나요?**  
A: 예, GroupDocs.Viewer가 지원하는 다양한 출력 형식에 대해 유사한 옵션이 있습니다.

**Q: 렌더링된 문서 파일 이름이 예상과 다르면 어떻게 해야 하나요?**  
A: 경로 정의를 다시 확인하고 특히 `ArchiveOptions.setPdfFileName`이 올바르게 설정되었는지 모든 구성을 확인하십시오.

**Q: GroupDocs.Viewer로 대용량 아카이브 파일을 처리하려면 어떻게 해야 하나요?**  
A: 메모리 사용을 최적화하고 아카이브를 작은 청크로 처리하거나 스트리밍하여 전체 파일을 메모리에 로드하지 않도록 고려하십시오.

**Q: GroupDocs.Viewer 사용에 대한 추가 리소스를 어디서 찾을 수 있나요?**  
A: 포괄적인 가이드와 API 레퍼런스를 보려면 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)을 방문하십시오.

## 리소스
- **문서**: [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)
- **문서**: [GroupDocs Viewer Java 문서](https://docs.groupdocs.com/viewer/java/)
- **API 레퍼런스**: [GroupDocs Viewer Java 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- **다운로드**: [GroupDocs Viewer 릴리스](https://releases.groupdocs.com/viewer/java/)
- **구매**: [GroupDocs 라이선스 구매](https://purchase.groupdocs.com/buy)
- **무료 체험**: [GroupDocs Viewer 체험](https://releases.groupdocs.com/viewer/java/)
- **임시 라이선스**: [임시 라이선스 받기](https://purchase.groupdocs.com/temporary-license/)
- **지원**: [GroupDocs 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-05-31  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs  

---

## 관련 튜토리얼

- [groupdocs viewer java: 문서를 PDF로 변환 – 완전 가이드](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java에서 라이선스 설정 방법: 파일 및 URL 설정 가이드](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)
- [GroupDocs.Viewer for Java를 사용한 효율적인 PDF 페이지 재정렬 – 포괄적인 가이드](/viewer/java/advanced-rendering/master-pdf-page-reorder-groupdocs-java/)