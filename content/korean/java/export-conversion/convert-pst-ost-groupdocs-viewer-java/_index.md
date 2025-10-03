---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java를 사용하여 Outlook PST/OST 파일을 HTML, JPG, PNG, PDF 등 접근 가능한 형식으로 손쉽게 변환하는 방법을 알아보세요. 이 가이드에서는 필요한 모든 단계와 구성을 다룹니다."
"title": "GroupDocs.Viewer for Java를 사용하여 PST/OST를 HTML, JPG, PNG, PDF로 변환 | 내보내기 및 변환 가이드"
"url": "/ko/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/"
"weight": 1
type: docs
---
# GroupDocs.Viewer for Java를 사용하여 PST/OST를 HTML, JPG, PNG, PDF로 변환

## 소개

Outlook PST 또는 OST 파일을 HTML, JPG, PNG, PDF처럼 접근성이 높은 형식으로 변환하고 싶으신가요? 강력한 GroupDocs.Viewer for Java 라이브러리를 사용하면 이 작업이 간편하고 효율적입니다. 이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 PST/OST 문서를 렌더링하는 방법을 안내하며, 다양한 플랫폼에서 쉽게 공유하고 볼 수 있도록 지원합니다.

**배울 내용:**
- Java용 GroupDocs.Viewer를 사용하여 환경을 설정하는 방법.
- PST/OST 파일을 HTML, JPG, PNG, PDF 형식으로 변환하기 위한 단계별 지침입니다.
- 문서 변환 프로세스를 최적화하기 위한 주요 구성 옵션입니다.

시작하기에 앞서 필요한 전제 조건을 검토해 보겠습니다.

## 필수 조건

이 튜토리얼을 따라하려면 다음 사항이 있는지 확인하세요.

### 필수 라이브러리 및 종속성
- **Java용 GroupDocs.Viewer**: 25.2 버전 이상이 필요합니다.
- **자바 개발 키트(JDK)**애플리케이션을 컴파일하고 실행하려면 JDK 8 이상이 필요합니다.

### 환경 설정 요구 사항
- IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 호환 가능한 통합 개발 환경(IDE).
- 종속성을 관리하기 위해 시스템에 Maven을 설치합니다.

### 지식 전제 조건
- Java 프로그래밍에 대한 기본적인 이해.
- 종속성 관리를 위해 Maven을 사용하는 데 익숙합니다.

필수 구성 요소를 갖추었으니 Java용 GroupDocs.Viewer를 설정해 보겠습니다.

## Java용 GroupDocs.Viewer 설정

Java용 GroupDocs.Viewer를 사용하려면 프로젝트에 종속성을 추가해야 합니다. Maven을 사용하는 경우 다음 단계를 따르세요.

**Maven 구성:**

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

### 라이센스 취득 단계
- **무료 체험**: 무료 체험판을 통해 기능을 탐색해 보세요.
- **임시 면허**: 평가에 더 많은 시간이 필요하다면 임시 면허를 신청하세요.
- **구입**: 장기 사용을 위해 라이센스를 구매하세요.

### 기본 초기화 및 설정

Maven 구성이 완료되면 Java 애플리케이션에서 GroupDocs.Viewer를 초기화합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // 샘플 PST 파일 경로로 뷰어 초기화
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

설정이 완료되었으므로 렌더링 기능을 구현해 보겠습니다.

## 구현 가이드

이 섹션은 PST/OST 문서를 HTML, JPG, PNG, PDF로 렌더링하려는 형식에 따라 논리적 단계로 구분됩니다.

### PST/OST 문서를 HTML로 렌더링

**개요:**
PST/OST 파일을 HTML로 변환하면 웹 브라우저에서 쉽게 볼 수 있습니다. 이 기능은 HTML 파일 내에 리소스를 직접 임베드하여 원활하게 볼 수 있도록 합니다.

#### 1단계: 출력 디렉토리 설정

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

**설명**: HTML 파일이 저장될 위치를 정의합니다. `Paths` 클래스는 파일 경로를 효율적으로 관리하는 데 도움이 됩니다.

#### 2단계: 로드 옵션 구성

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**설명**: 렌더링 중 지연을 방지하기 위해 리소스 로딩에 대한 시간 초과를 설정합니다.

#### 3단계: 뷰어 초기화 및 HTML 렌더링

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

**설명**: 사용하세요 `HtmlViewOptions` HTML 파일 내에 리소스를 삽입합니다. `view()` 메서드는 렌더링을 수행합니다.

### PST/OST 문서를 JPG로 렌더링

**개요:**
PST/OST 파일의 각 페이지를 별도의 JPG 이미지로 변환하여 쉽게 공유하고 볼 수 있습니다.

#### 1단계: 출력 디렉토리 설정

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

**설명**: 출력 JPG 파일에 대한 디렉토리 및 파일 이름 패턴을 지정합니다.

#### 2단계: 로드 옵션 구성

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**설명**: HTML 렌더링과 유사하게 리소스 로딩에 대한 시간 초과를 설정합니다.

#### 3단계: 뷰어 초기화 및 JPG 렌더링

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**설명**: 사용 `JpgViewOptions` 각 페이지를 별도의 JPG 파일로 렌더링합니다.

### PST/OST 문서를 PNG로 렌더링

**개요:**
PST/OST 파일을 고품질 프레젠테이션과 인쇄물에 적합한 PNG 이미지로 변환하세요.

#### 1단계: 출력 디렉토리 설정

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

**설명**: PNG 파일에 대한 디렉토리 및 파일 이름 패턴을 정의합니다.

#### 2단계: 로드 옵션 구성

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**설명**렌더링 시간을 효율적으로 관리하기 위해 리소스 로딩 타임아웃을 설정합니다.

#### 3단계: 뷰어 초기화 및 PNG 렌더링

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**설명**: 사용 `PngViewOptions` 각 페이지를 별도의 PNG 파일로 렌더링합니다.

### PST/OST 문서를 PDF로 렌더링

**개요:**
전체 PST/OST 문서를 하나의 PDF 파일로 변환하여 쉽게 배포하고 보관할 수 있습니다.

#### 1단계: 출력 디렉토리 설정

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

**설명**: 출력 PDF 파일의 디렉토리와 파일 이름을 지정합니다.

#### 2단계: 로드 옵션 구성

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**설명**: 지연 없이 원활하게 렌더링하려면 시간 초과를 설정하세요.

#### 3단계: 뷰어 초기화 및 PDF 렌더링

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**설명**: 사용 `PdfViewOptions` 전체 문서를 단일 PDF 파일로 만듭니다.

## 실제 응용 프로그램

PST/OST 문서를 렌더링하는 실제 사용 사례는 다음과 같습니다.

1. **이메일 보관:** 이메일 보관 자료를 HTML이나 PDF로 변환하여 쉽게 접근하고 공유할 수 있습니다.
2. **문서 관리 시스템:** 저장 및 검색을 위해 문서 변환이 필요한 시스템과 통합합니다.
3. **협업 도구:** Slack이나 Microsoft Teams와 같은 협업 도구에서 변환된 문서를 공유하세요.
4. **법적 문서:** 법률 문서를 보편적으로 접근 가능한 형식으로 변환하여 준비합니다.
5. **백업 솔루션:** 다양한 형식으로 중요한 이메일과 첨부 파일의 백업을 만듭니다.

## 성능 고려 사항

Java용 GroupDocs.Viewer를 사용할 때 성능을 최적화하려면 다음 팁을 고려하세요.
- 렌더링하는 동안 효율적인 리소스 관리를 보장합니다.
- 메모리 사용량을 모니터링하고 필요에 따라 구성을 조정하여 병목 현상을 방지합니다.
- 애플리케이션 컨텍스트에서 지원하는 경우 비동기 처리를 활용하여 응답성을 개선하세요.

이 가이드를 따르면 GroupDocs.Viewer for Java를 사용하여 PST/OST 파일을 다양한 형식으로 효율적으로 변환하고, 다양한 플랫폼에서 접근성과 사용성을 향상시킬 수 있습니다.