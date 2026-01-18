---
date: '2026-01-18'
description: GroupDocs.Viewer for Java를 사용하여 zip을 PDF로 변환하고 아카이브 렌더링 시 사용자 지정 파일 이름을
  설정하는 방법을 배웁니다. 단계별 가이드에서는 설정, Maven 통합 및 PDF 출력 이름을 제어하는 코드를 다룹니다.
keywords:
- GroupDocs.Viewer Java
- custom filenames PDF rendering
- archive files to PDF
title: 'GroupDocs.Viewer Java로 zip을 PDF로 변환: 사용자 지정 파일명'
type: docs
url: /ko/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/
weight: 1
---

# GroupDocs.Viewer Java 마스터하기: 아카이브를 PDF로 렌더링할 때 사용자 지정 파일명 지정

ZIP 아카이브를 PDF 파일로 변환하는 것은 문서를 보편적으로 읽을 수 있는 형식으로 공유하거나 보관해야 할 때 흔히 수행되는 작업입니다. 이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 **zip을 pdf로 변환하는 방법**을 배우면서 출력 파일명을 여러분의 명명 규칙에 맞게 제어하는 방법을 알아봅니다.

![GroupDocs.Viewer for Java를 사용한 아카이브 PDF 렌더링을 위한 사용자 지정 파일명](/viewer/advanced-rendering/custom-filenames-for-pdf-rendering-of-archives-java.png)

**배우게 될 내용:**
- GroupDocs.Viewer for Java 설정
- 지정된 파일명으로 아카이브 파일을 PDF로 렌더링
- 사용자 지정 파일명 기능의 실용적인 적용 사례
- 성능 최적화를 위한 모범 사례

환경을 설정하고 GroupDocs.Viewer가 문서 렌더링에 강력한 도구가 되는 핵심 기능을 살펴보면서 시작해 보겠습니다.

## Quick Answers
- **주요 사용 사례는 무엇인가요?** 사용자 지정 출력 이름으로 ZIP 아카이브를 PDF로 변환합니다.  
- **필요한 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java (v25.2 이상).  
- **라이선스가 필요한가요?** 평가용으로는 트라이얼 또는 임시 라이선스로 충분하지만, 프로덕션에서는 구매 라이선스가 필요합니다.  
- **다른 형식의 파일명도 변경할 수 있나요?** 예, HTML, PNG 등 다른 출력 형식에도 유사한 옵션이 있습니다.  
- **Maven이 유일한 설치 방법인가요?** Maven이 권장되지만 JAR 파일을 직접 사용할 수도 있습니다.

## “convert zip to pdf”란?

ZIP 아카이브를 단일 PDF 문서로 변환하면 아카이브 내부에 포함된 모든 지원 파일(DOCX, PPTX, 이미지 등)을 하나의 휴대용 파일로 병합합니다. 이를 통해 배포가 간편해지고 플랫폼 간 일관된 렌더링을 보장하며, 조직의 명명 표준에 맞는 사용자 지정 파일명을 적용할 수 있습니다.

## 이 작업에 GroupDocs.Viewer를 사용하는 이유

GroupDocs.Viewer는 아카이브 내부의 다양한 파일 형식을 처리하는 복잡성을 추상화하는 고수준 API를 제공합니다. 또한 **ArchiveOptions**를 통해 정확한 PDF 파일명을 지정할 수 있어 배치 처리와 자동화 워크플로를 훨씬 깔끔하게 만들 수 있습니다.

## Prerequisites

시작하기 전에 다음 항목을 확인하세요.

### Required Libraries and Dependencies
- **GroupDocs.Viewer for Java**: 버전 25.2 이상.

### Environment Setup Requirements
- JDK(Java Development Kit)가 설치되어 있어야 합니다.
- IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용해 Java 애플리케이션을 개발합니다.

### Knowledge Prerequisites
- Java 프로그래밍에 대한 기본 이해
- Maven을 빌드 자동화 도구로 사용하는 경험

위 전제 조건을 모두 갖췄다면, 이제 GroupDocs.Viewer for Java 설정을 진행합니다.

## Setting Up GroupDocs.Viewer for Java

### Installation via Maven

Maven을 사용해 프로젝트에 GroupDocs.Viewer를 통합하려면 `pom.xml` 파일에 다음 저장소와 의존성을 추가합니다:

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
- **Free Trial**: 기능을 평가할 수 있는 완전한 트라이얼 버전을 사용합니다.
- **Temporary License**: 제한 없이 장기간 평가할 수 있는 라이선스를 획득합니다.
- **Purchase**: 상업적 사용을 위한 라이선스를 구매합니다.

#### Basic Initialization and Setup

Maven 설정이 완료되면 다음 코드 스니펫으로 GroupDocs.Viewer를 초기화합니다:

```java
import com.groupdocs.viewer.Viewer;
// Initialize viewer object
try (Viewer viewer = new Viewer("YOUR_ARCHIVE_FILE_PATH")) {
    // Configure options here
} catch (Exception e) {
    e.printStackTrace();
}
```

## Implementation Guide

이제 **zip을 pdf로 변환**하면서 사용자 지정 파일명을 지정하는 방법에 집중해 보겠습니다.

### How to convert zip to pdf with custom filenames

이 기능을 사용하면 렌더링된 PDF 문서의 출력 파일명을 자유롭게 지정할 수 있습니다. 단계별로 살펴보세요.

#### Step 1: Define Output Directory and File Path

플레이스홀더를 활용해 출력 디렉터리와 파일 경로를 설정합니다:

```java
import java.nio.file.Path;
// Define output directory and file path
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path outputFilePath = outputDirectory.resolve("output.pdf");
```

#### Step 2: Initialize Viewer Object

렌더링하려는 아카이브 파일을 사용해 `Viewer` 객체를 생성합니다:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP")) {
    // Continue to next steps
} catch (Exception e) {
    e.printStackTrace();
}
```

#### Step 3: Create PdfViewOptions

렌더링 구성을 지정하기 위해 `PdfViewOptions`를 설정합니다:

```java
import com.groupdocs.viewer.options.PdfViewOptions;
// Configure PDF view options
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
```

#### Step 4: Set Custom Filename

`ArchiveOptions`를 사용해 렌더링된 PDF 문서의 사용자 지정 파일명을 지정합니다:

```java
import com.groupdocs.viewer.options.FileName;
import com.groupdocs.viewer.options.ArchiveOptions;
// Specify the output PDF filename
viewOptions.getArchiveOptions().setFileName(new FileName("my_custom_filename.pdf"));
```

#### Step 5: Render Archive File to PDF

지정한 옵션을 적용해 아카이브 파일을 PDF로 렌더링합니다:

```java
// Execute rendering process
viewer.view(viewOptions);
```

### Troubleshooting Tips
- 모든 경로가 올바르게 설정되고 디렉터리가 존재하는지 확인하세요.
- 사용 중인 GroupDocs.Viewer 버전이 정확한지 검증하세요.

## Practical Applications

**zip을 pdf로 변환**하고 사용자 지정 파일명을 설정하는 것이 다음과 같은 시나리오에서 유용합니다:
1. **브랜딩 일관성** – 여러 문서에 걸쳐 브랜드 목적의 파일명을 맞춤 설정합니다.  
2. **조직 효율성** – 일관된 명명 규칙을 유지해 문서 관리와 검색을 용이하게 합니다.  
3. **자동 보고서** – 예약 작업을 통해 특정 파일명을 가진 보고서를 자동으로 생성합니다.

## Performance Considerations

GroupDocs.Viewer를 사용할 때 성능을 최적화하려면 다음 사항을 고려하세요:
- Java에서 효율적인 메모리 관리 방식을 적용합니다.
- 렌더링 작업 중 리소스 사용량을 모니터링합니다.
- 대용량 문서 아카이브를 처리할 때 시스템 성능에 영향을 주지 않도록 최선의 방법을 적용합니다.

## Conclusion

이 튜토리얼을 통해 GroupDocs.Viewer for Java를 사용해 **zip을 pdf로 변환**하면서 사용자 지정 파일명을 지정하는 방법을 배웠습니다. 이 절차를 따르면 문서 관리 프로세스를 간소화하고 생성된 PDF의 일관성을 유지할 수 있습니다.

### Next Steps
- GroupDocs.Viewer의 추가 기능(예: HTML, PNG 출력)을 탐색합니다.  
- TAR 또는 7z와 같은 다른 아카이브 유형 렌더링을 실험해 봅니다.  

프로젝트에 이 솔루션을 적용해 보시겠습니까? 오늘 바로 시도해 보세요!

## Frequently Asked Questions

**Q: GroupDocs.Viewer for Java를 어떻게 설치하나요?**  
A: Maven을 사용하고 `pom.xml`에 지정된 저장소와 의존성을 추가합니다.

**Q: PDF 외에 다른 파일 형식에도 파일명을 지정할 수 있나요?**  
A: 예, GroupDocs.Viewer가 지원하는 다양한 출력 형식에 대해 유사한 옵션이 제공됩니다.

**Q: 렌더링된 문서 파일명이 기대와 다르면 어떻게 해야 하나요?**  
A: 경로 정의를 다시 확인하고 모든 설정이 올바르게 적용되었는지 점검합니다.

**Q: 대용량 아카이브 파일을 처리하려면 어떻게 해야 하나요?**  
A: 메모리 사용을 최적화하고 큰 파일을 작은 청크로 나누어 처리하는 방안을 고려합니다.

**Q: GroupDocs.Viewer에 대한 추가 자료는 어디서 찾을 수 있나요?**  
A: 포괄적인 가이드와 API 레퍼런스는 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)을 참고하세요.

## Resources
- **Documentation**: [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs Viewer Java Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Releases](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Try GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs