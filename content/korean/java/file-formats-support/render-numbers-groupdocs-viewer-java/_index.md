---
date: '2026-03-05'
description: GroupDocs.Viewer for Java를 사용하여 숫자를 PDF 및 HTML, JPG, PNG와 같은 다른 형식으로
  변환하는 방법을 배웁니다. 이 가이드는 설정, 렌더링 기술 및 실용적인 적용 사례를 다룹니다.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: GroupDocs.Viewer for Java를 사용하여 Numbers를 PDF로 변환하기
type: docs
url: /ko/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Numbers를 PDF(및 기타 형식)로 변환하기, GroupDocs.Viewer for Java와 함께

Apple Numbers 문서를 웹이나 데스크톱 애플리케이션에 표시하는 것은 까다로울 수 있습니다, 특히 **convert numbers to pdf**를 수행하거나 이미지로 삽입해야 할 때 더욱 그렇습니다. 이 튜토리얼에서는 **GroupDocs.Viewer for Java**를 사용하여 Numbers 파일을 HTML, JPG, PNG, **및 PDF**로 렌더링하는 방법을 단계별로 안내합니다—스프레드시트를 공유, 미리 보기 또는 보관하기 위한 유연한 옵션을 제공합니다.

![GroupDocs.Viewer for Java로 Apple Numbers 문서 렌더링](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### 배울 내용
- Maven‑기반 Java 프로젝트에서 GroupDocs.Viewer를 설정하는 방법  
- **convert numbers to pdf**, **convert numbers to html**, **convert numbers to jpg**를 수행하는 단계별 코드  
- 문서 변환이 웹 포털, 이메일 워크플로, DMS 통합에 가치를 더하는 실제 시나리오  

## 빠른 답변
- **Java로 Numbers를 PDF로 변환할 수 있나요?** 예, GroupDocs.Viewer의 `PdfViewOptions`를 사용합니다.  
- **웹 미리보기에 가장 적합한 형식은 무엇인가요?** HTML이 가장 인터랙티브한 경험을 제공합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 비시험 배포에는 상업용 라이선스가 필요합니다.  
- **이미지 변환이 지원되나요?** 물론입니다—고품질 이미지를 얻으려면 `JpgViewOptions` 또는 `PngViewOptions`를 사용하세요.  
- **필요한 Java 버전은 무엇인가요?** Java 8 이상 및 Maven이 필요합니다.  

## 사전 요구 사항
- Java Development Kit (JDK) 8 이상이 설치되어 있어야 합니다.  
- 의존성 관리를 위한 Maven이 필요합니다.  
- Java 파일 I/O 및 경로에 대한 기본적인 이해가 필요합니다.  

## GroupDocs.Viewer for Java 설정

### Maven 설치
`pom.xml`에 저장소와 의존성을 추가합니다. 이 블록은 그대로 유지되어야 합니다:

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
- **Free Trial:** 비용 없이 모든 기능을 평가할 수 있습니다.  
- **Temporary License:** 확장 테스트를 위한 기간 제한 키를 요청하세요.  
- **Purchase:** 상업 프로젝트를 위한 전체 라이선스를 획득합니다.  

## Numbers 문서를 HTML로 렌더링  
*사용 사례: 스프레드시트를 웹 페이지에 직접 삽입하기.*

### Step 1: Initialize Viewer and Configure HTML Options
아래 코드를 그대로 실행합니다. 주석은 각 줄을 설명하지만 **코드 블록을 수정하지 마세요**.

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

- **Why this matters:** `HtmlViewOptions.forEmbeddedResources()`는 CSS와 이미지를 HTML 내부에 번들링하여 빠른 웹 미리보기에 최적화됩니다.

## Numbers 문서를 JPG로 렌더링  
*소셜 미디어나 이메일에 스프레드시트 스냅샷을 공유할 때 유용합니다.*

### Step 1: Set Up Viewer and JPG Options
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

- **Tip:** 파일 크기를 줄여야 할 경우 `options.setQuality(int)`로 이미지 품질을 조정하세요.

## Numbers 문서를 PNG로 렌더링  
*보고서에 손실 없이 고해상도 이미지를 필요로 할 때 이상적입니다.*

### Step 1: Initialize and Configure PNG Options
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

- **Pro tip:** 인쇄용 이미지를 위해 DPI를 제어하려면 `options.setResolution(int)`를 사용하세요.

## Numbers 문서를 PDF로 렌더링  
*많은 개발자에게 주요 목표: **convert numbers to pdf**를 통해 보관 또는 배포하기.*

### Step 1: Set Up Viewer for PDF Conversion
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

- **Key configuration:** `PdfViewOptions`를 사용하면 폰트를 포함하고 페이지 크기를 제어할 수 있어 출력물이 브랜드 요구 사항에 맞게 됩니다.

## 실용적인 적용 사례
- **Web Integration:** HTML로 렌더링하여 사이트에 인터랙티브 스프레드시트 뷰어를 제공합니다.  
- **Content Sharing:** JPG/PNG로 변환해 뉴스레터나 채팅에 빠르게 이미지 삽입이 가능합니다.  
- **Enterprise DMS:** **convert numbers to pdf**를 사용해 편집 불가능하고 검색 가능한 스프레드시트 버전을 저장합니다.  

## 성능 고려 사항
- **Resource Management:** 예시와 같이 `Viewer`를 try‑with‑resources 블록에서 항상 닫아 네이티브 리소스를 즉시 해제하세요.  
- **Large Files:** 대용량 Numbers 파일은 페이지별 처리 및 스트리밍 결과를 사용해 메모리 사용량을 최소화하세요.  
- **Thread Safety:** 클래스가 스레드‑안전하지 않으므로 스레드당 별도의 `Viewer` 인스턴스를 생성하세요.  

## 결론
이제 **convert numbers to pdf**뿐만 아니라 HTML, JPG, PNG로 변환할 수 있는 완전한 도구 상자를 GroupDocs.Viewer for Java와 함께 갖추었습니다. 이러한 기능을 활용해 웹 포털에 데이터를 공급하거나 보고서를 생성하고 스프레드시트를 보관하는 등 유연한 문서 파이프라인을 구축할 수 있습니다.

### 다음 단계
[GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)에서 추가 커스터마이징 옵션을 살펴보고 이러한 기능을 직접 애플리케이션에 통합해 보세요.

## FAQ 섹션

**Q1: GroupDocs.Viewer가 지원하는 파일 형식은 무엇인가요?**  
A1: DOCX, XLSX, PDF 등 다양한 문서 형식을 지원합니다.

**Q2: 대용량 Numbers 파일을 효율적으로 처리하려면 어떻게 해야 하나요?**  
A2: Java 메모리 관리 기법을 활용하고 코드를 최적화하여 큰 파일 크기를 효과적으로 처리하세요.

**Q3: GroupDocs.Viewer를 상업 프로젝트에 사용할 수 있나요?**  
A4: 예, 상업용으로 사용하려면 라이선스를 구매해야 합니다.

**Q4: 이미지 출력 품질을 커스터마이징할 수 있나요?**  
A5: 물론입니다. `JpgViewOptions`와 `PngViewOptions` 내 설정을 조정하면 됩니다.

**Q5: 더 고급 사용 예시는 어디서 찾을 수 있나요?**  
A5: 자세한 문서는 [API reference](https://reference.groupdocs.com/viewer/java/)를 참고하세요.

## 자주 묻는 질문

**Q: Numbers 파일을 포맷 손실 없이 PDF로 변환하려면?**  
A: 위에 보여진 대로 `PdfViewOptions`를 사용하면 뷰어가 레이아웃, 폰트, 셀 스타일을 자동으로 보존합니다.

**Q: 스프레드시트를 한 번에 이미지로 변환할 수 있나요?**  
A: 예, `JpgViewOptions` 또는 `PngViewOptions`를 사용하면 한 단계로 변환하면서 해상도와 품질을 지정할 수 있습니다.

**Q: 여러 Numbers 파일을 배치 처리할 방법이 있나요?**  
A: 뷰어 로직을 루프에 넣고 파일마다 `Viewer`를 재초기화한 뒤 각 출력물을 별도 폴더에 저장하면 됩니다.

**Q: 출력 형식마다 별도의 라이선스가 필요합니까?**  
A: 아니요, 단일 GroupDocs.Viewer 라이선스로 모든 지원 형식을 사용할 수 있습니다.

**Q: 이러한 기능을 사용하려면 어떤 버전의 GroupDocs.Viewer가 필요합니까?**  
A: 예제는 버전 25.2를 대상으로 하며, Numbers를 PDF/HTML/Image로 변환하는 전체 지원을 포함합니다.

## 리소스
- **Documentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Buy a License](https://purchase.groupdocs.com/buy)
- **Free Trial:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License:** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **Support Forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-03-05  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs