---
date: '2026-01-18'
description: GroupDocs.Viewer for Java를 사용하여 zip을 PDF로 변환하고 아카이브 렌더링 시 사용자 지정 파일 이름을
  설정하는 방법을 배웁니다. 단계별 가이드에서는 설정, Maven 통합 및 PDF 출력 이름을 제어하는 코드를 다룹니다.
keywords:
- GroupDocs.Viewer Java
- custom filenames PDF rendering
- archive files to PDF
title: 'GroupDocs.Viewer Java로 zip을 PDF로 변환 - 사용자 지정 파일명'
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

## 빠른 답변
- **주요 국가는 무엇입니까?** 사용자 지정 출력으로 ZIP 아카이브를 PDF로 변환합니다.
- **필요한 클래스는 무엇입니까?** GroupDocs.Viewer for Java(v25.2 이상).
- **라이선스가 필요한 가요?** 평가용 파워 파워 또는 파워만으로 충분하지만, 내부적으로는 구매 파워가 필요합니다.
- **다른 형식의 파일명도 부품이 있습니까?** 예, HTML, PNG 등 다른 형식에도 적용할 수 있습니다.
- **Maven이 유일한 설치 방법입니까?** Maven이 지원하는 JAR 파일을 직접 사용할 수도 있습니다.

## “zip을 pdf로 변환”란?

ZIP 아카이브를 단일 PDF 문서로 변환하면 아카이브 내부에 포함된 모든 지원 파일(DOCX, PPTX, 이미지 등)을 하나의 휴대용 파일로 압축합니다. 이를 통해 배포가 분할되기 플랫폼 간 서버를 가리키며, 조직의 그룹 표준에 사용자 지정 파일명을 적용할 수 있습니다.

## 이 작업에 GroupDocs.Viewer를 사용하는 이유

GroupDocs.Viewer는 아카이브 내부의 다양한 파일 형식을 처리하는 제거를 추상화하는 수준 높은 API를 제공합니다. **ArchiveOptions**를 통해 충분히 PDF 파일명을 확인할 수 있어 배치 처리와 작업 플로어를 훨씬 깔끔하게 만들 수 있습니다.

## 전제조건

시작하기 전에 다음 항목을 확인하세요.

### 필수 라이브러리 및 종속성
- **Java용 GroupDocs.Viewer**: 버전 25.2 이상.

### 환경 설정 요구 사항
- JDK(Java Development Kit)가 설치되어 있어야 합니다.
- IntelliJ IDEA 또는 Eclipse와 같은 IDE를 활용하여 Java 제작을 개발합니다.

### 지식 전제조건
- Java 프로그래밍에 대한 기본 이해
- Maven을 구축하는 도구를 사용하는 환경

이제 조건을 모두 포함한다면, 이제 Java용 GroupDocs.Viewer 설정을 처리합니다.

## Java용 GroupDocs.Viewer 설정

### Maven을 통한 설치

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

### 라이선스 취득 단계
- **무료 평가판**: 기능을 평가할 수 있는 완전한 기능 버전을 사용합니다.
- **임시 라이선스**: 제한 없이 별도로 평가할 수 있는 능력을 획득합니다.
- **구매**: 사용을 기념하여 구매합니다.

#### 기본 초기화 및 설정

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

## 구현 가이드

이제 **zip을 pdf로 변환**하면서 사용자 지정 파일명을 목적지에 집어넣는 방법입니다.

### 사용자 정의 파일 이름을 사용하여 zip을 pdf로 변환하는 방법

이 문서를 사용하면 PDF 문서의 출력 파일명을 사용할 수 있습니다. 계속해서 살펴보세요.

#### 1단계: 출력 디렉터리 및 파일 경로 정의

플레이스홀더를 활용해 출력 디렉터리와 파일 경로를 설정합니다:

```java
import java.nio.file.Path;
// Define output directory and file path
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path outputFilePath = outputDirectory.resolve("output.pdf");
```

#### 2단계: 뷰어 객체 초기화

렌더링하려는 아카이브 파일을 사용해 `Viewer` 객체를 생성합니다:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP")) {
    // Continue to next steps
} catch (Exception e) {
    e.printStackTrace();
}
```

#### 3단계: PdfViewOptions 생성

렌더링 구성을 지정하기 위해 `PdfViewOptions`를 설정합니다:

```java
import com.groupdocs.viewer.options.PdfViewOptions;
// Configure PDF view options
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
```

#### 4단계: 사용자 지정 파일 이름 설정

`ArchiveOptions`를 사용해 렌더링된 PDF 문서의 사용자 지정 파일명을 지정합니다:

```java
import com.groupdocs.viewer.options.FileName;
import com.groupdocs.viewer.options.ArchiveOptions;
// Specify the output PDF filename
viewOptions.getArchiveOptions().setFileName(new FileName("my_custom_filename.pdf"));
```

#### 5단계: 압축 파일을 PDF로 렌더링

지정한 옵션을 적용해 아카이브 파일을 PDF로 렌더링합니다:

```java
// Execute rendering process
viewer.view(viewOptions);
```

### 문제 해결 팁
- 모든 도로가 설정되고 존재하도록 확인하세요.
- GroupDocs.Viewer를 사용하면서 검증하시기 바랍니다.

## 실제 적용

**zip을 pdf로 변환**하고 사용자 파일명을 설정하는 것이 다음과 같은 시나리오에서 유용합니다:
1. **브랜딩 일관성** – 다양한 문서에 모양을 만드는 목적의 파일명을 맞춤 설정합니다.
2. **조직 관계** – 이해하기 쉬운 규칙을 유지해 문서를 관리하고 검색을 용이하게 해주세요.
3. **자동 보고서** – 예약 작업을 통해 특정 파일명에 대한 제안을 자동으로 생성합니다.

## 성능 고려 사항

GroupDocs.Viewer를 사용할 때 성능을 최적화하려면 다음 사항을 고려하세요.
- Java의 효율적인 메모리 관리 방식을 적용합니다.
- 작업 중 페인트를 모니터링합니다.
- 데스크탑 클라이언트를 처리할 때 시스템 성능에 영향을 미치도록 최선을 다하는 방법을 적용합니다.

## 결론

이 튜토리얼을 통해 Java용 GroupDocs.Viewer를 사용하여 **zip을 pdf로 변환**하면서 사용자 파일명을 체크인하는 방법을 배웠습니다. 이 프로세스는 문서 관리 프로세스를 처리하고 생성된 PDF의 일관성을 유지할 수 있음을 설명합니다.

### 다음 단계
- GroupDocs.Viewer의 추가 기능(예: HTML, PNG 출력)을 검사합니다.
- TAR 또는 7z와 같은 보호를 위해 실험해 보겠습니다.

프로젝트에 이 솔루션을 적용할 생각이 있으신가요? 지금 바로 시작하세요!

## 자주 묻는 질문

**Q: GroupDocs.Viewer for Java를 어떻게 설치했나요?**
A: Maven을 사용하고 `pom.xml`에 응답하고 의존성을 추가합니다.

**Q: PDF 형식의 파일 형식에도 파일명을 사용할 수 있습니까?**
A: 예, GroupDocs.Viewer가 지원하는 다양한 형식에 대해 설명합니다.

**Q: 위임된 문서를 관계자와 다르면 어떻게 하고 싶습니까?**
A: 정의된 위치를 다시 확인하고 모든 설정이 조정되도록 해야 합니다.

**Q: 보관 파일을 처리하려면 어떻게 해야 합니까?**
A: 메모리 사용을 최적화하고 큰 파일을 작은 청크로 나누어 처리하는 것을 고려합니다.

**Q: GroupDocs.Viewer에 대한 추가 자료는 반대 품목이 있습니까?**
A: 전체적인 가이드와 API 반대는 [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)를 참고하세요.

## 리소스
- **문서**: [GroupDocs Viewer Java 문서](https://docs.groupdocs.com/viewer/java/)
- **API 참조**: [GroupDocs Viewer Java 참조](https://reference.groupdocs.com/viewer/java/)
- **다운로드**: [GroupDocs Viewer 릴리스](https://releases.groupdocs.com/viewer/java/)
- **구매**: [GroupDocs 라이선스 구매](https://purchase.groupdocs.com/buy)
- **무료 체험**: [GroupDocs Viewer 체험하기](https://releases.groupdocs.com/viewer/java/)
- **임시 라이선스**: [임시 라이선스 받기](https://purchase.groupdocs.com/temporary-license/)
- **지원**: [GroupDocs [포럼](https://forum.groupdocs.com/c/viewer/9)

---

**최종 업데이트:** 2026년 1월 18일
**테스트 환경:** GroupDocs.Viewer 25.2 for Java
**제작자:** GroupDocs