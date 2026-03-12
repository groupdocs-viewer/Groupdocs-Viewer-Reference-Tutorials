---
date: '2026-01-18'
description: 'GroupDocs.Viewer for Java를 사용하여 PDF 페이지를 회전하는 방법을 배워보세요. 이 단계별 튜토리얼에서는
  Maven 설정, 페이지 회전(예: PDF를 90도 회전) 및 문제 해결을 다룹니다.'
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: Java에서 GroupDocs.Viewer를 사용하여 PDF 페이지 회전하는 방법 – 종합 가이드
type: docs
url: /ko/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Java에서 GroupDocs.Viewer를 사용하여 PDF 페이지를 회전하는 방법

PDF 내 특정 페이지를 회전하는 것은 문서를 방향으로 바꾸거나 슬라이드 슬라이드를 조정하는 데 사용할 수 있습니다. **이 가이드에서는 GroupDocs.Viewer를 사용하여 프로그래밍 방식으로 pdf 페이지를 회전하는 방법**을 배웁니다, 90도 회전, 전체 섹션 뒤집기, 또는 단일 호출로 여러 페이지를 처리하는 경우에도.

![Java용 GroupDocs.Viewer로 특정 PDF 페이지 회전](/viewer/advanced-rendering/rotate-special-pdf-pages-java.png)

**배우가 될 내용:**
- Java 프로젝트에 GroupDocs.Viewer 설정하기 (Maven GroupDocs Viewer 구성 포함)
- 특정 PDF 페이지를 프로그래밍 방식으로 회전하기(pdf 90도, 180 회전도 등)
- 북극 사용을 주요 구성으로 한다.
- 자주 발생하는 문제 해결

## 빠른 답변
- **Java에서 PDF 페이지를 회전할 수 있는 클래스는 무엇입니까?** GroupDocs.Viewer for Java.
- **단일 페이지를 90도 회전할 수 있습니까?** 예, `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`를 사용합니다.
- **개발에 전력이 필요합니까?** 무료로 체험을 하는 동안 인스턴스를 사용할 수 있습니다.
- **Maven이 필요합니까?** Maven은 GroupDocs를 강력하게 관리하는 권장 방법입니다.
- **응답한 페이지를 어떻게 받아들일까요?** `HtmlViewOptions`를 사용하고 `viewer.view(...)`를 호출합니다.

## 전제조건

### 필수 라이브러리 및 종속성

시작하려면 다음을 설치해야 하는지 확인하십시오:
- JDK(Java Development Kit) 버전 8 이상 기계에 설치해야 합니다.
- IntelliJ IDEA 또는 Eclipse와 동일한 통합 개발 환경(IDE).
- Maven을 통해 힘을 모아 관리하기.

### 환경 설정 요구 사항

1. **Maven 구성**: `pom.xml`에 필요한 추진력과 추진력을 포함하여 GroupDocs.Viewer를 Maven 프로젝트에 추가합니다.
2. **라이선스 획득**: 개발 중 제한 없이 모든 기능을 검색할 수 있도록 GroupDocs에서 임시 인스턴스를 제공합니다. [GroupDocs 무료 평가판](https://releases.groupdocs.com/viewer/java/)을 방문하거나 [GroupDocs 임시 라이선스 페이지](https://purchase.groupdocs.com/temporary-license/)에서 임시 VM을 신청하십시오.

## Java용 GroupDocs.Viewer 설정

Maven을 사용하여 Java 프로젝트에 GroupDocs.Viewer를 통합하려면 `pom.xml`을 업데이트해야 합니다.

**메이븐 구성**
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

### 기본 초기화 및 설정

문서 출력 및 출력은 GroupDocs.Viewer를 통해 이루어집니다:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## 구현 가이드

### GroupDocs.Viewer를 사용하여 특정 페이지 회전

**개요:** 문서 프레젠테이션을 개선하기 위해 특정 PDF 페이지를 회전합니다.

#### 1단계: 페이지 회전 구성

`HtmlViewOptions`를 사용하여 첫 번째 페이지를 90도, 두 번째 페이지를 180도 회전합니다:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### 2단계: 뷰어 초기화 및 렌더링

문서와 함께 `Viewer` 인스턴스를 생성하고 지정된 페이지를 렌더링합니다:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### 매개변수 및 구성

- **회전**: `rotatePage`를 사용하여 페이지 번호와 회전 방향을 사용합니다. 사용 회전 가능: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.
- **HtmlViewOptions**: PDF 페이지를 HTML로 변환하도록 구성하여 사용자에게 전달합니다.
- **pdf에서 html java로**: `HtmlViewOptions` 클래스는 종속을 유지하면서 PDF‑to‑HTML 변환을 처리합니다.

#### 문제 해결 팁(PDF 회전 문제 해결)

- 문서 및 출력을 정상적으로 수행하십시오.
- 해당하는 분들은 신뢰할 수 있는 버전을 확인하시기 바랍니다.
- 체험 중 기능을 제한하면 인스턴스가 적용되도록 합니다.
- 메모리 증가가 발생하면 페이지를 작은 배치로 받아들이는 것을 고려하시기 바랍니다(여러 pdf 페이지를 회전시켜서).

## 실제 적용

### 실제 사용 사례
1. **문서 반대** – 스캔한 문서를 올바른 디지털 방향으로 회전합니다.
2. **프레젠테이션 조정** – 공유하기 전에 PDF 내 슬라이드 슬라이드를 수정합니다.
3. **아카이브 워크** – 디지털화 속에 있는 액티비티의 방향을 자동으로 조정합니다.

### 통합 가능성
신뢰성 기능은 필수 Java 기반 문서 관리 시스템, 콘텐츠 플랫폼 또는 연결 솔루션에 GroupDocs.Viewer를 통합합니다.

## 성능 고려 사항

- **리소스 관리**: `Viewer`를 선택하여 활동을 할 수 있습니다.
- **Java 메모리 관리**: 대형 문서를 전송할 때 메모리 모델링을 모니터링하고 효율적인 데이터 구조를 사용합니다.
- **모범 참가자**: 자주 접근하는 문서나 페이지에 캐싱을 활용합니다.

## 결론

이 튜토리얼에서는 Java에서 GroupDocs.Viewer를 사용하여 **pdf를 회전하는 방법**을 환경 설정부터 실용적으로 적용했습니다. Watermaking이나 문서를 다른 형식으로 변환하는 등 추가 기능을 실험해 보세요.

**다음 단계:** 문서 처리 기능을 강화하기 위해 GroupDocs.Viewer의 더 많은 기능을 살펴보세요.

## FAQ 섹션

### 일반적인 질문
1. **회전 문제 해결**: 페이지 번호와 개별적으로 개별적으로 해결하십시오.
2. **대용량 PDF 파일 처리**: 적절한 리소스 관리를 통해 대형 문서를 처리합니다.
3. **라이선스 요구 사항**: 개발에는 기적의 기계를 사용하고, 관리하는 능력을 구매하십시오.
4. **다중 페이지 회전**: 서로 다른 페이지 번호와 규칙으로 `rotatePage`를 여러 번 부여합니다.
5. **Java 라이브러리와 통합**: 더 큰 특징이나 프레임워크에 GroupDocs.Viewer를 별개히 통합합니다.

## 자주 묻는 질문

**Q: PDF의 모든 페이지를 한 번에 회전할 수 있습니까?**
답: 예. 페이지 번호를 순회하면서 각 페이지에 `rotatePage(page, Rotation.ON_90_DEGREE)`를 호출하면 됩니다.

**Q: 회전이 원본 PDF 파일에 영향을 주겠습니까?**
A: 아니오. 교체는 과정에서만, 원본 PDF는 변경되지 않습니다.

**Q: PDF가 포스틱으로 보호해 드리고 싶은데 어떻게 해야 할까요?**
A: `Viewer`를 생성할 때 포스틱을 제공합니다: `new Viewer(경로, 비밀번호)`.

**Q: HtmlViewOptions 설정 시 “null 포인터” 오류를 선택하려면 어떻게 해야 합니까?**
A: 출력 로그를 존재하는지 확인하고 `pageFilePathFormat`이 작동하도록 삽입하십시오.

**Q: 다른 형식(예: PNG)으로 변환할 호스트를 이동할 수 있습니까?**
A: 대상 형식에 맞는 옵션과 함께 일치 `rotatePage` 구성을 사용하면 됩니다.

## 자원
- **문서**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 레퍼런스**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **다운로드**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **구매**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)
- **무료 체험**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **임시 라이선스 요청**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **지원**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-01-18  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs