---
date: '2026-01-15'
description: 특정 시간 간격 내에서 프로젝트 문서에서 HTML을 생성하기 위해 GroupDocs Viewer를 사용하는 방법을 배웁니다.
  이 가이드는 설정, 코드 및 실제 사용 사례를 다룹니다.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Java에서 GroupDocs Viewer를 사용하여 시간 간격별 프로젝트 문서 렌더링하는 방법
type: docs
url: /ko/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Java에서 시간 간격별 프로젝트 문서를 렌더링하기 위해 GroupDocs Viewer 사용 방법

프로젝트 일정을 특정 시간 창에서 렌더링하기 위한 **how to use GroupDocs**를 찾고 있다면, 여기가 바로 정답입니다. 이 튜토리얼에서는 Maven 설정부터 프로젝트 문서에서 HTML을 생성하는 전체 과정을 단계별로 안내하므로, 정확한 타임라인 뷰를 애플리케이션에 직접 삽입할 수 있습니다.

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## 빠른 답변
- **What does the feature do?** 시작 날짜와 종료 날짜 사이에 해당하는 Microsoft Project 파일의 일부만 렌더링합니다.  
- **Which output format is used?** 웹 통합에 적합한 임베디드 리소스가 포함된 HTML.  
- **Do I need a license?** 평가용으로는 무료 체험판으로 충분하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **Can I change the date range at runtime?** 예—렌더링 옵션에서 `setStartDate`와 `setEndDate` 값을 조정하면 됩니다.  
- **Is this supported on all Java versions?** GroupDocs.Viewer 25.2 이상을 사용한다면 Java 8+에서 작동합니다.

## 이 맥락에서 “How to Use GroupDocs”란 무엇인가요?
GroupDocs Viewer는 100개 이상의 파일 형식을 웹 친화적인 형태로 변환하는 Java 라이브러리입니다. 프로젝트 파일에 대해 **how to use GroupDocs**를 수행하면, 클라이언트 측에 Microsoft Project가 없어도 일정 데이터를 추출·시각화·공유할 수 있는 기능을 얻게 됩니다.

## 왜 시간 간격으로 프로젝트 문서를 렌더링할까요?
- **Focused analysis:** 관심 있는 단계만 표시합니다 (예: 2024년 3분기).  
- **Performance:** HTML 출력이 작아져 페이지 로드가 빨라집니다.  
- **Integration:** 대시보드, 보고 포털 또는 맞춤형 PM 도구에 타임라인 뷰를 삽입합니다.

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
1. **Free Trial** – [GroupDocs 다운로드 페이지](https://releases.groupdocs.com/viewer/java/)에서 체험판을 다운로드합니다.  
2. **Temporary License** – [이 링크](https://purchase.groupdocs.com/temporary-license/)를 통해 연장 테스트용 임시 라이선스를 획득합니다.  
3. **Purchase** – 제한 없는 프로덕션 사용을 위해 [GroupDocs 구매 페이지](https://purchase.groupdocs.com/buy)에서 라이선스를 구매합니다.

### 기본 Viewer 초기화
다음 스니펫은 Microsoft Project 파일(`.mpp`)을 가리키는 `Viewer` 인스턴스를 생성하는 방법을 보여줍니다:

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

## 단계별 구현 가이드
### 1. 출력 디렉터리 정의
생성된 HTML 페이지를 저장할 폴더를 만듭니다:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Why?* 렌더링된 파일을 정리하면 웹 서버에서 제공하거나 UI에 삽입하기가 더 쉬워집니다.

### 2. 프로젝트 파일로 Viewer 초기화
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Why?* 문서를 로드하면 내부 파서가 준비되고 프로젝트별 메타데이터에 접근할 수 있게 됩니다.

### 3. 프로젝트 파일에 대한 뷰 정보 가져오기
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Why?* `ProjectManagementViewInfo`는 일정의 시작 및 종료 날짜를 제공하며, 이후 렌더링 범위를 제한하는 데 사용됩니다.

### 4. HTML 렌더링 옵션 구성 (프로젝트에서 HTML 생성)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Why?* `StartDate`와 `EndDate`를 설정하면 해당 기간 내의 프로젝트 데이터만을 대상으로 GroupDocs가 **HTML을 생성**하도록 지정합니다.

### 5. 렌더링 프로세스 실행
```java
viewer.view(viewOptions);
```

*Why?* 이 호출은 선택한 시간 구간의 프로젝트 일정을 나타내는 자체 포함형 HTML 페이지 시리즈를 생성합니다.

## 일반적인 함정 및 문제 해결
- **Incorrect file paths** – 소스 `.mpp` 파일과 출력 디렉터리가 모두 존재하는지 다시 확인하세요.  
- **Unsupported file type** – 문서가 지원되는 Project 형식인지 확인하세요 (예: `.mpp`, `.mpt`).  
- **License errors** – 체험판 라이선스는 렌더링 제한이 있을 수 있으니, 제한 없는 사용을 위해 정식 라이선스로 전환하세요.

## 실용적인 적용 사례
1. **Project Timeline Analysis** – 이해관계자에게 현재 단계만 보여줍니다.  
2. **Automated Reporting** – 주간 상태 업데이트를 위한 시간 제한 HTML 보고서를 생성합니다.  
3. **Integration with Dashboards** – 렌더링된 페이지를 BI 도구나 맞춤 포털에 삽입합니다.  
4. **Archival** – 향후 참조를 위해 프로젝트 일정의 웹 친화적인 스냅샷을 저장합니다.

## 성능 팁
- *embedded resources* 옵션을 사용하여 각 HTML 페이지를 자체 포함형으로 유지하면 HTTP 요청 수를 줄일 수 있습니다.  
- 매우 큰 프로젝트의 경우, 메모리 사용량을 낮게 유지하기 위해 작은 날짜 청크로 렌더링하는 것을 고려하세요.  
- 파일을 제공한 후 임시 파일을 정리하여 디스크 용량이 늘어나는 것을 방지하세요.

## 결론
이제 **how to use GroupDocs** Viewer를 사용해 특정 시간 간격 내에서 프로젝트 문서를 렌더링하고 Java에서 **project** 데이터를 HTML로 **generate**하는 방법을 알게 되었습니다. 이 기능은 타임라인 시각화를 간소화하고 보고 효율성을 향상시키며 최신 웹 애플리케이션과 원활하게 통합됩니다.

### 다음 단계
- 워터마크, 비밀번호 보호, 맞춤 CSS 스타일링 등 추가 Viewer 기능을 탐색하세요.  
- 이 렌더링 파이프라인을 REST API와 결합하여 필요 시 타임라인 뷰를 제공하도록 합니다.

## 자주 묻는 질문
**Q: GroupDocs.Viewer가 지원하는 파일 형식은 무엇인가요?**  
A: GroupDocs.Viewer는 Microsoft Project (MPP), PDF, Word, Excel, PowerPoint 등 다양한 형식을 지원합니다.

**Q: GroupDocs.Viewer 무료 체험을 어떻게 시작하나요?**  
A: You can download the trial version from [here](https://releases.groupdocs.com/viewer/java/).

**Q: 리소스를 임베드하지 않고 문서를 렌더링할 수 있나요?**  
A: 예, 임베드 대신 외부 리소스를 참조하는 다른 HTML 뷰 옵션을 선택할 수 있습니다.

**Q: 문서가 너무 커서 렌더링이 어려운 경우는 어떻게 해야 하나요?**  
A: 위에서 보여준 것처럼 문서를 작은 섹션으로 나누거나 필요한 날짜 범위만 렌더링하는 것을 고려하세요.

**Q: 렌더링 오류를 어떻게 처리하나요?**  
A: 모든 구성 설정을 확인하고 유효한 라이선스가 있는지 확인한 뒤, 자세한 오류 코드는 GroupDocs 문서를 참고하세요.

## 리소스
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-01-15  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs