---
date: '2026-09-30'
description: 了解如何在 Java 中使用 GroupDocs Viewer 將頁面旋轉 90 度，包括設定、程式碼與效能技巧。
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: 在 Java 中使用 GroupDocs Viewer 將頁面旋轉 90 度。一步一步的指南、效能技巧以及開發人員的實際案例。
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: 使用 GroupDocs Viewer for Java 將頁面旋轉 90 度
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: 使用 GroupDocs Viewer for Java 將頁面旋轉 90 度
type: docs
url: /zh-hant/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# 將頁面旋轉 90 度（使用 GroupDocs Viewer for Java）

如果您需要在文件中**將頁面旋轉 90 度**——無論是 PDF、Word 檔案或試算表——以 Java 程式方式執行可節省時間、避免人工錯誤，並且能將此操作嵌入自動化流程中。在本進階指南中，您將學習如何使用**GroupDocs Viewer for Java**將任何支援的文件的第一頁旋轉，了解此功能在實務專案中的重要性，以及如何保持流程輕量且記憶體效能高。

![使用 GroupDocs.Viewer for Java 旋轉文件的第一頁](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## 快速答覆
- **「rotate page 90 degrees」是什麼意思？** 它會將選取的頁面順時針旋轉四分之一圈。  
- **哪個函式庫負責旋轉？** GroupDocs Viewer for Java 提供 `rotatePage` 方法。  
- **我可以使用 Java 旋轉 PDF 頁面嗎？** 可以——使用相同的 `rotatePage` 呼叫；它支援 PDF、DOCX、XLSX 等格式。  
- **我需要授權嗎？** 免費試用可用於開發；正式環境需購買授權。  
- **此操作會佔用大量記憶體嗎？** 若及時關閉 `Viewer` 實例則不會；請參考以下效能提示。

## 「rotate page 90 degrees」是什麼？

將頁面旋轉 90 度會將頁面從直向重新定位為橫向（或相反），而不會更改其底層內容。這在簡報、列印僅橫向的圖形，或校正掃描時側向拍攝的文件時非常實用。旋轉於渲染時套用，原始檔案保持不變。

## 為何使用 GroupDocs Viewer for Java 以程式方式旋轉頁面？

GroupDocs Viewer 支援 **50 多種輸入與輸出格式**——包括 PDF、DOCX、PPTX、XLSX 以及多種影像類型——讓您無需外部轉換器即可渲染任何文件。API 設計流暢、執行緒安全，且可在任何 Java 8 以上的執行環境上運行，是必須一致處理數十種檔案類型的企業級自動化的可靠選擇。

## 前置條件

- GroupDocs Viewer for Java（最新版本）
- JDK 8 或更新版本
- Maven（或 Gradle）用於相依管理
- IntelliJ IDEA 或 Eclipse 等 IDE
- 基本的 Java I/O 知識

## 設定 GroupDocs.Viewer for Java

將 GroupDocs 儲存庫與相依加入您的 `pom.xml`。此程式碼片段與原始教學相同：

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
- **Temporary license** – 若需延長評估期間可申請。  
- **Full license** – 購買以供正式部署使用。

### 基本 Viewer 初始化
`Viewer` 類別是載入文件並提供渲染與轉換方法的入口。請保持程式碼與示範完全相同：

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## 如何使用 GroupDocs Viewer 在 Java 中旋轉 PDF 頁面

使用 `Viewer` 載入目標檔案，指定頁碼，然後呼叫 `rotatePage`。此方法適用於 PDF、DOCX、PPTX、XLSX 以及庫支援的其他格式。旋轉後，您可以將文件渲染為新的 PDF，或直接串流至客戶端，確保原始檔案保持不變。

## 步驟說明：將第一頁旋轉 90 度

### 1. 匯入所需套件
`PdfViewOptions` 告訴 Viewer 輸出 PDF 檔案，而 `Rotation` 列舉則定義旋轉角度。這兩個類別皆屬於 `com.groupdocs.viewer.options` 套件。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 定義輸出位置並建立 Viewer
將佔位路徑替換為實際目錄。`Viewer` 建構子接受指向來源文件的 `File` 物件。

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
`rotatePage(int, Rotation)` 方法接受 **1 基礎**（即從 1 開始計算）的頁碼與 `Rotation` 列舉值。在此範例中，我們使用 `Rotation.ON_90_DEGREE` 使第一頁順時針旋轉。

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. 渲染文件
呼叫 `view` 並傳入設定好的選項，即可將旋轉後的 PDF 寫入輸出資料夾。

```java
viewer.view(viewOptions);
```

#### 工作原理
- **PdfViewOptions** 指示 Viewer 產生 PDF 輸出檔案。  
- **rotatePage(int, Rotation)** 只旋轉指定的頁面，其他頁面保持不變。  
- 此方法支援三個旋轉常數：`ON_90_DEGREE`、`ON_180_DEGREE` 與 `ON_270_DEGREE`。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| **FileNotFoundException** | 路徑不正確或資料夾遺失 | 請確認 `YOUR_OUTPUT_DIRECTORY` 與 `YOUR_DOCUMENT_DIRECTORY` 存在且可讀取。 |
| **Unsupported file format** | 嘗試旋轉 Viewer 不支援的格式 | 請檢查 [GroupDocs Viewer supported formats] 頁面。 |
| **No rotation visible** | 使用了錯誤的頁碼（0 基礎） | 請記得 `rotatePage` 使用 **1 基礎** 索引。 |
| **Out‑of‑memory errors on large docs** | 在單一執行緒中渲染大量大型檔案 | 請改為順序處理文件，或使用併發度受限的執行緒池。 |

## 實務應用

1. **簡報調整** – 即時將直向投影片轉為橫向，以提升視覺效果。  
2. **大量文件校正** – 自動修正側向掃描的 PDF，節省大量人工時間。  
3. **列印就緒輸出** – 確保橫向圖形在直向紙張上正確列印，無需在印表機驅動程式中手動旋轉。

## 效能建議

- **及時關閉資源** – `try‑with‑resources` 區塊會自動釋放 `Viewer`，釋放記憶體。  
- **批次處理** – 每個執行緒重複使用單一 `Viewer` 實例，以減少初始化開銷。  
- **監控記憶體** – 對於大於 100 MB 的文件，將輸出串流至磁碟而非全部載入記憶體；GroupDocs Viewer 可在低於 250 MB RAM 的情況下處理 200 MB 檔案。

## 常見問答

**Q: 我可以一次旋轉多個頁面嗎？**  
A: 可以——對每個需要旋轉的頁碼呼叫 `rotatePage()`，可在迴圈中或串接呼叫。

**Q: 渲染後有辦法撤銷旋轉嗎？**  
A: 直接撤銷不可行。需要在不使用旋轉選項的情況下重新渲染文件。

**Q: 哪些檔案格式在 GroupDocs Viewer 中支援頁面旋轉？**  
A: DOCX、PDF、PPTX、XLSX 以及官方文件中列出的其他多種格式。

**Q: 如何自動在一批文件中旋轉頁面？**  
A: 將旋轉邏輯包在迴圈中，遍歷檔案路徑集合，對每個檔案套用相同的 `rotatePage` 設定。

**Q: 處理旋轉過程中的錯誤最佳實踐是什麼？**  
A: 將 Viewer 的使用包在 `try‑catch` 區塊中，記錄例外細節，並可選擇繼續處理下一個檔案，以免單一失敗中斷整個批次。

## 資源

- **文件說明**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 參考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下載**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **購買**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **免費試用**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **臨時授權**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **支援**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-09-30  
**測試環境：** GroupDocs Viewer 25.2 for Java  
**作者：** GroupDocs

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 旋轉特定 PDF 頁面](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [在 Java 中從 URL 載入文件 – GroupDocs.Viewer 教學](/viewer/java/document-loading/)
- [GroupDocs Viewer Java 文件檢視](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)