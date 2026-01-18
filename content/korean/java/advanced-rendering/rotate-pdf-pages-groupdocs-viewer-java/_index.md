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

# Java에서 GroupDocs.Viewer를 사용하여 PDF 페이지 회전하는 방법

PDF 내 특정 페이지를 회전하는 것은 문서를 정렬하거나 프레젠테이션 슬라이드를 조정하는 데 필수적일 수 있습니다. **이 가이드에서는 GroupDocs.Viewer를 사용하여 프로그래밍 방식으로 pdf 페이지를 회전하는 방법**을 배웁니다, 90도 회전, 전체 섹션 뒤집기, 또는 단일 호출로 여러 페이지를 처리하는 경우에도.

![Java용 GroupDocs.Viewer로 특정 PDF 페이지 회전](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**배우게 될 내용:**
- Java 프로젝트에 GroupDocs.Viewer 설정하기 (Maven GroupDocs Viewer 구성 포함)
- 특정 PDF 페이지를 프로그래밍 방식으로 회전하기 (pdf 90도 회전, 180도 회전 등)
- 최적 사용을 위한 주요 구성
- 구현 중 흔히 발생하는 문제 해결

## Quick Answers
- **Java에서 PDF 페이지를 회전할 수 있는 라이브러리는 무엇인가요?** GroupDocs.Viewer for Java.
- **단일 페이지를 90도 회전할 수 있나요?** 예, `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`를 사용합니다.
- **개발에 라이선스가 필요합니까?** 무료 체험을 위한 임시 라이선스를 사용할 수 있습니다.
- **Maven이 필요합니까?** Maven은 GroupDocs 종속성을 관리하는 권장 방법입니다.
- **회전된 페이지를 어떻게 렌더링합니까?** `HtmlViewOptions`를 사용하고 `viewer.view(...)`를 호출합니다.

## Prerequisites

### Required Libraries and Dependencies

시작하려면 다음이 설치되어 있는지 확인하십시오:
- Java Development Kit (JDK) 버전 8 이상이 머신에 설치되어 있어야 합니다.
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE).
- 프로젝트 종속성을 관리하기 위한 Maven.

### Environment Setup Requirements

1. **Maven 구성**: `pom.xml`에 필요한 저장소와 종속성을 포함하여 GroupDocs.Viewer를 Maven 프로젝트에 추가합니다.
2. **라이선스 획득**: 개발 중 제한 없이 모든 기능을 탐색할 수 있도록 GroupDocs에서 임시 라이선스를 받습니다. [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)을 방문하거나 [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/)에서 임시 라이선스를 신청하십시오.

## Setting Up GroupDocs.Viewer for Java

Maven을 사용하여 Java 프로젝트에 GroupDocs.Viewer를 통합하려면 `pom.xml`을 업데이트하십시오:

**Maven Configuration**
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

### Basic Initialization and Setup

문서 디렉터리와 출력 경로를 지정하여 GroupDocs.Viewer를 초기화합니다:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Implementation Guide

### Rotating Specific Pages with GroupDocs.Viewer

**개요:** 문서 프레젠테이션을 개선하기 위해 특정 PDF 페이지를 회전합니다.

#### Step 1: Configure Page Rotation

`HtmlViewOptions`를 사용하여 첫 번째 페이지를 90도, 두 번째 페이지를 180도 회전합니다:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### Step 2: Initialize Viewer and Render

문서와 함께 `Viewer` 인스턴스를 생성하고 지정된 페이지를 렌더링합니다:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### Parameters and Configuration

- **Rotation**: 페이지 번호와 회전 각도를 사용하여 `rotatePage`를 사용합니다. 사용 가능한 회전: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.
- **HtmlViewOptions**: PDF 페이지를 HTML로 변환하도록 구성하며, 임베디드 리소스가 포함되도록 합니다.
- **pdf to html java**: `HtmlViewOptions` 클래스는 레이아웃을 유지하면서 PDF‑to‑HTML 변환을 처리합니다.

#### Troubleshooting Tips (troubleshoot pdf rotation)

- 문서 및 출력 디렉터리 경로를 확인하십시오.
- 누락된 종속성이나 잘못된 라이브러리 버전을 확인하십시오.
- 체험 중 기능 제한이 발생하면 라이선스가 올바르게 적용되었는지 확인하십시오.
- 메모리 급증이 발생하면 페이지를 작은 배치로 렌더링하는 것을 고려하십시오(여러 pdf 페이지를 점진적으로 회전).

## Practical Applications

### Real‑world Use Cases
1. **문서 정렬** – 스캔한 문서를 올바른 디지털 방향으로 회전합니다.
2. **프레젠테이션 조정** – 공유 전에 PDF 내 프레젠테이션 슬라이드를 수정합니다.
3. **아카이브 워크플로** – 디지털화 중에 역사적 문서의 방향을 자동으로 조정합니다.

### Integration Possibilities
동적 뷰 기능이 필요한 Java 기반 문서 관리 시스템, 콘텐츠 플랫폼 또는 맞춤형 엔터프라이즈 솔루션에 GroupDocs.Viewer를 통합합니다.

## Performance Considerations

- **리소스 관리**: `Viewer` 인스턴스를 닫아 리소스를 해제합니다.
- **Java 메모리 관리**: 대형 문서를 렌더링할 때 메모리 사용량을 모니터링하고 효율적인 데이터 구조를 사용합니다.
- **모범 사례**: 자주 접근하는 문서나 페이지에 캐싱을 활용합니다.

## Conclusion

이 튜토리얼에서는 Java에서 GroupDocs.Viewer를 사용하여 **pdf 페이지를 회전하는 방법**을 환경 설정부터 실용적인 적용까지 다루었습니다. 워터마킹이나 문서를 다른 형식으로 변환하는 등 추가 기능을 실험해 보세요.

**다음 단계:** 문서 처리 기능을 강화하기 위해 GroupDocs.Viewer의 더 많은 기능을 탐색하십시오.

## FAQ Section

### Common Questions
1. **회전 문제 해결**: 페이지 번호와 회전 매개변수가 올바른지 확인하십시오.
2. **대용량 PDF 파일 처리**: 적절한 리소스 관리를 통해 대형 문서를 효율적으로 처리합니다.
3. **라이선스 요구 사항**: 개발에는 임시 라이선스를 사용하고, 프로덕션에는 정식 라이선스를 구매하십시오.
4. **다중 페이지 회전**: 서로 다른 페이지 번호와 각도로 `rotatePage`를 여러 번 호출합니다.
5. **Java 라이브러리와 통합**: 더 큰 애플리케이션이나 프레임워크에 GroupDocs.Viewer를 원활히 통합합니다.

## Frequently Asked Questions

**Q: PDF의 모든 페이지를 한 번에 회전할 수 있나요?**  
A: 예. 페이지 번호를 순회하면서 각 페이지에 `rotatePage(page, Rotation.ON_90_DEGREE)`를 호출하면 됩니다.

**Q: 회전이 원본 PDF 파일에 영향을 줍니까?**  
A: 아니오. 회전은 렌더링 과정에서만 적용되며, 원본 PDF는 변경되지 않습니다.

**Q: PDF가 비밀번호로 보호되어 있으면 어떻게 해야 하나요?**  
A: `Viewer` 인스턴스를 생성할 때 비밀번호를 제공합니다: `new Viewer(path, password)`.

**Q: HtmlViewOptions 설정 시 “null pointer” 오류를 디버그하려면 어떻게 해야 하나요?**  
A: 출력 디렉터리가 존재하는지 확인하고 `pageFilePathFormat`이 올바르게 해석되는지 확인하십시오.

**Q: 다른 형식(예: PNG)으로 변환할 때도 페이지를 회전할 수 있나요?**  
A: 대상 형식에 맞는 뷰 옵션과 함께 동일한 `rotatePage` 구성을 사용하면 됩니다.

## Resources
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