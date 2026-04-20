---
date: '2026-03-05'
description: 學習如何在 Java 中透過調整 JPG 品質使用 GroupDocs.Viewer 壓縮 PDF——一種簡單的 Java PDF 壓縮方法，兼顧檔案大小與視覺保真度。
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: 如何在 Java 中壓縮 PDF – 優化 JPG 品質
type: docs
url: /zh-hant/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# 如何在 Java 中壓縮 PDF – 優化 JPG 品質

在處理 PDF 時，平衡檔案大小與視覺清晰度是一項常見挑戰。在本教學中，您將透過使用 GroupDocs.Viewer for Java 調整 PDF 文件內的 JPG 圖像品質，了解 **如何壓縮 PDF**。我們將逐步說明設定、程式碼實作與實用技巧，讓您能在不犧牲可讀性的前提下，自信地壓縮 PDF 圖像。

![使用 GroupDocs.Viewer for Java 優化 PDF 中的 JPG 品質](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## 快速解答
- **「reduce PDF size Java」是什麼意思？** 調整圖像品質、壓縮與資源處理，以在 Java 應用程式中產生較小的 PDF 檔案。  
- **哪個設定控制 JPG 品質？** `PdfViewOptions.setJpgQuality(byte quality)` 其中值範圍為 0（最低）至 100（最高）。  
- **我可以在同一流程中同時將 PPTX 轉換為 PDF 嗎？** 可以——只需將 `Viewer` 指向 `.pptx` 檔案，即可套用相同的選項。  
- **網路發佈時常用的品質等級是多少？** 大約 **50‑70** 的數值在大多數網路情境下提供良好的平衡。  
- **此功能需要授權嗎？** 免費試用版可用於評估；正式環境需購買永久授權。

## 如何在 Java 中壓縮 PDF – 概觀
在 Java 中縮減 PDF 大小的做法是最佳化 PDF 內的資源——尤其是圖像——讓最終檔案佔用更少的儲存空間且載入更快。透過降低 JPG 品質，即可有效 **壓縮 PDF 圖像**，而圖像往往是文件大小的主要來源。

## 什麼是「reduce PDF size Java」？
在 Java 中縮減 PDF 大小的做法是最佳化 PDF 內的資源——尤其是圖像——讓最終檔案佔用更少的儲存空間且載入更快。透過降低 JPG 品質，即可有效 **壓縮 PDF 圖像**，而圖像往往是文件大小的主要來源。

## 為何使用 GroupDocs Viewer 調整 JPG 品質？
- **顯著的大小縮減**：降低圖像品質可依原始解析度不同，使 PDF 縮小 30‑70 %。  
- **單次轉換**：不需額外的圖像處理步驟；GroupDocs 會在 PDF 產生過程中直接處理。  
- **彈性調整**：可依專案需求微調 `byte` 品質值（例如高品質列印 vs 輕量化網頁預覽）。

## 前置條件
- **GroupDocs.Viewer for Java** 版本 25.2 或更新。  
- 使用 Maven 的 Java 專案，JDK 8 以上。  
- 具備基本的 Java 與 PDF 操作知識。

## 設定 GroupDocs.Viewer for Java
將 GroupDocs 套件庫與相依性加入 `pom.xml`：

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

> **專業提示：** 請保持版本為最新，以獲得效能提升與新壓縮選項。

## 實作指南

### 步驟 1：解析輸出目錄路徑
建立輔助類別，用於產生儲存 PDF 的輸出資料夾。

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

**說明：**  
- `setJpgQuality(byte quality)` 告訴 GroupDocs 對 JPG 圖像套用多少壓縮。較低的數值會產生較小的檔案，但可能降低視覺銳利度。  
- 此範例使用 `source.pptx` 來示範 **將 pptx 轉換為 pdf**，同時壓縮圖像。

### 步驟 3：執行程式碼並驗證結果
執行 `FeatureAdjustQualityOfJpgImages.run()`。產生的 `output.pdf` 內的 JPG 圖像會以您指定的品質等級呈現，從而 **壓縮 PDF 圖像** 並減少整體檔案大小。

## 常見問題與疑難排解
- **檔案路徑錯誤：** 確認來源文件 (`source.pptx`) 相對於工作目錄的路徑正確。  
- **權限不足：** 輸出資料夾必須可寫入，否則會拋出 `RuntimeException`。  
- **PDF 異常大：** 請確認 `quality` 數值足夠低以符合您的大小目標。

## 實務應用
1. **文件歸檔：** 較小的 PDF 可節省儲存成本並提升檢索速度。  
2. **網路發佈：** PDF 嵌入或連結於網站時，可加快頁面載入。  
3. **電子郵件附件：** 透過降低圖像品質符合附件大小限制後再傳送。

## 效能考量
- **批次處理：** 大量文件時，可使用平行執行緒處理，同時監控記憶體使用量。  
- **最佳品質設定：** 列印用 PDF 建議使用較高品質 (80‑100)；網頁預覽則常用 30‑50 即可。

## 結論
現在您已了解 **如何透過調整 JPG 圖像品質**，使用 GroupDocs.Viewer 來壓縮 PDF。可自行嘗試不同的品質等級，將程式碼整合至現有工作流程，享受更快、更輕的 PDF。

### 後續步驟
- 測試各種品質設定，找出最適合您使用情境的平衡點。  
- 探索 GroupDocs 其他功能，如浮水印或密碼保護。

## 常見問答

1. **調整 JPG 品質如何影響檔案大小？**  
   降低品質會減少檔案大小，讓文件更易於分享或儲存。

2. **我可以調整除 JPG 之外的其他格式圖像品質嗎？**  
   此功能專門針對 PDF 內的 JPG 圖像；不過 GroupDocs.Viewer 亦提供其他格式的相關選項。

3. **網路使用的理想 JPG 品質設定是多少？**  
   約 50‑70 的平衡點通常能在保持良好清晰度的同時，降低檔案大小，適合網路應用。

4. **能否在批次工作流程中自動化此過程？**  
   可以，您可將此功能整合至自動化系統，以有效處理多份文件。

5. **若輸出 PDF 未如預期產生，該怎麼辦？**  
   請檢查輸入文件路徑，並確保所有相依性已正確配置。

## 常見問題

**Q:** *我可以使用此方法將其他格式（如 DOCX）轉換為 PDF 同時減少大小嗎？*  
**A:** 當然可以。相同的 `PdfViewOptions.setJpgQuality` 設定適用於任何會在 PDF 中產生 JPG 圖像的來源格式。

**Q:** *降低 JPG 品質會影響文字渲染嗎？*  
**A:** 不會。文字是向量式的，仍保持清晰；僅影響點陣圖。

**Q:** *能否為不同頁面設定不同的品質等級？*  
**A:** GroupDocs 目前在一次轉換中僅支援統一的品質設定。若需逐頁控制，需使用專門的圖像處理函式庫於 PDF 產生後進行後處理。

**Q:** *生產環境需要授權嗎？*  
**A:** 需要。正式使用必須擁有有效的 GroupDocs.Viewer 授權。可先使用免費試用版進行評估。

**Q:** *如何驗證實際的品質降低程度？*  
**A:** 比較轉換前後的檔案大小，並開啟 PDF 目視檢查圖像清晰度。

---

**資源**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**最後更新：** 2026-03-05  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs