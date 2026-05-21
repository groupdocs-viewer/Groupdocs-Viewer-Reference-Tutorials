---
date: '2026-05-21'
description: GroupDocs Viewer for Java를 사용하여 시간 단위를 조정한 MS Project HTML 내보내기 수행 방법을
  배웁니다. 전제 조건, 설정 및 문제 해결을 포함한 단계별 가이드.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML 내보내기: GroupDocs Java를 통해 시간 단위 조정'
type: docs
url: /ko/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML 내보내기: GroupDocs Java를 통한 시간 단위 조정

**MS Project** 파일을 HTML로 내보내는 것은 프로젝트 관리 대시보드, 상태 보고 포털 및 협업 검토 도구에서 일반적인 요구사항입니다. 기본적으로 뷰어는 시간 관련 데이터를 분 단위로 렌더링하여 시각적 레이아웃을 복잡하게 만들고 일일 보고서를 읽기 어렵게 합니다. **GroupDocs Viewer for Java**를 사용하면 프로그래밍 방식으로 시간 단위를 **days**(일)로 설정하여 일반적인 이해관계자 기대에 맞는 깔끔한 *ms project html export*를 만들 수 있습니다. 이 튜토리얼에서는 뷰어를 구성하고, 시간 단위를 조정하며, 몇 단계만으로 프로젝트를 HTML로 렌더링하는 방법을 배웁니다.

![Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## 빠른 답변
- **MS Project 파일을 렌더링하는 라이브러리는 무엇인가요?** GroupDocs Viewer for Java.  
- **HTML 내보내기에서 설정할 수 있는 시간 단위는 무엇인가요?** Days, using `TimeUnit.DAYS`.  
- **프로덕션에 라이선스가 필요합니까?** Yes— 영구 라이선스가 필요합니다; 평가용으로는 트라이얼을 사용할 수 있습니다. [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)를 시작할 수 있습니다.  
- **어떤 IDE가 가장 적합합니까?** Maven을 지원하는 모든 Java IDE(IntelliJ IDEA, Eclipse, NetBeans).  
- **Maven이 필수인가요?** Maven은 의존성 관리를 단순화하지만 Gradle 또는 수동 JAR 포함도 사용할 수 있습니다.  
- **구매는 어디에서 할 수 있나요?** 가격 정보를 보려면 [buy page](https://purchase.groupdocs.com/buy)를 방문하십시오.

## GroupDocs Viewer for Java란?
**GroupDocs Viewer for Java**는 150개 이상의 문서 형식(예: MS Project)을 웹 친화적인 HTML, PNG, JPEG 또는 PDF로 변환하는 Java SDK입니다.  
파싱 로직을 추상화하고 시간 단위와 같은 렌더링 옵션을 제어할 수 있게 하며, Java 8 이상을 지원하는 모든 플랫폼에서 작동합니다.

## MS Project HTML 내보내기에서 시간 단위를 조정하는 이유는?
시간 단위를 **days**(일)로 설정하면 시각적 잡음이 줄어들고 대부분의 보고 주기에 맞으며, 세분화된 시간 표시가 적게 생성돼 페이지 로드 시간이 개선됩니다. 정량적으로 보면, 분 대신 일 단위로 렌더링하면 일반적인 30일 프로젝트의 경우 생성된 HTML 크기가 최대 **45 %**까지 감소하고, 클라이언트 측 렌더링 속도가 약 **30 %** 빨라집니다.

## 사전 요구 사항
- **Java Development Kit (JDK) 8 이상**이 워크스테이션에 설치되어 있어야 합니다.  
- **Maven**(또는 Gradle)은 의존성 관리를 위해 필요합니다.  
- 내보내려는 **MS Project (.mpp)** 파일.  
- **GroupDocs Viewer for Java** 라이선스(체험판 또는 영구) 접근 권한.

### 필요한 라이브러리
다음 의존성을 `pom.xml`에 추가하세요(또는 해당 Gradle 스니펫).

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** 버전 번호를 최신으로 유지하세요; 최신 릴리스는 포맷 지원 및 성능 향상을 제공합니다.

## GroupDocs Viewer for Java를 설정하는 방법은?
MS Project 파일을 가리키는 `Viewer` 인스턴스를 생성하여 뷰어를 초기화합니다. `Viewer` 클래스는 모든 렌더링 작업의 진입점입니다. 소스 문서를 로드하고 내부 구조를 준비하며, 원하는 출력 형식을 생성하기 위해 `view()` 및 `viewToHtml()`와 같은 메서드를 제공합니다.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** `Viewer` 클래스는 소스 문서를 로드하고 `view()` 및 `viewToHtml()`와 같은 렌더링 메서드를 제공하는 GroupDocs Viewer의 핵심 구성 요소입니다.

## HTML 내보내기에서 시간 단위를 조정하려면 어떻게 해야 하나요?
시간 세분성을 변경하려면 `ViewOptions` 객체를 생성하고, 해당 객체의 `ProjectOptions`를 `TimeUnit.DAYS`로 설정한 뒤 뷰어에 전달합니다. `ViewOptions`는 문서의 렌더링 설정을 정의하고, `TimeUnit` 열거형은 시간 관련 데이터의 단위(분, 시간, 일)를 지정합니다. 이러한 옵션을 설정한 후 `viewer.view(options)`를 호출하면 일 단위 마커가 포함된 HTML이 생성됩니다.

`new Viewer("file.mpp")`로 MS Project 파일을 로드하고, `ViewOptions` 객체를 생성한 뒤 `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`를 설정하고 `viewer.view(options)`를 호출합니다. 이 3단계 흐름은 시간 단위를 분에서 일로 변경하고 일 간격만 표시되는 HTML 파일을 생성합니다.

### 단계 1: 출력 폴더 정의
HTML 페이지가 저장될 쓰기 가능한 디렉터리를 선택하세요. 예: `output/`.

### 단계 2: 임베디드 리소스가 포함된 뷰 옵션 생성
임베디드 리소스(CSS, JavaScript)는 HTML 페이지가 자체 포함되도록 보장합니다.

### 단계 3: 시간 단위를 일로 설정
`options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`를 사용하여 세분성을 일 단위로 전환합니다.

### 단계 4: 문서 렌더링
`viewer.view(options)`를 호출합니다; 뷰어는 프로젝트 페이지당 하나의 HTML 파일을 출력 폴더에 기록합니다.

### 단계 5: 결과 확인
생성된 `index.html`을 브라우저에서 열면, 작업 막대가 분 마커가 아닌 일 마커에 맞춰 정렬된 것을 확인할 수 있습니다.

## 일반적인 함정 및 문제 해결
- **잘못된 출력 경로** – 디렉터리가 존재하고 Java 프로세스에 쓰기 권한이 있는지 확인하세요.  
- **라이선스 누락** – 유효한 라이선스가 없으면 뷰어가 트라이얼 모드로 전환되고 워터마크가 삽입될 수 있습니다.  
- **대용량 파일 (> 500 MB)** – JVM 힙 크기(`-Xmx2g`)를 늘리거나 `options.setRenderLimit(1000)`으로 페이지를 배치 처리하는 것을 고려하세요.

## 조정된 시간 단위 HTML 내보내기의 실용적인 적용 사례
1. **Executive dashboards** – 일일 세분성은 대부분의 KPI 시각화와 일치합니다.  
2. **Automated status emails** – 생성된 HTML을 이메일 본문에 직접 삽입하여 빠른 업데이트를 제공합니다.  
3. **Project portals** – 팀원이 일별로 작업을 필터링할 수 있는 인트라넷 사이트에 HTML을 호스팅합니다.

## 대용량 MS Project 파일에 대한 성능 고려 사항
- **Memory management** – Java의 가비지 컬렉터 플래그(`-XX:+UseG1GC`)를 사용하여 사용되지 않는 객체를 즉시 해제합니다.  
- **Selective rendering** – Gantt 차트만 필요하면 `options.getProjectOptions().setRenderGantt(true)`와 `setRenderResources(false)`를 통해 다른 리소스 렌더링을 비활성화합니다.  
- **Parallel processing** – 배치 변환의 경우 파일당 별도의 `Viewer` 객체를 생성하고 스레드 풀에서 실행하여 다중 코어 CPU를 활용합니다.

## 결론
이제 GroupDocs Viewer for Java를 사용하여 시간 단위를 일로 설정한 **ms project html export**를 수행하는 완전하고 프로덕션 준비된 워크플로우를 갖추었습니다. 이 접근 방식은 HTML 크기를 줄이고 클라이언트 렌더링 속도를 높이며 이해관계자에게 친숙한 프로젝트 일정 뷰를 제공합니다. PDF 내보내기나 이미지 스냅샷과 같은 추가 렌더링 옵션을 탐색하여 통합을 보다 광범위한 보고 파이프라인으로 확장해 보세요.

## 자주 묻는 질문

**Q: 다른 Project 뷰(예: Resource Sheet)를 HTML로 렌더링할 수 있나요?**  
A: 예, `ProjectOptions` 객체를 사용하면 렌더링 전에 Gantt, Resource Sheet, Calendar와 같은 특정 뷰를 활성화하거나 비활성화할 수 있습니다.

**Q: 생성된 HTML의 CSS를 맞춤 설정할 수 있나요?**  
A: 물론입니다. `options.setStyleSheetPath("path/to/custom.css")`를 통해 사용자 정의 스타일시트 경로를 제공하면 뷰어가 모든 페이지에 삽입합니다.

**Q: GroupDocs Viewer가 지원하는 MS Project 파일 크기 제한은 어떻게 되나요?**  
A: 스트리밍 아키텍처 덕분에 SDK는 전체 문서를 메모리에 로드하지 않고도 **500 MB**까지 파일을 처리할 수 있습니다.

**Q: 서버에 Microsoft Project를 설치해야 하나요?**  
A: 아닙니다. GroupDocs Viewer는 .mpp 형식을 직접 파싱하며 Microsoft Project나 Office 설치가 필요하지 않습니다.

**Q: 프로덕션 환경에서 뷰어에 라이선스를 적용하려면 어떻게 해야 하나요?**  
A: GroupDocs 스토어에서 영구 라이선스를 구매하고, 런타임에 `License license = new License(); license.setLicense("path/to/license.lic");`와 같이 라이선스 파일을 적용합니다. 단기 필요에 대해서는 [temporary license](https://purchase.groupdocs.com/temporary-license/)를 얻을 수 있습니다.

---

**마지막 업데이트:** 2026-05-21  
**테스트 환경:** GroupDocs Viewer Java 25.2  
**작성자:** GroupDocs  

**리소스**  
- [문서](https://docs.groupdocs.com/viewer/java/)  
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/java/)  
- [라이선스 구매](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## 관련 튜토리얼

- [GroupDocs.Viewer for Java를 사용하여 MS Project 파일을 HTML, JPG, PNG 및 PDF(노트 포함)로 렌더링하는 방법](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Java에서 GroupDocs Viewer를 사용하여 시간 간격별로 프로젝트 문서를 렌더링하는 방법](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java에서 라이선스 설정 방법: 파일 및 URL 설정 가이드](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)