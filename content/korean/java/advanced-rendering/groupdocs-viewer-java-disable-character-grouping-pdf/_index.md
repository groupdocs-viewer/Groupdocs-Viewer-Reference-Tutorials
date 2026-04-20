---
date: '2026-03-22'
description: GroupDocs Viewer for Java를 사용하여 PDF에서 HTML을 생성하고 문자 그룹화를 비활성화하여 정확한 텍스트
  표현을 구현하는 방법을 배워보세요.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: PDF에서 HTML 생성 및 그룹화 비활성화 – GroupDocs Java
type: docs
url: /ko/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# PDF에서 HTML 생성 및 GroupDocs Viewer for Java에서 그룹화 비활성화

많은 프로젝트에서 **PDF에서 HTML을 생성**하면서 각 글리프가 정확히 제자리에 있도록 유지해야 합니다. 이는 복잡한 스크립트, 고대 언어, 또는 하나의 문자만 잘못 배치되어도 의미가 바뀔 수 있는 법률 문서에 특히 해당됩니다. 이 튜토리얼에서는 GroupDocs Viewer for Java를 사용하여 PDF를 HTML로 렌더링하는 전체 과정을 안내하고 **그룹화를 비활성화하는 방법**을 보여드려 각 문자가 독립적인 요소로 처리되도록 합니다.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 빠른 답변
- **“그룹화 비활성화”가 무엇을 하나요?** 렌더러가 각 문자를 독립적인 요소로 처리하도록 강제하여 정확한 레이아웃을 유지합니다.  
- **어떤 API 옵션이 이를 제어하나요?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **라이선스가 필요합니까?** 테스트용으로는 체험판으로도 가능하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **PDF와 동시에 HTML을 생성할 수 있나요?** 예—`HtmlViewOptions`를 사용하여 그룹화를 비활성화하면서 HTML 출력을 생성합니다.  
- **이 기능이 PDF에만 제한되나요?** 주로 PDF에 적용되지만, 뷰어는 다른 많은 형식도 지원합니다.

## 소개

PDF 문서를 다룰 때 렌더링 정확도는 매우 중요합니다—특히 복잡한 텍스트 구조(예: 상형문자나 정확한 문자 표현이 필요한 언어)를 다룰 때 더욱 그렇습니다. "문자 그룹화" 기능은 문자를 잘못 그룹화하여 문서 내용이 오해될 수 있게 만들곤 합니다. 이는 문서 텍스트 레이아웃을 정확히 복제해야 하는 사용자에게 특히 문제가 됩니다.

### 사전 요구 사항

- **라이브러리 및 종속성**: GroupDocs.Viewer for Java 버전 25.2 이상이 필요합니다.  
- **환경 설정**: Java Development Kit (JDK)가 설치되어 있고, IDE가 Maven 프로젝트와 함께 작동하도록 설정되어 있는지 확인하십시오.  
- **지식 사전 요구 사항**: 특히 파일 경로 처리와 외부 라이브러리 사용에 대한 기본적인 Java 프로그래밍 이해가 필요합니다.

## GroupDocs Viewer를 사용하여 PDF에서 HTML 생성 방법

PDF에서 HTML을 생성하는 과정은 두 단계로 이루어집니다: 뷰어를 구성하고, 문서를 렌더링합니다. 핵심은 렌더링 전에 문자 그룹화를 끄는 것으로, 이렇게 하면 HTML 출력이 원본 PDF 레이아웃을 문자 단위로 정확히 반영합니다.

### GroupDocs.Viewer for Java 설정

#### Maven을 통한 설치

먼저, 필요한 라이브러리를 프로젝트에 통합합니다. `pom.xml`에 다음 구성을 추가하십시오:

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

GroupDocs.Viewer를 완전히 활용하려면 라이선스를 획득하는 것을 고려하십시오:
- **무료 체험**: 기능을 테스트하려면 무료 체험으로 시작하십시오.  
- **임시 라이선스**: 더 많은 시간이 필요하면 임시 라이선스를 신청하십시오.  
- **구매**: 장기 프로젝트의 경우 라이선스를 구매하는 것이 권장됩니다.

#### 기본 초기화 및 설정

다음은 실행 가능한 스니펫으로, 출력 폴더 설정부터 문자 그룹화를 비활성화하면서 PDF를 HTML로 렌더링하는 전체 워크플로우를 보여줍니다:

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

아래에서는 예제의 각 줄을 자세히 설명하여 **왜** 그렇게 하는지와 **어떻게** 원하지 않는 문자 병합 없이 PDF에서 HTML을 생성하는 데 기여하는지 이해할 수 있도록 합니다.

##### 단계 1: 출력 디렉터리 정의  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**왜?** 렌더링된 HTML 파일이 전용 폴더에 저장되어 나중에 쉽게 찾고 관리할 수 있게 합니다.

##### 단계 2: 파일 경로 형식 구성  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**왜?** 플레이스홀더(`{0}`)를 사용하면 뷰어가 각 PDF 페이지마다 별도의 HTML 파일을 생성하여 출력이 체계적으로 정리됩니다.

##### 단계 3: HTML 보기 옵션 초기화  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**왜?** 임베디드 리소스가 이미지, 폰트 및 CSS를 각 HTML 페이지와 직접 번들링하므로 웹 기반 뷰어나 e‑learning 플랫폼에 이상적입니다.

##### 단계 4: 문자 그룹화 비활성화  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**왜?** 이 라인은 렌더링 엔진에 인접한 문자를 **병합하지 않도록** 지시하는 핵심 라인으로, 생성된 HTML이 원본 PDF의 정확한 글리프 배치를 반영하도록 보장합니다.

##### 단계 5: 문서 렌더링  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**왜?** `Viewer`를 try‑with‑resources 블록으로 감싸면 모든 네이티브 리소스가 자동으로 해제되어 장시간 실행되는 애플리케이션에서 메모리 누수를 방지합니다.

### 그룹화 없이 Java에서 PDF를 HTML로 생성하기

`HtmlViewOptions` 클래스를 사용하면 각 문자를 별도로 유지하면서 **PDF에서 HTML을 생성**할 수 있습니다. 이는 렌더링된 페이지를 웹 포털이나 정확한 글리프 배치가 중요한 e‑learning 플랫폼에 삽입해야 할 때 특히 유용합니다.

### 일반적인 문제와 해결책

- **FileNotFoundException** – `new Viewer(...)`에 전달하는 경로를 다시 확인하십시오. 명확성을 위해 절대 경로나 `Path.of(...)`를 사용하세요.  
- **쓰기 권한** – 출력 디렉터리가 Java 프로세스에 의해 쓰기 가능한지 확인하십시오; Linux에서는 폴더 권한(`chmod 775`)을 조정해야 할 수도 있습니다.  
- **버전 불일치** – `setDisableCharsGrouping` 옵션은 버전 25.2부터 사용할 수 있습니다. `pom.xml`에 올바른 버전이 명시되어 있는지 확인하십시오.

### 실용적인 적용 사례

1. **언어 보존** – 문자 간격이 의미를 전달하는 중국어, 일본어, 아랍어 또는 고대 스크립트 문서를 렌더링하는 데 이상적입니다.  
2. **법률 및 재무 문서** – 규제가 엄격한 문서에 대해 정확한 텍스트 복제를 보장합니다.  
3. **교육 자료** – 복잡한 도표, 주석 또는 다국어 콘텐츠가 포함된 교과서에 적합합니다.

### 성능 고려 사항

- **리소스 사용 최적화** – 대용량 PDF는 상당한 메모리를 소모할 수 있습니다. 페이지를 배치로 처리하고 `Viewer` 인스턴스를 즉시 해제하는 것을 고려하십시오.  
- **Java 메모리 관리** – 수백 페이지에 달하는 PDF를 처리할 경우 JVM 힙(`-Xmx2g` 이상)을 조정하십시오.  
- **병렬 렌더링** – 대량 변환의 경우 각기 별도의 `Viewer` 인스턴스를 가진 스레드를 생성하여 멀티코어 CPU를 활용하십시오.

## 자주 묻는 질문

**Q:** *왜 문자 그룹화를 비활성화해야 할까요?*  
**A:** 그룹화를 비활성화하면 서로 다른 글리프에 속하는 문자를 병합하지 않게 되어, 문자 간격과 순서가 의미를 전달하는 스크립트에 필수적입니다.

**Q:** *`setDisableCharsGrouping` 설정이 HTML 출력에만 적용되나요?*  
**A:** 아니요, 이 설정은 기본 PDF 렌더링 엔진에 영향을 미치므로 모든 출력 형식(HTML, PNG, JPEG 등)에 적용됩니다.

**Q:** *이 설정을 사용자 정의 폰트와 결합할 수 있나요?*  
**A:** 예—`Viewer`를 초기화하기 전에 사용자 정의 폰트를 로드하면 그룹화 규칙이 그대로 적용됩니다.

**Q:** *그룹화를 비활성화하면 성능에 영향을 미치나요?*  
**A:** 약간 영향을 미칩니다. 엔진이 각 문자를 개별적으로 처리하기 때문이지만 대부분의 문서에서는 영향이 미미합니다.

**Q:** *페이지별로 그룹화를 토글할 수 있는 방법이 있나요?*  
**A:** 현재 이 옵션은 `PdfOptions` 인스턴스당 전역적으로 적용됩니다. 혼합된 동작이 필요하다면 페이지마다 별도의 `Viewer` 인스턴스를 사용해야 합니다.

## 리소스

- [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs Viewer 다운로드](https://releases.groupdocs.com/viewer/java/)
- [라이선스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험 버전](https://releases.groupdocs.com/viewer/java/)
- [임시 라이선스 신청](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 지원 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-03-22  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs