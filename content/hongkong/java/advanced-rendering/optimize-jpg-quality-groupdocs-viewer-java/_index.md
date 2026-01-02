---
date: '2026-01-02'
description: 了解如何透過調整 JPG 品質，使用 GroupDocs.Viewer 在 Java 中減少 PDF 檔案大小，這是一種簡單的 PDF 圖像壓縮方法，能在檔案大小與視覺品質之間取得平衡。
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: 減少 PDF 大小 Java – 使用 GroupDocs 優化 JPG 品質
type: docs
url: /zh-hant/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# 減少 PDF 大小 Java – 使用 GroupDocs 優化 JPG 品質

Balancing file size and visual fidelity is a common challenge when working with PDFs. In this tutorial you’ll discover how to **reduce PDF size Java** by adjusting the JPG image quality inside PDF documents using GroupDocs.Viewer for Java. We'll walk through the setup, code implementation, and practical tips so you can confidently compress PDF images without sacrificing readability.

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## 快速解答
- **What does “reduce PDF size Java” mean?** 調整圖像品質、壓縮與資源處理，以在 Java 應用程式中產生較小的 PDF 檔案。  
- **Which setting controls JPG quality?** `PdfViewOptions.setJpgQuality(byte quality)`，其值範圍為 0（最低）至 100（最高）。  
- **Can I also convert PPTX to PDF in the same flow?** 可以——只需將 `Viewer` 指向 `.pptx` 檔案，即可套用相同的選項。  
- **What quality level is typical for web publishing?** 約 **50‑70** 的數值在大多數網路情境下提供良好平衡。  
- **Do I need a license for this feature?** 免費試用可用於評估；正式環境需購買永久授權。

## 什麼是 “reduce PDF size Java”？
在 Java 中縮減 PDF 大小是指優化 PDF 內的資源——尤其是圖像——使最終檔案佔用更少的儲存空間並加快載入速度。透過降低 JPG 品質，您實際上 **compress PDF images**，而圖像通常佔文件大小的主要部分。

## 為何使用 GroupDocs Viewer 調整 JPG 品質？
- **Significant size reduction**：根據原始解析度，降低圖像品質可將 PDF 縮小 30‑70 %。  
- **Single‑pass conversion**：無需額外的圖像處理步驟；GroupDocs 於 PDF 產生過程中直接處理。  
- **Flexibility**：可依專案需求微調 `byte` 品質值（例如高品質列印與輕量化網頁預覽）。

## 前置條件
- **GroupDocs.Viewer for Java** 版本 25.2 或更新版本。  
- 基於 Maven 的 Java 專案，使用 JDK 8 或以上。  
- 具備 Java 與 PDF 處理的基本知識。

## 設定 GroupDocs.Viewer for Java
在 `pom.xml` 中加入 GroupDocs 儲存庫與相依性：

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
建立輔助類別，用於建立儲存 PDF 的輸出資料夾。

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

### 步驟 2：使用所需的 JPG 品質設定 `PdfViewOptions`
在渲染文件前設定 JPG 品質等級（0‑100）。

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
- `setJpgQuality(byte quality)` 告訴 GroupDocs 對 JPG 圖像套用多少壓縮。較低的值會產生較小的檔案，但可能降低視覺銳利度。  
- 範例使用 `source.pptx` 來示範 **convert pptx to pdf**，同時壓縮圖像。

### 步驟 3：執行程式碼並驗證結果
執行 `FeatureAdjustQualityOfJpgImages.run()`。產生的 `output.pdf` 會包含您指定品質等級的 JPG 圖像，實際上 **compressing PDF images**，並降低整體檔案大小。

## 常見問題與除錯
- **Incorrect file path:** 確認來源文件 (`source.pptx`) 相對於工作目錄存在。  
- **Insufficient permissions:** 輸出資料夾必須具備寫入權限；否則會拋出 `RuntimeException`。  
- **Unexpected large PDFs:** 確認 `quality` 值足夠低以符合您的大小目標。

## 實務應用
1. **Document Archiving:** 較小的 PDF 可節省儲存成本並提升檢索速度。  
2. **Web Publishing:** 當 PDF 嵌入或連結於網站時，可加快頁面載入速度。  
3. **Email Attachments:** 透過降低圖像品質以符合附件大小限制。

## 效能考量
- **Batch Processing:** 處理大量文件時，可使用平行執行緒並監控記憶體使用情況。  
- **Optimal Quality Settings:** 針對列印就緒的 PDF 使用較高品質 (80‑100)；網頁預覽則常以 30‑50 為佳。

## 結論
現在您已了解如何透過 GroupDocs.Viewer 調整 JPG 圖像品質來 **reduce PDF size Java**。嘗試不同的品質等級，將程式碼整合至現有流程，享受更快速、更輕量的 PDF。

### 後續步驟
- 測試不同的品質設定，以找出最適合您使用情境的平衡點。  
- 探索其他 GroupDocs 功能，如浮水印或密碼保護。

## 常見問答

1. **How does adjusting JPG quality affect file size?**  
   降低品質會減少檔案大小，讓文件更易於分享或儲存。

2. **Can I adjust image quality for formats other than JPG?**  
   此功能專門針對 PDF 內的 JPG 圖像；然而，GroupDocs.Viewer 亦提供其他格式的選項。

3. **What is the ideal JPG quality setting for web use?**  
   約 50‑70 的平衡設定通常在保持清晰度的同時，提供適合網路應用的檔案大小。

4. **Is it possible to automate this process in a batch workflow?**  
   可以，您可將此功能整合至自動化系統，以有效處理多份文件。

5. **What should I do if the output PDF is not generated as expected?**  
   檢查輸入文件路徑，並確保所有相依性正確設定。

## 常見問答

**Q:** *Can I use this approach to convert other formats like DOCX to PDF while reducing size?*  
**A:** 絕對可以。相同的 `PdfViewOptions.setJpgQuality` 設定適用於任何會在 PDF 中產生 JPG 圖像的來源格式。

**Q:** *Does reducing JPG quality impact text rendering?*  
**A:** 不會。文字是向量式的，保持清晰；僅影響點陣圖圖像。

**Q:** *Is there a way to set different quality levels for different pages?*  
**A:** GroupDocs 目前在每次轉換時使用統一的品質設定。若需每頁不同的控制，需使用專門的圖像處理函式庫在 PDF 產生後進行後處理。

**Q:** *Do I need a license for production deployments?*  
**A:** 是的，正式環境必須擁有有效的 GroupDocs.Viewer 授權。可使用免費試用版進行評估。

**Q:** *How can I verify the actual quality reduction?*  
**A:** 比較轉換前後的檔案大小，並開啟 PDF 目視檢查圖像清晰度。

---

**Last Updated:** 2026-01-02  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**資源**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)