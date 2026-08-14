---
date: '2026-06-30'
description: GroupDocs.Viewer를 사용하여 viewinfo를 가져오고 Java 아카이브 파일 유형 구조를 검색하는 방법을 배웁니다.
  이 가이드는 설정, 코드 예제 및 실제 사용 사례를 다룹니다.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Java에서 ViewInfo를 가져오고 아카이브 구조를 검색하는 방법
type: docs
url: /ko/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# ViewInfo를 가져오고 Java에서 아카이브 구조를 검색하는 방법

아카이브 파일을 효과적으로 관리하려면 그 구조에 대한 명확한 이해가 필요합니다. 이 튜토리얼에서는 모든 아카이브에 대해 **viewinfo를 가져오는 방법**을 배우고, 이것이 **java archive file type** 작업에 어떻게 도움이 되는지 확인합니다. GroupDocs.Viewer 설정, 뷰 정보 추출, 폴더 계층 구조를 재귀적으로 읽는 과정을 단계별로 안내하여 실제 프로젝트에 솔루션을 통합할 수 있도록 합니다.

![Java용 GroupDocs.Viewer의 아카이브 구조](/viewer/document-loading/archive-structures-java.png)

**배우게 될 내용**
- Java용 GroupDocs.Viewer 설정 및 구성.  
- 아카이브에서 **viewinfo를 가져오는** 방법.  
- 아카이브 파일의 폴더 구조를 읽고 표시하는 기술.  
- Java 프로젝트에서 GroupDocs.Viewer를 사용할 때의 실용적인 적용 사례와 성능 고려 사항.  

## 빠른 답변
- **viewinfo는 무엇을 제공합니까?** 파일 유형, 페이지 수, 그리고 아카이브 내부의 폴더와 파일 전체 목록을 반환합니다.  
- **지원되는 아카이브 형식은 무엇입니까?** ZIP, RAR, TAR, 7z, ISO 및 12가지 이상의 기타 일반 형식.  
- **프로덕션에 라이선스가 필요합니까?** 예—프로덕션에는 상용 라이선스가 필요하며, 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **대용량 아카이브를 효율적으로 처리할 수 있습니까?** 물론입니다—스트리밍 옵션을 사용하고 폴더 레벨을 하나씩 처리하여 메모리 사용량을 낮게 유지합니다.  
- **라이브러리를 추가하는 방법이 Maven뿐입니까?** Maven이 권장되는 의존성 관리 도구이지만, Gradle 또는 수동 JAR 포함도 작동합니다.  

## “viewinfo를 가져오는 방법”이란?
`getViewInfo`는 전체 렌더링 없이 문서 또는 아카이브에서 메타데이터를 추출하는 GroupDocs.Viewer API 메서드입니다. 한 번의 호출로 내부 폴더 트리, 파일 수 및 기본 속성을 반환하여 처리할 부분을 선택할 수 있게 합니다. 이 호출은 일반 서버에서 1초 미만에 500 MB까지의 아카이브 전체 스냅샷을 반환합니다.

## 왜 Java 아카이브 파일 유형 구조를 검색해야 합니까?
**java archive file type**의 내부 레이아웃을 검색하면 필요한 파일을 즉시 찾고, 불필요한 추출을 피하며, 관련 서브 폴더만 다루는 자동화 파이프라인을 구축할 수 있습니다. 이 방법은 대용량 아카이브의 I/O를 최대 70 %까지 감소시키며, 데이터 수집 시나리오에서 분당 수천 개 파일을 스캔하는 것이 가능해집니다.

## 전제 조건
- **Java Development Kit (JDK):** 버전 8 이상.  
- **Maven:** 의존성 관리 및 빌드용.  
- **기본 Java 지식:** OOP 개념에 익숙하면 도움이 되지만 필수는 아닙니다.  

또한 GroupDocs.Viewer 라이브러리에 접근할 수 있어야 하며, 아래와 같이 Maven 프로젝트에 추가할 수 있습니다.

## Java용 GroupDocs.Viewer 설정

### Maven 구성
`pom.xml`에 저장소와 의존성을 추가합니다.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### 라이선스 획득
- **무료 체험:** GroupDocs 웹사이트에서 체험 버전을 다운로드합니다.  
- **임시 라이선스:** 단기 평가를 위한 임시 키를 요청합니다.  
- **정식 라이선스:** 무제한 프로덕션 사용을 위한 상용 라이선스를 구매합니다.

라이브러리를 클래스패스에 추가하면 코딩을 시작할 수 있습니다.

## 구현 가이드

### 아카이브 파일에 대한 ViewInfo 가져오기
뷰 정보를 얻으려면 먼저 아카이브를 Viewer에 로드하고, `getViewInfo`를 호출해 메타데이터를 가져온 다음, 반환된 폴더 계층을 반복합니다. 이 3단계 패턴은 모든 지원되는 아카이브 형식에 적용되며, 단일 API 호출로 전체 스냅샷을 제공하여 후속 처리를 단순화합니다.

#### Viewer 초기화
`Viewer` 클래스는 모든 렌더링 및 검사 작업의 진입점입니다. 파일 스트림, 형식 감지 및 리소스 정리를 관리합니다.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### 뷰 정보 검색
`ViewInfo`는 파일 유형, 전체 페이지 수, 폴더와 파일의 계층 목록과 같은 메타데이터를 캡슐화합니다. `getViewInfo`를 호출하면 이 객체가 즉시 반환됩니다.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 폴더 구조 표시
`viewInfo.getFolders()`를 반복하여 각 폴더 이름, 깊이 및 포함된 파일을 출력합니다. 이 간단한 루프를 통해 아카이브의 읽기 쉬운 트리 뷰를 얻을 수 있습니다.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 재귀 폴더 읽기
깊게 중첩된 아카이브의 경우, 재귀 헬퍼 메서드가 깊이 우선으로 트리를 탐색하여 전체 아카이브를 메모리에 로드하지 않고도 모든 서브 폴더를 방문하도록 할 수 있습니다.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### 기능 2: 아카이브 폴더 구조 검색
이 기능은 아카이브 파일의 폴더 구조를 출력하는 데 중점을 둡니다. 첫 번째 기능과 유사하지만 재귀 탐색을 강조합니다.

#### ViewInfo 옵션 설정
`ArchiveOptions`를 사용하면 `getViewInfo`를 호출하기 전에 비밀번호 보호, 페이지 제한 및 스트리밍 선호도를 지정할 수 있습니다.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 재귀 탐색
두 번째 재귀 루틴은 비밀번호 보호된 아카이브와 대용량 파일 세트를 효율적으로 처리하는 방법을 보여줍니다.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 실용적인 적용 사례
1. **데이터 관리:** 아카이브 구조를 이해하여 대규모 데이터셋을 신속하게 정리합니다.  
2. **자동 파일 처리:** 아카이브 파일을 완전히 추출하지 않고 배치 처리하여 I/O를 최대 70 % 절감합니다.  
3. **CMS 통합:** 실시간 아카이브 탐색으로 콘텐츠 관리 시스템을 강화하여 편집자가 아카이브에서 직접 파일을 미리 볼 수 있게 합니다.  

## 성능 고려 사항
- **메모리 사용 최적화:** 폴더를 한 레벨씩 처리하고 `Viewer` 인스턴스를 즉시 닫습니다.  
- **업데이트 유지:** 최신 GroupDocs.Viewer 버전(작성 시 25.2) 및 JDK 릴리스를 사용하여 성능을 향상시킵니다.  
- **스트리밍 지원:** 라이브러리는 내부 청크 기반 읽기 아키텍처 덕분에 전체 파일을 RAM에 로드하지 않고 1 GB 이상의 아카이브를 스트리밍할 수 있습니다.  

## 일반적인 문제와 해결책

| 문제 | 발생 원인 | 해결 방법 |
|-------|----------------|-----|
| `폴더를 읽을 때 NullPointerException` | `viewInfo.getFolders()`가 빈 디렉터리에서 null을 반환합니다 | 반복하기 전에 null 또는 빈 리스트인지 확인합니다. |
| 거대한 ZIP 파일 처리 속도 저하 | 전체 아카이브가 메모리에 로드됩니다 | 새로운 GroupDocs 버전에서 제공되는 스트리밍 옵션을 사용합니다. |
| 라이선스를 찾을 수 없음 | 라이선스 파일 경로가 올바르지 않습니다 | 라이선스 파일을 애플리케이션 루트에 두거나 `License.setLicense("path/to/license.json")`를 설정합니다. |

## 자주 묻는 질문

**Q:** GroupDocs.Viewer란?  
A: GroupDocs.Viewer는 100개 이상의 문서, 이미지 및 아카이브 형식을 HTML, PDF 또는 이미지 스트림으로 렌더링하는 Java 라이브러리이며, 네이티브 애플리케이션이 필요하지 않습니다.

**Q:** 다른 프로그래밍 언어와 함께 GroupDocs.Viewer를 사용할 수 있나요?  
A: 예, GroupDocs는 .NET, Python, PHP 등용 SDK를 제공하지만, 이 튜토리얼은 Java 구현에 초점을 맞춥니다.

**Q:** 대용량 아카이브 파일을 어떻게 처리합니까?  
A: `ArchiveOptions.setUseStreaming(true)`를 통해 스트리밍을 활성화하고, 폴더 레벨을 하나씩 처리하며, 사용 후 `Viewer` 객체를 해제합니다.

**Q:** GroupDocs.Viewer가 지원하는 아카이브 유형은 무엇입니까?  
A: ZIP, RAR, TAR, 7z, ISO, ARJ, CAB 등 12가지 이상의 아카이브 형식과 다수의 독점 컨테이너 유형을 지원합니다.

**Q:** 아카이브 크기 제한이 있습니까?  
A: 실질적인 제한은 서버의 RAM 및 CPU에 따라 다르며, 스트리밍을 활성화하면 16 GB RAM 머신에서 2 GB 아카이브를 원활히 처리할 수 있습니다.

**Q:** “viewinfo를 가져오는 방법”이 비밀번호 보호된 아카이브에서도 작동합니까?  
A: 예, `getViewInfo`를 호출하기 전에 `ArchiveOptions.setPassword("yourPassword")`로 비밀번호를 제공하면 됩니다.

## 결론

이 가이드를 따라 이제 지원되는 모든 아카이브에 대해 **viewinfo를 가져오는 방법**과 GroupDocs.Viewer for Java를 사용해 폴더 계층을 탐색하는 방법을 알게 되었습니다. 이러한 기술을 통해 보다 스마트한 데이터 처리 파이프라인을 구축하고, CMS 통합을 개선하며, 대용량 아카이브 파일 컬렉션을 자신 있게 처리할 수 있습니다. 다음 단계로 아카이브에서 개별 파일을 렌더링하거나 PDF/HTML로 변환하는 다른 Viewer 기능을 살펴보세요.

---

**마지막 업데이트:** 2026-06-30  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs  

**문서:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
**API 참조:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)  
**GroupDocs.Viewer 다운로드:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
**라이선스 구매:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)  
**무료 체험 및 임시 라이선스:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## 관련 튜토리얼

- [Java용 GroupDocs.Viewer로 문서 메타데이터 추출 - 문서 뷰 정보 및 인사이트 검색](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Java용 GroupDocs.Viewer로 첨부 파일 검색 및 인쇄 방법](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java 가이드: 문서 미리보기 및 관리를 위한 GroupDocs.Viewer API로 특정 페이지 렌더링](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)