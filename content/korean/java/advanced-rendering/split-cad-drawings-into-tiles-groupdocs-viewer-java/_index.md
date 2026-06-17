---
date: '2026-04-01'
description: GroupDocs Viewer for Java를 사용하여 CAD 도면을 타일로 분할하는 방법을 배우고, 렌더링 성능을 향상시키며
  대용량 파일 처리를 간소화하세요.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: GroupDocs Viewer를 사용하여 CAD 도면을 타일로 분할하는 방법
type: docs
url: /ko/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer로 CAD 도면을 타일로 분할하는 방법

CAD 파일을 더 작고 관리하기 쉬운 조각으로 **분할하는 방법**을 궁금해 하신다면, 바로 여기입니다. 이 튜토리얼에서는 **GroupDocs Viewer for Java**를 사용해 대형 CAD 도면을 타일로 분할하는 정확한 단계를 안내합니다. 끝까지 따라오시면 렌더링 속도가 향상되고 메모리 사용량이 감소하며 웹 또는 모바일 애플리케이션에서 도면을 보다 쉽게 표시할 수 있는 준비된 솔루션을 얻을 수 있습니다.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## 빠른 답변
- **“CAD 분할”은 어떤 효과가 있나요?** 대용량 도면을 더 작은 이미지(타일)로 나누어 로드 속도가 빨라지고 메모리 사용량이 감소합니다.  
- **타일 형식은 무엇을 사용하나요?** 기본적으로 PNG 파일이 생성되며, Viewer 옵션을 통해 다른 형식도 지원됩니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 프로덕션에서는 유료 라이선스가 필요합니다.  
- **타일 크기를 변경할 수 있나요?** 예 – `tileWidth`와 `tileHeight` 계산식을 조정하여 원하는 크기로 설정할 수 있습니다.  
- **이 방법은 스레드‑안전한가요?** 각 타일을 별도의 `Viewer` 인스턴스로 `try‑with‑resources`와 함께 렌더링하면 동시 실행에 안전합니다.

## “CAD 분할”이란 무엇인가?
CAD 분할은 하나의 크고 복잡한 CAD 도면을 여러 개의 직사각형 구역(타일)으로 나누는 것을 의미합니다. 각 타일은 독립적으로 렌더링되므로 사용자가 실제로 필요로 하는 부분만 로드할 수 있어 웹 지도, 문서 포털, 모바일 뷰어 등에 최적화됩니다.

## 왜 GroupDocs Viewer for Java를 사용하나요?
GroupDocs Viewer는 DWG, DXF, DWF 등 100개 이상의 파일 형식을 즉시 지원합니다. 타일 API를 통해 정확한 좌표를 지정할 수 있어 전체 파일을 먼저 처리하지 않고도 필요한 영역만 렌더링할 수 있습니다. 이는 CPU 사용량을 절감하고 대역폭을 줄이며 보다 부드러운 사용자 경험을 제공합니다.

## 사전 요구 사항
- **라이브러리**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: 최신 Java Development Kit (Java 8 이상).  
- **IDE**: IntelliJ IDEA, Eclipse 또는 기타 Java‑호환 IDE.  
- **빌드 도구**: Maven (다른 빌드 도구도 의존성을 추가하면 사용 가능).

## GroupDocs.Viewer for Java 설정
`pom.xml`에 GroupDocs 저장소와 의존성을 추가합니다:

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
GroupDocs.Viewer는 평가용 무료 체험 라이선스를 제공합니다:

- **무료 체험**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)에서 라이브러리를 다운로드하세요.  
- **임시 라이선스**: [Temporary License Page](https://purchase.groupdocs.com/temporary-license/)에서 신청하세요.  
- **정식 라이선스**: [Purchase Page](https://purchase.groupdocs.com/buy)에서 프로덕션 라이선스를 구매하세요.

### 기본 초기화
라이브러리가 정상적으로 로드되는지 확인하기 위해 간단한 `Viewer` 인스턴스를 생성합니다:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## CAD 도면을 타일로 분할하는 단계별 가이드

### 단계 1: 출력 디렉터리 정의
각 타일을 별도의 PNG 파일로 저장합니다. 유틸리티 메서드를 사용하면 경로 로직을 깔끔하고 재사용 가능하게 유지할 수 있습니다.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### 단계 2: 뷰 옵션 구성
렌더링 형식을 PNG로 설정하고, 모든 페이지를 미리 로드하지 않도록 지정하면 메모리를 절약할 수 있습니다.

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### 단계 3: 타일 크기 계산
먼저 도면의 원본 너비와 높이를 가져온 뒤, 이를 네 개의 동일한 사분면으로 나눕니다.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### 단계 4: 타일 렌더링 및 저장
계산된 타일을 렌더링 옵션에 추가하고 `Viewer`가 PNG 파일을 생성하도록 합니다.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### 문제 해결 팁
- **빌드 경로** – GroupDocs JAR 파일이 클래스패스에 포함되어 있는지 확인하세요.  
- **권한** – 출력 폴더가 Java 프로세스에 의해 쓰기 가능해야 합니다.  
- **예외** – `ViewerException`이 발생하면 DWG 파일이 손상되지 않았는지, 올바른 라이선스가 적용되었는지 다시 확인하세요.

## CAD 타일 분할의 일반적인 사용 사례
1. **웹 매핑** – 사용자가 팬/줌할 때 화면에 보이는 부분만 로드합니다.  
2. **문서 관리** – 각 타일을 별도로 저장해 미리보기 생성 속도를 높입니다.  
3. **모바일 뷰잉** – 현재 화면에 필요한 타일만 다운로드해 대역폭을 절감합니다.

## 성능 고려 사항
- **타일 크기** – 큰 타일은 파일 수를 줄이지만 렌더링 속도가 느려집니다. UI 요구에 맞는 균형을 찾으세요.  
- **메모리 모니터링** – VisualVM 같은 Java 프로파일링 도구를 사용해 대형 도면 처리 시 힙 사용량을 관찰하세요.  
- **리소스 정리** – 위에서 보여준 `try‑with‑resources` 패턴이 네이티브 리소스를 자동으로 해제합니다.

## 자주 묻는 질문

**Q: 같은 방법으로 다른 파일 형식(PDF, 이미지 등)을 타일로 분할할 수 있나요?**  
A: 예. GroupDocs Viewer는 다양한 형식을 지원하므로 해당 옵션 클래스(예: `PdfViewOptions`)를 사용하면 됩니다.

**Q: 출력 이미지 품질을 어떻게 조정하나요?**  
A: `viewOptions.setResolution(int dpi)`를 조정하거나 `PngOptions` 객체의 압축 설정을 변경하세요.

**Q: 매우 큰 DWG 파일에서 메모리 부족 오류가 발생합니다—어떻게 해결할 수 있나요?**  
A: 타일 크기를 줄이거나 JVM 힙(`-Xmx`)을 늘리거나, 별도의 `Viewer` 인스턴스로 순차적으로 타일을 렌더링하세요.

**Q: 타일을 비동기적으로 렌더링할 수 있나요?**  
A: 가능합니다. 각 타일 렌더링 호출을 `CompletableFuture`로 감싸거나 ExecutorService를 사용해 작업을 병렬화하세요.

**Q: 타일마다 별도의 라이선스가 필요합니까?**  
A: 아닙니다. 하나의 유효한 GroupDocs Viewer 라이선스로 애플리케이션 내 모든 렌더링 작업을 커버합니다.

## 리소스
- [문서](https://docs.groupdocs.com/viewer/java/)
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/java/)
- [라이선스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험](https://releases.groupdocs.com/viewer/java/)
- [임시 라이선스](https://purchase.groupdocs.com/temporary-license/)
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)

---

**마지막 업데이트:** 2026-04-01  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs