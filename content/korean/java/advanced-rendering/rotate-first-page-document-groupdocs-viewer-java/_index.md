---
date: '2026-09-30'
description: GroupDocs Viewer를 사용하여 Java에서 페이지를 90도 회전하는 방법을 배우세요. 설정, 코드 및 성능 팁을
  포함합니다.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: GroupDocs Viewer를 사용하여 Java에서 페이지를 90도 회전합니다. 단계별 가이드, 성능 팁 및 개발자를
  위한 실제 사용 사례.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: GroupDocs Viewer for Java를 사용하여 페이지를 90도 회전하기
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: GroupDocs Viewer for Java를 사용하여 페이지를 90도 회전하기
type: docs
url: /ko/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# GroupDocs Viewer for Java로 페이지를 90도 회전하기

문서에서 **페이지를 90도 회전**해야 할 경우—PDF, Word 파일, 스프레드시트 여부와 관계없이—Java로 프로그래밍하면 시간을 절약하고 수동 오류를 제거하며 작업을 자동 파이프라인에 삽입할 수 있습니다. 이 고급 가이드에서는 **GroupDocs Viewer for Java**를 사용하여 지원되는 모든 문서의 첫 페이지를 회전하는 방법, 이 기능이 실제 프로젝트에서 왜 중요한지, 그리고 프로세스를 가볍고 메모리 효율적으로 유지하는 방법을 배웁니다.

![GroupDocs.Viewer for Java로 문서의 첫 페이지 회전](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## 빠른 답변
- **“rotate page 90 degrees”는 무엇을 의미하나요?** 선택한 페이지를 시계 방향으로 90도(¼ 회전) 회전합니다.  
- **어떤 라이브러리가 회전을 처리하나요?** GroupDocs Viewer for Java가 `rotatePage` 메서드를 제공합니다.  
- **Java로 PDF 페이지를 회전할 수 있나요?** 예—동일한 `rotatePage` 호출을 사용하면 PDF, DOCX, XLSX 등에서도 작동합니다.  
- **라이선스가 필요합니까?** 개발용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 유료 라이선스가 필요합니다.  
- **작업이 메모리를 많이 사용하나요?** `Viewer` 인스턴스를 즉시 닫으면 메모리 사용량이 많지 않습니다; 아래 성능 팁을 참고하세요.

## “rotate page 90 degrees”란 무엇인가요?
페이지를 90도 회전하면 기본 콘텐츠를 변경하지 않고 페이지를 세로 방향에서 가로 방향(또는 그 반대)으로 재배치합니다. 이는 프레젠테이션, 가로 전용 그래픽 인쇄, 또는 옆으로 스캔된 문서를 바로잡을 때 유용합니다. 회전은 렌더링 시에 적용되며 원본 파일은 변경되지 않습니다.

## GroupDocs Viewer for Java로 페이지를 프로그래밍 방식으로 회전하는 이유는?
GroupDocs Viewer는 **50개 이상의 입력 및 출력 형식**을 지원합니다—PDF, DOCX, PPTX, XLSX 및 다양한 이미지 형식을 포함—따라서 외부 변환기 없이도 모든 문서를 렌더링할 수 있습니다. API는 유창하고 스레드‑안전하며 Java 8+ 런타임에서 실행되어, 수십 가지 파일 유형을 일관되게 처리해야 하는 엔터프라이즈급 자동화에 신뢰할 수 있는 선택입니다.

## 사전 요구 사항
- GroupDocs Viewer for Java (최신 버전)
- JDK 8 이상
- Maven(또는 Gradle) 의존성 관리
- IntelliJ IDEA 또는 Eclipse와 같은 IDE
- Java I/O에 대한 기본 지식

## GroupDocs.Viewer for Java 설정
GroupDocs 저장소와 의존성을 `pom.xml`에 추가합니다. 이 스니펫은 원본 튜토리얼과 동일합니다:

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
- **무료 체험** – GroupDocs 사이트에서 다운로드합니다.  
- **임시 라이선스** – 평가 기간을 연장해야 할 경우 요청합니다.  
- **전체 라이선스** – 프로덕션 배포를 위해 구매합니다.

### 기본 Viewer 초기화
`Viewer` 클래스는 문서를 로드하고 렌더링 및 변환 메서드를 제공하는 진입점입니다. 코드는 아래와 같이 그대로 유지하십시오:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer로 Java에서 PDF 페이지 회전하기
`Viewer`로 대상 파일을 로드하고 페이지 번호를 지정한 뒤 `rotatePage`를 호출합니다. 이 메서드는 PDF, DOCX, PPTX, XLSX 및 라이브러리가 지원하는 모든 형식에서 작동합니다. 회전 후에는 문서를 새 PDF로 렌더링하거나 클라이언트에 직접 스트리밍할 수 있어 원본 파일은 그대로 유지됩니다.

## 단계별 구현: 첫 페이지를 90도 회전하기

### 1. 필요한 패키지 가져오기
`PdfViewOptions`는 Viewer가 PDF 파일을 출력하도록 지정하고, `Rotation` 열거형은 각도를 정의합니다. 두 클래스 모두 `com.groupdocs.viewer.options` 패키지에 속합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 출력 위치 정의 및 Viewer 생성
플레이스홀더 경로를 실제 디렉터리로 교체하십시오. `Viewer` 생성자는 소스 문서를 가리키는 `File` 객체를 받습니다.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF 뷰 옵션 구성 및 회전 적용
`rotatePage(int, Rotation)` 메서드는 **1‑기반** 페이지 인덱스와 `Rotation` 열거형 값을 받습니다. 이 예제에서는 첫 페이지를 시계 방향으로 회전하기 위해 `Rotation.ON_90_DEGREE`를 사용합니다.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. 문서 렌더링
구성된 옵션으로 `view`를 호출하면 회전된 PDF가 출력 폴더에 기록됩니다.

```java
viewer.view(viewOptions);
```

#### 작동 원리
- **PdfViewOptions**는 Viewer가 PDF 출력 파일을 생성하도록 지정합니다.  
- **rotatePage(int, Rotation)**은 지정된 페이지만 회전시키고 다른 페이지는 그대로 유지합니다.  
- 이 메서드는 세 가지 회전 상수를 지원합니다: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.

## 일반적인 문제 및 해결책
| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| **FileNotFoundException** | 경로가 잘못되었거나 폴더가 없음 | `YOUR_OUTPUT_DIRECTORY`와 `YOUR_DOCUMENT_DIRECTORY`가 존재하고 읽을 수 있는지 확인하십시오. |
| **Unsupported file format** | Viewer가 지원하지 않는 형식을 회전하려고 함 | [GroupDocs Viewer supported formats] 페이지를 확인하십시오. |
| **No rotation visible** | 잘못된 페이지 번호 사용(0‑기반) | `rotatePage`는 **1‑기반** 인덱스를 사용한다는 점을 기억하십시오. |
| **Out‑of‑memory errors on large docs** | 단일 스레드에서 많은 대용량 파일을 렌더링 | 문서를 순차적으로 처리하거나 제한된 동시성을 가진 스레드 풀을 사용하십시오. |

## 실용적인 적용 사례
1. **프레젠테이션 조정** – 세로 슬라이드를 가로로 실시간 변환하여 시각적 효과를 향상시킵니다.  
2. **대량 문서 교정** – 옆으로 스캔된 PDF를 자동으로 수정하여 수시간의 수작업을 절감합니다.  
3. **인쇄 준비 출력** – 가로 그래픽이 세로 용지에 올바르게 인쇄되도록 하여 프린터 드라이버에서 수동 회전을 할 필요가 없습니다.

## 성능 팁
- **리소스를 즉시 닫기** – `try‑with‑resources` 블록은 `Viewer`를 자동으로 해제하여 메모리를 해제합니다.  
- **배치 처리** – 스레드당 하나의 `Viewer` 인스턴스를 재사용하여 초기화 오버헤드를 줄입니다.  
- **메모리 모니터링** – 100 MB보다 큰 문서는 전체 파일을 메모리에 보관하지 말고 디스크로 스트리밍하십시오; GroupDocs Viewer는 200 MB 파일을 250 MB 이하 RAM으로 처리할 수 있습니다.

## 자주 묻는 질문
**Q: 여러 페이지를 한 번에 회전할 수 있나요?**  
A: 예—회전해야 할 각 페이지 번호에 대해 `rotatePage()`를 호출하면 됩니다. 루프에서 호출하거나 체인 방식으로 사용할 수 있습니다.

**Q: 렌더링 후 회전을 취소할 방법이 있나요?**  
A: 직접적인 방법은 없습니다. 회전 옵션 없이 문서를 다시 렌더링해야 합니다.

**Q: GroupDocs Viewer에서 페이지 회전을 지원하는 파일 형식은 무엇인가요?**  
A: DOCX, PDF, PPTX, XLSX 및 공식 문서에 나열된 기타 많은 형식이 지원됩니다.

**Q: 문서 배치를 자동으로 회전하려면 어떻게 해야 하나요?**  
A: 파일 경로 컬렉션을 순회하는 루프에 회전 로직을 감싸서 각 파일에 동일한 `rotatePage` 구성을 적용합니다.

**Q: 회전 중 오류를 처리하기 위한 모범 사례는 무엇인가요?**  
A: `Viewer` 사용을 `try‑catch` 블록으로 감싸고 예외 세부 정보를 로그에 기록하며, 필요에 따라 다음 파일 처리를 계속 진행하여 단일 실패가 전체 배치를 중단하지 않도록 합니다.

## 리소스
- **문서**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 참조**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **다운로드**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **구매**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **무료 체험**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **임시 라이선스**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **지원**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-09-30  
**테스트 환경:** GroupDocs Viewer 25.2 for Java  
**작성자:** GroupDocs

## 관련 튜토리얼
- [GroupDocs.Viewer for Java로 특정 PDF 페이지 회전하기](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Java에서 URL로 문서 로드 – GroupDocs.Viewer 튜토리얼](/viewer/java/document-loading/)
- [GroupDocs Viewer Java 문서 보기](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)