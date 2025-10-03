---
"date": "2025-04-24"
"description": "Java에서 GroupDocs.Viewer를 사용하여 아카이브 구조를 효율적으로 검색하는 방법을 알아보세요. 이 가이드를 따라 하면 간편한 설정, 코드 예제, 그리고 실용적인 활용법을 배울 수 있습니다."
"title": "GroupDocs.Viewer for Java를 사용하여 아카이브 구조를 검색하는 방법&#58; 종합 가이드"
"url": "/ko/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/"
"weight": 1
type: docs
---
# Java용 GroupDocs.Viewer를 사용하여 아카이브 구조를 검색하는 방법

## 소개

아카이브 파일을 효과적으로 관리하려면 파일의 구조를 명확하게 이해해야 합니다. 이 종합 가이드는 Java에서 GroupDocs.Viewer 라이브러리를 사용하여 폴더 구조를 포함한 아카이브 파일 정보를 추출하는 방법을 보여줍니다. 이러한 기술을 숙달하면 데이터 관리 프로세스를 간소화하고 워크플로 효율성을 향상시킬 수 있습니다.

**배울 내용:**
- Java용 GroupDocs.Viewer 설정 및 구성.
- 아카이브에서 뷰 정보를 검색하는 방법.
- 보관 파일의 폴더 구조를 읽고 표시하는 기술.
- Java 프로젝트에서 GroupDocs.Viewer를 사용할 때의 실용적인 적용 및 성능 고려 사항.

Java용 GroupDocs.Viewer를 사용하여 이러한 기능을 구현하기 전에 필요한 전제 조건을 알아보는 것으로 시작해 보겠습니다.

## 필수 조건

이 튜토리얼을 따르려면 다음 사항이 필요합니다.

- **자바 개발 키트(JDK):** 컴퓨터에 8 이상 버전이 설치되어 있어야 합니다.
- **메이븐:** 종속성과 프로젝트 빌드를 관리합니다.
- **Java 프로그래밍에 대한 기본 이해:** 객체 지향 프로그래밍 개념에 익숙해지면 도움이 됩니다.

또한 Maven을 사용하여 프로젝트에 특정 저장소와 종속성을 추가하여 GroupDocs.Viewer 라이브러리를 포함합니다. `pom.xml` 파일.

## Java용 GroupDocs.Viewer 설정

Java로 GroupDocs.Viewer를 사용하려면 다음 단계를 따르세요.

### Maven 구성

Maven 구성 파일에 다음을 추가합니다.

**저장소:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**종속성:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### 라이센스 취득

- **무료 체험:** 시작하려면 GroupDocs 웹사이트에서 무료 평가판 버전을 다운로드하세요.
- **임시 면허:** 제한 없이 장기적으로 접근하고 싶다면 임시 라이선스를 신청하세요.
- **라이센스 구매:** 장기 프로젝트의 경우 전체 라이선스 구매를 고려하세요.

구성이 완료되면, 필요한 클래스를 가져오고 기본 뷰어 인스턴스를 설정하여 GroupDocs.Viewer로 프로젝트를 초기화합니다.

## 구현 가이드

### 기능 1: 보관 파일의 보기 정보 가져오기

이 기능은 GroupDocs.Viewer를 사용하여 아카이브 파일에 대한 자세한 정보를 가져오는 방법을 보여줍니다. Viewer 클래스를 초기화하고, 뷰 옵션을 지정하고, 파일 형식과 페이지 수를 추출하는 과정이 포함됩니다.

#### 뷰어 초기화

먼저 다음을 만들어 보세요. `Viewer` 대상 아카이브 파일 경로가 있는 인스턴스:

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // 여기에 추가 단계가 나와 있습니다.
}
```

#### 보기 정보 검색

사용 `getViewInfo()` HTML 보기 옵션을 사용하여 보관 파일에 대한 세부 정보를 얻으려면:

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 폴더 구조 표시

아카이브 내의 폴더 구조를 탐색하려면 재귀적 메서드를 호출합니다.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 재귀적 폴더 읽기

이 도우미 메서드는 다음을 사용합니다. `ViewInfoOptions` 폴더 보기를 지정하고 하위 폴더를 재귀적으로 읽습니다.

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

### 기능 2: 보관 폴더 구조 검색

이 기능은 아카이브 파일의 폴더 구조를 출력하는 데 중점을 둡니다. 첫 번째 기능과 유사하지만 재귀적 탐색을 강조합니다.

#### 보기 정보 옵션 설정

구성 `ViewInfoOptions` 특정 폴더 포함:

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 재귀적 탐색

이 방법은 하위 폴더를 반복하면서 각각을 인쇄하고 재귀적으로 더 깊이 탐색합니다.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 실제 응용 프로그램

1. **데이터 관리:** 보관 구조를 이해하여 대규모 데이터 세트를 빠르게 구성하세요.
2. **자동 파일 처리:** 이 기술을 사용하여 일괄 작업에서 보관된 파일의 처리를 자동화합니다.
3. **CMS 시스템과의 통합:** GroupDocs.Viewer를 통합하여 효율적인 파일 처리를 통해 콘텐츠 관리 시스템을 개선하세요.

## 성능 고려 사항

- **메모리 사용 최적화:** 특히 많은 수의 파일이나 크기가 큰 파일을 다루는 경우 리소스를 현명하게 관리하여 대규모 보관소를 효율적으로 처리하세요.
- **모범 사례:** 성능 향상을 위해 라이브러리와 JDK를 최신 버전으로 정기적으로 업데이트하세요.

## 결론

이 튜토리얼을 따라 하면 Java용 GroupDocs.Viewer를 효과적으로 사용하여 아카이브 구조를 검색하고 관리하는 방법을 배우게 됩니다. 이러한 기술은 데이터 구성 및 처리와 관련된 다양한 애플리케이션에서 중요한 자산이 될 수 있습니다. 다음 단계로, GroupDocs.Viewer 라이브러리의 다른 기능을 살펴보거나 이러한 기술을 대규모 프로젝트에 통합하는 것을 고려해 보세요.

## FAQ 섹션

**질문: GroupDocs.Viewer란 무엇인가요?**
답변: 아카이브를 포함한 문서를 HTML, 이미지, PDF 등 다양한 형식으로 렌더링하기 위한 강력한 Java 라이브러리입니다.

**질문: GroupDocs.Viewer를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**
답변: 네, GroupDocs는 다양한 플랫폼에 대한 SDK를 제공하지만, 이 튜토리얼에서는 Java 구현에 중점을 둡니다.

**질문: 대용량 보관 파일을 어떻게 처리하나요?**
A: 효율적인 메모리 관리 관행을 사용하고, 필요한 경우 보관 자료를 분해하는 것을 고려하세요.

**질문: GroupDocs.Viewer는 어떤 유형의 보관소를 지원하나요?**
A: ZIP, RAR, TAR 등 다양한 형식을 지원합니다.

**질문: 처리할 수 있는 아카이브 크기에 제한이 있나요?**
A: 제한 사항은 시스템 리소스에 따라 달라집니다. 항상 특정 환경을 고려하여 테스트하시기 바랍니다.

## 자원

- **선적 서류 비치:** [GroupDocs 뷰어 Java 문서](https://docs.groupdocs.com/viewer/java/)
- **API 참조:** [Java용 GroupDocs API 참조](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs.Viewer 다운로드:** [GroupDocs 다운로드 페이지](https://releases.groupdocs.com/viewer/java/)
- **라이센스 구매:** [GroupDocs 구매](https://purchase.groupdocs.com/buy)
- **무료 체험판 및 임시 라이센스:** [GroupDocs 무료 평가판](https://releases.groupdocs.com/viewer/java/) | [임시 면허](https://purchase.groupdocs.com/temporary-license/)

GroupDocs.Viewer를 사용하여 Java 애플리케이션의 아카이브 파일 처리 기능을 향상시키려면 다음 단계를 프로젝트에서 시도해 보세요. 즐거운 코딩 되세요!