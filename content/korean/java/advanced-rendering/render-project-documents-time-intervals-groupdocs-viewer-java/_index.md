---
date: '2026-09-25'
description: GroupDocs Viewer for Java를 사용하여 mpp HTML 보기를 만드는 방법을 배우고, 시간 간격별로 프로젝트
  문서를 렌더링하는 단계별 코드를 확인하세요.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: GroupDocs Viewer for Java를 사용하여 Microsoft Project 파일을 특정 시간 간격으로 렌더링하고,
  단계별 설정, 라이선스 및 코드 스니펫을 따라 정확한 타임라인 시각화를 구현하세요.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: GroupDocs Viewer for Java로 mpp HTML 보기 만들기
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: GroupDocs Viewer (Java)를 사용하여 mpp HTML 보기 만들기
type: docs
url: /ko/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Java에서 시간 간격별 프로젝트 문서를 렌더링하기 위해 GroupDocs Viewer 사용 방법

이 튜토리얼에서는 GroupDocs Viewer for Java를 사용하여 **create html view mpp**를 만드는 방법을 배우게 되며, 특정 시작 날짜와 종료 날짜 범위에 해당하는 Microsoft Project 파일의 일부만 렌더링할 수 있습니다. Maven 설정, 라이선스, 그리고 애플리케이션에 정확한 타임라인 뷰를 직접 삽입하기 위해 필요한 API 호출을 단계별로 안내합니다.

![시간 간격별 프로젝트 문서 렌더링 with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

미리 보려면 [Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)를 확인하세요.

## 빠른 답변
- **What does the feature do?** 시작 날짜와 종료 날짜 사이에 해당하는 Microsoft Project 파일의 일부만 렌더링합니다.  
- **Which output format is used?** 웹 통합에 적합한 임베디드 리소스가 포함된 HTML.  
- **Do I need a license?** 평가용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **Can I change the date range at runtime?** 예—렌더링 옵션에서 `setStartDate`와 `setEndDate` 값을 조정하면 됩니다.  
- **Is this supported on all Java versions?** GroupDocs.Viewer 25.2 이상을 사용하면 Java 8+에서 작동합니다.

## create html view mpp란?
`create html view mpp`는 Microsoft Project 파일(`.mpp` 또는 `.mpt`)을 일정을 나타내는 HTML 페이지 집합으로 변환하는 과정입니다. GroupDocs Viewer는 서버 측에서 변환을 수행하므로 Microsoft Project를 설치하지 않아도 브라우저에서 타임라인을 표시할 수 있습니다.

## 왜 시간 간격별로 프로젝트 문서를 렌더링하나요?
필요한 시간 간격만 렌더링하면 생성된 HTML 크기가 감소하고 페이지 로드 속도가 빨라지며 분석이 필요한 특정 프로젝트 단계에 집중할 수 있습니다. 이러한 타깃 뷰는 대시보드, 상태 보고서 또는 전체 프로젝트 데이터가 과도할 수 있는 맞춤형 PM 도구에 삽입하기에 이상적입니다.

## 사전 요구 사항
- **GroupDocs.Viewer for Java** 버전 25.2 이상.  
- Java Development Kit (JDK) 8 이상.  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
- 기본 Maven 지식.  

## GroupDocs.Viewer for Java 설정

### Maven 의존성

`pom.xml`에 저장소와 의존성을 추가합니다:

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

### 라이선스 획득 단계

1. **Free trial** – [GroupDocs 다운로드 페이지](https://releases.groupdocs.com/viewer/java/)에서 체험 버전을 다운로드합니다.  
2. **Temporary license** – [temporary‑license 페이지](https://purchase.groupdocs.com/temporary-license/)를 통해 연장 테스트용 임시 라이선스를 획득합니다.  
3. **Purchase** – 제한 없는 프로덕션 사용을 위해 [GroupDocs 구매 페이지](https://purchase.groupdocs.com/buy)에서 라이선스를 구매합니다.

## 기본 Viewer 초기화

`Viewer`는 문서를 로드하고 렌더링 기능을 제공하는 GroupDocs.Viewer for Java의 주요 클래스입니다.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## 프로젝트 파일에 대한 뷰 정보 가져오기

`ProjectManagementViewInfo`는 Microsoft Project 파일에 대한 메타데이터를 제공하며, 전체 일정의 시작 및 종료 날짜를 포함합니다.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## HTML 렌더링 옵션 구성 (프로젝트에서 HTML 생성)

`HtmlViewOptions`는 GroupDocs가 HTML을 렌더링하는 방식을 구성하며, 날짜 범위 설정, 리소스 임베드, 외관 맞춤화를 할 수 있습니다.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## 렌더링 프로세스 실행

`viewer.render`는 제공된 옵션에 따라 변환을 실행하고 결과 HTML 파일을 대상 폴더에 기록합니다.

```java
viewer.view(viewOptions);
```

## 일반적인 함정 및 문제 해결
- **Incorrect file paths** – 소스 `.mpp` 파일과 출력 디렉터리가 모두 존재하는지 다시 확인하십시오.  
- **Unsupported file type** – 문서가 지원되는 Project 형식(예: `.mpp`, `.mpt`)인지 확인하십시오.  
- **License errors** – 체험 라이선스는 렌더링 제한을 둘 수 있으므로, 제한 없는 사용을 위해 정식 라이선스로 전환하십시오.  

## 실용적인 적용 사례
1. **Project timeline analysis** – 이해관계자에게 현재 단계만 표시합니다.  
2. **Automated reporting** – 주간 상태 업데이트를 위한 시간 제한 HTML 보고서를 생성합니다.  
3. **Integration with dashboards** – 렌더링된 페이지를 BI 도구나 맞춤형 포털에 삽입합니다.  
4. **Archival** – 향후 참조를 위해 프로젝트 일정의 웹 친화적인 스냅샷을 저장합니다.  

## 성능 팁
- *embedded resources* 옵션을 사용하여 각 HTML 페이지를 자체 포함형으로 유지하면 HTTP 요청을 줄일 수 있습니다.  
- 매우 큰 프로젝트의 경우 메모리 사용량을 낮게 유지하기 위해 작은 날짜 청크로 렌더링하는 것을 고려하십시오. 1년 단위로 렌더링하면 전체 프로젝트 내보내기에 비해 HTML 크기를 최대 80 %까지 줄일 수 있어 일반 서버에서 로드 시간이 몇 초에서 1초 이하로 단축됩니다.  
- 제공 후 임시 파일을 정리하여 디스크 용량이 늘어나는 것을 방지하십시오.  

## 결론
이제 **how to use GroupDocs** Viewer를 사용하여 특정 시간 간격 내에서 프로젝트 문서를 렌더링하고 Java에서 **generate HTML from project** 데이터를 생성하는 방법을 알게 되었습니다. 이 기능은 타임라인 시각화를 간소화하고 보고 효율성을 향상시키며 최신 웹 애플리케이션과 원활하게 통합됩니다.

### 다음 단계
- 워터마킹, 비밀번호 보호, 맞춤 CSS 스타일링 등 추가 Viewer 기능을 탐색하십시오.  
- 이 렌더링 파이프라인을 REST API와 결합하여 필요에 따라 타임라인 뷰를 제공하십시오.  

## 자주 묻는 질문
**Q: GroupDocs.Viewer가 지원하는 파일 형식은 무엇인가요?**  
A: GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 및 Microsoft Project 파일을 포함한 100개 이상의 입력 형식을 지원하여 범용 문서 시각화를 가능하게 합니다.

**Q: GroupDocs.Viewer의 무료 체험을 시작하려면 어떻게 해야 하나요?**  
A: 무료 체험 버전은 [GroupDocs Viewer Java 다운로드 페이지](https://releases.groupdocs.com/viewer/java/)에서 다운로드할 수 있습니다.

**Q: 리소스를 임베드하지 않고 문서를 렌더링할 수 있나요?**  
A: 예, 리소스를 임베드하지 않고 외부 리소스를 참조하는 다른 HTML 뷰 옵션을 선택할 수 있습니다.

**Q: 문서가 너무 커서 렌더링이 어려운 경우는 어떻게 해야 하나요?**  
A: 위에서 설명한 대로 문서를 작은 섹션으로 나누거나 필요한 날짜 범위만 렌더링하는 것을 고려하십시오.

**Q: 렌더링 오류를 어떻게 처리하나요?**  
A: 모든 구성 설정을 확인하고, 유효한 라이선스가 있는지 확인한 뒤, 자세한 오류 코드는 GroupDocs 문서를 참고하십시오.

## 리소스
- **문서**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 참조**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **다운로드**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **구매**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **무료 체험**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **임시 라이선스**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **지원**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-09-25  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## 관련 튜토리얼
- [GroupDocs.Viewer for Java를 사용하여 메모와 함께 MS Project 파일을 HTML, JPG, PNG, PDF로 렌더링하는 방법](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [MS Project HTML 내보내기: GroupDocs Java를 통해 시간 단위 조정](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [GroupDocs Viewer Java 반응형 HTML 렌더링](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)