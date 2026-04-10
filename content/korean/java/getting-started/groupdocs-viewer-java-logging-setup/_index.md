---
date: '2026-04-10'
description: GroupDocs.Viewer for Java에서 로깅을 설정하는 방법을 배우고, 콘솔 로거와 파일 로거를 추가하여 문서 렌더링을
  향상시키는 방법을 포함합니다.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: GroupDocs.Viewer for Java에서 로깅 구성 방법
type: docs
url: /ko/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# GroupDocs.Viewer for Java에서 로깅 구성 방법

이 튜토리얼에서는 GroupDocs.Viewer for Java에서 **로깅을 구성하는 방법**을 배우게 되며, 이를 통해 문서 렌더링 파이프라인에 대한 실시간 인사이트를 얻고 문제를 신속하게 해결할 수 있습니다.

## 빠른 답변
- **로깅은 무엇을 제공합니까?** 렌더링 작업에 대한 실시간 피드백 및 오류 세부 정보.  
- **콘솔에 출력하는 로거는 무엇입니까?** `ConsoleLogger` (콘솔 로거 추가).  
- **파일에 기록하는 로거는 무엇입니까?** `FileLogger` (파일 로거 추가).  
- **로깅을 활성화하려면 라이선스가 필요합니까?** 아니요, 로깅은 평가판 및 정식 라이선스 버전 모두에서 작동합니다.  
- **로그 형식을 사용자 정의할 수 있습니까?** 예, 로거 클래스를 확장하여 가능합니다.

## 소개
Java 애플리케이션에서 **GroupDocs.Viewer for Java**를 사용하여 문서 렌더링 프로세스를 향상시키세요. 이 가이드는 콘솔 또는 파일에 로깅을 구성하는 방법을 단계별로 안내하며, 문서 렌더링이 어떻게 작동하는지에 대한 중요한 인사이트를 제공합니다.

![Console and File Logging with GroupDocs.Viewer for Java](/viewer/getting-started/console-and-file-logging-java.png)

**핵심 학습 포인트:**
- GroupDocs.Viewer for Java에서 로깅을 구성합니다.  
- 콘솔 및 파일 기반 로깅 시스템을 구현합니다.  
- GroupDocs.Viewer를 사용하여 임베디드 리소스가 포함된 HTML로 문서를 렌더링합니다.

## 사전 요구 사항
다음이 준비되어 있는지 확인하십시오:
1. **필수 라이브러리:**  
   - GroupDocs.Viewer for Java 라이브러리 (버전 25.2 이상).  

2. **환경 설정 요구 사항:**  
   - 시스템에 설치된 Java Development Kit (JDK).  
   - IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경 (IDE).  

3. **지식 사전 요구 사항:**  
   - Java 프로그래밍에 대한 기본 이해.  
   - 의존성 관리를 위한 Maven에 대한 친숙함.  

이러한 사전 요구 사항이 충족되면 GroupDocs.Viewer for Java를 설정할 준비가 된 것입니다!

## GroupDocs.Viewer for Java 설정
GroupDocs.Viewer를 사용하려면 Maven을 사용하여 프로젝트에 종속성으로 추가하십시오. 방법은 다음과 같습니다:

### Maven 설정
다음 구성을 `pom.xml` 파일에 추가하십시오:
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
- **무료 체험:** [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/)에서 무료 체험판을 다운로드하십시오.  
- **임시 라이선스:** [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/)에서 평가 제한을 해제하는 임시 라이선스를 획득하십시오.  
- **구매:** 전체 액세스를 위해 [GroupDocs Purchase](https://purchase.groupdocs.com/buy)에서 라이선스를 구매하는 것을 고려하십시오.  

### 기본 초기화
다음 패턴으로 GroupDocs.Viewer를 초기화하십시오:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

이 설정은 보다 복잡한 로깅 구성을 위한 기반을 형성합니다.

## 로깅 구성 방법
GroupDocs.Viewer를 사용하여 **콘솔 로거 추가** 및 **파일 로거 추가** 방법을 살펴보세요.

### 기능 1: 콘솔에 로깅
#### 개요
콘솔에 로깅하면 터미널에서 즉시 피드백을 제공하므로 개발 또는 디버깅 단계에서 유용합니다.

#### 단계
##### 단계 1: 필요한 클래스 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### 단계 2: 로깅 구성 설정
`ConsoleLogger`를 사용하여 로그를 콘솔로 전달합니다.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**설명**  
- **ConsoleLogger:** 이 클래스는 로그를 콘솔로 전달하여 작업을 실시간으로 볼 수 있게 합니다.  
- **HtmlViewOptions.forEmbeddedResources:** 각 페이지에 임베디드 리소스가 포함된 HTML을 생성하며, **html view options**를 효과적으로 사용하는 예시입니다.

#### 문제 해결 팁
문서 경로가 올바르고 접근 가능한지 확인하십시오. 콘솔 설정에서 로깅 문이 적절히 구성되어 있는지 확인하십시오.

### 기능 2: 파일에 로깅
#### 개요
파일에 로깅하면 작업의 영구 기록을 유지할 수 있어 감사 또는 사후 분석에 유용합니다.

#### 단계
##### 단계 1: 필요한 클래스 가져오기
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### 단계 2: 파일 기반 로깅 구성 설정
`FileLogger`를 사용하여 지정된 파일에 로그를 기록합니다.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**설명**  
- **FileLogger:** 이 클래스는 `output.log`라는 파일에 로그를 기록합니다.  
- **ViewerSettings with FileLogger:** GroupDocs.Viewer가 지정된 로그 파일에 **뷰어 로그를 캡처**하도록 구성합니다.

#### 문제 해결 팁
출력 파일이 저장될 디렉터리가 쓰기 가능한지 확인하십시오. 로깅이 실패할 경우 파일 권한을 확인하십시오.

## 실용적인 적용 사례
GroupDocs.Viewer는 문서 관리 및 렌더링 기능을 향상시킬 수 있습니다:
1. **웹 포털:** 웹 사용자를 위해 직접 다운로드 없이 실시간으로 문서를 렌더링합니다.  
2. **엔터프라이즈 시스템:** CRM 도구와 통합하여 계약서나 합의서를 표시합니다.  
3. **내부 대시보드:** 인트라넷 내에서 보고서와 프레젠테이션을 쉽게 볼 수 있도록 제공합니다.

## 성능 고려 사항 및 Java 로깅 모범 사례
Java에서 GroupDocs.Viewer를 사용할 때 다음 사항을 기억하십시오:
- **리소스 사용 최적화:** 대용량 문서를 렌더링할 때 메모리 사용량을 모니터링합니다.  
- **Java 메모리 관리:** 자동 리소스 정리를 위해 try‑with‑resources를 활용합니다.  
- **로깅 상세 수준:** 로거 레벨(INFO, DEBUG 등)을 조정하여 상세도와 성능 영향을 균형 있게 맞춥니다—이는 **java logging best practices**의 핵심 요소입니다.

## 결론
GroupDocs.Viewer for Java에서 **로깅을 구성하는 방법**을 배웠으며, 빠른 콘솔 뷰가 필요하든 영구적인 파일 기록이 필요하든 상관없습니다. 이 기능은 애플리케이션 디버깅, 모니터링 및 감사에 매우 유용합니다. 추가 구성을 탐색하고, 맞춤형 로거를 실험하며, 다른 시스템과 GroupDocs.Viewer를 통합하여 견고성을 강화하십시오.

구현 역량을 한 단계 끌어올릴 준비가 되셨나요? 다양한 환경에서 로깅을 설정해 보고 애플리케이션 신뢰성이 어떻게 향상되는지 확인해 보세요!

## 리소스
- [문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [다운로드](https://downloads.groupdocs.com/viewer/java/)

---

**마지막 업데이트:** 2026-04-10  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs