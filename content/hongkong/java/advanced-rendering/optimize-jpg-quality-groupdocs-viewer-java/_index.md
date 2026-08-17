---
date: '2026-08-13'
description: 了解如何透過調整 JPG 品質並使用 GroupDocs Viewer 來減少 Java PDF 大小，同時支援將 PPTX 轉換為 PDF（Java）以及其他縮小檔案大小的技巧。
keywords:
- reduce pdf size java
- convert pptx to pdf java
- java reduce pdf file size
lastmod: '2026-08-13'
og_description: 透過使用 GroupDocs Viewer 調整 JPG 品質來減少 Java PDF 大小。本指南將示範如何壓縮圖片、將 PPTX
  轉換為 PDF（Java），以及在不影響可讀性的前提下獲得更小的 PDF。
og_image_alt: 'Guide: optimizing JPG quality to reduce PDF size in Java with GroupDocs
  Viewer'
og_title: 減少 Java PDF 大小 – 使用 GroupDocs Viewer 進行 JPG 品質優化
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
title: 如何在 Java 中減少 PDF 大小 – 優化 JPG 品質
type: docs
url: /zh-hant/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# 如何在 Java 中減少 PDF 大小 – 優化 JPG 品質

在處理 PDF 時，平衡檔案大小與視覺品質是一項常見挑戰。在本教學中，您將透過使用 GroupDocs Viewer for Java 調整 PDF 文件內 JPG 圖片品質，了解 **how to reduce PDF size Java**。我們將逐步說明設定、程式碼實作與實用技巧，讓您能自信地壓縮 PDF 圖片而不影響可讀性。

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## 快速解答
- **What does “reduce PDF size Java” mean?** 它表示降低影像品質、套用壓縮，並優化資源，使最終的 PDF 佔用更少的儲存空間且載入更快。  
- **Which setting controls JPG quality?** `PdfViewOptions.setJpgQuality(byte quality)`，其值範圍為 0（最低）至 100（最高）。  
- **Can I also convert PPTX to PDF Java in the same flow?** 可以——將 `Viewer` 指向 `.pptx` 檔案，即可套用相同的選項。  
- **What quality level is typical for web publishing?** 約 50‑70 的數值在大多數網路情境下提供清晰度與檔案大小的良好平衡。  
- **Do I need a license for this feature?** 免費試用可用於評估；正式環境則需永久的 GroupDocs Viewer 授權。

## 什麼是 reduce PDF size Java？
Reducing PDF size Java 指在 Java 應用程式中透過壓縮嵌入資源（尤其是點陣圖）來縮小 PDF 檔案的過程。降低 JPG 品質可直接減少 PDF 的容量，通常可達 30‑70 % 的大小縮減，同時保留可讀的文字。

## 為何使用 GroupDocs Viewer 調整 JPG 品質？
使用 GroupDocs Viewer 調整 JPG 品質可提供單次、伺服器端的解決方案，免除外部影像處理步驟。此函式庫支援 **50+ input formats**，且能處理 **hundreds of pages** 的 PDF 而無需將整個檔案載入記憶體，從而加快轉換速度並降低記憶體使用量。

## 前置條件
- **GroupDocs.Viewer for Java** 版本 25.2 或更新版本。  
- 基於 Maven 的 Java 專案，使用 JDK 8 或更高版本。  
- 具備 Java 與 PDF 處理的基本知識。  

## 設定 GroupDocs.Viewer for Java
在 `pom.xml` 中加入 GroupDocs 的儲存庫與相依性：

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

> **Pro tip:** 保持版本為最新，以獲得效能提升與新壓縮選項的好處。

## 實作指南

### 步驟 1：解析輸出目錄路徑
建立一個輔助類別，用於建立儲存 PDF 的輸出資料夾。

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

### 步驟 2：使用欲設定的 JPG 品質配置 `PdfViewOptions`
`PdfViewOptions` 是告訴 GroupDocs 如何渲染輸出 PDF 的設定物件。  
`setJpgQuality(byte quality)` 方法指定結果文件中所有 JPG 圖片的壓縮等級。

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
- 較低的數值會產生較小的檔案，但可能降低視覺清晰度。  
- 此範例使用 `source.pptx` 來示範 **convert PPTX to PDF Java**，同時壓縮圖像。

### 步驟 3：執行程式碼並驗證結果
`FeatureAdjustQualityOfJpgImages` 是一個示範類別，使用已設定的 JPG 品質執行轉換。執行 `FeatureAdjustQualityOfJpgImages.run()`。產生的 `output.pdf` 會包含您指定品質等級的 JPG 圖片，從而有效 **compressing PDF images** 並降低整體檔案大小。

## 常見問題與故障排除
- **Incorrect file path:** 確認來源文件 (`source.pptx`) 在工作目錄相對路徑下存在。  
- **Insufficient permissions:** 輸出資料夾必須可寫入，否則會拋出 `RuntimeException`。  
- **Unexpectedly large PDFs:** 確認 `quality` 值足夠低以符合您的大小目標。

## 實務應用
1. **Document archiving:** 較小的 PDF 可節省儲存成本並提升檢索速度。  
2. **Web publishing:** 當 PDF 嵌入或連結於網站時，可加快頁面載入速度。  
3. **Email attachments:** 在寄送前降低影像品質，以符合常見的大小限制。

## 效能考量
- **Batch processing:** 對於大量文件，可在平行執行緒中處理，同時監控記憶體使用情況。  
- **Optimal quality settings:** 印刷用 PDF 建議使用較高品質 (80‑100)；網頁預覽則常用 30‑50 即可。

## 結論
現在您已了解如何透過 GroupDocs Viewer 調整 JPG 圖片品質 **how to reduce PDF size Java**。嘗試不同的品質等級，將程式碼整合至現有流程，享受更快速、更輕量的 PDF。

### 後續步驟
- 測試不同的品質設定，以找出最適合您使用情境的平衡點。  
- 探索其他 GroupDocs 功能，如浮水印或密碼保護。  

## 常見問答

**Q: How does adjusting JPG quality affect file size?**  
A: 降低 JPG 品質會減少每張圖片儲存的資料量，從而可將 PDF 大小縮減 30‑70 %，同時保持文字清晰。

**Q: Can I adjust image quality for formats other than JPG?**  
A: 此設定僅針對 JPG 圖片；其他點陣圖格式在 GroupDocs Viewer 中有各自的壓縮選項。

**Q: What is the ideal JPG quality setting for web use?**  
A: 介於 50 至 70 的品質值通常能提供清晰的圖片與適中的檔案大小，適合大多數網路應用。

**Q: Is it possible to automate this process in a batch workflow?**  
A: 可以，您可以遍歷來源檔案目錄，套用相同的 `PdfViewOptions` 設定，並平行產生壓縮的 PDF。

**Q: Do I need a license for production deployments?**  
A: 是的，正式環境需要有效的 GroupDocs Viewer 授權。可使用免費試用版進行評估。

**Q: How can I verify the actual quality reduction?**  
A: 比較轉換前後的檔案大小，並開啟 PDF 目視檢查圖片清晰度；大小差異應與所選品質等級相符。

**Q: Can I set different quality levels for individual pages?**  
A: 目前 GroupDocs Viewer 於一次轉換中僅支援統一的 JPG 品質設定。若需針對單頁調整，需在後處理階段使用專門的影像函式庫。

## 資源
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**最後更新:** 2026-08-13  
**測試環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs

## 相關教學

- [如何在 Java 中使用 GroupDocs.Viewer 將 PDF 轉換為 HTML 並優化圖像品質](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [限制 JPG 大小（Java） – 使用 GroupDocs.Viewer 進行渲染](/viewer/java/rendering-basics/groupdocs-viewer-java-limit-jpg-size-rendering/)
- [在 Java 中渲染分層 PDF – 使用 GroupDocs.Viewer 高效分層渲染](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)