---
date: '2026-01-02'
description: GroupDocs.Viewer를 사용하여 JPG 품질을 조정함으로써 Java에서 PDF 크기를 줄이는 방법을 배우세요. 이는
  PDF 이미지를 압축하고 파일 크기와 시각적 품질을 균형 있게 맞추는 간단한 방법입니다.
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: PDF 크기 축소 Java – GroupDocs로 JPG 품질 최적화
type: docs
url: /ko/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# PDF 크기 감소 Java – GroupDocs로 JPG 품질 최적화

Balancing file size and visual fidelity is a common challenge when working with PDFs. In this tutorial you’ll discover how to **reduce PDF size Java** by adjusting the JPG image quality inside PDF documents using GroupDocs.Viewer for Java. We'll walk through the setup, code implementation, and practical tips so you can confidently compress PDF images without sacrificing readability.

![GroupDocs.Viewer for Java를 사용한 PDF에서 JPG 품질 최적화](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## Quick Answers
- **“reduce PDF size Java”는 무엇을 의미하나요?** 이미지 품질, 압축 및 리소스 처리를 조정하여 Java 애플리케이션에서 더 작은 PDF 파일을 만드는 것을 의미합니다.  
- **JPG 품질을 제어하는 설정은 무엇인가요?** `PdfViewOptions.setJpgQuality(byte quality)`이며 값은 0(최저)에서 100(최고)까지 범위합니다.  
- **같은 흐름에서 PPTX를 PDF로 변환할 수도 있나요?** 예—`.pptx` 소스를 `Viewer`에 지정하면 동일한 옵션이 적용됩니다.  
- **웹 게시에 일반적인 품질 수준은 얼마인가요?** 대부분의 웹 시나리오에서는 **50‑70** 정도가 좋은 균형을 제공합니다.  
- **이 기능에 라이선스가 필요합니까?** 평가용 무료 체험이 가능하지만, 프로덕션 사용에는 영구 라이선스가 필요합니다.

## “reduce PDF size Java”란?
Reducing PDF size in Java involves optimizing the resources inside a PDF—most notably images—so the final file occupies less storage and loads faster. By lowering JPG quality, you effectively **compress PDF images**, which often constitute the bulk of a document’s size.

## 왜 GroupDocs Viewer로 JPG 품질을 조정하나요?
- **크기 감소 효과가 큽니다**: 이미지 품질을 낮추면 원본 해상도에 따라 PDF 크기가 30‑70 %까지 감소할 수 있습니다.  
- **단일 패스 변환**: 별도의 이미지 처리 단계가 필요 없으며, GroupDocs가 PDF 생성 중에 이를 처리합니다.  
- **유연성**: 프로젝트 요구사항에 따라 `byte` 품질 값을 미세 조정할 수 있습니다(예: 고품질 인쇄 vs. 가벼운 웹 미리보기).  

## Prerequisites
- **GroupDocs.Viewer for Java** 버전 25.2 이상.  
- Maven 기반 Java 프로젝트와 JDK 8 이상.  
- Java 및 PDF 처리에 대한 기본 지식.  

## Setting Up GroupDocs.Viewer for Java
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

> **전문가 팁:** 최신 버전을 유지하면 성능 향상 및 새로운 압축 옵션을 활용할 수 있습니다.

## Implementation Guide

### Step 1: Resolve the Output Directory Path
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

### Step 2: Configure `PdfViewOptions` with Desired JPG Quality
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

**Explanation:**  
- `setJpgQuality(byte quality)` tells GroupDocs how much compression to apply to JPG images. Lower values produce smaller files but may reduce visual sharpness.  
- The example uses `source.pptx` to demonstrate **convert pptx to pdf** while simultaneously compressing images.

### Step 3: Run the Code and Verify the Result
Execute `FeatureAdjustQualityOfJpgImages.run()`. The generated `output.pdf` will contain JPG images at the quality level you specified, effectively **compressing PDF images** and reducing overall file size.

## Common Issues & Troubleshooting
- **Incorrect file path:** Ensure the source document (`source.pptx`) exists relative to the working directory.  
- **Insufficient permissions:** The output folder must be writable; otherwise, `RuntimeException` will be thrown.  
- **Unexpected large PDFs:** Verify that the `quality` value is low enough for your size targets.  

## Practical Applications
1. **Document Archiving:** Smaller PDFs save storage costs and improve retrieval speeds.  
2. **Web Publishing:** Faster page loads when PDFs are embedded or linked on websites.  
3. **Email Attachments:** Meet size limits by lowering image quality before sending.  

## Performance Considerations
- **Batch Processing:** For large numbers of documents, process them in parallel threads while monitoring memory usage.  
- **Optimal Quality Settings:** Use higher quality (80‑100) for print‑ready PDFs; for web previews, 30‑50 often suffices.  

## Conclusion
You now know how to **reduce PDF size Java** by adjusting JPG image quality with GroupDocs.Viewer. Experiment with different quality levels, integrate the code into your existing pipelines, and enjoy faster, lighter PDFs.

### Next Steps
- Test various quality settings to find the sweet spot for your use case.  
- Explore additional GroupDocs features like watermarking or password protection.  

## FAQ Section

1. **How does adjusting JPG quality affect file size?**  
   Lowering the quality reduces file size, making it easier to share or store documents.

2. **Can I adjust image quality for formats other than JPG?**  
   This feature specifically targets JPG images within PDFs; however, GroupDocs.Viewer offers other options for different formats.

3. **What is the ideal JPG quality setting for web use?**  
   A balance around 50‑70 often provides good clarity with reduced file size suitable for web applications.

4. **Is it possible to automate this process in a batch workflow?**  
   Yes, you can integrate this feature into automated systems to handle multiple documents efficiently.

5. **What should I do if the output PDF is not generated as expected?**  
   Check your input document path and ensure all dependencies are correctly configured.

## Frequently Asked Questions

**Q:** *Can I use this approach to convert other formats like DOCX to PDF while reducing size?*  
**A:** Absolutely. The same `PdfViewOptions.setJpgQuality` setting works for any source format that produces JPG images in the PDF.

**Q:** *Does reducing JPG quality impact text rendering?*  
**A:** No. Text is vector‑based and remains crisp; only raster images are affected.

**Q:** *Is there a way to set different quality levels for different pages?*  
**A:** GroupDocs currently applies a uniform quality setting per conversion. For per‑page control, you’d need to post‑process the PDF with a dedicated image handling library.

**Q:** *Do I need a license for production deployments?*  
**A:** Yes, a valid GroupDocs.Viewer license is required for production use. A free trial is available for evaluation.

**Q:** *How can I verify the actual quality reduction?*  
**A:** Compare the file sizes before and after conversion, and open the PDF to visually inspect image clarity.

---

**Last Updated:** 2026-01-02  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**  
- [문서](https://docs.groupdocs.com/viewer/java/)  
- [API 레퍼런스](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer for Java 다운로드](https://releases.groupdocs.com/viewer/java/)  
- [라이선스 구매](https://purchase.groupdocs.com/buy)  
- [무료 체험 버전](https://releases.groupdocs.com/viewer/java/)  
- [임시 라이선스 정보](https://purchase.groupdocs.com/temporary-license/)  
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)