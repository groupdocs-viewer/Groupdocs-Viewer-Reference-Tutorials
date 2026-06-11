---
date: '2026-03-05'
description: GroupDocs.Viewer를 사용해 JPG 품질을 조정하여 Java에서 PDF를 압축하는 방법을 배우세요 – 파일 크기와
  시각적 품질을 균형 있게 유지하는 간단한 Java PDF 압축 방법입니다.
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: Java에서 PDF 압축 방법 – JPG 품질 최적화
type: docs
url: /ko/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# Java에서 PDF 압축하기 – JPG 품질 최적화

Balancing file size and visual fidelity is a common challenge when working with PDFs. In this tutorial you’ll discover **PDF 압축 방법** by adjusting the JPG image quality inside PDF documents using GroupDocs.Viewer for Java. We'll walk through the setup, code implementation, and practical tips so you can confidently compress PDF images without sacrificing readability.

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## 빠른 답변
- **“reduce PDF size Java”가 의미하는 바는?** 이미지 품질, 압축 및 리소스 처리를 조정하여 Java 애플리케이션에서 더 작은 PDF 파일을 생성하는 것입니다.  
- **JPG 품질을 제어하는 설정은?** `PdfViewOptions.setJpgQuality(byte quality)`이며 값은 0(최저)부터 100(최고)까지 범위입니다.  
- **같은 흐름에서 PPTX를 PDF로 변환할 수 있나요?** 예—`Viewer`를 `.pptx` 소스에 지정하면 동일한 옵션이 적용됩니다.  
- **웹 게시에 일반적인 품질 수준은?** **50‑70** 정도의 값이 대부분의 웹 시나리오에 좋은 균형을 제공합니다.  
- **이 기능에 라이선스가 필요합니까?** 평가용으로는 무료 체험판으로 충분하지만, 실제 운영에서는 정식 라이선스가 필요합니다.

## Java에서 PDF 압축하기 – 개요
Reducing PDF size in Java involves optimizing the resources inside a PDF—most notably images—so the final file occupies less storage and loads faster. By lowering JPG quality, you effectively **compress PDF images**, which often constitute the bulk of a document’s size.

## “reduce PDF size Java”란 무엇인가요?
Reducing PDF size in Java involves optimizing the resources inside a PDF—most notably images—so the final file occupies less storage and loads faster. By lowering JPG quality, you effectively **compress PDF images**, which often constitute the bulk of a document’s size.

## GroupDocs Viewer로 JPG 품질을 조정하는 이유
- **크기 감소 효과**: 이미지 품질을 낮추면 원본 해상도에 따라 PDF 크기를 30‑70 % 정도 줄일 수 있습니다.  
- **단일 패스 변환**: 별도의 이미지 처리 단계가 필요 없으며, GroupDocs가 PDF 생성 중에 이를 처리합니다.  
- **유연성**: 프로젝트 요구에 따라 `byte` 품질 값을 세밀하게 조정할 수 있습니다(예: 고품질 인쇄 vs. 가벼운 웹 미리보기).  

## 사전 요구 사항
- **GroupDocs.Viewer for Java** 버전 25.2 이상.  
- Maven 기반 Java 프로젝트이며 JDK 8 이상.  
- Java 및 PDF 처리에 대한 기본 지식.  

## GroupDocs.Viewer for Java 설정
Add the GroupDocs repository and dependency to your `pom.xml`:

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

> **Pro tip:** 최신 버전을 유지하여 성능 향상 및 새로운 압축 옵션의 혜택을 받으세요.

## 구현 가이드

### 단계 1: 출력 디렉터리 경로 확인
Create a helper class that builds the output folder where the PDF will be saved.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class FeatureResolveOutputDirectoryPath {
    public static Path getOutputDirectoryPath(String subdirectory) {
        String directory = Paths.get("YOUR_OUTPUT_DIRECTORY", "AdjustQualityOfJpgImages", subdirectory).toString();
        
        try {
            return Paths.get(directory);
        } catch (IOException e) {
            throw new RuntimeException("Failed to create output directory.", e);
        }
    }
}
```

### 단계 2: 원하는 JPG 품질로 `PdfViewOptions` 설정
Set the JPG quality level (0‑100) before rendering the document.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class FeatureAdjustQualityOfJpgImages {
    public static void run() {
        Path outputDirectory = FeatureResolveOutputDirectoryPath.getOutputDirectoryPath("YOUR_DOCUMENT_DIRECTORY");
        Path filePath = outputDirectory.resolve("output.pdf");

        PdfViewOptions viewOptions = new PdfViewOptions(filePath);
        
        // Set desired JPG quality (0-100 scale)
        byte quality = 10;
        viewOptions.setJpgQuality(quality);

        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/source.pptx")) {
            viewer.view(viewOptions);
        }
    }
}
```

**설명:**  
- `setJpgQuality(byte quality)`는 JPG 이미지에 적용할 압축 정도를 GroupDocs에 알려줍니다. 값이 낮을수록 파일이 작아지지만 시각적 선명도가 감소할 수 있습니다.  
- 예제에서는 `source.pptx`를 사용해 **convert pptx to pdf**를 시연하면서 동시에 이미지를 압축합니다.

### 단계 3: 코드를 실행하고 결과 확인
Execute `FeatureAdjustQualityOfJpgImages.run()`. The generated `output.pdf` will contain JPG images at the quality level you specified, effectively **compressing PDF images** and reducing overall file size.

## 일반적인 문제 및 해결 방법
- **잘못된 파일 경로:** 작업 디렉터리 기준으로 소스 문서(`source.pptx`)가 존재하는지 확인하세요.  
- **권한 부족:** 출력 폴더에 쓰기 권한이 있어야 하며, 그렇지 않으면 `RuntimeException`이 발생합니다.  
- **예상보다 큰 PDF:** 목표 크기에 맞게 `quality` 값이 충분히 낮은지 확인하세요.  

## 실용적인 적용 사례
1. **문서 보관:** 작은 PDF는 저장 비용을 절감하고 검색 속도를 향상시킵니다.  
2. **웹 게시:** 웹사이트에 PDF를 삽입하거나 링크할 때 페이지 로드 속도가 빨라집니다.  
3. **이메일 첨부:** 전송 전에 이미지 품질을 낮춰 크기 제한을 충족합니다.  

## 성능 고려 사항
- **배치 처리:** 많은 문서를 다룰 때는 메모리 사용량을 모니터링하면서 병렬 스레드로 처리합니다.  
- **최적 품질 설정:** 인쇄용 PDF는 높은 품질(80‑100)을 사용하고, 웹 미리보기는 보통 30‑50 정도면 충분합니다.  

## 결론
이제 GroupDocs.Viewer를 사용해 JPG 이미지 품질을 조정하여 **PDF 압축 방법**을 알게 되었습니다. 다양한 품질 수준을 실험하고 코드를 기존 파이프라인에 통합하여 더 빠르고 가벼운 PDF를 활용하세요.

### 다음 단계
- 사용 사례에 맞는 최적의 품질 설정을 찾기 위해 다양한 품질 값을 테스트하세요.  
- 워터마크나 암호 보호와 같은 추가 GroupDocs 기능을 살펴보세요.  

## FAQ 섹션

1. **JPG 품질을 조정하면 파일 크기에 어떤 영향을 미치나요?**  
   품질을 낮추면 파일 크기가 감소하여 문서를 공유하거나 저장하기가 쉬워집니다.

2. **JPG 외 다른 포맷의 이미지 품질을 조정할 수 있나요?**  
   이 기능은 PDF 내 JPG 이미지에만 적용되지만, GroupDocs.Viewer는 다른 포맷에 대한 옵션도 제공합니다.

3. **웹 사용에 적합한 JPG 품질 설정은?**  
   50‑70 정도의 균형 잡힌 값이 좋은 선명도와 웹 애플리케이션에 적합한 파일 크기 감소를 제공합니다.

4. **이 과정을 배치 워크플로우에서 자동화할 수 있나요?**  
   예, 이 기능을 자동화 시스템에 통합하여 여러 문서를 효율적으로 처리할 수 있습니다.

5. **예상대로 출력 PDF가 생성되지 않으면 어떻게 해야 하나요?**  
   입력 문서 경로를 확인하고 모든 종속성이 올바르게 구성되었는지 확인하세요.

## 자주 묻는 질문

**Q:** *DOCX와 같은 다른 포맷을 PDF로 변환하면서 크기를 줄이는 데 이 방법을 사용할 수 있나요?*  
**A:** 물론 가능합니다. `PdfViewOptions.setJpgQuality` 설정은 PDF에 JPG 이미지가 포함되는 모든 소스 포맷에 적용됩니다.

**Q:** *JPG 품질을 낮추면 텍스트 렌더링에 영향을 주나요?*  
**A:** 아닙니다. 텍스트는 벡터 기반이므로 선명함을 유지하고, 영향을 받는 것은 래스터 이미지뿐입니다.

**Q:** *페이지마다 다른 품질 수준을 설정할 수 있나요?*  
**A:** 현재 GroupDocs는 변환당 하나의 일관된 품질 설정만 적용합니다. 페이지별 제어가 필요하면 전용 이미지 처리 라이브러리로 PDF를 후처리해야 합니다.

**Q:** *프로덕션 배포에 라이선스가 필요합니까?*  
**A:** 예, 프로덕션 사용을 위해서는 유효한 GroupDocs.Viewer 라이선스가 필요합니다. 평가용 무료 체험판을 제공하고 있습니다.

**Q:** *실제 품질 감소를 어떻게 확인할 수 있나요?*  
**A:** 변환 전후의 파일 크기를 비교하고 PDF를 열어 이미지 선명도를 시각적으로 확인하세요.

---

**리소스**  
- [문서](https://docs.groupdocs.com/viewer/java/)  
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer for Java 다운로드](https://releases.groupdocs.com/viewer/java/)  
- [라이선스 구매](https://purchase.groupdocs.com/buy)  
- [무료 체험 버전](https://releases.groupdocs.com/viewer/java/)  
- [임시 라이선스 정보](https://purchase.groupdocs.com/temporary-license/)  
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)  

---

**마지막 업데이트:** 2026-03-05  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs