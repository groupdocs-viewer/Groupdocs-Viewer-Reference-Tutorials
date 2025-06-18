---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java를 사용하여 사용자 정의 치수와 배경색을 사용하여 CAD 도면을 고품질 PNG 이미지로 렌더링하는 방법을 알아보세요."
"title": "GroupDocs.Viewer for Java를 사용하여 사용자 지정 크기 및 배경색을 사용하여 CAD 도면을 PNG로 렌더링하는 방법"
"url": "/ko/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/"
"weight": 1
---

# GroupDocs.Viewer for Java를 사용하여 사용자 지정 크기 및 배경색을 사용하여 CAD 도면을 PNG로 렌더링하는 방법

## 소개

특정 치수와 미적 감각을 유지하면서 CAD 도면을 고품질 이미지로 변환하는 데 어려움을 겪고 계신가요? GroupDocs.Viewer for Java를 사용하면 이 작업이 훨씬 수월해집니다. 이 튜토리얼에서는 GroupDocs.Viewer를 사용하여 CAD 도면을 사용자 지정 크기와 배경색을 적용한 PNG 파일로 렌더링하는 방법을 안내합니다. 이러한 기능을 통합하여 기술 문서의 시각적인 완성도를 높이고 필요에 맞게 치수를 정확하게 지정할 수 있습니다.

**배울 내용:**
- 프로젝트에서 Java용 GroupDocs.Viewer 설정
- 사용자 정의 치수를 사용하여 CAD 도면을 PNG 형식으로 렌더링
- 렌더링 중 배경색을 적용하여 시각적 매력을 향상시킵니다.
- 산업 전반에 걸친 이러한 기능의 실제적 응용

시작하기에 앞서 전제 조건을 살펴보겠습니다.

## 필수 조건

### 필수 라이브러리 및 종속성
이 튜토리얼을 따르려면 다음이 필요합니다.
- Java Development Kit (JDK) 버전 8 이상.
- 종속성 관리를 위한 Maven.

### 환경 설정 요구 사항
IntelliJ IDEA나 Eclipse와 같은 적합한 IDE로 개발 환경을 설정하세요. Java 프로그래밍 개념에 대한 기본적인 지식도 필요합니다.

### 지식 전제 조건
Java에 대한 기본적인 이해와 프로그래밍 방식으로 파일을 처리하는 경험이 도움이 될 것입니다.

## Java용 GroupDocs.Viewer 설정
시작하려면 Maven 프로젝트에 필요한 종속성을 추가하세요.

**Maven 설정:**
다음 구성을 추가하세요. `pom.xml` 파일:
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

### 라이센스 취득
필요한 경우 임시 라이선스를 얻거나 구매하여 GroupDocs.Viewer의 모든 기능을 제한 없이 탐색할 수 있습니다.

### 기본 초기화 및 설정
GroupDocs.Viewer를 사용하려면 Java 애플리케이션 내에서 초기화해야 합니다.
```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // 렌더링 작업은 여기에 있습니다
}
```

## 구현 가이드

### 기능 1: 사용자 정의 이미지 크기 및 배경색을 사용하여 CAD 도면 렌더링

#### 개요
이 기능을 사용하면 CAD 파일을 PNG 이미지로 렌더링하여 이미지 크기와 배경색을 모두 지정할 수 있습니다.

#### 단계별 구현
##### 필수 패키지 가져오기
필요한 패키지를 모두 가져왔는지 확인하세요.
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```
##### 출력 디렉토리 및 파일 경로 형식 설정
렌더링된 이미지가 저장될 위치를 정의합니다.
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 사용자 정의 렌더링 옵션으로 뷰어 초기화
생성하다 `Viewer` CAD 파일에 대한 인스턴스를 만들고 지정된 치수와 배경색으로 PNG로 렌더링하도록 구성하세요.
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // 렌더링을 위한 너비를 지정하세요
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```
##### 매개변수 설명
- `PngViewOptions` 파일이 저장되는 방식(형식 및 레이아웃 포함)을 결정합니다.
- `forRenderingByWidth(int width)` CAD 도면을 렌더링하기 위한 사용자 정의 이미지 너비를 설정합니다.
- `setBackgroundColor(Color color)` 렌더링된 이미지에 사용할 배경색을 지정합니다.

#### 문제 해결 팁
- 코드를 실행하기 전에 출력 디렉터리가 있는지 확인하세요. 없으면 직접 만들거나 프로그래밍 방식으로 만드세요.
- 입력 파일 경로가 올바르고 애플리케이션의 작업 디렉토리에서 액세스할 수 있는지 확인하세요.

### 기능 2: 렌더링 옵션에서 배경색 설정
이 기능은 사용자 정의 배경색을 포함하여 렌더링 옵션을 구성하고 시각적 표현을 향상시키는 데 중점을 둡니다.

#### 개요
렌더링 과정에서 특정 배경색을 설정하여 렌더링된 이미지의 모양을 사용자 정의합니다.

#### 단계별 구현
##### 필수 패키지 가져오기
이전과 마찬가지로, 필요한 모든 수입품이 있는지 확인하세요.
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```
##### 배경색으로 렌더링 옵션 구성
다음 코드를 사용하여 사용자 정의 배경색을 설정하고 적용하세요.
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```
#### 주요 구성 옵션
- 조정하다 `forRenderingByWidth(int width)` 다양한 이미지 크기에 대해서.
- 다양한 사용 `Color` 상수 또는 사용자 정의 RGB 값을 사용하여 배경색을 설정합니다.

## 실제 응용 프로그램

### 1. 엔지니어링 문서
CAD 도면은 엔지니어링 프로젝트에서 매우 중요합니다. 맞춤형 렌더링을 통해 엔지니어는 특정 시각적 지침을 바탕으로 프레젠테이션에 바로 적용 가능한 문서를 제작할 수 있습니다.

### 2. 건축 시각화
건축가는 이러한 기능을 사용하여 프로젝트 청사진을 시각적으로 매력적인 형식으로 렌더링하여 고객에게 프레젠테이션할 수 있으므로 명확성과 미적 매력을 보장할 수 있습니다.

### 3. 제조 프로토타입 제작
제조업체는 프로토타입을 제작하기 위해 정확한 디자인 이미지가 필요한 경우가 많습니다. 맞춤형 이미지 렌더링을 통해 치수를 정확하게 표현할 수 있습니다.

### 통합 가능성
이러한 기능을 문서 관리 시스템이나 CAD 소프트웨어와 통합하여 시각적 문서 생성 프로세스를 자동화할 수 있습니다.

## 성능 고려 사항

### 성능 최적화
- **일괄 처리:** 가능하면 여러 문서를 동시에 렌더링하세요.
- **자원 관리:** 대규모 렌더링 작업에 맞게 메모리 사용량을 모니터링하고 필요에 따라 JVM 설정을 조정합니다.

### 리소스 사용 지침
다른 애플리케이션에 영향을 주지 않고 렌더링 프로세스를 처리할 수 있는 충분한 리소스(CPU, RAM)가 시스템에 있는지 확인하세요.

### Java 메모리 관리를 위한 모범 사례
- try-with-resources를 사용하여 처리하세요. `Viewer` 인스턴스.
- 메모리 누수를 방지하려면 사용 후 리소스를 즉시 해제하세요.

## 결론
이 튜토리얼을 따라 GroupDocs.Viewer for Java를 사용하여 CAD 도면을 사용자 지정 치수와 배경색을 적용한 PNG 형식으로 효과적으로 렌더링하는 방법을 익혔습니다. 이 기능은 문서 시각화가 중요한 역할을 하는 다양한 산업 분야에서 매우 유용합니다.

### 다음 단계
GroupDocs.Viewer의 추가 기능을 살펴보거나 Java 메모리 관리 기술을 심층적으로 살펴보고 애플리케이션의 성능을 향상시키세요.

**행동 촉구:** 다음 프로젝트에서 이러한 기능을 구현해보고 문서 렌더링 워크플로를 어떻게 변화시킬 수 있는지 살펴보세요.