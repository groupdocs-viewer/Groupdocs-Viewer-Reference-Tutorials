---
date: '2025-12-21'
description: GroupDocs.Viewer for Java를 사용하여 PDF에서 그룹화를 비활성화하는 방법을 배우고, PDF 렌더링 옵션의
  java html을 활용해 정확한 텍스트 표현을 보장하세요.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: GroupDocs.Viewer for Java를 사용하여 PDF에서 그룹화 비활성화하는 방법
type: docs
url: /ko/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# GroupDocs.Viewer for Java를 사용하여 PDF에서 그룹화 비활성화하는 방법

PDF를 렌더링할 때 **그룹화를 비활성화하는 방법**이 필요하고, 특히 복잡한 스크립트나 고대 언어의 경우 정확한 문자 배치가 필수적입니다. 기본 *Character Grouping* 기능은 문자를 잘못 병합하여 내용이 오해될 수 있습니다. 이 가이드에서는 GroupDocs.Viewer for Java를 사용하여 그룹화를 비활성화하는 방법을 단계별로 보여드리며, 모든 글리프가 정확한 위치에 유지되도록 합니다.

![GroupDocs.Viewer for Java를 사용한 정밀 렌더링 기술](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 빠른 답변
- **그룹화를 비활성화하면 무엇을 하나요?** 렌더러가 각 문자를 독립적인 요소로 처리하도록 강제하여 정확한 레이아웃을 유지합니다.  
- **어떤 API 옵션이 이를 제어합니까?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **라이선스가 필요합니까?** 테스트용으로는 무료 체험판으로 충분하지만, 프로덕션 환경에서는 정식 라이선스가 필요합니다.  
- **PDF와 동시에 Java HTML을 생성할 수 있나요?** 예—`HtmlViewOptions`를 사용하여 그룹화를 비활성화하면서 HTML 출력을 생성할 수 있습니다.  
- **이 기능이 PDF에만 제한됩니까?** 주로 PDF에 적용되지만, 뷰어는 다른 많은 형식도 지원합니다.

## 소개

PDF 문서를 다룰 때 렌더링 정확도는 매우 중요합니다—특히 히에라틱 문자나 정확한 문자 표현이 필요한 언어와 같은 복잡한 텍스트 구조를 다룰 때 더욱 그렇습니다. “Character Grouping” 기능은 문자를 잘못 그룹화하여 문서 내용이 오해될 수 있습니다. 이는 문서 텍스트 레이아웃을 정확히 복제해야 하는 사용자에게 특히 문제가 됩니다.

### 전제 조건

- **Libraries & Dependencies**: GroupDocs.Viewer for Java 버전 25.2 이상이 필요합니다.  
- **Environment Setup**: Java Development Kit (JDK)가 설치되어 있고, IDE가 Maven 프로젝트와 함께 작동하도록 설정되어 있는지 확인하십시오.  
- **Knowledge Prerequisites**: 파일 경로 처리 및 외부 라이브러리 사용을 포함한 Java 프로그래밍에 대한 기본 이해가 필요합니다.

## PDF 렌더링에서 그룹화 비활성화 방법

### GroupDocs.Viewer for Java 설정

#### Maven을 통한 설치

먼저 필요한 라이브러리를 프로젝트에 통합합니다. `pom.xml`에 다음 구성을 추가하십시오:

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

GroupDocs.Viewer를 완전히 활용하려면 라이선스를 고려하십시오:
- **Free Trial**: 기능을 테스트하려면 무료 체험판으로 시작하십시오.  
- **Temporary License**: 더 많은 시간이 필요하면 임시 라이선스를 신청하십시오.  
- **Purchase**: 장기 프로젝트의 경우 라이선스를 구매하는 것이 바람직합니다.

#### 기본 초기화 및 설정

프로젝트 환경을 설정합니다:

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

##### 단계 1: 출력 디렉터리 정의

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**왜?** 출력이 정리되고 쉽게 접근할 수 있도록 보장합니다.

##### 단계 2: 파일 경로 형식 구성

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**왜?** PDF 문서의 페이지를 체계적으로 정리하는 데 도움이 됩니다.

##### 단계 3: HTML View Options 초기화

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**왜?** 각 페이지의 HTML 파일에 필요한 모든 자산이 포함되도록 임베디드 리소스를 사용합니다.

##### 단계 4: 문자 그룹화 비활성화

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**왜?** 문자가 개별적으로 렌더링되어 의도된 레이아웃과 의미가 보존됩니다.

##### 단계 5: 문서 렌더링

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**왜?** 모든 리소스를 적절히 닫아 메모리 누수를 방지합니다.

### 그룹화 없이 PDF에서 Java HTML 생성

`HtmlViewOptions` 클래스를 사용하면 **java html from pdf**를 생성하면서 각 문자를 별도로 유지할 수 있습니다. 이는 렌더링된 페이지를 웹 포털이나 e‑learning 플랫폼에 삽입해야 할 때, 정확한 글리프 배치가 중요한 경우에 특히 유용합니다.

### 문제 해결 팁

- `FileNotFoundException`을 방지하려면 문서 경로가 올바른지 확인하십시오.  
- 출력 디렉터리에 쓰기 권한이 있는지 확인하십시오.  
- 사용 중인 GroupDocs.Viewer for Java 버전이 호환되는지 다시 확인하십시오.

## 실용적인 적용 사례

1. **Language Preservation**: 문자 정밀도가 중요한 중국어, 일본어 또는 고대 스크립트와 같은 언어 문서 렌더링에 이상적입니다.  
2. **Legal and Financial Documents**: 규정 준수를 위해 정확한 텍스트 표현이 필요한 법률 및 재무 문서의 정확성을 보장합니다.  
3. **Educational Resources**: 복잡한 다이어그램이나 주석이 포함된 교과서 및 학술 논문에 적합합니다.

## 성능 고려 사항

- **Optimize Resource Usage**: 대용량 PDF 파일을 처리할 수 있도록 서버에 충분한 리소스가 있는지 확인하십시오.  
- **Java Memory Management**: 효율적인 데이터 구조와 가비지 컬렉션 방식을 사용하여 메모리를 효과적으로 관리하십시오.  
- **Batch Processing**: 여러 문서를 렌더링할 때 배치 처리하여 처리량을 향상시킵니다.

## 결론

이제 GroupDocs.Viewer for Java를 사용한 PDF 렌더링 중 **그룹화를 비활성화하는 방법**을 마스터했습니다. 이 기능은 정밀한 텍스트 표현이 요구되는 애플리케이션에 필수적입니다. 더 나아가 다른 문서 관리 시스템과 이 기능을 통합하거나 추가 렌더링 옵션을 실험해 보십시오.

다음 단계로는 GroupDocs.Viewer의 고급 기능을 탐색하고 대규모 배포를 위한 성능을 미세 조정하는 것을 권장합니다.

## FAQ 섹션

1. **그룹화를 비활성화하면 무엇을 달성할 수 있나요?**  
   - 각 문자를 개별적으로 렌더링하여 원본 레이아웃을 보존합니다.  
2. **다른 문서 유형에도 이 기능을 사용할 수 있나요?**  
   - 예, 여기서는 PDF에 중점을 두었지만 GroupDocs.Viewer는 다양한 형식을 지원합니다.  
3. **대용량 문서를 효율적으로 처리하려면 어떻게 해야 하나요?**  
   - 배치 처리를 사용하고 서버 리소스를 최적화하십시오.  
4. **출력 디렉터리에 쓰기 권한이 없으면 어떻게 해야 하나요?**  
   - 권한을 확인하거나 접근 권한이 있는 다른 디렉터리를 선택하십시오.  
5. **GroupDocs.Viewer의 라이선스 제한은 어떻게 되나요?**  
   - 무료 체험판을 이용할 수 있지만 장기 사용에는 정식 라이선스가 필요합니다.

## 자주 묻는 질문

**Q:** *왜 문자 그룹화를 비활성화해야 할까요?*  
**A:** 그룹화를 비활성화하면 렌더러가 서로 다른 글리프에 속하는 문자를 병합하지 않게 되며, 이는 문자 간 간격과 순서가 의미를 전달하는 스크립트에 필수적입니다.

**Q:** *`setDisableCharsGrouping` 설정은 HTML 출력에만 적용되나요?*  
**A:** 아니요, 기본 PDF 렌더링 엔진에 영향을 주므로 HTML, PNG 등 모든 출력 형식에 적용됩니다.

**Q:** *맞춤 폰트와 함께 이 설정을 사용할 수 있나요?*  
**A:** 예—`Viewer`를 초기화하기 전에 맞춤 폰트를 로드하면 그룹화 규칙은 그대로 적용됩니다.

**Q:** *그룹화를 비활성화하면 성능에 영향을 미치나요?*  
**A:** 약간의 영향을 받을 수 있습니다. 엔진이 각 문자를 개별적으로 처리하기 때문이지만 대부분의 문서에서는 영향이 최소 수준입니다.

**Q:** *페이지별로 그룹화를 토글할 방법이 있나요?*  
**A:** 현재 옵션은 `PdfOptions` 인스턴스당 전역적으로 적용됩니다. 페이지별로 다르게 적용하려면 페이지마다 별도의 `Viewer` 인스턴스를 생성해야 합니다.

## 리소스

- [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs Viewer 다운로드](https://releases.groupdocs.com/viewer/java/)
- [라이선스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험 버전](https://releases.groupdocs.com/viewer/java/)
- [임시 라이선스 신청](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 지원 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2025-12-21  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs