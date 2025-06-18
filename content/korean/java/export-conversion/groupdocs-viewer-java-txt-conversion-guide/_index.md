---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java를 사용하여 TXT 파일을 HTML, JPG, PNG, PDF 등 다양한 형식으로 효율적으로 변환하는 방법을 알아보세요. 이 단계별 가이드를 따라 해 보세요."
"title": "GroupDocs.Viewer for Java를 사용하여 TXT 파일을 HTML, JPG, PNG 및 PDF로 변환"
"url": "/ko/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/"
"weight": 1
---

# Java용 GroupDocs.Viewer를 사용하여 TXT 파일 변환: 포괄적인 가이드

## 소개

오늘날의 디지털 세상에서 효율적인 문서 관리는 기업과 개인 모두에게 매우 중요합니다. 웹에 텍스트 문서를 표시하거나 다양한 형식의 파일을 보관해야 하는 경우, 텍스트(TXT) 파일 변환은 빈번하게 필요합니다. **Java용 GroupDocs.Viewer** TXT 파일을 HTML, JPG, PNG, PDF 등 다양한 형식으로 손쉽게 변환할 수 있는 효과적인 솔루션을 제공합니다. 이 가이드에서는 이 다재다능한 라이브러리를 사용하여 원활하게 변환하는 방법을 안내합니다.

### 배울 내용:
- Java 환경에서 GroupDocs.Viewer 설정
- TXT 파일을 다중 페이지 및 단일 페이지 HTML로 변환
- TXT 문서를 이미지 형식(JPG, PNG)으로 렌더링
- TXT 콘텐츠를 PDF 형식으로 변환

구현을 시작하기 전에 필요한 전제 조건을 살펴보겠습니다.

## 필수 조건

Java용 GroupDocs.Viewer를 사용하기 전에 다음 사항을 확인하세요.

### 필수 라이브러리 및 종속성:
- **Java용 GroupDocs.Viewer** 버전 25.2 이상.
  
### 환경 설정 요구 사항:
- 시스템에 호환 가능한 Java 개발 키트(JDK)가 설치되어 있어야 합니다(Java 8 이상 권장).
- IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 통합 개발 환경(IDE).

### 지식 전제 조건:
- Java 프로그래밍과 파일 처리에 대한 기본적인 이해가 있습니다.
- 종속성 관리를 위해 Maven에 익숙해지는 것이 좋습니다.

## Java용 GroupDocs.Viewer 설정

사용을 시작하려면 **그룹 문서 뷰어**다음과 같이 Maven을 통해 프로젝트에 포함하세요.

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

### 라이센스 취득 단계:
- 로 시작하세요 **무료 체험** 또는 얻다 **임시 면허** GroupDocs.Viewer의 모든 기능을 살펴보세요.
- 공식 라이선스를 통해 구매하는 것을 고려하세요. [구매 페이지](https://purchase.groupdocs.com/buy) 장기간 사용을 위해.

### 기본 초기화 및 설정:
1. 프로젝트에 Maven 종속성을 추가합니다.
2. JDK와 IDE로 환경을 설정했는지 확인하세요.

이제 GroupDocs.Viewer의 다양한 기능을 구현하여 TXT 파일을 다양한 형식으로 변환하는 방법을 살펴보겠습니다.

## 구현 가이드

### 기능 1: TXT를 여러 페이지 HTML로 렌더링

#### 개요:
이 기능은 TXT 문서를 여러 페이지 HTML 형식으로 변환하여 여러 웹 페이지에서 텍스트 구조를 보존합니다.

##### 단계:

**필수 라이브러리 가져오기**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**경로 및 뷰어 설정**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // 내장된 리소스로 렌더링하기 위한 옵션 구성
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // 이러한 옵션을 사용하여 문서를 HTML로 렌더링합니다.
    viewer.view(options);
}
```

**설명:**
- `HtmlViewOptions.forEmbeddedResources` 여기서는 모든 리소스가 출력 파일에 내장되어 자체적으로 포함되도록 보장하는 데 사용됩니다.

### 기능 2: TXT를 단일 페이지 HTML로 렌더링

#### 개요:
이 기능을 사용하면 전체 텍스트 문서를 단일 HTML 페이지로 압축하여 빠르게 미리 보거나 요약하는 데 적합합니다.

##### 단계:

**필수 라이브러리 가져오기**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**경로 및 뷰어 설정**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // 내장된 리소스로 렌더링하기 위한 옵션 구성
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // 단일 페이지 HTML로 렌더링하는 옵션을 설정합니다.
    options.setRenderToSinglePage(true);
    
    // 이러한 옵션을 사용하여 문서를 렌더링합니다.
    viewer.view(options);
}
```

**설명:**
그만큼 `setRenderToSinglePage(true)` 이 방법은 모든 텍스트를 하나의 웹 페이지로 압축합니다.

### 기능 3: TXT를 JPG로 렌더링

#### 개요:
TXT 파일을 공유나 인쇄에 적합한 고품질 JPEG 이미지로 변환하세요.

##### 단계:

**필수 라이브러리 가져오기**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**경로 및 뷰어 설정**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // JPEG 이미지로 렌더링하기 위한 옵션 구성
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // 이러한 옵션을 사용하여 문서를 JPG로 렌더링합니다.
    viewer.view(options);
}
```

**설명:**
- `JpgViewOptions` 이미지 변환에 맞게 출력 경로와 렌더링 설정을 지정할 수 있습니다.

### 기능 4: TXT를 PNG로 렌더링

#### 개요:
텍스트 문서를 PNG(Portable Network Graphics) 형식으로 변환하여 손실 없는 압축으로 고품질 이미지를 제공합니다.

##### 단계:

**필수 라이브러리 가져오기**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**경로 및 뷰어 설정**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // PNG 이미지로 렌더링하기 위한 옵션 구성
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // 이러한 옵션을 사용하여 문서를 PNG로 렌더링합니다.
    viewer.view(options);
}
```

**설명:**
- `PngViewOptions` 여기서는 다음과 유사하게 사용됩니다. `JpgViewOptions`하지만 PNG 형식에만 적용되는 장점이 있습니다.

### 기능 5: TXT를 PDF로 렌더링

#### 개요:
텍스트 문서에서 PDF 파일을 생성하여 전 세계적으로 수용되는 형식으로 배포하거나 보관하는 데 적합합니다.

##### 단계:

**필수 라이브러리 가져오기**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**경로 및 뷰어 설정**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // PDF로 렌더링하기 위한 옵션 구성
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // 이러한 옵션을 사용하여 문서를 PDF로 렌더링합니다.
    viewer.view(options);
}
```

**설명:**
- `PdfViewOptions` 페이지 설정 및 리소스 포함을 포함하여 PDF 변환에 대한 특정 설정을 제공합니다.

## 실제 응용 프로그램

Java용 GroupDocs.Viewer의 기능은 여러 가지 실제 사용 사례로 확장됩니다.

1. **문서 관리 시스템:** 텍스트 기반 문서를 내부 포털의 웹 친화적 포맷으로 자동으로 변환합니다.
2. **출판 플랫폼:** 콘텐츠 관리 시스템에 원활하게 통합하기 위해 작성자의 제출물을 TXT에서 HTML로 변환합니다.
3. **보관 솔루션:** 기존 텍스트 파일을 현대적이고 쉽게 접근할 수 있는 PDF나 이미지 형식으로 보존합니다.
4. **클라우드 스토리지와의 통합:** 더 나은 접근성을 위해 클라우드 플랫폼 전반에서 문서를 자동으로 변환하고 저장합니다.