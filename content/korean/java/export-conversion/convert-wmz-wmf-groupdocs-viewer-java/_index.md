---
date: '2026-02-18'
description: GroupDocs Viewer for Java를 사용하여 WMZ 및 WMF 파일을 PDF, HTML, JPG 및 PNG로 변환하는
  방법을 배웁니다. 이 가이드는 GroupDocs Viewer Java와 Java 벡터 그래픽 변환에 대해 다룹니다.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: GroupDocs Viewer for Java를 사용하여 WMZ를 PDF 및 기타 형식으로 변환하는 방법
type: docs
url: /ko/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Java를 사용하여 WMZ를 PDF 및 기타 형식으로 변환하는 방법

WMZ(Web Metafile) 및 WMF(Windows Metafile) 파일을 보다 접근하기 쉬운 형식—특히 **convert WMZ to PDF**—으로 변환하는 것은 이러한 벡터 그래픽 형식이 픽셀 데이터가 아니라 그리기 명령을 저장하기 때문에 까다로울 수 있습니다. **GroupDocs Viewer for Java**를 사용하면 몇 줄의 코드만으로 WMZ/WMF 문서를 HTML, JPG, PNG, **PDF**, 및 기타 인기 형식으로 렌더링할 수 있습니다.

![GroupDocs.Viewer for Java를 사용한 WMZ/WMF 문서 변환](/viewer/export-conversion/convert-wmz-wmf-documents.png)

이 튜토리얼에서는 라이브러리를 설정하고, WMZ/WMF 파일을 원하는 출력 형식으로 렌더링하며, 일반적인 함정을 처리하는 방법을 배웁니다. 끝까지 진행하면 **groupdocs viewer java**를 Java 애플리케이션에 통합하여 **java convert vector graphics**를 빠르고 안정적으로 수행할 수 있게 됩니다.

## 빠른 답변
- **WMZ/WMF를 변환할 수 있는 형식은 무엇인가요?** HTML, JPG, PNG, 그리고 PDF가 완전히 지원됩니다.  
- **개발에 라이선스가 필요합니까?** 평가용 무료 체험판을 사용할 수 있으며, 상용 라이선스를 적용하면 평가 제한이 해제됩니다.  
- **필요한 Java 버전은 무엇입니까?** Java 8 이상을 권장합니다.  
- **특정 페이지만 렌더링할 수 있나요?** 예, 뷰 옵션에서 페이지 범위를 지정할 수 있습니다.  
- **대용량 파일에서 메모리 사용량이 문제가 되나요?** try‑with‑resources를 사용하고 필요한 페이지만 렌더링하여 메모리 사용량을 낮게 유지하세요.

## “convert WMZ to PDF”란 무엇인가요?
WMZ를 PDF로 변환한다는 것은 벡터 기반 WMZ 파일을 PDF 컨테이너 안에 래스터화(또는 벡터 데이터를 보존)하는 것을 의미합니다. PDF는 전 세계적으로 보기, 검색, 인쇄가 가능하여 WMZ 그래픽을 보관하고 공유하기에 이상적인 형식입니다.

## 벡터 그래픽 변환에 GroupDocs Viewer for Java를 사용하는 이유
- **High fidelity**: 라이브러리는 PDF이든 PNG이든 원본 드로잉 품질을 보존합니다.  
- **Zero external dependencies**: 네이티브 Windows 라이브러리가 필요 없으며, JDK가 설치된 모든 플랫폼에서 실행됩니다.  
- **Simple API**: `Viewer` 인스턴스 하나와 단일 `view` 호출만으로 전체 변환을 처리합니다.  
- **Scalable**: 단일 페이지 아이콘부터 다중 페이지 기술 도면까지 동일하게 잘 동작합니다.

## 사전 요구 사항

### 필수 라이브러리
- **GroupDocs.Viewer for Java** – 핵심 렌더링 엔진.  
- Java Development Kit (JDK) 8+.

### 환경 설정
- IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
- Maven을 통한 의존성 관리(또는 선호한다면 Gradle).

### 지식 사전 요구 사항
- Java 파일 I/O(`java.nio.file.Path`)에 익숙함.  
- 문서 뷰어가 콘텐츠를 렌더링하는 방식에 대한 기본 이해.

## GroupDocs.Viewer for Java 설정

`pom.xml`에 리포지토리와 의존성을 추가합니다:

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

> **License tip:** 평가를 위해 무료 체험판을 사용하고, 전체 기능을 사용하려면 임시 또는 구매한 라이선스를 적용하십시오.

의존성이 해결되면 각 변환 단계에서 재사용할 `Viewer` 인스턴스를 생성할 수 있습니다.

## 구현 가이드

HTML, JPG, PNG, PDF 네 가지 변환 시나리오를 단계별로 살펴봅니다. 각 예제는 동일한 패턴을 따릅니다—출력 경로 정의, 소스 WMZ 파일로 `Viewer` 인스턴스 생성, 적절한 뷰 옵션 구성, 그리고 `view` 호출.

### WMZ/WMF를 HTML로 렌더링

#### 개요
HTML 출력은 그래픽을 웹 페이지에 직접 삽입할 수 있게 해 주며, 모든 리소스(이미지, CSS)가 하나의 파일에 포함됩니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Step 2: Viewer 초기화 및 HTML로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF를 JPG로 렌더링

#### 개요
JPG는 널리 지원되는 래스터 형식으로, 빠른 미리보기나 이메일 첨부에 적합합니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Step 2: Viewer 초기화 및 JPG로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF를 PNG로 렌더링

#### 개요
PNG는 투명도를 지원하므로 다양한 배경과 조화시켜야 하는 그래픽에 이상적입니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Step 2: Viewer 초기화 및 PNG로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF를 PDF로 렌더링

#### 개요
PDF는 플랫폼에 독립적이며 검색 가능한 문서로, 원본 레이아웃을 유지합니다.

**Step 1: 출력 디렉터리 경로 정의**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Step 2: Viewer 초기화 및 PDF로 렌더링**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결책 |
|------|------|--------|
| **OutOfMemoryError** 대용량 WMZ 파일 | Viewer가 전체 문서를 메모리에 로드함 | `PageStreamViewOptions`를 사용해 페이지당 하나씩 렌더링하거나 JVM 힙(`-Xmx`)을 늘리세요. |
| **Missing fonts** PDF에서 | 소스 WMZ에 폰트가 포함되지 않음 | 호스트 머신에 필요한 폰트를 설치하거나 `FontSettings`를 사용해 사용자 정의 폰트를 제공하세요. |
| **Blank PNG output** | 잘못된 출력 경로나 쓰기 권한 부족 | `outputDirectory`가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하세요. |
| **HTML resources not loading** | `forExternalResources`를 사용했지만 파일을 복사하지 않음 | 자체 포함형 HTML 파일을 위해 `forEmbeddedResources`를 사용하세요. |

## 자주 묻는 질문

**Q: 같은 코드를 사용해 WMF를 PNG로 변환할 수 있나요?**  
A: 예. PNG 예제는 WMZ와 WMF 모두에 적용되며, `TestFiles.SAMPLE_WMZ`를 WMF 소스 파일로 교체하면 됩니다.

**Q: 페이지의 일부만 변환할 수 있나요?**  
A: 물론 가능합니다. `PdfViewOptions`(또는 다른 형식에 해당하는 옵션)를 사용하고 렌더링 전에 `setPageNumbers(List<Integer>)`를 호출하세요.

**Q: 각 출력 형식마다 별도의 라이선스가 필요합니까?**  
A: 아닙니다. 단일 GroupDocs Viewer 라이선스로 HTML, JPG, PNG, PDF 등 모든 지원 형식을 사용할 수 있습니다.

**Q: “java convert vector graphics”가 성능에 어떤 영향을 미칩니까?**  
A: 벡터‑대‑래스터 변환은 CPU 집약적입니다. 대량 배치 처리 시 멀티스레딩을 고려하고 파일당 하나의 `Viewer` 인스턴스를 재사용하세요.

**Q: PDF가 벡터 품질을 유지합니까, 아니면 래스터화됩니까?**  
A: WMZ/WMF를 PDF로 변환할 때 GroupDocs Viewer는 가능한 경우 벡터 명령을 보존하여 확장 가능한 PDF를 생성합니다.

## 결론

이제 **GroupDocs Viewer for Java**를 사용해 **convert WMZ to PDF** 및 기타 일반 형식으로 변환하는 완전하고 프로덕션 준비된 가이드를 확보했습니다. 그래픽을 실시간으로 제공하는 웹 서비스든, 문서를 PDF로 보관하는 아카이브 도구든, 위 단계들을 따르면 빠르게 목표를 달성할 수 있습니다.

---

**Last Updated:** 2026-02-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs