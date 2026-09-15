---
date: '2026-09-15'
description: GroupDocs.Viewer for Java를 사용하여 맞춤 datetime 형식 및 timezone offset을 적용해
  eml을 html로 변환하는 방법을 배웁니다—이메일 보관 및 지원 포털에 이상적입니다.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: GroupDocs.Viewer for Java를 사용하여 맞춤 datetime 형식 및 timezone offset을
  적용해 eml을 html로 변환합니다. 정확한 email 렌더링을 위해 이 step‑by‑step 가이드를 따라 주세요.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: GroupDocs.Viewer를 사용하여 Java에서 맞춤 datetime으로 eml을 html로 변환
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: GroupDocs.Viewer를 사용하여 Java에서 맞춤 datetime으로 eml을 html로 변환
type: docs
url: /ko/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Java에서 GroupDocs.Viewer를 사용하여 사용자 지정 날짜/시간으로 eml을 html로 변환

현대적인 지원 및 보관 시스템에서 **eml을 html로 변환**하면서 정확한 타임스탬프를 유지하는 것은 필수 기능입니다. 이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 EML 이메일을 HTML로 렌더링하고 **사용자 지정 날짜/시간 형식**을 적용하며 **시간대 오프셋**을 설정하는 방법을 보여줍니다. 끝까지 따라 하면 **이메일을 html로 변환** 워크플로우에 사용할 수 있는 재사용 가능한 스니펫을 얻을 수 있습니다.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## 빠른 답변
- **GroupDocs.Viewer가 EML을 HTML로 변환할 수 있나요?** 예 – API가 외부 메일 클라이언트 없이 EML 파일을 직접 HTML로 렌더링합니다.  
- **프로덕션에 라이선스가 필요합니까?** 테스트용 무료 체험판이면 충분합니다; 프로덕션 배포에는 유료 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상을 완벽히 지원합니다.  
- **표시되는 날짜 형식을 어떻게 변경하나요?** `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`를 호출합니다.  
- **시간대를 조정할 수 있나요?** 예, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`를 사용합니다.

## “eml을 html로 변환”이란?
`Convert eml to html`은 EML 이메일 파일을 브라우저에서 렌더링할 수 있는 HTML 문서로 변환하는 과정입니다. EML 파일을 HTML로 변환하면 헤더, 본문, 첨부 파일을 포함한 원시 이메일을 웹 친화적인 형식으로 바꿔 브라우저가 별도 플러그인 없이 표시할 수 있게 됩니다. 이를 통해 웹 애플리케이션, 아카이브, 지원 대시보드 등에 이메일을 쉽게 삽입할 수 있습니다.

## 이 작업에 GroupDocs.Viewer를 사용하는 이유
GroupDocs.Viewer는 **50개 이상의 입력 및 출력 형식**을 지원하며, EML, MSG, PST, PDF 등을 포함합니다. 또한 전체 파일을 메모리에 로드하지 않고 수백 페이지에 달하는 이메일을 렌더링할 수 있습니다. Outlook이나 서드파티 파서를 필요로 하지 않는 무의존성 엔진으로 **사용자 지정 날짜/시간 형식**과 **시간대 오프셋**을 완벽히 제어하면서 리소스 사용량을 최소화합니다.

## 사전 요구 사항
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ 및 Java IDE (IntelliJ IDEA, Eclipse, VS Code)  
- Maven(의존성 관리)

## GroupDocs.Viewer for Java 설정

### Maven 구성
`pom.xml` 파일에 GroupDocs 저장소와 Viewer 의존성을 추가합니다.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
무료 체험판으로 시작하거나 테스트 기간 연장을 위해 임시 라이선스를 요청합니다. 프로덕션 사용을 위해서는 정식 라이선스를 구매합니다.

### 기본 초기화
변환하려는 EML 파일을 가리키는 `Viewer` 인스턴스를 생성합니다.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Java에서 사용자 지정 날짜/시간으로 eml을 html로 변환

다음 단계에서는 EML 파일을 HTML로 렌더링하면서 사용자 지정 날짜/시간 형식과 시간대 오프셋을 적용하는 방법을 안내합니다.

### 단계 1: 출력 디렉터리 및 파일 경로 설정
생성된 HTML이 저장될 위치를 정의합니다.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*설명:* `Path.of()`는 HTML이 저장될 폴더에 대한 참조를 생성합니다. `resolve()`는 파일 이름을 추가합니다.

### 단계 2: 이메일 파일로 Viewer 초기화
대상 EML 파일에 대해 `Viewer` 클래스를 인스턴스화합니다.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*설명:* `Viewer` 인스턴스는 변환하려는 EML 파일을 가리킵니다.

### 단계 3: HtmlViewOptions 구성
이미지 및 기타 리소스를 HTML 출력에 직접 포함하도록 `HtmlViewOptions` 객체를 생성합니다.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*설명:* `forEmbeddedResources()`는 이미지와 기타 리소스를 HTML에 직접 포함합니다.

### 단계 4: 사용자 지정 날짜/시간 형식 설정 *(custom datetime java)*
`setDateTimeFormat`은 이메일 타임스탬프를 렌더링할 때 사용할 날짜‑시간 패턴을 지정합니다.  
렌더링된 HTML의 모든 타임스탬프에 적용될 패턴을 정의합니다.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*설명:* 이 패턴은 월, 일, 연도, 시, 분, AM/PM 표시 및 시간대 오프셋(`zzz`)을 표시합니다.

### 단계 5: 시간대 오프셋 설정 *(timezone offset java)*
`setTimeZoneOffset`은 모든 이메일 타임스탬프에 적용될 시간대를 지정합니다.  
원하는 시간대로 타임스탬프를 조정합니다.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*설명:* 렌더링된 타임스탬프를 원하는 시간대로 조정합니다. `"GMT+1"`을 유효한 영역 식별자로 교체하면 됩니다.

### Java에서 이메일 시간대 조정 방법
단순 오프셋을 넘어 **이메일 시간대 조정**이 필요할 경우, `java.util.TimeZone` API에서 `"Europe/Paris"` 또는 `"America/New_York"`와 같은 지역 ID를 사용해 적절한 `TimeZone` 객체를 가져와 `setTimeZoneOffset`에 전달하면 됩니다. 이렇게 하면 이메일 타임스탬프가 항상 올바른 현지 시간을 반영합니다.

### 단계 6: 문서 렌더링
변환을 실행하고 최종 HTML 파일을 생성합니다.

```java
viewer.view(options);
```
*설명:* 변환을 실행하여 사용자 지정 날짜‑시간 설정이 적용된 HTML 파일을 생성합니다.

## 사용자 지정 날짜/시간 형식이 렌더링된 HTML에 미치는 영향
사용자 지정 날짜/시간 형식은 생성된 HTML에서 각 이메일 타임스탬프가 어떻게 표시되는지를 결정합니다. `"MMM dd, yyyy hh:mm a zzz"`와 같은 패턴을 지정하면 월 약어, 일, 연도, 시, 분, AM/PM 표시 및 명시적인 시간대 오프셋이 일관되게 표시되어 전 세계 지원 팀이 날짜 정보를 정확히 이해할 수 있습니다.

## GroupDocs.Viewer가 지원하는 이메일 렌더링 파일 형식은?
GroupDocs.Viewer는 **EML, MSG, PST, MBOX, EMLX** 파일을 HTML, PDF, PNG, JPEG 등으로 렌더링할 수 있습니다. 총 50개 이상의 문서 및 이미지 형식을 지원하므로 추가 변환 도구 없이도 가장 일반적인 웹 친화적 출력으로 이메일을 변환할 수 있습니다.

## 여러 eml 파일을 배치 변환하려면?
모든 EML 파일을 하나의 디렉터리에 넣고 `for` 또는 `foreach` 루프를 사용해 각 파일을 순회합니다. 동일한 `HtmlViewOptions` 인스턴스를 재사용하고 각 파일에 대해 `viewer.view`를 호출하면 객체 생성 오버헤드가 최소화되고 대량 변환 속도가 향상됩니다.

## 문제 해결 팁
- **FileNotFoundException:** `Viewer`와 `Path.of()`에 사용된 경로를 확인합니다.  
- **잘못된 타임스탬프:** `TimeZone` ID가 목표 지역과 일치하는지 확인합니다.  
- **이미지 누락:** `HtmlViewOptions.forEmbeddedResources()`를 사용했는지 확인합니다. 그렇지 않으면 외부 리소스가 제외될 수 있습니다.

## 실용적인 적용 사례
1. **이메일 아카이빙:** 규정 준수를 위한 검색 가능한 HTML 스냅샷을 저장합니다.  
2. **고객 지원 포털:** 전 세계 에이전트가 정확한 현지 시간을 확인할 수 있도록 티켓에 표시합니다.  
3. **법률 문서:** 표준화된 타임스탬프가 포함된 법원 제출용 이메일 기록을 생성합니다.

## 성능 고려 사항
- 대량 변환을 위해 전용 서버에 배포합니다.  
- Java 힙 사용량을 모니터링하고 `OutOfMemoryError`가 발생하면 `-Xmx` 옵션을 늘립니다.  
- 동일한 이메일이 반복 요청될 경우 렌더링된 HTML을 캐시하여 CPU 부하를 줄입니다.

## 결론
이제 GroupDocs.Viewer for Java를 사용해 **eml을 html로 변환**하면서 사용자 지정 날짜/시간 형식과 시간대 오프셋을 적용하는 완전한 프로덕션‑레디 방법을 갖추었습니다. 이 솔루션은 가독성을 높이고 타임스탬프 정확성을 보장하며 아카이빙, 지원, 법률 워크플로우에 자연스럽게 통합됩니다.

**다음 단계:** 커스텀 CSS 삽입, 페이지 매김 또는 PDF 변환과 같은 추가 Viewer 옵션을 탐색하여 애플리케이션 요구에 맞게 출력을 더욱 맞춤화하세요.

## 자주 묻는 질문

**Q: 첨부 파일이 있는 eml 파일은 어떻게 처리하나요?**  
A: `HtmlViewOptions.forEmbeddedResources()`를 사용하면 첨부 파일이 자동으로 포함됩니다. 별도 파일이 필요하면 Viewer API를 통해 추출할 수도 있습니다.

**Q: HTML 템플릿을 변경하거나 커스텀 CSS를 추가할 수 있나요?**  
A: 예, 렌더링 후 생성된 HTML 파일을 편집하거나 저장하기 전에 프로그래밍 방식으로 CSS를 주입할 수 있습니다.

**Q: 여러 eml 파일을 배치로 렌더링할 수 있나요?**  
A: 렌더링 로직을 루프에 넣고 각 파일마다 동일한 `HtmlViewOptions` 인스턴스를 재사용하면 됩니다.

**Q: msg와 같은 다른 이메일 형식을 지원하려면 어떻게 해야 하나요?**  
A: GroupDocs.Viewer는 MSG, PST 등 다른 이메일 컨테이너도 지원하므로 `Viewer` 생성자에 파일 확장자를 변경하기만 하면 됩니다.

**Q: 서버마다 별도의 라이선스가 필요합니까?**  
A: 라이선스는 배포당 적용됩니다; 다중 서버 시나리오에 대해서는 GroupDocs 라이선스 가이드를 참고하세요.

## 리소스

- [문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [다운로드](https://releases.groupdocs.com/viewer/java/)
- [구매](https://purchase.groupdocs.com/buy)
- [무료 체험](https://releases.groupdocs.com/viewer/java/)
- [임시 라이선스](https://purchase.groupdocs.com/temporary-license/)
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-09-15  
**테스트 환경:** GroupDocs.Viewer 25.2 (Java)  
**작성자:** GroupDocs

## 관련 튜토리얼

- [이메일을 HTML로 변환하고 필드 이름 바꾸기 – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – GroupDocs.Viewer로 이메일‑PDF 렌더링 최적화](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java 반응형 HTML 렌더링](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
