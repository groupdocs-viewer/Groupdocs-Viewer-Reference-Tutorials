---
date: '2026-03-29'
description: 學習如何在 Java 中使用 GroupDocs Viewer 將頁面旋轉 90 度，包括設定、程式碼與效能技巧。
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: 使用 GroupDocs Viewer for Java 將頁面旋轉 90 度
type: docs
url: /zh-hant/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs Viewer for Java 將頁面旋轉 90 度

當您需要在文件中 **將頁面旋轉 90 度**——無論是 PDF、Word 檔案或試算表——以程式方式執行可節省時間並避免人工錯誤。在本進階指南中，我們將逐步說明如何使用 **GroupDocs Viewer for Java** 旋轉任何支援文件的第一頁。完成後，您將擁有可直接嵌入自己專案的可重用程式碼片段。  
我們亦會討論在 Java 中旋轉頁面的重要性、此技術的常見應用情境，以及如何保持操作輕量化。

![使用 GroupDocs.Viewer for Java 旋轉文件的第一頁](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## 快速解答
- **「rotate page 90 degrees」是什麼意思？** 它會將選取的頁面順時針旋轉四分之一圈。  
- **哪個函式庫負責旋轉？** GroupDocs Viewer for Java 提供 `rotatePage` 方法。  
- **我可以使用 Java 旋轉 PDF 頁面嗎？** 可以——使用相同的 `rotatePage` 呼叫；它支援 PDF、DOCX、XLSX 等格式。  
- **我需要授權嗎？** 免費試用可用於開發；正式環境需購買授權。  
- **此操作會佔用大量記憶體嗎？** 若及時關閉 `Viewer` 實例則不會；請參考以下效能提示。

## 「rotate page 90 degrees」是什麼？
將頁面旋轉 90 度會將頁面從直向（portrait）重新定位為橫向（landscape），或反之，且不會更改其底層內容。此功能特別適用於簡報、列印僅橫向的圖形，或校正掃描時因側向拍攝而產生的文件。

## 為何使用 GroupDocs Viewer for Java 以程式方式旋轉頁面？
GroupDocs Viewer 抽象化了處理數十種檔案格式的複雜性。它允許您在保持原始檔案不變的情況下，對頁面層級執行轉換（例如旋轉）。API 設計流暢、執行緒安全，且可在任何 Java 8 以上的執行環境運行，成為企業級自動化的可靠選擇。

## 前置條件

- **GroupDocs.Viewer for Java**（最新版本）
- **JDK 8** 或更新版本
- **Maven**（或 Gradle）用於相依性管理
- 如 IntelliJ IDEA 或 Eclipse 等 IDE
- 具備基本的 Java I/O 知識

## 設定 GroupDocs.Viewer for Java

將 GroupDocs 儲存庫與相依性加入您的 `pom.xml`。此程式碼片段與原始教學相同，未作變更：

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

### 取得授權
- **Free trial** – 從 GroupDocs 網站下載。  
- **Temporary license** – 如需延長評估期間可申請臨時授權。  
- **Full license** – 購買正式授權以供生產環境使用。

### 基本 Viewer 初始化
以下程式碼示範建立 `Viewer` 實例的最小寫法。請保持與示範完全相同：

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## 如何使用 GroupDocs Viewer 在 Java 中旋轉 PDF 頁面
雖然 API 支援多種格式，PDF 是最常見的頁面旋轉使用情境。使用相同的 `rotatePage` 方法，只需將 Viewer 指向 PDF 檔案並指定頁碼即可。

## 步驟說明：將第一頁旋轉 90 度

### 1. 匯入所需套件
以下匯入可讓您使用 PDF 渲染選項與旋轉列舉型別。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 定義輸出位置並建立 Viewer
請將佔位路徑替換為實際的目錄路徑。

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. 設定 PDF 檢視選項並套用旋轉
`rotatePage` 方法接受頁碼（從 1 開始）以及 `Rotation` 列舉值。

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. 產生文件
最後，呼叫 `view` 產生旋轉後的 PDF。

```java
viewer.view(viewOptions);
```

#### 工作原理
- **PdfViewOptions** 告訴 Viewer 輸出 PDF 檔案。  
- **rotatePage(int, Rotation)** 僅旋轉您指定的頁面，其他頁面保持不變。  
- 此方法支援 `ON_90_DEGREE`、`ON_180_DEGREE` 與 `ON_270_DEGREE`。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| **FileNotFoundException** | 路徑不正確或資料夾遺失 | 驗證 `YOUR_OUTPUT_DIRECTORY` 與 `YOUR_DOCUMENT_DIRECTORY` 是否存在且可讀取。 |
| **Unsupported file format** | 嘗試旋轉 Viewer 不支援的格式 | 檢查 [GroupDocs Viewer supported formats] 頁面。 |
| **No rotation visible** | 使用了錯誤的頁碼（0 為基礎） | 記得 `rotatePage` 使用 **1‑based** 索引。 |
| **Out‑of‑memory errors on large docs** | 在單一執行緒中渲染大量大型檔案 | 將文件逐一處理，或使用限制併發數的執行緒池。 |

## 實務應用

1. **Presentation adjustments** – 即時將直向投影片轉為橫向。  
2. **Bulk document correction** – 自動校正側向掃描的 PDF。  
3. **Print‑ready output** – 確保橫向圖形在直向紙張上正確列印。

## 效能建議

- **Close resources promptly** – `try‑with‑resources` 區塊會自動釋放 `Viewer`。  
- **Batch processing** – 處理大量檔案時，於每個執行緒重複使用單一 `Viewer` 實例以降低開銷。  
- **Monitor memory** – 若文件超過 100 MB，建議將輸出串流至磁碟，而非保留於記憶體中。

## 常見問答

**Q: 我可以一次旋轉多個頁面嗎？**  
A: 可以——對每個需要旋轉的頁碼呼叫 `rotatePage()`。

**Q: 渲染後有辦法撤銷旋轉嗎？**  
A: 無法直接撤銷。必須在不使用旋轉選項的情況下重新渲染文件。

**Q: 哪些檔案格式在 GroupDocs Viewer 中支援頁面旋轉？**  
A: DOCX、PDF、PPTX、XLSX 以及官方文件中列出的其他多種格式。

**Q: 如何自動在一批文件中旋轉頁面？**  
A: 將程式碼包在迴圈中，遍歷檔案路徑集合，對每個檔案套用相同的 `rotatePage` 邏輯。

**Q: 處理旋轉過程中的錯誤最佳做法是什麼？**  
A: 將 Viewer 的使用包在 `try‑catch` 區塊中，記錄例外，並可選擇繼續處理下一個檔案。

## 資源

- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-03-29  
**測試環境：** GroupDocs Viewer 25.2 for Java  
**作者：** GroupDocs