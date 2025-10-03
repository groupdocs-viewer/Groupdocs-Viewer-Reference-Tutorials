---
"date": "2025-04-24"
"description": "Java 애플리케이션에서 GroupDocs.Viewer의 미터링 라이선스를 설정하고 관리하는 방법을 알아보고, 비용을 관리하면서 효율적인 문서 보기를 확보하세요."
"title": "Java에서 GroupDocs.Viewer에 대한 계량형 라이선스 구현&#58; 개발자 가이드"
"url": "/ko/java/security-permissions/groupdocs-viewer-java-metered-license-setup-guide/"
"weight": 1
type: docs
---
# Java용 GroupDocs.Viewer에 대한 계량형 라이선스 구현: 개발자 가이드

## 소개

Java 애플리케이션에서는 문서 열람을 효율적이고 비용 효율적으로 관리하는 것이 매우 중요합니다. GroupDocs.Viewer for Java를 사용하여 계량형 라이선스를 설정하면 처리되거나 열람된 문서 수에 따라 사용량을 제어할 수 있어 예상치 못한 비용 없이 확장성을 확보할 수 있습니다.

이 종합 가이드에서는 Java 애플리케이션에서 GroupDocs.Viewer의 계량형 라이선스를 설정하고 구성하는 방법을 알아봅니다. 다음 내용을 이해하게 됩니다.
- 미터링 라이센스를 취득하고 적용하는 방법
- GroupDocs.Viewer를 프로젝트에 통합하는 데 필요한 설정 단계
- 실제 사용 사례의 실용적인 예

필수 조건을 자세히 살펴보겠습니다!

## 필수 조건

미터링 라이센스 설정 기능을 구현하기 전에 다음 사항이 있는지 확인하세요.

### 필수 라이브러리 및 종속성

Maven을 사용하여 GroupDocs.Viewer를 통합해야 합니다. 프로젝트 설정에 다음 사항이 포함되어 있는지 확인하세요.
- **메이븐**: 종속성 관리를 위해.
- **자바 개발 키트(JDK)**: 버전 8 이상.

### 환경 설정 요구 사항

IntelliJ IDEA나 Eclipse와 같은 적합한 IDE와 종속성을 다운로드하기 위한 활성 인터넷 연결을 포함하여 Java 애플리케이션에 맞게 개발 환경이 구성되어 있는지 확인하세요.

### 지식 전제 조건

Java 프로그래밍에 대한 기본적인 이해와 Maven 빌드 도구에 대한 지식이 있으면 도움이 됩니다. 소프트웨어 애플리케이션의 라이선스 관리 경험은 도움이 되지만 필수는 아닙니다.

## Java용 GroupDocs.Viewer 설정

시작하려면 Maven을 사용하여 GroupDocs.Viewer를 프로젝트에 종속성으로 포함합니다.

**Maven 설정**

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

### 라이센스 취득 단계

1. **무료 체험**: 무료 평가판 버전을 다운로드하여 시작하세요. [GroupDocs 무료 평가판](https://releases.groupdocs.com/viewer/java/).

2. **임시 또는 정식 면허**: 테스트 목적으로 임시 라이선스를 취득하거나 필요에 따라 정식 라이선스를 구매하세요. [구매 페이지](https://purchase.groupdocs.com/buy) 계속하려면.

### 기본 초기화 및 설정

프로젝트 구조를 설정하고 모든 종속성이 올바르게 구성되었는지 확인하여 Java 애플리케이션에서 GroupDocs.Viewer를 초기화하세요. 방법은 다음과 같습니다.

```java
import com.groupdocs.viewer.Metered;

public class ViewerSetup {
    public static void main(String[] args) {
        // 여기에서 라이센스 설정을 초기화하세요
    }
}
```

## 구현 가이드

### 미터링 라이센스 기능 설정

이 기능을 사용하면 GroupDocs.Viewer API를 사용하여 미터링된 라이선스를 설정하여 사용과 비용 관리를 제어할 수 있습니다.

#### 개요

그만큼 `Metered` 이 클래스는 GroupDocs.Viewer 라이브러리의 일부입니다. 개발자는 이 클래스를 사용하여 문서 수나 사용자 세션과 같은 사용 지표를 기반으로 라이선스를 구성할 수 있습니다.

#### 구현 단계

##### 1단계: 라이선스 키 정의

먼저, 미터링된 라이선스에 대한 공개 키와 개인 키를 정의하세요.

```java
String publicKey = "your-public-key";
String privateKey = "your-private-key";
```

바꾸다 `"your-public-key"` 그리고 `"your-private-key"` 귀하가 계량 라이선스를 취득했을 때 GroupDocs에서 제공한 실제 값을 사용합니다.

##### 2단계: 미터링된 인스턴스 초기화

인스턴스를 생성합니다 `Metered` 수업:

```java
Metered metered = new Metered();
```

##### 3단계: 라이선스 키 설정

사용하세요 `setMeteredKey` 공개 키와 개인 키를 적용하는 방법:

```java
metered.setMeteredKey(publicKey, privateKey);
```

이 단계는 귀하의 애플리케이션을 GroupDocs 라이선스 서버와 연결하여 사용량을 추적하는 데 중요합니다.

#### 문제 해결 팁

- 키가 올바른 형식으로 되어 있고 유효한지 확인하세요.
- 원격으로 라이선스를 설정하는 동안 문제가 발생하면 네트워크 연결을 확인하세요.
- 버전별 변경 사항이나 업데이트가 있는지 GroupDocs 문서를 검토하세요.

## 실제 응용 프로그램

계량형 라이선스를 구현하면 여러 가지 실용적인 응용 프로그램이 제공됩니다.

1. **구독 기반 서비스**: 문서 조회수에 따라 사용량을 청구할 수 있는 SaaS 플랫폼에 이상적입니다.
2. **엔터프라이즈 솔루션**: 부서 간 문서 처리를 추적하여 대규모 조직의 비용을 관리하는 데 도움이 됩니다.
3. **협업 도구**: 문서 공유 및 보기에 크게 의존하는 도구를 개선하여 공정한 리소스 분배를 보장합니다.

CRM이나 ERP 애플리케이션 등 다른 시스템과 통합하면 운영을 더욱 간소화하고, 라이선스를 효과적으로 관리하는 동시에 원활한 사용자 환경을 제공할 수 있습니다.

## 성능 고려 사항

Java용 GroupDocs.Viewer를 사용할 때 최적의 성능을 보장하려면 다음을 수행하세요.
- **리소스 사용 최적화**메모리 사용량을 모니터링하고 데이터 처리를 최적화하여 병목 현상을 방지합니다.
- **자바 메모리 관리**: 효율적인 가비지 수집 방식을 사용하고 애플리케이션의 요구 사항에 따라 충분한 힙 공간을 할당합니다.
- **모범 사례**: 성능 개선과 새로운 기능을 활용하기 위해 라이브러리를 정기적으로 업데이트합니다.

## 결론

이 가이드를 따라 하면 Java 애플리케이션에서 GroupDocs.Viewer의 계량형 라이선스를 설정하는 방법을 배우게 됩니다. 이 설정은 비용을 효과적으로 관리하는 데 도움이 될 뿐만 아니라 비즈니스 요구에 따라 문서 보기 기능을 확장할 수 있도록 해줍니다.

다음 단계에는 GroupDocs.Viewer의 추가 기능을 살펴보거나 더 복잡한 시스템에 통합하는 것이 포함됩니다. 자유롭게 실험하고 특정 요구 사항에 맞게 구현 방식을 조정해 보세요.

## FAQ 섹션

1. **라이센스 오류는 어떻게 해결하나요?**
   - 키 유효성을 확인하고, 네트워크 설정을 확인하고, 최신 설명서를 참조하여 업데이트를 확인하세요.
2. **정액제 라이선스에서 일반 라이선스로 전환할 수 있나요?**
   - 네, GroupDocs 웹사이트에 설명된 구매 절차에 따라 업그레이드할 수 있습니다.
3. **라이센스 설정과 관련된 일반적인 문제는 무엇입니까?**
   - 잘못된 키 형식이나 네트워크 연결 문제는 일반적인 문제입니다. 사용자 환경이 모든 필수 조건을 충족하는지 확인하세요.
4. **미터링 라이선스는 성능에 어떤 영향을 미칩니까?**
   - 올바르게 구현하면 자세한 사용 분석을 제공하는 동시에 영향은 최소화됩니다.
5. **어려움이 발생할 경우 지원 옵션이 있나요?**
   - GroupDocs는 지원을 위한 포럼과 직접적인 지원 채널을 제공합니다.

## 자원

더 자세히 알아보고 심도 있게 이해하려면:
- [GroupDocs 문서](https://docs.groupdocs.com/viewer/java/)
- [API 참조](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/java/)
- [라이센스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험판](https://releases.groupdocs.com/viewer/java/)
- [임시 면허 정보](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 지원 포럼](https://forum.groupdocs.com/c/viewer/9)