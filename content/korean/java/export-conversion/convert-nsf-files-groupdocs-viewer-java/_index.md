---
date: '2026-02-13'
description: GroupDocs.Viewer for Java를 사용하여 nsf를 pdf 및 기타 형식(HTML, JPG, PNG)으로 변환하는
  방법을 배웁니다. 이 단계별 가이드는 nsf 파일을 효율적으로 변환하는 방법을 보여줍니다.
keywords:
- GroupDocs.Viewer Java
- NSF Document Conversion
- Convert NSF Files
title: GroupDocs.Viewer for Java를 사용하여 NSF를 PDF, HTML, JPG, PNG로 변환
type: docs
url: /ko/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java를 사용하여 NSF 파일을 여러 형식으로 변환

Java를 사용하여 NSF 문서를 HTML, JPG, PNG, PDF와 같은 다양한 형식으로 변환하는 것은 GroupDocs.Viewer for Java를 통해 간단합니다. **이 튜토리얼에서는 nsf를 pdf로 변환하는 방법**과 기타 유용한 형식들을 보여주며, 설정, 구현 및 모범 사례 팁을 단계별로 안내합니다.

![GroupDocs.Viewer for Java를 사용하여 NSF 파일을 HTML, JPG, PNG 및 PDF로 변환](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## 빠른 답변
- **주요 사용 사례는 무엇인가요?** 웹, 아카이브 또는 공유를 위해 NSF 파일을 PDF, HTML, JPG 또는 PNG로 렌더링합니다.  
- **어떤 라이브러리가 변환을 처리하나요?** GroupDocs.Viewer for Java.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 프로덕션 환경에서는 정식 라이선스가 필요합니다.  
- **필요한 Java 버전은 무엇인가요?** JDK 8 이상.  
- **여러 NSF 파일을 일괄 처리할 수 있나요?** 예 – 렌더링 로직을 루프로 감싸고 try‑with‑resources로 리소스를 관리하면 됩니다.

## “convert nsf to pdf”란 무엇인가요?

NSF(Lotus Notes 데이터베이스) 파일을 PDF로 변환하면 원본 Notes 클라이언트 없이도 모든 기기에서 열 수 있는 정적이며 광범위하게 지원되는 문서가 생성됩니다. 이 변환은 아카이빙, 법적 준수 및 손쉬운 배포에 유용합니다.

## 왜 NSF를 PDF 및 기타 형식으로 변환해야 할까요?

- **범용 접근성:** PDF, HTML, JPG 및 PNG는 사실상 모든 플랫폼에서 읽을 수 있습니다.  
- **레이아웃 보존:** PDF는 원본 페이지 레이아웃, 폰트 및 그래픽을 유지합니다.  
- **웹 통합:** HTML은 추가 플러그인 없이 브라우저에서 빠르게 볼 수 있게 합니다.  
- **이미지 추출:** JPG/PNG는 썸네일, 미리보기 또는 다른 애플리케이션에 삽입하기에 적합합니다.

## 사전 요구 사항

GroupDocs.Viewer for Java를 구현하기 전에 다음 사항을 확인하십시오:

1. **라이브러리 및 종속성:**  
   - Maven(종속성 관리용)  
   - 시스템에 설치된 JDK 8 이상.  

2. **환경 설정:**  
   - Java 프로그래밍에 대한 기본 이해  
   - 프로젝트 설정을 위한 Maven에 대한 친숙함  

3. **지식 사전 요구 사항:**  
   - Java 파일 처리 기본  
   - 문서 변환 개념  

## GroupDocs.Viewer for Java 설정

### Maven 구성

다음 구성을 `pom.xml`에 추가하여 GroupDocs.Viewer를 Java 프로젝트에 포함시킵니다:

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

GroupDocs.Viewer를 사용하려면 다음 중 하나를 선택할 수 있습니다:

- **무료 체험:** 도구의 기본 기능에 접근하여 평가할 수 있습니다.  
- **임시 라이선스:** 전체 기능을 위한 임시 라이선스를 얻을 수 있습니다.  
- **구매:** 프로덕션 환경을 위해 라이선스를 구매하는 것을 고려하십시오.  

### 기본 초기화

다음과 같이 GroupDocs.Viewer를 초기화합니다:

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## NSF를 PDF로 변환하는 방법

다음 섹션에서는 NSF 파일을 HTML, JPG, PNG, **그리고 PDF**로 렌더링하는 방법을 보여줍니다. PDF 예제는 주요 키워드 “convert nsf to pdf”를 직접 만족합니다.

### Rendering NSF to HTML
#### 개요
NSF 문서를 HTML 형식으로 변환하고, HTML 내에 리소스를 삽입하여 웹에서 쉽게 볼 수 있게 합니다.

#### 단계별 가이드

**1. 출력 디렉터리 및 파일 경로 설정**  
출력 HTML 파일을 저장할 위치를 정의합니다.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

**2. 로드 옵션 구성**  
리소스 로드 타임아웃과 같은 특정 옵션으로 로드 프로세스를 맞춤 설정합니다.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

**3. Viewer 초기화 및 렌더링**  
Viewer 클래스를 사용하여 문서를 HTML 형식으로 렌더링합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

### Rendering NSF to JPG
#### 개요
NSF 문서를 고품질 JPG 이미지로 변환하여 공유하거나 이미지 기반 시스템에 통합합니다.

**1. 출력 경로 정의**  
렌더링된 JPG를 저장할 파일 경로 형식을 설정합니다.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

**2. 구성 및 렌더링**  
Viewer를 설정하고 문서를 JPEG 이미지로 렌더링합니다.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

### Rendering NSF to PNG
#### 개요
문서를 PNG 형식으로 렌더링합니다. PNG는 무손실 압축과 높은 해상도로 알려져 있습니다.

**1. 출력 경로 설정**

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

**2. 문서 렌더링**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

### Rendering NSF to PDF
#### 개요
NSF 문서를 PDF 형식으로 변환합니다. PDF는 전 세계적으로 인정받는 문서 표준입니다.

**1. 출력 경로 정의**

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```

**2. PDF로 렌더링**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## 실용적인 적용 사례

1. **웹 기반 문서 공유:** NSF 파일을 HTML로 렌더링하여 웹 플랫폼에서 쉽게 공유합니다.  
2. **이미지 아카이빙:** 문서의 고품질 이미지를 JPG 또는 PNG 형식으로 저장합니다.  
3. **범용 문서 접근:** PDF 변환을 사용하여 모든 기기에서 문서 호환성을 보장합니다.  

## 성능 고려 사항

- **리소스 로드 최적화:** 시스템 성능에 따라 `setResourceLoadingTimeout`을 조정합니다.  
- **메모리 관리:** Viewer 인스턴스를 try‑with‑resources로 적절히 관리하여 효율적인 메모리 사용을 보장합니다.  
- **배치 처리:** 대규모 변환의 경우, 리소스 활용을 관리하기 위해 문서를 배치로 처리하는 것을 고려하십시오.  

## FAQ 섹션

1. **NSF 문서를 변환하기에 가장 좋은 형식은 무엇인가요?**  
   - 필요에 따라 다릅니다: 웹 보기에는 HTML, 범용 접근에는 PDF, 이미지용은 JPG/PNG.  

2. **대용량 NSF 파일을 효율적으로 처리하려면 어떻게 해야 하나요?**  
   - 로드 옵션을 최적화하고 배치 처리하는 것을 고려하십시오.  

3. **이미지 형식의 출력 품질을 맞춤 설정할 수 있나요?**  
   - 예, `JpgViewOptions` 또는 `PngViewOptions` 설정 시 해상도와 같은 매개변수를 조정하면 됩니다.  

4. **변환이 실패하면 어떻게 해야 하나요?**  
   - 파일 경로를 확인하고 Viewer 인스턴스 설정이 올바른지 확인한 뒤, 문제 해결 팁은 GroupDocs 문서를 참고하십시오.  

5. **배치 프로세스에서 이러한 변환을 자동화할 방법이 있나요?**  
   - 물론입니다! 여러 문서에 대해 루프를 구현하면 이 프로세스를 효율적으로 자동화할 수 있습니다.  

## 자주 묻는 질문

**Q: 주석을 잃지 않고 NSF 파일을 PDF로 변환하려면 어떻게 해야 하나요?**  
A: GroupDocs.Viewer는 `PdfViewOptions` 렌더링 단계에서 대부분의 주석을 보존하여 PDF가 원본 레이아웃을 그대로 반영하도록 합니다.

**Q: 비밀번호로 보호된 NSF 파일을 변환할 수 있나요?**  
A: 예. Viewer를 초기화하기 전에 `LoadOptions`를 통해 적절한 자격 증명을 제공하면 됩니다.

**Q: 최상의 성능을 위해 권장되는 Java 버전은 무엇인가요?**  
A: JDK 11 이상은 향상된 가비지 컬렉션 및 동시성 처리를 제공하여 배치 변환에 도움이 됩니다.

**Q: JPG/PNG 출력에 사용자 정의 DPI를 설정할 수 있나요?**  
A: `viewer.view(options)`를 호출하기 전에 `JpgViewOptions` 또는 `PngViewOptions`를 구성하여 DPI를 조정할 수 있습니다.

**Q: GroupDocs.Viewer가 출력 결과를 웹 응답으로 직접 스트리밍하는 것을 지원하나요?**  
A: 예. 파일 경로에 쓰는 대신, view 옵션의 `Stream` 오버로드를 사용하여 결과를 HTTP 응답으로 직접 전송할 수 있습니다.

## 결론

이 가이드는 GroupDocs.Viewer for Java를 사용하여 **nsf를 pdf로 변환** 및 기타 형식으로 변환하는 방법을 살펴보았습니다. 이 단계들을 따르면 애플리케이션에 문서 변환 기능을 원활히 통합할 수 있습니다. GroupDocs.Viewer의 추가 기능을 탐색하고 프로젝트에 통합하여 보다 풍부한 문서 처리를 구현해 보세요.

---

**마지막 업데이트:** 2026-02-13  
**테스트 환경:** GroupDocs.Viewer 25.2  
**작성자:** GroupDocs