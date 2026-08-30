---
date: '2026-08-30'
description: GroupDocs.Viewer for Java를 사용하여 DWG를 PNG로 변환하고, Java에서 배경 색상을 설정하며, 이미지
  크기를 사용자 지정하는 방법을 배웁니다.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: GroupDocs.Viewer for Java를 사용하여 DWG를 PNG로 변환하면서 사용자 지정 이미지 너비와 배경
  색상을 설정합니다. 이 가이드는 단계별 설정, 코드 스니펫 및 문제 해결 팁을 제공합니다.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Java에서 사용자 지정 크기와 배경 색상으로 DWG를 PNG로 변환하기
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: GroupDocs.Viewer for Java를 사용하여 DWG를 PNG로 변환하고 사용자 지정 크기 및 배경 색상 적용하는 방법
type: docs
url: /ko/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# 맞춤 크기 및 배경 색상으로 DWG를 PNG로 변환하는 방법 – GroupDocs.Viewer for Java 사용

이 튜토리얼에서는 **DWG를 PNG로 변환하는 방법**을 배우면서 출력 크기와 배경 색상을 제어하는 방법을 GroupDocs.Viewer for Java를 사용해 설명합니다. 보고서에 CAD 도면을 삽입하거나 웹 포털용 썸네일을 생성하거나 배치 렌더링을 자동화해야 할 때, 아래 단계들을 통해 각 PNG 파일의 시각적 모습을 완전히 제어할 수 있습니다.

## 빠른 답변
- **“DWG를 PNG로 변환”이란 무엇인가요?** 코드를 통해 DWG CAD 파일을 PNG 이미지로 변환하는 과정이며, 벡터 세부 정보를 래스터 픽셀로 보존합니다.  
- **맞춤 너비를 설정할 수 있나요?** 예 – `CadOptions.forRenderingByWidth(int width)`를 호출하여 필요한 정확한 픽셀 너비를 정의합니다.  
- **배경 색상을 어떻게 변경하나요?** 렌더링 전에 `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`를 사용합니다.  
- **필요한 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java (버전 25.2 이상).  
- **라이선스가 필요합니까?** 임시 또는 정식 라이선스를 적용하면 평가 제한이 해제되고 무제한 렌더링이 가능합니다.

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## GroupDocs.Viewer for Java란?
GroupDocs.Viewer for Java는 서버‑사이드 API로, CAD 파일을 포함한 150개 이상의 파일 형식을 이미지, PDF 또는 HTML로 렌더링합니다. AutoCAD와 같은 서드‑파티 소프트웨어가 필요 없으며 자동화 파이프라인에 최적화되어 있습니다.

## 맞춤 크기 및 배경 색상으로 DWG를 PNG로 변환하는 방법
DWG 파일을 `Viewer` 인스턴스로 로드하고, 원하는 너비와 배경을 지정하기 위해 `CadOptions`를 구성한 뒤, `viewer.view`를 `PngViewOptions`와 함께 호출합니다. 이 3단계 흐름은 파일 I/O, 렌더링, 출력 명명을 한 번에 메모리 효율적으로 처리합니다.

Viewer는 문서를 로드하고 렌더링을 수행하는 주요 클래스입니다.  
CadOptions는 이미지 너비와 배경 색상 같은 CAD‑특화 설정을 구성합니다.  
PngViewOptions는 PNG 출력 형식과 렌더링된 페이지의 명명 패턴을 정의합니다.

이제 지정한 정확한 너비의 PNG로 DWG 도면을 렌더링할 수 있으며, 브랜드나 UI 테마에 맞는 고체 색상(또는 투명) 배경을 선택할 수 있습니다.

## 맞춤 배경 색상을 설정하는 이유
배경 색상을 지정하면 렌더링된 PNG가 주변 UI 요소와 자연스럽게 어우러지고, 원치 않는 흰색 여백을 방지하며, 기본 흰색 캔버스에서는 놓칠 수 있는 도면 세부 정보를 강조할 수 있습니다. GroupDocs.Viewer는 사용자 정의 RGB 값을 포함한 모든 `java.awt.Color`를 지원하여 픽셀‑단위의 정밀 제어를 제공합니다.

java.awt.Color는 배경을 렌더링하는 데 사용되는 색상 값을 나타냅니다.

## 전제 조건

- **Java Development Kit (JDK) 8+** – API는 Java 8 및 이후 버전을 대상으로 합니다.  
- **Maven** – 의존성 관리를 위해 사용합니다.  
- **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 편집기.  
- **기본 Java 파일‑처리 지식** – DWG 파일을 읽고 PNG 출력을 쓰는 방법을 알고 있어야 합니다.

## GroupDocs.Viewer for Java 설정
Maven `pom.xml`에 GroupDocs 저장소와 Viewer 의존성을 추가합니다:

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
GroupDocs 포털에서 임시 또는 정식 라이선스 키를 받아 `license.lic` 파일을 프로젝트 리소스 폴더에 배치합니다. 이렇게 하면 20페이지 평가 제한이 해제되고 전체 해상도 렌더링이 가능해집니다.

### 기본 초기화 및 설정
DWG 파일이 들어 있는 폴더를 가리키는 `Viewer` 인스턴스를 생성합니다:

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
CAD 배경 색상을 변경하려면 렌더링 전에 CadOptions 객체를 구성합니다. `forRenderingByWidth`로 원하는 너비를 설정하고 `setBackgroundColor`로 새로운 배경을 적용합니다. 이렇게 하면 지정된 색상이 반영된 PNG 이미지가 생성되어 모든 출력 파일에 일관된 시각적 스타일을 유지합니다.

#### 단계별 구현

##### 필요한 패키지 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 출력 디렉터리 및 파일‑경로 형식 설정
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
- `PngViewOptions` – PNG 출력 형식과 명명 패턴을 정의합니다.  
- `forRenderingByWidth(int width)` – 지정된 픽셀 값에 맞춰 이미지 너비를 강제하고, 높이는 비례적으로 조정합니다.  
- `setBackgroundColor(Color color)` – 기본 흰색 캔버스를 선택한 색상으로 덮어써서 생성된 자산의 시각적 일관성을 향상시킵니다.

#### 문제 해결 팁
- 출력 폴더가 존재하는지 확인하고, 없으면 `Files.createDirectories(outputDir)`를 사용합니다.  
- 입력 파일 경로가 올바른지, 애플리케이션에 읽기 권한이 있는지 확인합니다.

## 기능 2: 렌더링 옵션에서 배경 색상 설정

### PNG 배경 색상 설정 방법
PNG 배경 색상을 설정하려면 `Color` 인스턴스를 생성하고 렌더링 전에 CadOptions에 할당합니다. 이렇게 하면 각 PNG가 지정된 배경을 사용해 브랜드 가이드라인이나 UI 테마와 일치합니다. 미리 정의된 상수를 사용하거나 정확한 제어를 위해 사용자 정의 RGB 값을 정의할 수 있습니다.

java.awt.Color는 배경을 렌더링하는 데 사용되는 색상 값을 나타냅니다.

#### 단계별 구현

##### 필요한 패키지 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 배경 색상이 포함된 렌더링 옵션 구성
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
- `forRenderingByWidth(int width)`를 조정하여 웹 썸네일용 800 px 또는 고해상도 인쇄용 1920 px 등 다양한 크기를 지정합니다.  
- `Color` 상수(`Color.LIGHT_GRAY` 등)를 사용하거나 `new Color(r, g, b)`로 사용자 정의 인스턴스를 만들어 정확한 브랜딩을 구현합니다.  

## 실용적인 적용 사례

### 1. 엔지니어링 문서화
맞춤 렌더링을 통해 모든 도면이 회사 스타일 가이드를 준수하므로, 내보낸 후 별도의 이미지 편집이 필요 없습니다.

### 2. 건축 시각화
슬라이드 자료나 클라이언트 포털에 맞는 배경을 적용해 청사진을 제시하면 시각적 일관성이 향상됩니다.

### 3. 제조 프로토타이핑
다운스트림 도구가 특정 이미지 크기와 배경을 기대하는 경우, 빠른 프로토타입 워크플로를 위해 PNG를 생성합니다.

### 통합 가능성
이 렌더링 파이프라인을 문서 관리 시스템(예: SharePoint)과 연계하면 DWG 파일이 업로드될 때 자동으로 미리보기 이미지를 생성할 수 있습니다.

## 성능 고려 사항

### 성능 최적화
- **배치 처리:** DWG 파일이 들어 있는 디렉터리를 순회하면서 순차적으로 렌더링하면 JVM 워밍업 비용을 분산시킬 수 있습니다.  
- **리소스 관리:** 500페이지 이상 대형 도면의 경우 JVM 힙(`-Xmx2g`)을 늘리거나 파일을 작은 배치로 나누어 처리해 메모리 부족 오류를 방지합니다.

### 리소스 사용 가이드라인
VisualVM과 같은 도구로 CPU와 메모리 사용량을 모니터링하고, `Viewer` 인스턴스를 try‑with‑resources로 즉시 해제합니다.

### Java 메모리 관리 모범 사례
- 예시와 같이 try‑with‑resources를 사용해 `Viewer`를 자동으로 닫습니다.  
- 즉시 사용이 끝난 큰 `Path` 객체를 장기간 보관하지 않도록 합니다.  

## 일반적인 문제와 해결책

| 문제 | 해결책 |
|-------|----------|
| 출력 폴더를 찾을 수 없음 | 미리 디렉터리를 생성하거나 `Files.createDirectories(outputDirectory);`를 추가합니다. |
| 이미지가 빈 화면 | `forRenderingByWidth` 호출 후 `cadOptions.setBackgroundColor`가 실행되었는지 확인합니다. |
| 메모리 부족 오류 | `-Xmx` JVM 옵션을 늘리거나 파일을 작은 배치로 처리합니다. |

## 자주 묻는 질문

**Q: DWG 외에 다른 CAD 형식을 렌더링할 수 있나요?**  
A: 예, GroupDocs.Viewer는 DXF, DWF 및 기타 여러 CAD 형식을 지원합니다.

**Q: 미리 정의된 상수가 아닌 사용자 정의 RGB 색상을 사용하려면 어떻게 하나요?**  
A: `new Color(123, 45, 67)`와 같이 새로운 `Color` 인스턴스를 생성하고 `setBackgroundColor`에 전달합니다.

**Q: 특정 레이아웃이나 레이어만 렌더링할 수 있나요?**  
A: `viewer.view`를 호출하기 전에 `CadOptions`를 통해 레이아웃 또는 레이어 옵션을 지정할 수 있습니다.

**Q: 라이브러리가 투명 배경을 지원하나요?**  
A: 출력 형식이 지원한다면 `new Color(0,0,0,0)`으로 배경 색상을 설정하면 완전 투명 배경을 얻을 수 있습니다.

**Q: 필요한 GroupDocs.Viewer 버전은 무엇인가요?**  
A: 이 튜토리얼은 버전 25.2를 사용하지만, 최신 릴리스에서도 동일한 API를 제공합니다.

**마지막 업데이트:** 2026-08-30  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs

## 관련 튜토리얼

- [groupdocs viewer dwg – Java에서 GroupDocs.Viewer를 사용해 특정 CAD 도면 렌더링하는 방법](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java with GroupDocs.Viewer – 완전 가이드](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [How to convert pdf to html and optimize image quality in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)