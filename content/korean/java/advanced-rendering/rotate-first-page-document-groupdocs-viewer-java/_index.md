---
date: '2026-03-29'
description: GroupDocs Viewer를 사용하여 Java에서 페이지를 90도 회전하는 방법을 배우세요. 설정, 코드 및 성능 팁을
  포함합니다.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: GroupDocs Viewer for Java를 사용하여 페이지를 90도 회전하기
type: docs
url: /ko/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Java로 페이지를 90도 회전하기

문서에서 **rotate page 90 degrees**를 해야 할 때—PDF, Word 파일, 스프레드시트 등—프로그래밍 방식으로 수행하면 시간을 절약하고 수동 오류를 없앨 수 있습니다. 이 고급 가이드에서는 **GroupDocs Viewer for Java**를 사용하여 지원되는 모든 문서의 첫 페이지를 회전하는 정확한 단계를 안내합니다. 끝까지 읽으면 자체 프로젝트에 삽입할 수 있는 재사용 가능한 스니펫을 얻게 됩니다.  
또한 Java에서 페이지를 회전하는 이유, 이 기술이 빛을 발하는 일반적인 시나리오, 그리고 작업을 가볍게 유지하는 방법에 대해서도 논의합니다.

![GroupDocs.Viewer for Java로 문서의 첫 페이지 회전](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## 빠른 답변
- **rotate page 90 degrees**는 무엇을 의미합니까? 선택한 페이지를 시계 방향으로 90도(한 사분면) 회전합니다.  
- **Which library handles the rotation?** 회전을 처리하는 라이브러리는 GroupDocs Viewer for Java이며, `rotatePage` 메서드를 제공합니다.  
- **Can I rotate PDF pages with Java?** 예—동일한 `rotatePage` 호출을 사용하면 PDF, DOCX, XLSX 등에서 작동합니다.  
- **Do I need a license?** 무료 체험은 개발에 사용할 수 있으며, 프로덕션에는 유료 라이선스가 필요합니다.  
- **Is the operation memory‑intensive?** `Viewer` 인스턴스를 즉시 닫으면 메모리 사용이 많지 않습니다; 아래 성능 팁을 참고하십시오.

## “rotate page 90 degrees”란 무엇입니까?
페이지를 90도 회전하면 기본 콘텐츠를 변경하지 않고 페이지를 세로에서 가로(또는 그 반대)로 재배치합니다. 이는 프레젠테이션, 가로 전용 그래픽 인쇄, 또는 가로로 촬영된 스캔 문서를 수정할 때 특히 유용합니다.

## 왜 GroupDocs Viewer for Java로 페이지를 프로그래밍 방식으로 회전해야 할까요?
GroupDocs Viewer는 수십 가지 파일 형식을 처리하는 복잡성을 추상화합니다. 원본 파일을 그대로 유지하면서 회전과 같은 페이지 수준 변환을 적용할 수 있습니다. API는 유창하고 스레드 안전하며 Java 8+ 런타임에서 작동하므로 엔터프라이즈 수준 자동화에 신뢰할 수 있는 선택입니다.

## 필수 조건

- **GroupDocs.Viewer for Java** (최신 버전)
- **JDK 8** 이상
- **Maven** (또는 Gradle) – 의존성 관리용
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
- **Free trial** – GroupDocs 사이트에서 다운로드합니다.  
- **Temporary license** – 평가 기간을 연장하려면 요청합니다.  
- **Full license** – 프로덕션 배포를 위해 구매합니다.

### 기본 Viewer 초기화
다음 코드는 `Viewer` 인스턴스를 생성하는 최소 방법을 보여줍니다. 표시된 대로 정확히 유지하십시오:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer를 사용하여 Java에서 PDF 페이지 회전하기
API가 여러 형식에서 작동하지만, PDF가 페이지 회전의 가장 일반적인 사용 사례입니다. 동일한 `rotatePage` 메서드를 사용하므로 Viewer에 PDF 파일을 지정하고 페이지 번호만 지정하면 됩니다.

## 단계별 구현: 첫 페이지를 90도 회전하기

### 1. 필요한 패키지 가져오기
이 가져오기를 통해 PDF 렌더링 옵션 및 회전 열거형에 접근할 수 있습니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 출력 위치 정의 및 Viewer 생성
플레이스홀더 경로를 실제 디렉터리 경로로 교체하십시오.

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

### 3. PDF 보기 옵션 구성 및 회전 적용
`rotatePage` 메서드는 페이지 번호(1부터 시작)와 `Rotation` 열거형 값을 받습니다.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. 문서 렌더링
마지막으로 `view`를 호출하여 회전된 PDF를 생성합니다.

```java
viewer.view(viewOptions);
```

#### 작동 방식
- **PdfViewOptions**는 Viewer에게 PDF 파일을 출력하도록 지시합니다.  
- **rotatePage(int, Rotation)**은 지정한 페이지만 회전시키고 나머지는 그대로 둡니다.  
- 이 메서드는 `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`를 지원합니다.

## 일반적인 문제 및 해결책

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| **FileNotFoundException** | 잘못된 경로나 폴더가 없습니다 | `YOUR_OUTPUT_DIRECTORY`와 `YOUR_DOCUMENT_DIRECTORY`가 존재하고 읽을 수 있는지 확인하십시오. |
| **Unsupported file format** | Viewer에서 지원하지 않는 형식을 회전하려고 시도함 | 다음 페이지에서 [GroupDocs Viewer supported formats]를 확인하십시오. |
| **No rotation visible** | 잘못된 페이지 번호(0부터 시작)를 사용함 | `rotatePage`는 **1‑기반** 인덱싱을 사용한다는 점을 기억하십시오. |
| **Out‑of‑memory errors on large docs** | 단일 스레드에서 많은 대용량 파일을 렌더링함 | 문서를 순차적으로 처리하거나 제한된 동시성을 가진 스레드 풀을 사용하십시오. |

## 실용적인 적용 사례

1. **Presentation adjustments** – 실시간으로 세로 슬라이드를 가로로 변환합니다.  
2. **Bulk document correction** – 가로로 촬영된 스캔 PDF를 자동으로 수정합니다.  
3. **Print‑ready output** – 가로 그래픽이 세로 용지에 올바르게 인쇄되도록 보장합니다.

## 성능 팁

- **Close resources promptly** – `try‑with‑resources` 블록은 `Viewer`를 자동으로 해제합니다.  
- **Batch processing** – 많은 파일을 처리할 때 스레드당 하나의 `Viewer` 인스턴스를 재사용하여 오버헤드를 줄입니다.  
- **Monitor memory** – 100 MB보다 큰 문서는 메모리에 유지하는 대신 출력 스트림을 디스크에 기록하는 것을 고려하십시오.

## 자주 묻는 질문

**Q: 여러 페이지를 한 번에 회전할 수 있나요?**  
A: 예—회전해야 하는 각 페이지 번호에 대해 `rotatePage()`를 호출하면 됩니다.

**Q: 렌더링 후 회전을 취소할 방법이 있나요?**  
A: 직접적인 방법은 없습니다. 회전 옵션 없이 문서를 다시 렌더링해야 합니다.

**Q: GroupDocs Viewer에서 페이지 회전을 지원하는 파일 형식은 무엇입니까?**  
A: 공식 문서에 나열된 DOCX, PDF, PPTX, XLSX 및 기타 많은 형식이 지원됩니다.

**Q: 여러 문서 배치를 자동으로 회전하려면 어떻게 해야 하나요?**  
A: 파일 경로 컬렉션을 순회하는 루프에 코드를 감싸고 각 파일에 동일한 `rotatePage` 로직을 적용하면 됩니다.

**Q: 회전 중 오류를 처리하기 위한 모범 사례는 무엇입니까?**  
A: `Viewer` 사용을 `try‑catch` 블록으로 감싸고 예외를 로그에 기록한 뒤, 필요에 따라 다음 파일 처리를 계속합니다.

## 리소스

- **문서**: [GroupDocs Viewer Java 문서](https://docs.groupdocs.com/viewer/java/)  
- **API 레퍼런스**: [GroupDocs API 레퍼런스](https://reference.groupdocs.com/viewer/java/)  
- **다운로드**: [GroupDocs Viewer for Java 다운로드](https://releases.groupdocs.com/viewer/java/)  
- **구매**: [라이선스 구매](https://purchase.groupdocs.com/buy)  
- **무료 체험**: [무료 체험](https://releases.groupdocs.com/viewer/java/)  
- **임시 라이선스**: [임시 라이선스 요청](https://purchase.groupdocs.com/temporary-license/)  
- **지원**: [GroupDocs 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-03-29  
**테스트 환경:** GroupDocs Viewer 25.2 for Java  
**작성자:** GroupDocs