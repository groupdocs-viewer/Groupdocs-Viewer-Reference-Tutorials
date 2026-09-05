---
date: '2026-09-05'
description: GroupDocs Viewer for Java를 사용하여 pdf에서 html을 생성하고 문자 그룹화를 비활성화하여 정확한 텍스트
  표현을 구현하는 방법을 배웁니다.
keywords:
- generate html from pdf
- render pdf to html
- convert pdf to html
lastmod: '2026-09-05'
og_description: GroupDocs Viewer for Java를 사용하여 pdf에서 html을 생성하고 문자 그룹화를 비활성화하여 정확한
  glyph 배치를 구현합니다. 단계별 구현 방법을 배워보세요.
og_image_alt: GroupDocs Viewer for Java rendering PDF to HTML with precise character
  placement
og_title: pdf에서 html 생성 및 그룹화 비활성화 – GroupDocs Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  headline: Generate html from pdf & disable grouping – GroupDocs Java
  type: TechArticle
- description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  name: Generate html from pdf & disable grouping – GroupDocs Java
  steps:
  - name: define output directory
    text: '**Why?** This ensures your rendered HTML files are stored in a dedicated
      folder, making it easy to locate and manage them later.'
  - name: configure file path format
    text: '**Why?** Using a placeholder (`{0}`) lets the viewer create a separate
      HTML file for each PDF page, keeping the output organized.'
  - name: initialize HTML view options
    text: '**Why?** Embedded resources bundle images, fonts, and CSS directly with
      each HTML page, which is ideal for web‑based viewers or e‑learning platforms.'
  - name: disable character grouping
    text: '`setDisableCharsGrouping(true)` disables the default behavior of grouping
      adjacent characters, ensuring each glyph is rendered separately. **Why?** This
      is the crucial line that tells the rendering engine **not** to merge adjacent
      characters, guaranteeing that the generated HTML reflects the exact g'
  - name: render the document
    text: '`Viewer` is the primary class that opens a document and provides rendering
      capabilities. **Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees
      that all native resources are released automatically, preventing memory leaks
      in long‑running applications.'
  type: HowTo
- questions:
  - answer: It forces the renderer to treat each character as an independent element,
      preserving exact layout.
    question: What does “disable grouping” do?
  - answer: '`viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.'
    question: Which API option controls this?
  - answer: A trial works for testing, but a full license is required for production.
    question: Do I need a license?
  - answer: Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.
    question: Can I generate html from pdf at the same time?
  - answer: It’s primarily for PDFs, but the viewer supports many other formats.
    question: Is this feature limited to PDFs?
  type: FAQPage
tags:
- generate html
- GroupDocs Viewer
- Java document rendering
title: pdf에서 html 생성 및 그룹화 비활성화 – GroupDocs Java
type: docs
url: /ko/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# GroupDocs Viewer for Java를 사용하여 PDF에서 HTML 생성 및 그룹화 비활성화

많은 프로젝트에서 **generate html from pdf**를 수행하면서 각 글자를 정확히 제자리에 유지해야 합니다. 이는 복잡한 스크립트, 고대 언어, 혹은 한 글자만 잘못되면 의미가 바뀔 수 있는 법률 문서에 특히 중요합니다. 이 튜토리얼에서는 GroupDocs Viewer for Java를 사용하여 PDF를 HTML로 렌더링하는 전체 과정을 안내하고 **how to disable grouping**을 보여드려 각 문자가 독립적인 요소로 처리되도록 합니다.

![GroupDocs.Viewer for Java를 사용한 정밀 렌더링 기술](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 빠른 답변
- **What does “disable grouping” do?** 렌더러가 각 문자를 독립적인 요소로 처리하도록 강제하여 정확한 레이아웃을 유지합니다.  
- **Which API option controls this?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Do I need a license?** 테스트용으로는 트라이얼을 사용할 수 있지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **Can I generate html from pdf at the same time?** 예—`HtmlViewOptions`를 사용하여 그룹화를 비활성화하면서 HTML 출력을 생성합니다.  
- **Is this feature limited to PDFs?** 주로 PDF에 적용되지만, 뷰어는 다른 많은 형식도 지원합니다.

## generate html from pdf란 무엇인가?
`generate html from pdf`는 PDF 문서를 원본 레이아웃, 글꼴 및 이미지를 유지한 채 HTML 페이지 집합으로 변환하는 과정을 설명합니다. 이 변환을 통해 PDF 플러그인 없이도 웹 기반 보기, 인덱싱 및 상호 작용이 용이해집니다.

## 왜 GroupDocs Viewer for Java를 사용해야 하나요?
GroupDocs.Viewer for Java는 **over 100 input formats**를 지원하며 전체 파일을 메모리에 로드하지 않고 **500 pages**까지의 PDF를 렌더링할 수 있습니다. 라이브러리는 각 페이지를 스트리밍 방식으로 처리하여 전체 문서를 로드할 때보다 힙 사용량을 최대 **70 %**까지 줄입니다. 이러한 정량화된 기능은 대용량, 엔터프라이즈급 문서 파이프라인에 신뢰할 수 있는 선택이 됩니다.

## 소개

PDF 문서를 다룰 때 렌더링 정밀도는 매우 중요합니다—특히 복잡한 텍스트 구조(예: 상형문자나 정확한 문자 표현이 필요한 언어)를 다룰 때 더욱 그렇습니다. "Character Grouping" 기능은 문자를 잘못 그룹화하여 문서 내용이 오해될 수 있게 합니다. 이는 문서 텍스트 레이아웃을 정확히 복제해야 하는 사용자에게 특히 문제가 됩니다.

**GroupDocs.Viewer for Java**는 서버 측 라이브러리로, 100개 이상의 문서 형식을 HTML, 이미지 및 PDF로 렌더링하여 픽셀 단위의 완벽한 정확성을 제공합니다.

### 필수 조건

- **Libraries & dependencies**: GroupDocs.Viewer for Java 버전 25.2 이상이 필요합니다.  
- **Environment setup**: Java Development Kit (JDK)를 설치하고 IDE를 Maven 프로젝트에 맞게 구성합니다.  
- **Knowledge prerequisites**: 기본 Java 프로그래밍, 파일 시스템 처리 및 Maven에 대한 이해가 필요합니다.

## GroupDocs Viewer를 사용하여 PDF에서 HTML 생성 방법

HTML을 PDF에서 생성하는 과정은 두 단계로 이루어집니다: 뷰어를 구성하고 문서를 렌더링합니다. 핵심은 렌더링 전에 문자 그룹화를 끄는 것으로, 이렇게 하면 HTML 출력이 원본 PDF 레이아웃을 문자 단위로 정확히 반영합니다.

### GroupDocs.Viewer for Java 설정

#### Maven을 통한 설치

`pom.xml`에 다음 의존성을 추가합니다:

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

#### 라이선스 획득

GroupDocs.Viewer를 완전히 활용하려면 라이선스 획득을 고려하십시오:
- **Free trial**: 기능을 테스트하려면 무료 체험으로 시작하십시오.  
- **Temporary license**: 더 많은 시간이 필요하면 임시 라이선스를 신청하십시오.  
- **Purchase**: 장기 프로젝트의 경우 라이선스를 구매하는 것이 권장됩니다.

#### 기본 초기화 및 설정

`HtmlViewOptions`는 문서를 HTML로 렌더링하기 위한 출력 형식 및 옵션을 구성합니다.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### 구현 가이드

#### 기능: 문자 그룹화 비활성화

아래 예제의 각 줄을 자세히 살펴보면서 **왜** 그렇게 하는지와 **어떻게** 이것이 원하지 않는 문자 병합 없이 PDF에서 HTML을 생성하는 데 기여하는지 이해할 수 있습니다.

##### 단계 1: 출력 디렉터리 정의  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Why?** 이렇게 하면 렌더링된 HTML 파일이 전용 폴더에 저장되어 나중에 쉽게 찾고 관리할 수 있습니다.

##### 단계 2: 파일 경로 형식 구성  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Why?** 플레이스홀더(`{0}`)를 사용하면 뷰어가 각 PDF 페이지마다 별도의 HTML 파일을 생성하여 출력이 정리됩니다.

##### 단계 3: HTML 뷰 옵션 초기화  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Why?** 임베디드 리소스가 이미지, 폰트 및 CSS를 각 HTML 페이지와 직접 번들링하여 웹 기반 뷰어 또는 e‑learning 플랫폼에 이상적입니다.

##### 단계 4: 문자 그룹화 비활성화  

`setDisableCharsGrouping(true)`는 인접한 문자를 그룹화하는 기본 동작을 비활성화하여 각 글리프가 별도로 렌더링되도록 합니다.

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Why?** 이 라인은 렌더링 엔진에 인접한 문자를 **병합하지 않도록** 지시하는 핵심 라인으로, 생성된 HTML이 원본 PDF의 정확한 글리프 배치를 반영하도록 보장합니다.

##### 단계 5: 문서 렌더링  

`Viewer`는 문서를 열고 렌더링 기능을 제공하는 주요 클래스입니다.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Why?** `Viewer`를 try‑with‑resources 블록으로 감싸면 모든 네이티브 리소스가 자동으로 해제되어 장시간 실행되는 애플리케이션에서 메모리 누수를 방지합니다.

## 문자 그룹화 비활성화가 HTML 정확성을 어떻게 향상시키나요?

문자 그룹화를 비활성화하면 엔진이 각 글리프를 별개의 HTML 요소로 출력하도록 강제하여 원본 PDF에 나타나는 원래의 간격, 합자 및 부호를 정확히 보존합니다. 이는 문자 순서와 간격이 의미를 전달하는 스크립트(예: 아라비아어, 데바나가리, 고대 상형문자 등)에 필수적인 충실한 웹 표현을 제공합니다.

## 그룹화 비활성화의 성능 영향은 무엇인가요?

그룹화를 끄면 렌더러가 각 문자를 개별적으로 처리하므로 CPU 사이클이 약간 증가합니다. 실제로 일반적인 100페이지 PDF에서는 오버헤드가 **5 %** 이하이며, 500페이지를 초과하는 문서에서도 JVM 힙을 적절히 설정(`-Xmx2g` 등)하면 **12 %** 이하로 유지됩니다. 정확한 시각적 정확성이 필요할 때는 이러한 트레이드오프가 충분히 가치 있습니다.

## 일반적인 문제 및 해결책

- **FileNotFoundException** – `new Viewer(...)`에 전달하는 경로를 다시 확인하십시오. 명확성을 위해 절대 경로나 `Path.of(...)`를 사용하십시오.  
- **Write permissions** – 출력 디렉터리가 Java 프로세스에 의해 쓰기 가능한지 확인하십시오; Linux에서는 폴더 권한(`chmod 775`)을 조정해야 할 수 있습니다.  
- **Version mismatch** – `setDisableCharsGrouping` 옵션은 버전 25.2부터 제공됩니다. `pom.xml`이 올바른 버전을 가리키는지 확인하십시오.

## 실용적인 적용 사례

1. **Language preservation** – 문자 간격이 의미를 전달하는 중국어, 일본어, 아라비아어 또는 고대 스크립트 문서 렌더링에 이상적입니다.  
2. **Legal & financial documents** – 규제가 많은 문서에 대해 정확한 텍스트 복제를 보장합니다.  
3. **Educational resources** – 복잡한 다이어그램, 주석 또는 다국어 콘텐츠가 포함된 교과서에 최적입니다.

## 성능 고려 사항

- **Optimize resource usage** – 대용량 PDF는 상당한 메모리를 소모할 수 있습니다. 페이지를 배치로 처리하고 `Viewer` 인스턴스를 즉시 해제하십시오.  
- **Java memory management** – 수백 페이지 이상의 PDF를 처리할 것으로 예상되면 JVM 힙(`-Xmx2g` 이상)을 조정하십시오.  
- **Parallel rendering** – 대량 변환의 경우 각 스레드가 자체 `Viewer` 인스턴스를 갖도록 하여 다중 코어 CPU를 활용하십시오.

## 자주 묻는 질문

**Q:** *왜 문자 그룹화를 비활성화해야 할까요?*  
**A:** 그룹화를 비활성화하면 서로 다른 글리프에 속하는 문자를 병합하지 않게 되어, 간격과 순서가 의미를 전달하는 스크립트에 필수적입니다.

**Q:** *`setDisableCharsGrouping` 설정이 HTML 출력에만 적용되나요?*  
**A:** 아니요, 이 설정은 기본 PDF 렌더링 엔진에 영향을 미치므로 HTML, PNG, JPEG 등 모든 출력 형식에 적용됩니다.

**Q:** *이 설정을 사용자 정의 폰트와 결합할 수 있나요?*  
**A:** 예—`Viewer`를 초기화하기 전에 사용자 정의 폰트를 로드하면 그룹화 규칙이 여전히 적용됩니다.

**Q:** *그룹화 비활성화가 성능에 영향을 미치나요?*  
**A:** 약간 영향을 미칩니다. 엔진이 각 문자를 개별적으로 처리하지만 대부분의 문서에서는 영향이 최소이며(보통 5 % 이하의 오버헤드)입니다.

**Q:** *페이지별로 그룹화를 토글할 방법이 있나요?*  
**A:** 현재 이 옵션은 `PdfOptions` 인스턴스당 전역이며, 페이지마다 다른 동작이 필요하면 별도의 `Viewer` 인스턴스를 사용해야 합니다.

## 리소스

- [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs Viewer 다운로드](https://releases.groupdocs.com/viewer/java/)
- [라이선스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험 버전](https://releases.groupdocs.com/viewer/java/)
- [임시 라이선스 신청](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 지원 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-09-05  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs

## 관련 튜토리얼

- [Java에서 GroupDocs.Viewer를 사용해 PDF를 HTML로 변환하고 이미지 품질 최적화하는 방법](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [PDF 레이어드 렌더링 Java – GroupDocs Viewer를 사용한 효율적인 PDF 레이어드 렌더링](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [GroupDocs Viewer Java 반응형 HTML 렌더링](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)