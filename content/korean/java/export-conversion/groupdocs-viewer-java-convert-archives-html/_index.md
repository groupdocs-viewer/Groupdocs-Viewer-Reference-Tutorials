---
date: '2026-08-03'
description: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고, items per page을 설정하고, embed
  resources html을 삽입하며, batch convert archives를 효율적으로 수행하는 방법을 배웁니다.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고, items per page을 설정하고,
  embed resources html을 삽입하며, batch convert archives를 효율적으로 수행하는 방법을 배웁니다. step‑by‑step
  code와 performance tips를 따라 보세요.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고 페이지당 items per page 설정
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고 페이지당 items per page 설정
type: docs
url: /ko/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고 페이지당 항목 수 설정

많은 웹 애플리케이션에서 ZIP 또는 RAR 아카이브의 내용을 브라우저에 직접 표시해야 합니다. GroupDocs.Viewer for Java를 사용하면 **convert zip to html**을 한 번에 수행하고, 각 페이지에 표시되는 아카이브 항목 수를 제어하며, 모든 지원 이미지와 CSS를 포함하고, 수십 개의 아카이브를 배치 처리까지 할 수 있습니다. 이 튜토리얼은 Maven 설정부터 다중 페이지 렌더링까지 전체 워크플로를 안내하고, 각 설정이 성능 및 사용성에 왜 중요한지 설명합니다.

![GroupDocs.Viewer for Java로 아카이브를 HTML로 변환](/viewer/export-conversion/convert-archives-to-html-java.png)

## 빠른 답변
- **“set items per page”가 무엇을 제어하나요?** 아카이브의 파일 또는 폴더가 각 생성된 HTML 페이지에 몇 개 표시될지를 결정합니다.  
- **이미지와 CSS를 HTML에 직접 포함시킬 수 있나요?** 예 – `forEmbeddedResources` 옵션을 사용하여 리소스를 HTML에 포함시킵니다.  
- **배치 변환이 가능한가요?** 물론입니다; 아카이브 컬렉션을 반복하면서 동일한 설정으로 각각을 렌더링할 수 있습니다.  
- **GroupDocs.Viewer를 사용하려면 Maven이 필요합니까?** 예, 아래와 같이 `groupdocs-viewer` Maven 의존성을 추가하세요.  
- **지원되는 출력 형식은 무엇인가요?** 단일 페이지 HTML과 다중 페이지 HTML 모두 제공되며, 라이브러리는 50가지 이상의 입력 아카이브 형식을 지원합니다.

## GroupDocs.Viewer에서 “set items per page”란 무엇인가요?
**set items per page** 설정은 아카이브 렌더링 옵션에 속합니다. 멀티 페이지 HTML 문서를 생성할 때, 각 HTML 페이지에 표시될 아카이브 항목(파일 또는 폴더)의 수를 뷰어에 알려줍니다. 이 값을 조정하면 특히 큰 아카이브의 경우 페이지 크기와 탐색 속도 사이의 균형을 맞출 수 있습니다.

## 왜 리소스를 HTML에 포함시키나요?
리소스(이미지, CSS, 폰트)를 HTML 파일에 직접 포함하면 외부 파일 없이 열 수 있는 단일 휴대용 문서를 만들 수 있습니다. 이는 이메일 첨부 파일, 오프라인 보기, 또는 출력물을 다른 웹 페이지에 삽입할 때 이상적입니다. 외부 자산 경로를 관리할 필요가 없으므로 배포가 간소화됩니다.

## 전제 조건

- **필수 라이브러리:** GroupDocs.Viewer 버전 25.2 이상을 포함합니다.  
- **환경:** Java Development Kit (JDK)이 설치되고 구성되어 있어야 합니다.  
- **지식:** 기본 Java 및 Maven 의존성 관리.

## Maven GroupDocs Viewer 설정

Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer는 **무료 체험 링크**, 임시 라이선스 또는 정식 구매 옵션을 제공합니다. 프로젝트 일정에 맞는 옵션을 선택하세요.

### 기본 초기화
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 아카이브를 단일 페이지 HTML로 렌더링하는 방법
Viewer는 문서 또는 아카이브를 로드하여 렌더링하는 핵심 클래스입니다.

전체 아카이브를 포함하는 단일 HTML 파일을 생성하려면 ZIP 파일에 대한 `Viewer` 인스턴스를 만들고 `HtmlViewOptions.forEmbeddedResources()`를 사용하여 모든 이미지, CSS 및 폰트를 포함시킵니다. 이 옵션으로 아카이브를 렌더링하면 이메일이나 오프라인 사용에 적합한 단일 독립 페이지가 생성됩니다.

### 1단계: 출력 디렉터리 정의
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 2단계: 단일 페이지 출력 파일 이름 설정
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 3단계: 뷰어 초기화
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 4단계: 렌더링 옵션 구성 (리소스를 HTML에 포함)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 5단계: 단일 페이지로 렌더링
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 아카이브를 다중 페이지 HTML로 렌더링하고 페이지당 항목 수 설정하는 방법
`HtmlViewOptions`는 페이지 매김 및 리소스 포함을 포함하여 뷰어가 HTML 출력을 렌더링하는 방식을 구성합니다.

아카이브를 여러 페이지로 나누려면 `HtmlViewOptions.forEmbeddedResources()`를 생성하고 `options.setItemsPerPage(20)`으로 원하는 페이지 크기를 설정합니다. 뷰어는 지정된 항목 수까지 표시하는 별도의 HTML 파일을 생성하며, 이는 큰 아카이브의 탐색을 개선하고 로딩 속도를 높입니다.

### 1단계: 출력 디렉터리 재사용
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 2단계: 다중 페이지 파일 이름 형식 정의
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 3단계: 뷰어를 다시 초기화
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 4단계: 다중 페이지 옵션 구성 (리소스를 HTML에 포함)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 5단계: 페이지당 항목 수 설정 (동작의 주요 키워드)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 실제 적용 사례

- **문서 관리 시스템:** 추가 뷰어를 설치하지 않고도 아카이브 미리보기 기능을 추가합니다.  
- **웹 포털:** 사용자에게 번들된 문서를 빠르게, 다운로드 없이 탐색할 수 있는 방법을 제공합니다.  
- **협업 도구:** 팀이 공유 아카이브를 브라우저에서 직접 확인할 수 있게 합니다.

## 성능 고려 사항

- **리소스 관리:** 스트림으로 아카이브를 처리하여 메모리 사용량을 낮게 유지합니다; 뷰어는 전체 파일을 메모리에 로드하지 않고도 최대 500 MB 크기의 아카이브를 처리할 수 있습니다.  
- **아카이브 배치 변환:** 아카이브 파일 목록을 반복하면서 동일한 렌더링 로직을 호출하여 처리량을 최대화합니다.  
- **캐싱 전략:** 동일한 아카이브에 자주 접근하는 경우 렌더링된 HTML을 캐시에 저장하여 반복 처리 시간을 최대 70 %까지 줄입니다.

## 자주 묻는 질문

**Q: GroupDocs.Viewer Java란 무엇인가요?**  
A: GroupDocs.Viewer Java는 ZIP 및 RAR을 포함한 50가지 이상의 문서 및 아카이브 형식을 외부 애플리케이션 없이 HTML, PDF 또는 이미지 파일로 렌더링하는 서버 측 라이브러리입니다.

**Q: GroupDocs.Viewer의 무료 체험을 어떻게 얻을 수 있나요?**  
A: 무료 체험을 위해 [free trial link](https://releases.groupdocs.com/viewer/java/)를 방문하여 다운로드하고 테스트하세요.

**Q: 아카이브 외에 다른 문서 유형도 변환할 수 있나요?**  
A: 예, 뷰어는 PDF, Word, Excel, PowerPoint 및 35가지 이상의 추가 형식을 지원합니다.

**Q: 렌더링이 느릴 경우 어떻게 해야 하나요?**  
A: 페이지당 항목 수를 줄이거나 스트리밍을 활성화하고, 아카이브를 더 작은 배치로 처리하여 속도를 개선하세요.

**Q: 어디서 도움이나 지원을 받을 수 있나요?**  
A: [support forum](https://forum.groupdocs.com/c/viewer/9)를 통해 문의하세요.

**Q: CSS와 이미지를 HTML에 직접 포함시킬 수 있나요?**  
A: 물론입니다—예제와 같이 `HtmlViewOptions.forEmbeddedResources`를 사용하세요.

**Q: 아카이브 폴더를 배치 변환하려면 어떻게 해야 하나요?**  
A: `for` 루프를 사용해 각 파일을 반복하면서 동일한 `Viewer` 및 `HtmlViewOptions` 구성을 적용하면 됩니다.

## 리소스

- **문서:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)을 통해 기능을 자세히 살펴보세요.  
- **API 레퍼런스:** [GroupDocs API](https://reference.groupdocs.com/viewer/java/)에서 전체 API를 탐색하세요.  
- **다운로드:** [download page](https://releases.groupdocs.com/viewer/java/)에서 최신 바이너리를 받으세요.  
- **구매 및 라이선스:** [purchase page](https://purchase.groupdocs.com/buy)에서 옵션을 확인하세요.  
- **지원 및 커뮤니티:** [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9)에서 토론에 참여하세요.

---

**최종 업데이트:** 2026-08-03  
**테스트 환경:** GroupDocs.Viewer 25.2  
**작성자:** GroupDocs

## 관련 튜토리얼

- [GroupDocs.Viewer를 사용하여 Java에서 zip을 HTML로 변환하고 zip 폴더를 렌더링하는 방법](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java로 zip을 pdf로 변환 - 사용자 지정 파일 이름](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [GroupDocs.Viewer for Java를 사용하여 DOCX를 HTML로 변환하는 방법: 단계별 가이드](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)