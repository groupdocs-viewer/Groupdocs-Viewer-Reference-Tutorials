---
date: '2026-08-13'
description: GroupDocs Viewer를 사용하여 JPG 품질을 조정함으로써 Java에서 PDF 크기를 줄이는 방법을 배우고, PPTX를
  Java PDF로 변환하는 기능 및 기타 크기 감소 기술도 활용할 수 있습니다.
keywords:
- reduce pdf size java
- convert pptx to pdf java
- java reduce pdf file size
lastmod: '2026-08-13'
og_description: GroupDocs Viewer를 사용해 JPG 품질을 조정하여 Java에서 PDF 크기를 감소시킵니다. 이 가이드는 이미지를
  압축하고, PPTX를 Java PDF로 변환하며, 가독성을 잃지 않고 더 작은 PDF를 만드는 방법을 보여줍니다.
og_image_alt: 'Guide: optimizing JPG quality to reduce PDF size in Java with GroupDocs
  Viewer'
og_title: Java에서 PDF 크기 감소 – GroupDocs Viewer와 함께하는 JPG 품질 최적화
schemas:
- author: GroupDocs
  dateModified: '2026-08-13'
  description: Learn how to reduce PDF size Java by adjusting JPG quality with GroupDocs
    Viewer, also enabling convert PPTX to PDF Java and other size‑reduction techniques.
  headline: How to reduce PDF size Java – optimize JPG quality
  type: TechArticle
- description: Learn how to reduce PDF size Java by adjusting JPG quality with GroupDocs
    Viewer, also enabling convert PPTX to PDF Java and other size‑reduction techniques.
  name: How to reduce PDF size Java – optimize JPG quality
  steps:
  - name: resolve the output directory path
    text: Create a helper class that builds the output folder where the PDF will be
      saved.
  - name: configure `PdfViewOptions` with desired JPG quality
    text: '`PdfViewOptions` is the configuration object that tells GroupDocs how to
      render the output PDF. The `setJpgQuality(byte quality)` method specifies the
      compression level for all JPG images that appear in the resulting document.
      **Explanation:** - Lower values produce smaller files but may reduce visu'
  - name: run the code and verify the result
    text: '`FeatureAdjustQualityOfJpgImages` is a sample class that runs the conversion
      with the configured JPG quality. Execute `FeatureAdjustQualityOfJpgImages.run()`.
      The generated `output.pdf` will contain JPG images at the quality level you
      specified, effectively **compressing PDF images** and reducing ov'
  type: HowTo
- questions:
  - answer: Lowering the JPG quality reduces the amount of data stored for each image,
      which can shrink the PDF size by 30‑70 % while keeping text crisp.
    question: How does adjusting JPG quality affect file size?
  - answer: This setting targets JPG images only; other raster formats have their
      own compression options within GroupDocs Viewer.
    question: Can I adjust image quality for formats other than JPG?
  - answer: A quality value between 50 and 70 generally provides clear images with
      a modest file size, ideal for most web applications.
    question: What is the ideal JPG quality setting for web use?
  - answer: Yes, you can loop over a directory of source files, apply the same `PdfViewOptions`
      configuration, and generate compressed PDFs in parallel.
    question: Is it possible to automate this process in a batch workflow?
  - answer: Yes, a valid GroupDocs Viewer license is required for production use.
      A free trial is available for evaluation.
    question: Do I need a license for production deployments?
  type: FAQPage
tags:
- reduce pdf size
- groupdocs viewer
- java pdf compression
- convert pptx to pdf
- jpg quality optimization
title: Java에서 PDF 크기 줄이는 방법 – JPG 품질 최적화
type: docs
url: /ko/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# PDF 크기 감소 Java – JPG 품질 최적화

Balancing file size and visual fidelity is a common challenge when working with PDFs. In this tutorial you’ll discover **PDF 크기 감소 Java** by adjusting the JPG image quality inside PDF documents using GroupDocs Viewer for Java. We’ll walk through the setup, code implementation, and practical tips so you can confidently compress PDF images without sacrificing readability.

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## 빠른 답변
- **“reduce PDF size Java”가 무엇을 의미하나요?** 이미지 품질을 낮추고, 압축을 적용하며, 리소스를 최적화하여 최종 PDF가 더 적은 저장 공간을 차지하고 로드 속도가 빨라짐을 의미합니다.  
- **JPG 품질을 제어하는 설정은 무엇인가요?** `PdfViewOptions.setJpgQuality(byte quality)`이며 값은 0 (최저)부터 100 (최고)까지 범위입니다.  
- **같은 흐름에서 PPTX를 PDF Java로 변환할 수도 있나요?** 예—`Viewer`를 `.pptx` 소스에 지정하면 동일한 옵션이 적용됩니다.  
- **웹 게시에 일반적인 품질 수준은 무엇인가요?** 약 50‑70 값이 대부분의 웹 시나리오에서 선명도와 크기의 좋은 균형을 제공합니다.  
- **이 기능에 라이선스가 필요합니까?** 평가용으로는 무료 체험이 가능하며, 실제 사용을 위해서는 영구적인 GroupDocs Viewer 라이선스가 필요합니다.

## reduce PDF size Java란?
Reducing PDF size Java은 Java 애플리케이션 내에서 PDF 파일을 압축된 리소스, 특히 래스터 이미지들을 압축하여 축소하는 과정을 의미합니다. JPG 품질을 낮추면 PDF 용량의 대부분을 직접 줄일 수 있으며, 일반적으로 텍스트 가독성을 유지하면서 30‑70 % 정도 크기가 감소합니다.

## GroupDocs Viewer로 JPG 품질을 조정하는 이유
GroupDocs Viewer를 사용해 JPG 품질을 조정하면 외부 이미지 처리 단계가 필요 없는 단일 패스 서버‑사이드 솔루션을 제공합니다. 이 라이브러리는 **50개 이상의 입력 형식**을 지원하며 **수백 페이지**의 PDF도 전체 파일을 메모리에 로드하지 않고 처리할 수 있어 변환 속도가 빨라지고 메모리 사용량이 감소합니다.

## 사전 요구 사항
- **GroupDocs.Viewer for Java** 버전 25.2 이상.  
- Maven 기반 Java 프로젝트이며 JDK 8 이상.  
- Java 및 PDF 처리에 대한 기본적인 이해.  

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

> **Pro tip:** 성능 향상 및 새로운 압축 옵션의 이점을 얻으려면 버전을 최신 상태로 유지하세요.

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

### 단계 2: 원하는 JPG 품질로 `PdfViewOptions` 구성
`PdfViewOptions`는 GroupDocs에 출력 PDF를 어떻게 렌더링할지 알려주는 구성 객체입니다.  
`setJpgQuality(byte quality)` 메서드는 결과 문서에 나타나는 모든 JPG 이미지의 압축 수준을 지정합니다.

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
- 값이 낮을수록 파일이 작아지지만 시각적 선명도가 감소할 수 있습니다.  
- 예제는 `source.pptx`를 사용하여 **convert PPTX to PDF Java**를 보여주면서 동시에 이미지를 압축합니다.

### 단계 3: 코드를 실행하고 결과 확인
`FeatureAdjustQualityOfJpgImages`는 구성된 JPG 품질로 변환을 실행하는 샘플 클래스입니다. `FeatureAdjustQualityOfJpgImages.run()`을 실행하세요. 생성된 `output.pdf`에는 지정한 품질 수준의 JPG 이미지가 포함되어 **PDF 이미지를 압축**하고 전체 파일 크기를 감소시킵니다.

## 일반적인 문제 및 해결 방법
- **잘못된 파일 경로:** 작업 디렉터리를 기준으로 소스 문서(`source.pptx`)가 존재하는지 확인하세요.  
- **권한 부족:** 출력 폴더가 쓰기 가능해야 하며, 그렇지 않으면 `RuntimeException`이 발생합니다.  
- **예상보다 큰 PDF:** `quality` 값이 목표 크기에 충분히 낮은지 확인하세요.

## 실용적인 적용 사례
1. **문서 보관:** 작은 PDF는 저장 비용을 절감하고 검색 속도를 향상시킵니다.  
2. **웹 게시:** 웹사이트에 PDF를 삽입하거나 링크할 때 페이지 로드 속도가 빨라집니다.  
3. **이메일 첨부:** 전송 전에 이미지 품질을 낮춰 일반적인 크기 제한을 충족합니다.

## 성능 고려 사항
- **배치 처리:** 대량 작업의 경우 메모리 사용량을 모니터링하면서 병렬 스레드로 문서를 처리합니다.  
- **최적 품질 설정:** 인쇄용 PDF는 높은 품질(80‑100)을 사용하고, 웹 미리보기는 보통 30‑50이면 충분합니다.

## 결론
이제 GroupDocs Viewer를 사용해 JPG 이미지 품질을 조정하여 **how to reduce PDF size Java**을(를) 수행하는 방법을 알게 되었습니다. 다양한 품질 수준을 실험하고 코드를 기존 파이프라인에 통합하여 더 빠르고 가벼운 PDF를 활용하세요.

### 다음 단계
- 다양한 품질 설정을 테스트하여 사용 사례에 맞는 최적점을 찾으세요.  
- 워터마크 또는 비밀번호 보호와 같은 추가 GroupDocs 기능을 살펴보세요.  

## 자주 묻는 질문

**Q: JPG 품질을 조정하면 파일 크기에 어떤 영향을 줍니까?**  
A: JPG 품질을 낮추면 각 이미지에 저장되는 데이터 양이 감소하여 PDF 크기를 30‑70 % 정도 줄이면서 텍스트는 선명하게 유지됩니다.

**Q: JPG 외의 다른 형식에 대한 이미지 품질을 조정할 수 있나요?**  
A: 이 설정은 JPG 이미지에만 적용되며, 다른 래스터 형식은 GroupDocs Viewer 내에서 자체 압축 옵션을 가집니다.

**Q: 웹 사용에 적합한 JPG 품질 설정은 무엇인가요?**  
A: 품질 값을 50 에서 70 사이로 설정하면 대부분의 웹 애플리케이션에 적합한 선명한 이미지와 적당한 파일 크기를 제공합니다.

**Q: 배치 워크플로에서 이 프로세스를 자동화할 수 있나요?**  
A: 예, 소스 파일이 있는 디렉터리를 순회하면서 동일한 `PdfViewOptions` 구성을 적용하고 병렬로 압축된 PDF를 생성할 수 있습니다.

**Q: 프로덕션 배포에 라이선스가 필요합니까?**  
A: 예, 프로덕션 사용을 위해서는 유효한 GroupDocs Viewer 라이선스가 필요합니다. 평가용으로는 무료 체험을 제공합니다.

**Q: 실제 품질 감소를 어떻게 확인할 수 있나요?**  
A: 변환 전후의 파일 크기를 비교하고 PDF를 열어 이미지 선명도를 시각적으로 검사하면, 크기 차이가 선택한 품질 수준을 반영함을 확인할 수 있습니다.

**Q: 개별 페이지마다 다른 품질 수준을 설정할 수 있나요?**  
A: 현재 GroupDocs Viewer는 변환당 일관된 JPG 품질 설정을 적용합니다. 페이지별 제어가 필요하면 전용 이미지 라이브러리를 사용한 후처리 단계가 필요합니다.

## 리소스
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**마지막 업데이트:** 2026-08-13  
**테스트 환경:** GroupDocs.Viewer 25.2 for Java  
**작성자:** GroupDocs

## 관련 튜토리얼

- [How to convert pdf to html and optimize image quality in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [limit jpg size java – Rendering with GroupDocs.Viewer](/viewer/java/rendering-basics/groupdocs-viewer-java-limit-jpg-size-rendering/)
- [Render PDF Layered Java – Efficient PDF Layered Rendering with GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)