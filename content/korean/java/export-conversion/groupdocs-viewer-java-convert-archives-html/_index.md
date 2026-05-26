---
date: '2026-02-23'
description: GroupDocs.Viewer Java를 사용하여 페이지당 항목 수를 설정하고, 리소스 HTML을 삽입하며, 아카이브를 단일
  페이지 또는 다중 페이지 HTML로 일괄 변환하는 방법을 배우세요.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: '페이지당 항목 수 설정: GroupDocs.Viewer Java를 사용하여 아카이브를 HTML로 변환'
type: docs
url: /ko/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

Translate labels but keep bold.

- **Last Updated:** -> **마지막 업데이트:** 2026-02-23
- **Tested With:** -> **테스트 환경:** GroupDocs.Viewer 25.2 (maybe keep as is)
- **Author:** -> **작성자:** GroupDocs

Make sure to keep line breaks.

Now produce final content with all translations.

Check for any missed items: Ensure we didn't translate code block placeholders. They remain.

Check for any shortcodes: none.

Check for any markdown links: we kept.

Check for any URLs: unchanged.

Now produce final answer.# 페이지당 항목 설정: GroupDocs.Viewer Java로 아카이브를 HTML로 변환

ZIP 또는 RAR와 같은 아카이브 파일을 웹 친화적인 HTML로 변환하는 것은 브라우저에서 직접 문서를 공유하거나 검토하려는 경우 자주 필요한 작업입니다. 이 가이드에서는 **페이지당 항목을 설정하는 방법**을 아카이브를 렌더링할 때 배우고, 자체 포함된 출력을 위한 리소스 HTML을 임베드하는 방법, 그리고 GroupDocs.Viewer Java를 사용하여 아카이브를 효율적으로 배치 변환하는 방법을 배웁니다.

![GroupDocs.Viewer for Java로 아카이브를 HTML로 변환](/viewer/export-conversion/convert-archives-to-html-java.png)

## 빠른 답변
- **“페이지당 항목 설정”은 무엇을 제어하나요?** 아카이브의 파일 또는 폴더가 각 생성된 HTML 페이지에 몇 개 표시될지를 결정합니다.  
- **HTML에 이미지와 CSS를 직접 임베드할 수 있나요?** 예 – `forEmbeddedResources` 옵션을 사용하여 리소스 HTML을 임베드합니다.  
- **배치 변환이 가능한가요?** 물론입니다; 아카이브 컬렉션을 반복하면서 동일한 설정으로 각각을 렌더링할 수 있습니다.  
- **GroupDocs.Viewer를 사용하려면 Maven이 필요합니까?** 예, 아래와 같이 `maven groupdocs viewer` 의존성을 추가하십시오.  
- **지원되는 출력 형식은 무엇인가요?** Single‑page HTML Java와 multi‑page HTML Java 모두 사용할 수 있습니다.

## GroupDocs.Viewer에서 “페이지당 항목 설정”이란?
**페이지당 항목 설정**은 아카이브 렌더링 옵션에 속합니다. 멀티 페이지 HTML 문서를 생성할 때 각 HTML 페이지에 표시될 아카이브 항목(파일 또는 폴더)의 수를 뷰어에 알려줍니다. 이 값을 조정하면 특히 대용량 아카이브의 경우 페이지 크기와 탐색 속도의 균형을 맞출 수 있습니다.

## 왜 리소스 HTML을 임베드해야 할까요?
리소스(이미지, CSS, 폰트)를 HTML 파일 내부에 직접 임베드하면 외부 파일 없이도 열 수 있는 단일 포터블 문서를 만들 수 있습니다. 이는 이메일 첨부 파일, 오프라인 보기, 또는 다른 웹 페이지에 출력물을 임베드할 때 이상적입니다.

## 사전 요구 사항
- **필수 라이브러리:** GroupDocs.Viewer 버전 25.2 이상을 포함합니다.  
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
GroupDocs.Viewer는 **free trial link**, 임시 라이선스 또는 정식 구매 옵션을 제공합니다. 프로젝트 일정에 맞는 옵션을 선택하십시오.

### 기본 초기화
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 아카이브를 단일 페이지 HTML로 렌더링하는 방법

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
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 단계 5: 단일 페이지로 렌더링
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 아카이브를 멀티 페이지 HTML로 렌더링하고 페이지당 항목 설정하기

### 단계 1: 출력 디렉터리 재사용
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 단계 2: 다중 페이지 파일 이름 형식 정의
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 단계 3: 뷰어 다시 초기화
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 단계 4: 멀티 페이지 옵션 구성 (리소스 HTML 임베드)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 단계 5: 페이지당 항목 설정 (동작의 주요 키워드)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 실용적인 적용 사례
- **문서 관리 시스템:** 추가 뷰어를 설치하지 않고도 아카이브 미리보기 기능을 추가합니다.  
- **웹 포털:** 사용자에게 번들된 문서를 빠르게, 다운로드 없이 탐색할 수 있는 방법을 제공합니다.  
- **협업 도구:** 팀이 공유된 아카이브를 브라우저에서 직접 검사할 수 있게 합니다.

## 성능 고려 사항
- **리소스 관리:** 메모리 사용량을 주시하고, 대량 배치에 대해 JVM 가비지 컬렉터를 조정하는 것을 고려하십시오.  
- **아카이브 배치 변환:** 아카이브 파일 목록을 순회하면서 동일한 렌더링 로직을 호출하여 처리량을 최대화합니다.  
- **캐시 전략:** 동일한 아카이브에 자주 접근한다면 렌더링된 HTML을 캐시에 저장하십시오.

## 자주 묻는 질문

**Q: GroupDocs.Viewer Java란?**  
A: HTML, PDF, 이미지 등 다양한 형식으로 문서(아카이브 포함)를 렌더링하는 다목적 라이브러리입니다.

**Q: GroupDocs.Viewer의 무료 체험을 어떻게 얻을 수 있나요?**  
A: 다운로드 및 테스트를 위해 [free trial link](https://releases.groupdocs.com/viewer/java/)를 방문하십시오.

**Q: 아카이브 외에 다른 문서 유형도 변환할 수 있나요?**  
A: 예, 뷰어는 PDF, Word, Excel 등 다양한 형식을 지원합니다.

**Q: 렌더링이 느릴 경우 어떻게 해야 하나요?**  
A: 페이지당 항목 수를 줄이거나, 스트리밍을 활성화하거나, 아카이브를 더 작은 배치로 처리하십시오.

**Q: 어디서 도움이나 지원을 받을 수 있나요?**  
A: 다음 [support forum](https://forum.groupdocs.com/c/viewer/9)에서 문의하십시오.

**Q: CSS와 이미지를 HTML에 직접 임베드할 수 있나요?**  
A: 물론입니다—예제와 같이 `HtmlViewOptions.forEmbeddedResources`를 사용하십시오.

**Q: 아카이브 폴더를 배치 변환하려면 어떻게 해야 하나요?**  
A: `for` 루프를 사용해 각 파일을 순회하면서 동일한 `Viewer`와 `HtmlViewOptions` 구성을 적용하면 됩니다.

## 리소스
- **문서:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)을 통해 기능을 자세히 살펴보세요.  
- **API 레퍼런스:** [GroupDocs API](https://reference.groupdocs.com/viewer/java/)에서 전체 API를 확인하십시오.  
- **다운로드:** [download page](https://releases.groupdocs.com/viewer/java/)에서 최신 바이너리를 받으세요.  
- **구매 및 라이선스:** [purchase page](https://purchase.groupdocs.com/buy)에서 옵션을 검토하십시오.  
- **지원 및 커뮤니티:** [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9)에서 토론에 참여하십시오.

---

**마지막 업데이트:** 2026-02-23  
**테스트 환경:** GroupDocs.Viewer 25.2  
**작성자:** GroupDocs