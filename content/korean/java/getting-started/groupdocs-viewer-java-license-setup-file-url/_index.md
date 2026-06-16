---
date: '2026-03-08'
description: 로컬 파일 또는 URL을 사용하여 GroupDocs.Viewer Java의 라이선스를 설정하는 방법을 배워보세요. 이 단계별
  가이드는 라이선스를 빠르고 안정적으로 설정하는 방법을 보여줍니다.
keywords:
- GroupDocs.Viewer Java license
- setting license from file
- setting license via URL
title: GroupDocs.Viewer Java 라이선스 설정 방법 (파일 또는 URL)
type: docs
url: /ko/java/getting-started/groupdocs-viewer-java-license-setup-file-url/
weight: 1
---

# GroupDocs.Viewer Java 라이선스 설정 방법 (파일 또는 URL)

Java 애플리케이션에서 GroupDocs.Viewer의 전체 잠재력을 활용하려면 로컬 파일 또는 온라인 URL에서 **라이선스 설정 방법**을 배우세요. 이 가이드는 두 가지 접근 방식을 단계별로 안내하고, 각 방법이 중요한 이유를 설명하며, 문서 보기 기능을 중단 없이 유지하기 위한 실용적인 팁을 제공합니다.

## 빠른 답변
- **Java에서 GroupDocs.Viewer 라이선스를 설정하는 기본 방법은 무엇인가요?** `License` 클래스를 사용하고 파일 또는 URL에서 얻은 `InputStream`을 `setLicense`에 전달합니다.  
- **앱을 재배포하지 않고 라이선스를 변경할 수 있나요?** 예—라이선스를 웹 서버에 저장하고 URL을 새 파일을 가리키도록 변경하면 됩니다.  
- **로컬 파일 라이선스를 사용할 때 인터넷 연결이 필요합니까?** 아니요, 파일 기반 방법은 완전히 오프라인에서 작동합니다.  
- **필요한 Java 버전은?** Java 8 이상을 권장합니다.  
- **추가 Maven 설정이 필요합니까?** 아래에 표시된 GroupDocs.Viewer 의존성과 저장소 항목만 필요합니다.

## GroupDocs.Viewer에서 “라이선스 설정 방법”이란?

라이선스를 설정하면 GroupDocs.Viewer 엔진에 유효한 상업적 권한이 있음을 알립니다. 라이선스가 없으면 라이브러리는 평가 모드로 실행되어 기능이 제한되고 워터마크가 추가됩니다. 라이선스를 올바르게 구성하면 PDF, Office 문서, 이미지 등 모든 렌더링 기능을 사용할 수 있습니다.

## 로컬 파일과 URL 중 어느 것을 사용할까?

- **로컬 파일:** 안정적인 인터넷 연결이 없거나 가장 빠른 시작을 원할 때 이상적입니다.  
- **URL:** 중앙 집중식 라이선스 관리에 최적—한 곳에서 라이선스를 업데이트하면 모든 실행 중인 인스턴스가 자동으로 변경 사항을 반영합니다.

## 소개

Java에서 GroupDocs.Viewer를 사용할 때 라이선스는 평가 모드 이상의 전체 기능을 활용하기 위해 필수적입니다. 라이선스 파일이 로컬에 저장되든 URL에서 가져오든, 이를 효과적으로 관리하면 기능 중단 없이 사용할 수 있습니다.

![Java용 GroupDocs.Viewer 로컬 파일 또는 URL 가이드](/viewer/getting-started/local-file-or-url-guide.png)

**배우게 될 내용:**  
- 로컬 파일을 사용한 GroupDocs Viewer Java 라이선스 설정 방법  
- 온라인 리소스를 위한 URL 기반 라이선스 설정 방법  
- 전제 조건 및 환경 설정 이해  

Java 애플리케이션에서 **라이선스 설정 방법**을 시작해 봅시다.

### 전제 조건

- **라이브러리 및 의존성:** GroupDocs.Viewer for Java 라이브러리를 포함합니다. Maven을 사용하면 의존성 관리가 쉽습니다.  
- **환경 설정:** Java 8 이상 (신규 프로젝트에는 JDK 11+ 권장).  
- **지식 전제 조건:** 기본 Java 프로그래밍, 파일 처리, URL 작업.

### GroupDocs.Viewer for Java 설정

Java 프로젝트에 GroupDocs.Viewer를 통합하려면 다음 설정 단계를 따르세요:

**Maven 구성:**

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

**라이선스 획득:**

GroupDocs.Viewer를 사용하려면 공식 사이트에서 라이선스를 획득하세요. 옵션은 다음과 같습니다:
- **무료 체험:** 기능을 살펴볼 수 있는 체험판을 시작합니다.  
- **임시 라이선스:** 제한 없이 단기 평가에 유용합니다.  
- **구매:** 장기 사용 및 지원을 위해.

라이선스 파일을 확보했으면 Java 애플리케이션에서 초기화해 봅시다.

## 로컬 파일에서 라이선스 설정 방법

이 방법은 시스템에 로컬로 저장된 라이선스 파일을 읽는 것입니다. 오프라인에서 라이선스를 바로 사용할 수 있다면 간단합니다.

**개요:**  
파일에서 라이선스를 설정하면 초기 설정 후 인터넷 연결 없이도 애플리케이션이 전체 기능으로 시작할 수 있습니다.

1. **라이선스 파일 위치 찾기:**  
   `YOUR_DOCUMENT_DIRECTORY/your-license-file.lic`을 실제 로컬 라이선스 파일 경로로 교체합니다.

2. **코드 구현:**  

```java
import com.groupdocs.viewer.License;
import java.io.File;
import java.nio.file.Files;
import java.nio.file.Paths;

public class SetLicenseFromFile {
    public static void run() {
        final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
        if (new File(licensePath).isFile()) {
            try (
                java.io.InputStream stream = Files.newInputStream(Paths.get(licensePath))
            ) {
                License license = new License();
                license.setLicense(stream);
                System.out.println("License set successfully from file.");
            } catch (IOException ex) {
                ex.printStackTrace(); // Properly handle exceptions in production
            }
        } else {
            System.err.println("License file not found at the specified path.");
        }
    }
}
```

**설명:**  
- `License` 클래스를 가져와 라이선스 설정을 관리합니다.  
- Java NIO는 효율적이고 논블로킹 파일 I/O를 제공합니다.  
- 견고한 예외 처리를 통해 파일이 없거나 읽을 수 없을 때 충돌을 방지합니다.

## URL에서 라이선스 설정 방법

라이선스 파일이 온라인에 있다면 URL을 통해 설정하면 설정 과정을 간소화할 수 있습니다.

**개요:**  
온라인 소스에서 라이선스를 가져오는 것은 중앙 집중식 관리가 필요하거나 애플리케이션을 재배포하지 않고도 자주 업데이트해야 할 때 이상적입니다.

1. **라이선스 URL 준비:**  
   `YOUR_DOCUMENT_DIRECTORY/your-license-url`이 라이선스 파일을 포함하는 유효한 HTTP(s) 리소스를 가리키는지 확인합니다.

2. **코드 구현:**  

```java
import com.groupdocs.viewer.License;
import java.io.IOException;
import java.net.URL;

public class SetLicenseFromUrl {
    public static void run() {
        final String licenseUrl = "YOUR_DOCUMENT_DIRECTORY/your-license-url";
        if (licenseUrl.startsWith("http")) {
            try (
                java.io.InputStream stream = new URL(licenseUrl).openStream()
            ) {
                License license = new License();
                license.setLicense(stream);
                System.out.println("License set successfully from URL.");
            } catch (IOException ex) {
                ex.printStackTrace(); // Properly handle exceptions in production
            }
        } else {
            System.err.println("The provided path is not a valid URL.");
        }
    }
}
```

**설명:**  
- `URL` 클래스를 사용해 원격 라이선스 파일을 가져옵니다.  
- URL 검증을 통해 잘못된 경로 사용을 방지합니다.  
- 네트워크 관련 예외를 잡아 애플리케이션이 정상적으로 대응하도록 합니다(예: 재시도 또는 대체).

## 실용적인 적용 사례

1. **문서 관리 시스템:** 전체 기능 접근을 통해 문서 보기 기능을 강화합니다.  
2. **웹 애플리케이션:** 서버 측 의존성 없이 사용자가 원활하게 문서를 상호작용할 수 있게 합니다.  
3. **모바일 앱:** 백엔드 서비스로 활용해 모바일 기기에서 문서를 표시합니다.  
4. **콘텐츠 관리 플랫폼:** 디지털 라이브러리의 콘텐츠 전달 및 보기를 간소화합니다.

## 성능 고려 사항

애플리케이션 최적화에는 다음이 포함됩니다:
- **효율적인 자원 사용:** 스트림을 즉시 닫아 파일 핸들과 네트워크 소켓을 해제합니다.  
- **비동기 작업:** URL에서 라이선스를 가져올 때는 다운로드를 백그라운드 스레드에서 실행하거나 `CompletableFuture`를 사용해 메인 스레드가 차단되지 않도록 고려합니다.  
- **Java 메모리 관리:** 특히 대용량 문서를 렌더링할 때 힙 사용량을 모니터링하고 필요에 따라 JVM 옵션(`-Xmx`, `-XX:MaxMetaspaceSize`)을 조정합니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결책 |
|------|------|--------|
| **라이선스 파일을 찾을 수 없음** | 잘못된 경로나 파일 권한 누락 | 절대 경로를 확인하고 프로세스 사용자가 파일을 읽을 수 있는지 확인합니다. |
| **잘못된 URL** | 오타 또는 `http/https` 스키마 누락 | URL 문자열을 다시 확인하고, 예시와 같이 `startsWith("http")` 검증을 사용합니다. |
| **네트워크 시간 초과** | 서버가 느리거나 접근 불가 | 지수 백오프를 적용한 재시도 로직을 구현하거나 대체 로컬 복사본을 제공합니다. |
| **평가 워터마크가 계속 표시됨** | `Viewer` 인스턴스를 생성하기 전에 라이선스가 로드되지 않음 | 어떤 `Viewer` 객체도 인스턴스화하기 **전에** 라이선스 코드를 호출합니다. |

## 자주 묻는 질문

**Q: 로컬에서 라이선스 파일을 찾을 수 없으면 어떻게 해야 하나요?**  
A: 경로가 정확하고 파일이 존재하며 애플리케이션에 읽기 권한이 있는지 확인합니다. 빠른 해결책으로 URL 방법으로 전환할 수도 있습니다.

**Q: 재배포 없이 라이선스를 업데이트할 수 있나요?**  
A: 예—라이선스를 웹 서버에 저장하고 URL을 해당 위치로 지정합니다. 서버에서 파일을 업데이트하면 라이선스를 다시 로드한 모든 실행 중인 인스턴스에 즉시 반영됩니다.

**Q: URL을 통해 라이선스를 설정할 때 네트워크 오류를 어떻게 처리하나요?**  
A: 다운로드를 try‑catch 블록으로 감싸고 재시도 로직을 추가하며, 선택적으로 캐시된 로컬 복사본을 사용합니다.

**Q: Java에서 GroupDocs.Viewer를 사용하면 어떤 이점이 있나요?**  
A: 100개 이상의 포맷에 대해 강력하고 고성능의 문서 렌더링을 제공하며, 원활한 통합과 외부 종속성이 없습니다.

**Q: 문제가 발생했을 때 어디에서 지원을 받을 수 있나요?**  
A: [GroupDocs 지원 포럼](https://forum.groupdocs.com/c/viewer/9)에서 도움과 커뮤니티 인사이트를 확인하세요.

## 결론

이 튜토리얼을 따라 하면 로컬 파일이든 원격 URL이든 Java에서 GroupDocs.Viewer의 **라이선스 설정 방법**을 알게 됩니다. 올바른 라이선스를 적용하면 모든 기능을 활용할 수 있고, 성능이 향상되며, 평가 제한이 사라집니다.

**다음 단계:**  
- 다양한 문서 유형(PDF, DOCX, PPTX)을 실험해 전체 렌더링 기능을 확인합니다.  
- 페이지별 렌더링, 워터마크, 사용자 정의 폰트 등 고급 Viewer 옵션을 탐색합니다.

오늘 바로 이러한 솔루션을 구현하여 사용자에게 완벽한 문서 보기 경험을 제공하세요!

---

**마지막 업데이트:** 2026-03-08  
**테스트 환경:** GroupDocs.Viewer for Java 25.2  
**작성자:** GroupDocs