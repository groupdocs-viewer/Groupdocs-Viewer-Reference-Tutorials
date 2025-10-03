---
"date": "2025-04-24"
"description": "GroupDocs.Viewer for Java를 사용하여 PDF 문서 내 특정 페이지를 회전하는 방법을 알아보세요. 이 가이드에서는 설정, 구현 및 실제 적용 사례를 다룹니다."
"title": "Java에서 GroupDocs.Viewer를 사용하여 특정 PDF 페이지 회전하기 - 포괄적인 가이드"
"url": "/ko/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/"
"weight": 1
type: docs
---
# Java에서 GroupDocs.Viewer를 사용하여 특정 PDF 페이지 회전

## 소개

PDF 내 특정 페이지를 회전하는 기능은 문서를 정렬하거나 프레젠테이션 슬라이드를 조정하는 데 필수적입니다. 이 튜토리얼에서는 Java용 GroupDocs.Viewer를 사용하여 PDF 페이지를 쉽게 회전하는 방법을 보여줍니다.

**배울 내용:**
- Java 프로젝트에서 GroupDocs.Viewer 설정
- 특정 PDF 페이지를 프로그래밍 방식으로 회전
- 최적의 사용을 위한 주요 구성
- 구현 중 일반적인 문제 해결

## 필수 조건

### 필수 라이브러리 및 종속성

시작하려면 다음 사항이 있는지 확인하세요.
- 컴퓨터에 Java Development Kit(JDK) 버전 8 이상이 설치되어 있어야 합니다.
- IntelliJ IDEA나 Eclipse와 같은 통합 개발 환경(IDE).
- 프로젝트 종속성을 관리하기 위한 Maven.

### 환경 설정 요구 사항

1. **Maven 구성**: 필요한 저장소와 종속성을 Maven 프로젝트에 포함하여 GroupDocs.Viewer를 추가합니다. `pom.xml`.
2. **라이센스 취득**: GroupDocs에서 임시 라이선스를 구매하면 개발 중에 제한 없이 모든 기능을 사용할 수 있습니다. 방문하세요. [GroupDocs 무료 평가판](https://releases.groupdocs.com/viewer/java/) 또는 임시 면허를 신청하세요 [GroupDocs 임시 라이선스 페이지](https://purchase.groupdocs.com/temporary-license/).

## Java용 GroupDocs.Viewer 설정

Maven을 사용하여 GroupDocs.Viewer를 Java 프로젝트에 통합하려면 다음을 업데이트하세요. `pom.xml`:

**Maven 구성**
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

문서 디렉토리와 출력 경로를 지정하여 GroupDocs.Viewer를 초기화합니다.

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// 페이지 파일 경로 형식
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## 구현 가이드

### GroupDocs.Viewer를 사용하여 특정 페이지 회전

**개요:** 더 나은 문서 표현을 위해 특정 PDF 페이지를 회전합니다.

#### 1단계: 페이지 회전 구성

첫 번째 페이지를 90도 회전하고 두 번째 페이지를 180도 회전합니다. `HtmlViewOptions`:

```java
// 첫 번째 페이지를 시계 방향으로 90도 회전합니다.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// 두 번째 페이지를 180도 회전합니다.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### 2단계: 뷰어 초기화

생성하다 `Viewer` 문서와 함께 인스턴스를 생성하고 지정된 페이지를 렌더링합니다.

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// 구성된 옵션을 사용하여 지정된 페이지(1과 2)를 렌더링합니다.
viewer.view(viewOptions, 1, 2);

// 항상 뷰어를 닫아 리소스를 확보하세요.
viewer.close();
```

### 매개변수 및 구성

- **회전**: 사용 `rotatePage` 페이지 번호와 회전 각도를 포함합니다. 사용 가능한 회전: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.
- **HTMLView옵션**: PDF 페이지를 HTML로 변환하도록 구성하여 내장된 리소스가 포함되도록 합니다.

#### 문제 해결 팁

- 문서 및 출력 디렉토리 경로를 확인하세요.
- 누락된 종속성이나 잘못된 라이브러리 버전을 확인하세요.
- 평가판 사용 중 기능 제한이 발생하는 경우 라이선스가 제대로 적용되었는지 확인하세요.

## 실제 응용 프로그램

### 실제 사용 사례
1. **문서 정렬**: 올바른 디지털 정렬을 위해 스캔한 문서를 회전합니다.
2. **프레젠테이션 조정**: 공유하기 전에 PDF 내의 프레젠테이션 슬라이드를 수정하세요.
3. **보관 워크플로**: 디지털화 과정에서 역사적 문서의 방향을 자동으로 조정합니다.

### 통합 가능성
GroupDocs.Viewer를 Java 기반 문서 관리 시스템, 콘텐츠 플랫폼 또는 동적 보기 기능이 필요한 맞춤형 엔터프라이즈 솔루션과 통합합니다.

## 성능 고려 사항

- **자원 관리**: 닫기 `Viewer` 리소스를 해제하는 인스턴스입니다.
- **자바 메모리 관리**: 대용량 문서를 렌더링할 때 메모리 사용량을 모니터링하고 효율적인 데이터 구조를 사용합니다.
- **모범 사례**: 자주 액세스하는 문서나 페이지에 캐싱을 활용합니다.

## 결론

이 튜토리얼에서는 Java에서 GroupDocs.Viewer를 사용하여 특정 PDF 페이지를 회전하는 방법을 다루었으며, 환경 설정부터 실제 적용까지 다뤘습니다. 워터마킹이나 문서를 다른 형식으로 변환하는 등의 추가 기능도 실험해 보세요.

**다음 단계:** GroupDocs.Viewer의 더 많은 기능을 살펴보고 문서 처리 역량을 강화하세요.

## FAQ 섹션

### 자주 묻는 질문
1. **회전 문제 해결**: 페이지 번호와 회전 매개변수가 올바른지 확인하세요.
2. **대용량 PDF 파일 처리**: 적절한 리소스 관리를 통해 대용량 문서를 효율적으로 처리합니다.
3. **라이센스 요구 사항**: 개발에는 임시 라이선스를 사용하고, 운영에는 전체 라이선스를 구매하세요.
4. **여러 페이지 회전**부르다 `rotatePage` 여러 번 다른 페이지 번호와 각도로 게재되었습니다.
5. **Java 라이브러리와의 통합**: 대규모 애플리케이션이나 프레임워크 내에서 GroupDocs.Viewer를 원활하게 통합합니다.

## 자원
- **선적 서류 비치**: [GroupDocs 뷰어 문서](https://docs.groupdocs.com/viewer/java/)
- **API 참조**: [GroupDocs API 참조](https://reference.groupdocs.com/viewer/java/)
- **다운로드**: [GroupDocs 다운로드 페이지](https://releases.groupdocs.com/viewer/java/)
- **구입**: [GroupDocs 구매 옵션](https://purchase.groupdocs.com/buy)
- **무료 체험**: [GroupDocs 무료 평가판](https://releases.groupdocs.com/viewer/java/)
- **임시 면허**: [임시 면허 신청](https://purchase.groupdocs.com/temporary-license/)
- **지원하다**: [GroupDocs 지원 포럼](https://forum.groupdocs.com/c/viewer/9)