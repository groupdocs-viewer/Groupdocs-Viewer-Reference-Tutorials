---
date: '2026-03-16'
description: GroupDocs.Viewer for Java를 사용하여 DWG를 사용자 지정 크기와 배경 색상으로 PNG로 변환하는 방법을
  배우세요.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java를 사용하여 DWG를 맞춤 크기 및 배경색으로 PNG로 변환하는 방법
type: docs
url: /ko/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# GroupDocs.Viewer for Java를 사용한 맞춤 크기 및 배경 색상으로 DWG를 PNG로 변환하는 방법

DWG를 **PNG로 변환**하면서 이미지 크기와 배경 스타일을 완벽하게 제어하고 싶다면, 여기가 바로 정답입니다. 이 튜토리얼에서는 CAD 파일을 PNG로 렌더링하고, 너비를 사용자 지정하며, 배경 색상을 변경하여 출력이 보고서, 프레젠테이션 또는 웹 미리보기 요구 사항에 맞도록 하는 방법을 단계별로 안내합니다.

## 빠른 답변
- **“convert DWG to PNG”가 무엇을 의미하나요?** 코드를 사용하여 DWG CAD 파일을 PNG 이미지로 변환하는 과정입니다.  
- **맞춤 너비를 설정할 수 있나요?** 예 – `CadOptions.forRenderingByWidth(int width)`를 사용합니다.  
- **배경 색상을 어떻게 변경하나요?** `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`를 호출합니다.  
- **필요한 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java (버전 25.2 이상).  
- **라이선스가 필요하나요?** 임시 또는 정식 라이선스를 사용하면 평가 제한이 해제됩니다.

![GroupDocs.Viewer for Java를 사용한 맞춤 크기 및 배경 색상으로 CAD 도면을 PNG로 렌더링](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## DWG를 PNG로 변환하는 방법 – 개요
이 섹션에서는 주요 목표인 **DWG를 PNG로 변환하는 방법**을 크기와 배경을 제어하면서 자세히 설명합니다. 전체 설정 과정, 필요한 정확한 코드, 그리고 일반적인 함정을 피하기 위한 실용적인 팁을 확인할 수 있습니다.

## 배울 내용
- Maven 프로젝트에서 GroupDocs.Viewer for Java 설정하기  
- **DWG를 PNG로 변환**을 맞춤 크기로 수행하기  
- 렌더링 중 **CAD 배경 색상 변경**으로 깔끔한 외관 만들기  
- 맞춤 렌더링이 가치를 더하는 실제 시나리오  

## 사전 요구 사항

### 필요 라이브러리 및 종속성
- Java Development Kit (JDK) 8+  
- 종속성 관리를 위한 Maven  

### 환경 설정 요구 사항
- IntelliJ IDEA 또는 Eclipse와 같은 IDE  
- 기본 Java 지식  

### 지식 전제 조건
- Java에서 파일을 다루는 방법에 대한 이해  

## GroupDocs.Viewer for Java 설정하기
Maven `pom.xml`에 GroupDocs 저장소와 종속성을 추가합니다:

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
평가 제한을 해제하려면 임시 또는 정식 라이선스를 획득하세요.

### 기본 초기화 및 설정
CAD 파일을 가리키는 `Viewer` 인스턴스를 생성합니다:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## 기능 1: 맞춤 이미지 크기 및 배경 색상으로 CAD 도면 렌더링

### CAD 배경 색상 변경 방법
이 기능을 사용하면 맞춤 너비를 지정하고 새로운 배경 색조를 적용하면서 **DWG를 PNG로 변환**할 수 있습니다.

#### 단계별 구현

##### 필요한 패키지 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 출력 디렉터리 및 파일 경로 형식 설정
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### 맞춤 렌더링 옵션으로 Viewer 초기화
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**매개변수 설명**  
- `PngViewOptions` – 출력 형식 및 파일명 정의.  
- `forRenderingByWidth(int width)` – 맞춤 이미지 너비 설정.  
- `setBackgroundColor(Color color)` – **PNG 배경 색상 설정**으로 시각적 일관성 향상.

#### 문제 해결 팁
- 출력 폴더가 존재하는지 확인하고, 필요하면 생성합니다.  
- 입력 파일 경로와 권한을 다시 확인합니다.  

## 기능 2: 렌더링 옵션에서 배경 색상 설정

### PNG 배경 색상 설정 방법
여기서는 **set background color PNG** 옵션에 초점을 맞춰 모든 렌더링 이미지가 브랜드 색상표와 일치하도록 합니다.

#### 단계별 구현

##### 필요한 패키지 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 배경 색상으로 렌더링 옵션 구성
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

**핵심 구성 옵션**  
- 다양한 차원에 맞게 `forRenderingByWidth(int width)`를 조정합니다.  
- 원하는 배경을 위해 `Color` 상수 또는 사용자 정의 `new Color(r,g,b)`를 사용합니다.  

## 실용적인 적용 사례

### 1. 엔지니어링 문서화
맞춤 렌더링을 통해 엔지니어링 도면이 기업 스타일 가이드를 충족하도록 보장합니다.

### 2. 건축 시각화
프레젠테이션 자료와 일치하는 깔끔한 배경으로 청사진을 제시합니다.

### 3. 제조 프로토타이핑
신속한 프로토타이핑 워크플로를 위해 정밀한 PNG를 생성합니다.

### 통합 가능성
이 렌더링 파이프라인을 문서 관리 시스템과 결합하여 시각 자산 생성을 자동화합니다.

## 성능 고려 사항

### 성능 최적화
- **배치 처리:** 루프에서 여러 CAD 파일을 렌더링합니다.  
- **리소스 관리:** 대형 도면에 맞게 JVM 힙 크기를 조정합니다.

### 리소스 사용 가이드라인
CPU와 메모리를 모니터링하고 `Viewer` 인스턴스를 즉시 해제합니다.

### Java 메모리 관리 모범 사례
- try‑with‑resources(예시와 같이)를 사용하여 `Viewer`를 자동으로 닫습니다.  
- 필요 이상으로 큰 `Path` 객체를 보관하지 않도록 합니다.

## 일반적인 문제 및 해결책

| 문제 | 해결책 |
|-------|----------|
| **출력 폴더를 찾을 수 없음** | 디렉터리를 미리 생성하거나 `Files.createDirectories(outputDirectory);`를 추가합니다. |
| **빈 이미지** | `cadOptions.setBackgroundColor`가 `forRenderingByWidth` 이후에 설정되었는지 확인합니다. |
| **메모리 부족 오류** | `-Xmx` JVM 옵션을 늘리거나 파일을 더 작은 배치로 처리합니다. |

## 자주 묻는 질문

**Q: DWG 외에 다른 CAD 형식을 렌더링할 수 있나요?**  
A: 네, GroupDocs.Viewer는 DXF, DWF 및 기타 여러 CAD 파일 형식을 지원합니다.

**Q: 미리 정의된 상수가 아닌 사용자 정의 RGB 색상을 사용하려면 어떻게 해야 하나요?**  
A: 새로운 `Color` 인스턴스를 생성합니다. 예: `new Color(123, 45, 67)` 그리고 이를 `setBackgroundColor`에 전달합니다.

**Q: 특정 레이아웃이나 레이어만 렌더링할 수 있나요?**  
A: `viewer.view`를 호출하기 전에 `CadOptions`를 통해 레이아웃 또는 레이어 옵션을 지정할 수 있습니다.

**Q: 라이브러리가 투명 배경을 지원하나요?**  
A: 대상 형식이 지원한다면 배경 색상을 `new Color(0,0,0,0)`으로 설정하여 완전 투명을 구현할 수 있습니다.

**Q: 필요한 GroupDocs.Viewer 버전은 무엇인가요?**  
A: 이 튜토리얼은 버전 25.2를 사용하지만, 최신 버전도 동일한 API를 유지합니다.

---

**마지막 업데이트:** 2026-03-16  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs