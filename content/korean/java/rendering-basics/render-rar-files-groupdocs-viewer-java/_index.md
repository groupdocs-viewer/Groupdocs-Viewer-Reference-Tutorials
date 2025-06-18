---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java를 사용하여 RAR 파일을 HTML, JPG, PNG, PDF 등 접근 가능한 형식으로 변환하는 방법을 알아보세요. 이 단계별 가이드는 설정부터 특정 폴더 렌더링까지 모든 것을 다룹니다."
"title": "Java용 GroupDocs.Viewer를 사용하여 RAR 파일을 HTML, JPG, PNG 및 PDF로 렌더링"
"url": "/ko/java/rendering-basics/render-rar-files-groupdocs-viewer-java/"
"weight": 1
---

# Java용 GroupDocs.Viewer를 사용하여 RAR 파일을 다양한 형식으로 렌더링합니다.

GroupDocs.Viewer for Java를 사용하여 RAR 아카이브를 HTML, JPG, PNG, PDF와 같은 접근 가능한 형식으로 변환하여 잠재력을 최대한 활용하세요. 이 튜토리얼은 각 단계를 안내하여 원활한 문서 관리 및 프레젠테이션을 지원합니다.

## 당신이 배울 것
- GroupDocs.Viewer for Java를 사용하여 RAR 파일을 여러 형식으로 렌더링합니다.
- RAR 파일을 HTML, JPG, PNG, PDF로 변환하기 위한 단계별 코드 예제입니다.
- RAR 아카이브에서 뷰 정보를 검색합니다.
- RAR 파일 내의 특정 폴더를 렌더링합니다.

시작해 볼까요!

### 필수 조건
시작하기에 앞서 다음 사항이 있는지 확인하세요.

1. **자바 개발 키트(JDK)**: 버전 8 이상이 필요합니다.
2. **메이븐**이 튜토리얼에서는 종속성 관리를 위해 Maven을 사용합니다.
3. **Java 라이브러리용 GroupDocs.Viewer**: 25.2 버전을 사용하겠습니다.

#### 환경 설정
- JDK와 Maven이 설치되어 개발 환경이 설정되어 있는지 확인하세요.
- 기본적인 Java 프로그래밍 개념에 익숙하면 더 쉽게 따라갈 수 있습니다.

### Java용 GroupDocs.Viewer 설정
GroupDocs.Viewer를 프로젝트에 통합하려면 다음 종속성을 추가하세요. `pom.xml` 파일:

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

#### 라이센스 취득
- **무료 체험**: 무료 평가판을 다운로드하세요 [GroupDocs 웹사이트](https://releases.groupdocs.com/viewer/java/).
- **임시 면허**: 확장 기능에 대한 임시 라이센스를 얻으세요 [GroupDocs 라이선스 페이지](https://purchase.groupdocs.com/temporary-license/).
- **구입**: 장기 사용을 위해서는 라이선스를 구매하세요. [GroupDocs 구매 페이지](https://purchase.groupdocs.com/buy).

#### 기본 초기화
환경과 종속성을 설정한 후 다음과 같이 GroupDocs.Viewer를 초기화합니다.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/file.rar")) {
            // 여기에 렌더링 코드를 넣으세요
        }
    }
}
```

### 구현 가이드
RAR 파일을 다양한 형식으로 렌더링하는 방법을 살펴보겠습니다. 각 형식에는 고유한 구성 세트가 있습니다.

#### RAR을 HTML로 렌더링
**개요**: RAR 파일을 웹에서 볼 수 있는 HTML 문서로 변환합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class RenderRarToHtml {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options); // RAR 파일을 HTML 형식으로 렌더링합니다.
        }
    }
}
```
- **설명**: 그 `HtmlViewOptions` 클래스는 내장된 리소스와 함께 사용되어 CSS와 이미지를 포함한 전체 웹 페이지 렌더링을 허용합니다.

#### RAR을 JPG로 렌더링
**개요**: RAR 파일을 썸네일 미리보기에 적합한 JPEG 이미지로 변환합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;

public class RenderRarToJpg {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.jpg");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options); // RAR 파일을 JPG 형식으로 변환합니다
        }
    }
}
```
- **설명**: `JpgViewOptions` 출력 경로를 지정하고 이미지 렌더링을 처리합니다.

#### RAR을 PNG로 렌더링
**개요**: RAR 아카이브를 PNG 이미지로 변환하여 고품질 미리보기를 제공합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

public class RenderRarToPng {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.png");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options); // RAR 파일을 PNG 형식으로 렌더링합니다.
        }
    }
}
```
- **설명**: JPG와 유사, `PngViewOptions` RAR의 각 페이지를 PNG 이미지로 렌더링하는 데 사용됩니다.

#### RAR을 PDF로 렌더링
**개요**RAR 파일에서 PDF 문서를 생성하여 쉽게 공유하고 인쇄할 수 있습니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class RenderRarToPdf {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result.pdf");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options); // RAR 파일을 PDF 형식으로 변환합니다
        }
    }
}
```
- **설명**: `PdfViewOptions` PDF 문서의 출력 경로를 구성합니다.

#### RAR에 대한 보기 정보 가져오기
**개요**: RAR 아카이브에서 메타데이터와 구조 정보를 검색합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ArchiveViewInfo;

public class GetViewInfoForRar {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            ViewInfo info = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
            System.out.println("File type: " + info.getFileType());
            System.out.println("Pages count: " + info.getPages().size());

            readFolders(viewer, "");
        }
    }

    private static void readFolders(Viewer viewer, String folder) {
        ViewInfoOptions options = ViewInfoOptions.forHtmlView();
        options.getArchiveOptions().setFolder(folder);

        ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(options);
        for (String subFolder : viewInfo.getFolders()) {
            System.out.println(" - " + subFolder);
            readFolders(viewer, subFolder);
        }
    }
}
```
- **설명**: 이 코드는 RAR 아카이브에서 파일 유형과 페이지 수를 검색하여 인쇄합니다.

#### RAR 아카이브의 특정 폴더 렌더링
**개요**: RAR 파일 내의 특정 폴더를 HTML 형식으로 렌더링하는 데 중점을 둡니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class RenderSpecificArchiveFolder {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderSpecificArchiveFolder");
        Path pageFilePathFormat = outputDirectory.resolve("archive_folder_page_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            options.getArchiveOptions().setFolder("TargetFolderName"); // 렌더링할 폴더를 지정하세요
            viewer.view(options); // 지정된 폴더 내용을 HTML로 렌더링합니다.
        }
    }
}
```
- **설명**: 사용 `HtmlViewOptions` RAR 아카이브 내의 개별 폴더를 대상으로 지정하고 렌더링하기 위한 특정 폴더 설정이 있습니다.

이러한 단계를 따르면 GroupDocs.Viewer for Java를 효과적으로 사용하여 RAR 파일을 다양한 형식으로 관리하고 변환할 수 있습니다.

## 결론

이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 RAR 아카이브를 HTML, JPG, PNG, PDF와 같이 접근 가능한 형식으로 손쉽게 변환하는 방법을 설명합니다. 특정 폴더 렌더링, 아카이브 정보 검색, 문서 관리 기능 향상 등 단계별 구현 방법을 배우게 됩니다. 웹 보기, 미리보기 또는 공유 등 어떤 용도로든 이러한 기술을 활용하면 Java 애플리케이션에서 RAR 파일을 효율적으로 처리할 수 있습니다.

### 자주 묻는 질문

1. **암호로 보호된 RAR 파일을 GroupDocs.Viewer for Java로 변환할 수 있나요?**  

네, 하지만 보호된 보관 파일의 잠금을 해제하고 보려면 옵션에 비밀번호를 입력해야 합니다.

2. **RAR 내에서 특정 페이지나 폴더만 렌더링하는 것이 가능합니까?**  

물론입니다. 전용 옵션을 사용하여 렌더링할 폴더나 페이지를 지정할 수 있습니다. `setFolder()` 렌더링 설정 내에서.

3. **GroupDocs.Viewer는 RAR 파일에 대해 어떤 출력 형식을 지원합니까?**  

HTML, JPG, PNG, PDF 형식을 지원하여 보기와 공유에 대한 유연한 옵션을 제공합니다.

4. **GroupDocs.Viewer for Java를 사용하려면 라이선스가 필요합니까?**  

무료 체험판을 이용할 수 있으며, 모든 기능을 사용하고 장기간 사용하려면 라이선스를 구매하거나 임시 라이선스를 받는 것이 좋습니다.

5. **Java 애플리케이션에서 RAR 변환을 자동화할 수 있나요?**  

네, 제공된 코드 예제를 Java 프로젝트에 내장하여 원활하게 일괄 변환을 자동화할 수 있습니다.