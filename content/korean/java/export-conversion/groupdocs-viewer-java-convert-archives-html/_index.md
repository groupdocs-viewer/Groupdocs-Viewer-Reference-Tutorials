---
date: '2026-10-10'
description: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고, 페이지당 항목 수를 설정하며, html에 리소스를
  삽입하고, 아카이브를 효율적으로 일괄 변환하는 방법을 배웁니다.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고, 리소스를 삽입하며, 페이지당 항목 수를
  설정하고, 아카이브를 일괄 처리하여 빠르고 휴대 가능한 web previews를 만드는 방법을 배웁니다.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: GroupDocs.Viewer Java를 사용하여 zip을 HTML로 변환하고 페이지네이션 적용
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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
title: GroupDocs.Viewer Java를 사용하여 zip을 html로 변환하고 페이지당 항목 수를 설정
type: docs
url: /ko/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip을 html로 변환하고 GroupDocs.Viewer Java로 페이지당 항목 수 설정

많은 웹 애플리케이션에서 ZIP 또는 RAR 압축 파일의 내용을 브라우저에서 직접 표시해야 합니다. **zip 변환 방법**은 GroupDocs.Viewer for Java를 사용하여 HTML로 변환하는 것이 일반적인 요구 사항이며, 이 라이브러리는 이미지, CSS 및 글꼴을 임베드할 수 있어 결과가 단일, 휴대 가능한 페이지가 됩니다. 이 튜토리얼은 Maven 설정부터 다중 페이지 렌더링까지 모든 과정을 안내하고, 각 옵션이 성능 및 사용성에 왜 중요한지 설명합니다.

![GroupDocs.Viewer for Java를 사용한 아카이브를 HTML로 변환](/viewer/export-conversion/convert-archives-to-html-java.png)

## 빠른 답변
- **“set items per page”가 무엇을 제어하나요?** 아카이브에서 파일 또는 폴더가 각 생성된 HTML 페이지에 몇 개 표시될지 결정합니다.  
- **HTML에 이미지와 CSS를 직접 임베드할 수 있나요?** 예 – `forEmbeddedResources` 옵션을 사용하여 리소스를 HTML에 임베드합니다.  
- **배치 변환이 가능한가요?** 물론입니다; 아카이브 컬렉션을 반복하면서 동일한 설정으로 각각을 렌더링할 수 있습니다.  
- **GroupDocs.Viewer를 사용하려면 Maven이 필요합니까?** 예, 아래와 같이 `groupdocs-viewer` Maven 의존성을 추가하십시오.  
- **지원되는 출력 형식은 무엇인가요?** 단일 페이지 HTML과 다중 페이지 HTML 모두 지원되며, 라이브러리는 50개 이상의 입력 아카이브 형식을 지원합니다.

## GroupDocs.Viewer에서 “set items per page”란 무엇인가요?
이 옵션은 다중 페이지 문서를 생성할 때 각 HTML 페이지에 표시될 아카이브 항목(파일 또는 폴더)의 수를 뷰어에 알려줍니다. 이 값을 조정하면 특히 대용량 아카이브에서 페이지당 로드되는 데이터 양을 제한하고 렌더링 시간을 줄여 페이지 크기와 탐색 속도 사이의 균형을 맞출 수 있습니다.

## 왜 리소스를 HTML에 임베드하나요?
리소스(이미지, CSS, 글꼴)를 HTML 파일에 직접 임베드하면 외부 파일 없이 열 수 있는 단일, 휴대 가능한 문서가 생성됩니다. 이는 이메일 첨부 파일, 오프라인 보기, 또는 출력물을 다른 웹 페이지에 삽입할 때 이상적이며, 외부 자산 경로를 관리할 필요도 없어집니다.

## 사전 요구 사항
- **Required libraries:** GroupDocs.Viewer 버전 25.2 이상을 포함합니다.  
- **Environment:** Java Development Kit (JDK)가 설치되고 구성되어 있어야 합니다.  
- **Knowledge:** 기본 Java 및 Maven 의존성 관리.

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
GroupDocs.Viewer는 **무료 체험 링크**, 임시 라이선스 또는 정식 구매 옵션을 제공합니다. 프로젝트 일정에 맞는 옵션을 선택하십시오.

## 기본 초기화
The `Viewer` class is the entry point for rendering documents and archives. After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 아카이브를 단일 페이지 HTML로 렌더링하는 방법
`HtmlViewOptions` 클래스는 리소스 임베드와 같은 HTML 출력 설정을 정의합니다. 아카이브를 로드하고, HTML 옵션을 리소스 임베드하도록 구성한 뒤, 모든 내용을 하나의 자체 포함 페이지로 렌더링합니다. 이렇게 하면 모든 파일, 이미지, CSS 및 글꼴을 포함한 단일 HTML 파일이 생성되어 오프라인 사용이나 이메일 첨부에 적합합니다.

**Direct answer:** ZIP 파일에 대한 `Viewer` 인스턴스를 생성하고, `HtmlViewOptions.forEmbeddedResources()`를 호출한 뒤 `viewer.view(documentPath, options)`를 실행합니다. 이렇게 하면 모든 파일, 이미지, CSS 및 글꼴을 포함한 단일 HTML 파일이 생성되어 오프라인 사용이나 이메일 첨부에 적합합니다.

### 단계 1: 출력 디렉터리 정의
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 단계 2: 단일 페이지 출력 파일 이름 설정
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 단계 3: 뷰어 초기화
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 단계 4: 렌더링 옵션 구성 (리소스 HTML 임베드)
`HtmlViewOptions` 클래스는 리소스 임베드와 같은 HTML 출력 설정을 정의합니다. `forEmbeddedResources()`를 사용하여 모든 것을 하나의 파일로 번들링합니다.

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 단계 5: 단일 페이지로 렌더링
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 아카이브를 다중 페이지 HTML로 렌더링하고 페이지당 항목 수 설정
`HtmlViewOptions` 클래스는 페이지 매김도 지원합니다. `options.setItemsPerPage(N)`을 호출하면 뷰어가 아카이브를 여러 HTML 파일로 분할하고, 각 파일에 최대 **N**개의 항목을 표시하도록 지시합니다. 이 방법은 대용량 아카이브의 탐색 속도를 개선하면서 각 페이지를 가볍게 유지합니다.

**Direct answer:** `HtmlViewOptions.forEmbeddedResources()`를 사용하고, `options.setItemsPerPage(N)`을 호출한 뒤 아카이브를 렌더링합니다. 뷰어는 페이지당 하나씩 별도의 HTML 파일을 생성하며, 각 파일에 최대 **N**개의 항목을 포함해 대용량 아카이브의 탐색 속도를 높입니다.

### 단계 1: 출력 디렉터리 재사용
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 단계 2: 다중 페이지 파일 이름 형식 정의
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 단계 3: 뷰어 재초기화
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 단계 4: 다중 페이지 옵션 구성 (리소스 HTML 임베드)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 단계 5: 페이지당 항목 수 설정 (주요 키워드 동작)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 실용적인 적용 사례
- **Document management systems:** 추가 뷰어 설치 없이 아카이브 미리보기 기능을 추가합니다.  
- **Web portals:** 사용자가 번들된 문서를 빠르게 다운로드 없이 탐색할 수 있도록 제공합니다.  
- **Collaboration tools:** 팀이 공유된 아카이브를 브라우저에서 직접 검사할 수 있게 합니다.

## 성능 고려 사항
- **Resource management:** 스트림으로 아카이브를 처리하여 메모리 사용량을 낮게 유지합니다; 뷰어는 전체 파일을 메모리에 로드하지 않고도 최대 500 MB 아카이브를 처리할 수 있습니다.  
- **Batch convert archives:** 아카이브 파일 목록을 반복하면서 동일한 렌더링 로직을 호출하여 처리량을 극대화합니다.  
- **Caching strategy:** 동일한 아카이브가 자주 접근되는 경우 렌더링된 HTML을 캐시에 저장하여 재처리 시간을 최대 70 % 줄입니다.

## 자주 묻는 질문
**Q: GroupDocs.Viewer Java란 무엇인가요?**  
A: GroupDocs.Viewer Java는 서버 측 라이브러리로, ZIP 및 RAR을 포함한 50개 이상의 문서 및 아카이브 형식을 외부 애플리케이션 없이 HTML, PDF 또는 이미지 파일로 렌더링합니다.

**Q: GroupDocs.Viewer 무료 체험을 어떻게 얻을 수 있나요?**  
A: 다운로드 및 테스트를 위해 [무료 체험 링크](https://releases.groupdocs.com/viewer/java/)를 방문하십시오.

**Q: 아카이브 외에 다른 문서 유형도 변환할 수 있나요?**  
A: 예, 뷰어는 PDF, Word, Excel, PowerPoint 및 35개 이상의 추가 형식을 지원합니다.

**Q: 렌더링이 느릴 경우 어떻게 해야 하나요?**  
A: 페이지당 항목 수를 줄이거나, 스트리밍을 활성화하거나, 아카이브를 더 작은 배치로 처리하여 속도를 개선하십시오.

**Q: 어디서 도움이나 지원을 받을 수 있나요?**  
A: [지원 포럼](https://forum.groupdocs.com/c/viewer/9)을 통해 문의하십시오.

**Q: CSS와 이미지를 HTML에 직접 임베드할 수 있나요?**  
A: 물론입니다—예제와 같이 `HtmlViewOptions.forEmbeddedResources`를 사용하십시오.

**Q: 아카이브 폴더를 배치 변환하려면 어떻게 해야 하나요?**  
A: `for` 루프를 사용해 각 파일을 반복하면서 동일한 `Viewer` 및 `HtmlViewOptions` 구성을 적용하면 됩니다.

**Q: 다른 사용자와 문제를 논의하려면 어디서 할 수 있나요?**  
A: 커뮤니티 토론을 위해 [GroupDocs 포럼](https://forum.groupdocs.com/c/viewer/9)을 방문하십시오.

## 리소스
- **Documentation:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)을 통해 기능을 자세히 살펴보세요.  
- **API reference:** [GroupDocs API](https://reference.groupdocs.com/viewer/java/)에서 전체 API를 확인하십시오.  
- **Download:** [download page](https://releases.groupdocs.com/viewer/java/)에서 최신 바이너리를 다운로드하십시오.  
- **Purchase and licensing:** [purchase page](https://purchase.groupdocs.com/buy)에서 옵션을 검토하십시오.  
- **Support and community:** [support forum](https://forum.groupdocs.com/c/viewer/9)에서 토론에 참여하십시오.  
- **GroupDocs forum:** [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9)에서 커뮤니티 도움을 받으세요.

---

**마지막 업데이트:** 2026-10-10  
**테스트 환경:** GroupDocs.Viewer 25.2  
**작성자:** GroupDocs

## 관련 튜토리얼
- [GroupDocs.Viewer를 사용한 Java에서 zip을 HTML로 변환하고 zip 폴더를 렌더링하는 방법](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java로 zip을 pdf로 변환 - 사용자 지정 파일명](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [GroupDocs.Viewer for Java를 사용하여 DOCX를 HTML로 변환하는 단계별 가이드](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}