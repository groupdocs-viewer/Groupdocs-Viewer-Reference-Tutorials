---
date: '2026-01-10'
description: GroupDocs.Viewer를 사용하여 Java에서 사용자 정의 날짜/시간 형식으로 EML을 HTML로 변환하고 시간대 오프셋을
  설정하는 방법을 배워보세요. 이메일 보관 및 지원 시스템에 이상적입니다.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Java에서 GroupDocs.Viewer를 사용해 사용자 정의 날짜/시간으로 EML을 HTML로 변환
type: docs
url: /ko/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Java에서 GroupDocs.Viewer를 사용하여 사용자 정의 DateTime으로 EML을 HTML로 변환

## 소개

오늘날 빠르게 변화하는 디지털 환경에서 **EML을 HTML로 변환**을 신속하게 수행하고 올바른 날짜‑시간 표시를 제공하는 것은 아카이빙, 지원 포털 및 법적 준수를 위해 필수적입니다. 이 튜토리얼에서는 GroupDocs.Viewer for Java를 사용하여 이메일 메시지를 HTML로 렌더링하면서 **사용자 정의 datetime 형식**과 **시간대 오프셋**을 적용하는 방법을 단계별로 안내합니다. 마지막까지 읽으면 타임스탬프를 정확하고 읽기 쉽게 유지하는 재사용 가능한 솔루션을 얻을 수 있습니다.

![GroupDocs.Viewer for Java를 사용한 사용자 정의 DateTime으로 이메일 렌더링](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**배우게 될 내용**
- Java 프로젝트에서 GroupDocs.Viewer를 설정하는 방법  
- 임베디드 리소스를 포함하여 이메일을 HTML로 렌더링하는 방법  
- 이메일 메시지의 **날짜‑시간 형식**을 사용자 정의하는 방법 (custom datetime format java)  
- 정확한 타임스탬프를 위해 **시간대 오프셋**을 설정하는 방법 (set timezone offset java)  

## 빠른 답변
- **GroupDocs.Viewer가 EML을 HTML로 변환할 수 있나요?** 예, EML 파일을 직접 HTML로 렌더링합니다.  
- **라이선스가 필요합니까?** 테스트용으로는 무료 체험판으로 충분하지만, 프로덕션에서는 유료 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상.  
- **표시되는 날짜 형식을 어떻게 변경하나요?** `options.getEmailOptions().setDateTimeFormat(...)`를 사용합니다.  
- **시간대를 조정할 수 있나요?** 예, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`를 사용합니다.  

## “EML을 HTML로 변환”이란?
EML 파일을 HTML로 변환하면 원시 이메일(헤더, 본문 및 첨부 파일 포함)을 웹 친화적인 형식으로 바꾸어 브라우저가 추가 플러그인 없이도 표시할 수 있게 됩니다. 이를 통해 웹 애플리케이션, 아카이브 또는 지원 대시보드에 이메일을 손쉽게 삽입할 수 있습니다.

## 이 작업에 GroupDocs.Viewer를 사용하는 이유
- **Zero‑dependency 렌더링** – Outlook이나 외부 메일 파서가 필요 없습니다.  
- **임베디드 리소스**(이미지, 첨부 파일)에 대한 내장 지원.  
- **세밀한 제어**를 통해 날짜‑시간 형식 및 시간대 처리를 관리할 수 있습니다.  

## 사전 요구 사항
- **GroupDocs.Viewer for Java** 버전 25.2 이상.  
- **Java Development Kit (JDK)** 8 이상 및 IDE(IntelliJ IDEA, Eclipse 등).  
- 기본 Java 지식 및 Maven 사용 경험.  

## GroupDocs.Viewer for Java 설정

### Maven 구성
Add the GroupDocs repository and dependency to your `pom.xml`:

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
무료 체험판으로 시작하거나 확장 테스트를 위해 임시 라이선스를 요청하세요. 프로덕션 사용을 위해서는 정식 라이선스를 구매해야 합니다.

### 기본 초기화
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Java에서 사용자 정의 DateTime으로 EML을 HTML로 변환

다음 단계별 가이드는 **EML을 HTML로 변환**하면서 사용자 정의 datetime 형식과 시간대 오프셋을 적용하는 방법을 보여줍니다.

### 단계 1: 출력 디렉터리 및 파일 경로 설정
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*설명:* `Path.of()`는 HTML이 저장될 폴더에 대한 참조를 생성합니다. `resolve()`는 파일 이름을 추가합니다.

### 단계 2: 이메일 파일로 Viewer 초기화
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*설명:* `Viewer` 인스턴스는 변환하려는 EML 파일을 가리킵니다.

### 단계 3: HtmlViewOptions 구성
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*설명:* `forEmbeddedResources()`는 이미지 및 기타 리소스를 HTML 출력에 직접 포함합니다.

### 단계 4: 사용자 정의 DateTime 형식 설정 *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*설명:* 이 패턴은 월, 일, 연도, 시, 분, AM/PM 표시자 및 시간대 오프셋(`zzz`)을 표시합니다.

### 단계 5: TimeZone 오프셋 설정 *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*설명:* 렌더링된 타임스탬프를 원하는 시간대로 조정합니다. `"GMT+1"`을 유효한 다른 구역 식별자로 교체하세요.

### 단계 6: 문서 렌더링
```java
viewer.view(options);
```
*설명:* 변환을 실행하여 사용자 정의 날짜‑시간 설정이 적용된 HTML 파일을 생성합니다.

## 문제 해결 팁
- **FileNotFoundException:** `Viewer`와 `Path.of()`에 사용된 경로를 다시 확인하세요.  
- **잘못된 타임스탬프:** `TimeZone` ID가 목표 지역과 일치하는지 확인하세요.  
- **이미지 누락:** `HtmlViewOptions.forEmbeddedResources()`를 사용했는지 확인하세요; 그렇지 않으면 외부 리소스가 포함되지 않을 수 있습니다.  

## 실용적인 적용 사례
1. **이메일 아카이빙:** 컴플라이언스를 위해 검색 가능한 이메일 HTML 스냅샷을 저장합니다.  
2. **고객 지원 포털:** 정확한 현지 시간과 함께 들어오는 티켓을 표시합니다.  
3. **법률 문서:** 표준화된 타임스탬프가 포함된 법원 제출용 이메일 기록을 생성합니다.  

## 성능 고려 사항
- 대량 변환을 위해 전용 서버에 배포합니다.  
- Java 힙 사용량을 모니터링하고 `OutOfMemoryError`가 발생하면 `-Xmx`를 늘립니다.  
- 같은 이메일이 반복 요청될 경우 렌더링된 HTML을 캐시합니다.  

## 결론
이제 GroupDocs.Viewer for Java를 사용하여 사용자 정의 datetime 형식과 시간대 오프셋을 적용한 **EML을 HTML로 변환**하는 완전하고 프로덕션 준비된 방법을 갖추었습니다. 이는 가독성을 높이고 타임스탬프 정확성을 보장하며 아카이빙이나 지원 워크플로에 원활하게 통합됩니다.

**다음 단계:** CSS 스타일링, 페이지 매김 또는 PDF 변환과 같은 추가 Viewer 옵션을 탐색하여 필요에 맞게 출력을 더욱 맞춤화하세요.

## 자주 묻는 질문

**Q: 첨부 파일이 있는 EML 파일을 어떻게 처리하나요?**  
A: `HtmlViewOptions.forEmbeddedResources()`를 사용하면 첨부 파일이 자동으로 임베드됩니다. 필요하면 Viewer API를 통해 추출할 수도 있습니다.

**Q: HTML 템플릿을 변경하거나 사용자 정의 CSS를 추가할 수 있나요?**  
A: 예, 렌더링 후 생성된 HTML 파일을 편집하거나 저장하기 전에 프로그래밍 방식으로 CSS를 삽입할 수 있습니다.

**Q: 여러 EML 파일을 배치로 렌더링할 수 있나요?**  
A: 렌더링 로직을 루프에 감싸고 각 파일에 동일한 `HtmlViewOptions` 인스턴스를 재사용하면 됩니다.

**Q: MSG와 같은 다른 이메일 형식을 지원해야 한다면 어떻게 하나요?**  
A: GroupDocs.Viewer는 MSG, PST 및 기타 이메일 컨테이너도 지원하므로 `Viewer` 생성자에서 파일 확장자를 변경하면 됩니다.

**Q: 각 서버마다 별도의 라이선스가 필요합니까?**  
A: 라이선스는 배포당 적용되며, 다중 서버 시나리오에 대해서는 GroupDocs 라이선스 가이드를 참고하세요.

## 리소스

- [문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [다운로드](https://releases.groupdocs.com/viewer/java/)
- [구매](https://purchase.groupdocs.com/buy)
- [무료 체험](https://releases.groupdocs.com/viewer/java/)
- [임시 라이선스](https://purchase.groupdocs.com/temporary-license/)
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-01-10  
**테스트 환경:** GroupDocs.Viewer 25.2 (Java)  
**작성자:** GroupDocs