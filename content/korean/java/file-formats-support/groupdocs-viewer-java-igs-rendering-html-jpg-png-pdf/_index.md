---
date: '2026-02-23'
description: GroupDocs.Viewer for Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환하는 방법을 배워보세요.
  실행 가능한 코드 예제가 포함된 단계별 가이드를 따라하세요.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: GroupDocs.Viewer Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환
type: docs
url: /ko/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# GroupDocs.Viewer Java를 사용하여 IGS를 PDF, HTML, JPG 및 PNG로 변환하기

Java 애플리케이션에서 직접 **IGS를 PDF**(또는 HTML, JPG, PNG)로 변환해야 한다면, 바로 여기입니다. 이 튜토리얼에서는 라이브러리 설정부터 프로젝트에 맞는 형식으로 3‑D 모델을 렌더링하는 방법까지 모든 과정을 단계별로 안내합니다. GroupDocs.Viewer가 빠르고 안정적인 변환에 적합한 이유를 확인하고, 직접 솔루션에 적용할 수 있는 실전 코드를 제공합니다.

![GroupDocs.Viewer for Java를 사용하여 IGS 파일을 HTML, JPG, PNG 및 PDF로 변환하기](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 빠른 답변
- **Java로 IGS를 PDF로 변환할 수 있나요?** 네, GroupDocs.Viewer의 `PdfViewOptions`를 사용합니다.  
- **지원되는 출력 형식은 무엇인가요?** HTML, JPG, PNG, PDF.  
- **프로덕션에 라이선스가 필요합니까?** 상용 라이선스가 필요하며, 테스트용 무료 체험판을 사용할 수 있습니다.  
- **필요한 Java 버전은?** JDK 8 이상.  
- **라이브러리를 추가하는 방법이 Maven만인가요?** 아니오, Gradle 또는 수동 JAR 포함도 가능합니다.

## “IGS를 PDF로 변환”이란?
IGS(3‑D CAD 데이터용 중립 파일 형식)를 PDF로 변환한다는 것은 복잡한 3‑D 모델을 정적인 문서로 바꾸어, CAD 도구가 없는 이해관계자와도 쉽게 공유할 수 있게 하는 것을 의미합니다.

## IGS 변환에 GroupDocs.Viewer를 사용하는 이유
- **코드 없이 CAD 렌더링** – 라이브러리가 IGS 형식 파싱을 담당합니다.  
- **다중 출력 옵션** – 하나의 API 호출로 HTML, JPG, PNG, PDF를 생성할 수 있습니다.  
- **크로스 플랫폼** – Java를 지원하는 모든 OS에서 작동합니다.  
- **성능 중심** – 대형 어셈블리에서도 빠른 렌더링을 제공합니다.

## 전제 조건
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+**가 IDE(IntelliJ IDEA, Eclipse, NetBeans 등)에 설치되고 구성되어 있어야 합니다.  
- 기본 Maven 지식(선택 사항이지만 권장)

## GroupDocs.Viewer for Java 설정

### Maven 의존성
`pom.xml`에 GroupDocs 저장소와 Viewer 의존성을 추가합니다:

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
GroupDocs.Viewer는 다음을 제공합니다:
- **무료 체험** – 사용량 제한, 빠른 테스트에 적합합니다.  
- **임시 라이선스** – 짧은 평가 기간 동안 전체 기능 제공.  
- **상용 라이선스** – 제한 없는 프로덕션 사용.

### 기본 Viewer 초기화
아래 스니펫은 IGS 파일을 가리키는 `Viewer` 인스턴스를 만드는 방법을 보여줍니다:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## IGS를 HTML로 렌더링

### IGS를 HTML로 변환하는 방법?
HTML 출력은 3‑D 모델을 인터랙티브하고 브라우저 친화적으로 보여줍니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**핵심 포인트:** `HtmlViewOptions.forEmbeddedResources()`는 필요한 모든 자산(CSS, 이미지)을 HTML 파일에 직접 포함시켜 휴대성을 높입니다.

## IGS를 JPG로 렌더링

### IGS를 JPG로 변환하는 방법?
JPG 이미지는 썸네일이나 빠른 미리보기에 적합합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`JpgViewOptions`를 조정하여 해상도와 압축 품질을 제어할 수 있습니다.

## IGS를 PNG로 렌더링

### IGS를 PNG로 변환하는 방법?
PNG는 투명도를 지원하므로 다양한 배경에 모델을 오버레이할 때 유용합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PngViewOptions`를 실험하여 파일 크기와 시각적 품질 사이의 최적 균형을 찾으세요.

## IGS를 PDF로 렌더링

### IGS를 PDF로 변환하는 방법?
PDF는 상세 설계 문서를 공유할 때 가장 많이 사용되는 형식입니다. 이 섹션은 주요 키워드 **convert IGS to PDF**를 직접 다룹니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions`를 사용하면 페이지 레이아웃, 이미지 품질, 폰트 임베드 여부를 제어할 수 있습니다.

## 실용적인 적용 사례
- **웹 포털** – HTML로 렌더링된 모델을 제품 구성기에 직접 삽입합니다.  
- **마케팅 자산** – 브로셔용 고해상도 JPG/PNG 이미지를 생성합니다.  
- **기술 문서** – 사용자 매뉴얼에 CAD 모델의 PDF 렌더링을 포함합니다.  
- **품질 보증** – 대량 IGS 파일에 대한 썸네일 생성을 자동화합니다.

## 일반적인 문제 및 해결책

| **문제** | **해결책** |
|----------|------------|
| **출력 폴더를 찾을 수 없음** | `Path outputDirectory`에 전달된 경로를 확인하고 Java 프로세스에 쓰기 권한이 있는지 확인하십시오. |
| **PDF에 빈 페이지가 표시됨** | IGS 파일이 손상되지 않았는지 확인하고, 먼저 CAD 뷰어에서 열어 보세요. |
| **대형 어셈블리 렌더링이 느림** | JVM 힙을 늘리세요(`-Xmx2g` 이상) 및 필요 시 `viewer.getPageCount()`를 사용해 페이지별로 렌더링하는 것을 고려하십시오. |
| **PDF에서 폰트 누락** | 필요한 폰트를 임베드하려면 `PdfViewOptions`를 사용하거나 서버에 누락된 폰트를 설치하십시오. |

## 자주 묻는 질문

**Q: 한 번에 여러 IGS 파일을 변환할 수 있나요?**  
A: 가능합니다. 파일 경로 목록을 순회하면서 각 파일에 적절한 `view` 메서드를 호출하면 됩니다.

**Q: PDF 페이지 크기를 사용자 지정할 수 있나요?**  
A: 물론입니다. `PdfViewOptions`는 `setPageSize(PageSize.A4)`와 같은 메서드를 제공합니다.

**Q: 각 출력 형식마다 별도의 라이선스가 필요합니까?**  
A: 아닙니다. 하나의 GroupDocs.Viewer 라이선스로 모든 지원 형식을 사용할 수 있습니다.

**Q: 성능이 저하되기 전에 IGS 파일 크기는 어느 정도까지 허용되나요?**  
A: 라이브러리는 수백 메가바이트까지 처리하지만, 매우 큰 모델의 경우 JVM 메모리를 더 할당해야 할 수 있습니다.

**Q: 특정 뷰나 방향만 렌더링할 수 있나요?**  
A: GroupDocs.Viewer는 기본 뷰를 렌더링합니다. 맞춤 방향이 필요하면 변환 전에 CAD 도구로 IGS 파일을 전처리하십시오.

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs