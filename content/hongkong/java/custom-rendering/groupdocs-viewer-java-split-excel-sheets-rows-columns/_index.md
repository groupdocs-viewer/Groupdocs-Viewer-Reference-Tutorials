---
date: '2026-06-15'
description: 了解如何使用 GroupDocs Viewer 將 Excel 轉換為 PDF（Java）並按行列拆分工作表。包括設定、程式碼及最佳實踐。
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: 將 Excel 轉換為 PDF（Java）並按行列拆分工作表
type: docs
url: /zh-hant/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# 將 Excel 轉換為 PDF（Java）及按列與欄分割工作表（Java）

大型 Excel 活頁簿通常包含的資料量超過單一螢幕或列印頁面能舒適顯示的範圍。**convert excel to pdf java** 是在需要靜態、可分享格式時的常見需求，而 **splitting Excel sheets by rows and columns** 則能讓資料在網頁或列印版面上更易於閱讀。本指南將使用 **GroupDocs Viewer for Java** 逐步說明這兩項任務，展示如何設定分頁，並說明效能與除錯的最佳實踐技巧。

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## 快速解答
- **使用的函式庫是什麼？** GroupDocs Viewer for Java.  
- **我可以同時依列與欄分割嗎？** 是的——您可以同時定義每頁的列數與欄數。  
- **我需要授權嗎？** 開發階段可使用試用或暫時授權；正式上線則需完整授權。  
- **支援哪些輸出格式？** 示範為 HTML（嵌入式資源）；亦可使用相同選項產生 PDF。  
- **是否需要 Maven？** 建議使用 Maven 來管理相依性。  
- **我也可以將 Excel 轉換為 PDF 嗎？** 當然可以——只需將 `HtmlViewOptions` 換成 `PdfViewOptions`，其餘分頁設定保持不變。

## 什麼是「分割 Excel」？
分割 Excel 工作表是指將單一工作表依固定的列數、欄數或兩者同時分成多個頁面或檔案。此技巧在需要製作分頁報告、在網頁嵌入資料，或產生可列印區段而不一次載入整個活頁簿時非常實用。

## 為什麼使用 GroupDocs Viewer for Java？
GroupDocs Viewer 會在單次處理中解析試算表並自動分頁，免除手動計算。**快速渲染可在一般 2 核心伺服器上於 2 秒內處理 250 頁的 XLSX 活頁簿**，且 **函式庫支援超過 50 種輸入與輸出格式**，包括 XLS、XLSX、CSV、PDF 與 HTML。它可在任何相容 JVM 的平台上執行——Windows、Linux、macOS、Docker 容器或雲端無伺服器執行環境——讓您能在 Java 應用所在的任何環境中整合。

## 先決條件
- 已安裝 Java 17 或更新版本。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 使用 Maven 進行相依性管理。  
- 具備基本的 Java 知識並熟悉 Excel 檔案處理。

### 所需函式庫、版本與相依性
將 GroupDocs 倉庫與 viewer 相依性加入您的 `pom.xml`：

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
從 [GroupDocs](https://purchase.groupdocs.com/buy) 取得免費試用、暫時授權，或購買完整授權。

## 如何將 Excel 轉換為 PDF（Java）？

The `Viewer` 類別是 GroupDocs Viewer 的核心元件，負責載入文件並提供多種輸出格式的渲染方法。`SpreadsheetOptions` 讓您能控制試算表渲染的分頁設定，例如每頁的列數與欄數。

使用 `new Viewer("source.xlsx")` 載入 Excel 檔案，設定 `SpreadsheetOptions` 以進行分頁，然後呼叫 `viewer.view(pdfOptions, stream)`——此單一呼叫會在遵守您設定的列/欄限制下，將活頁簿轉換為 PDF。轉換過程會保留公式、圖片與儲存格樣式，產生可直接發佈的忠實 PDF 副本。

## 如何依列分割 Excel 工作表

依列分割會產生一系列 HTML 頁面，每頁包含固定數量的列（例如 15 列）。此方式非常適合在儀表板上每次顯示有限筆記錄。Viewer 會產生獨立的 HTML 檔案，如 `page_0.html`、`page_1.html` 等，每個檔案皆包含指定的列數。這讓您在網頁介面只載入所需部分，降低頻寬與渲染時間。

### 定義錨點
`Viewer` 是 GroupDocs Viewer 的核心類別，負責載入文件並協調渲染至選定的輸出格式。

### 步驟實作

#### 步驟 1：設定路徑並初始化 Viewer
首先，定義分割頁面的儲存位置，並為來源活頁簿建立 `Viewer` 實例。

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### 步驟 2：設定每頁列數
告訴 Viewer 每頁應包含多少列。

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### 步驟 3：渲染文件
最後，使用先前設定的選項渲染活頁簿。

```java
viewer.view(viewOptions);
```

## 如何同時依列與欄分割 Excel 工作表

有時單一頁面需要同時顯示列與欄的矩陣（例如 15 列 × 7 欄）。這讓您能完整掌控每個 HTML 頁面的版面配置。產生的頁面會呈現矩形區塊的儲存格，例如第一頁顯示第 1‑15 列與 A‑G 欄，第二頁顯示第 16‑30 列與 H‑N 欄。此格狀分頁方式適合製作符合標準紙張尺寸的可列印報告。

### 定義錨點
`SpreadsheetOptions` 設定每個產生頁面上顯示的列數與欄數。

### 步驟實作

#### 步驟 1：設定路徑並初始化 Viewer
設定方式與僅列分割的範例相同，僅檔名不同。

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### 步驟 2：設定每頁列數與欄數
同時指定列與欄的數量，以建立格狀分割。

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### 步驟 3：渲染文件
使用相同的 `view` 呼叫進行渲染。

```java
viewer.view(options);
```

## 實務應用
- **Generate Excel report Java**: 將大型財務模型轉換為一系列分頁的 HTML 報告。  
- **GroupDocs Viewer Excel**：將分割頁面直接嵌入網站入口，以進行互動式資料探索。  
- **Render Excel HTML Java**：透過 servlet 或 Spring 控制器提供產生的 HTML 頁面，以實現快速的客戶端渲染。  

## 效能考量
- **Memory usage** – 大型活頁簿可能佔用大量堆記憶體；建議提升 JVM 的 `-Xmx` 設定。  
- **Chunk size** – 選擇列/欄數量以在頁面大小與渲染速度之間取得平衡。  
- **Version updates** – 保持 GroupDocs Viewer 為最新版本以獲得效能提升；最新的 25.2 版相較於 24.x 可提升渲染速度最高 30 %。  

## 常見問題與除錯
| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| `OutOfMemoryError` | 每頁列數過多導致渲染極大工作表 | 減少 `countRowsPerPage` 或提升 JVM 堆記憶體 |
| 空白輸出檔案 | 檔案路徑不正確或缺少寫入權限 | 確認 `outputDirectory` 已存在且可寫入 |
| HTML 資源未載入 | 使用 `forEmbeddedResources` 但檔案從不同的基礎 URL 提供 | 提供整個輸出資料夾或改用 `forExternalResources` |

## 常見問與答

**Q: 我可以產生 PDF 而非 HTML 嗎？**  
A: 是的。將 `HtmlViewOptions` 換成 `PdfViewOptions`，其餘 `SpreadsheetOptions` 設定保持不變。

**Q: 能否依儲存格內容而非固定列/欄進行分割？**  
A: GroupDocs Viewer 本身未內建依內容分割的功能，但您可先使用 Apache POI 前置處理活頁簿，將其拆分為不同工作表再進行渲染。

**Q: GroupDocs Viewer 是否支援較舊的 Excel 格式（XLS）？**  
A: 當然支援。Viewer 可處理 XLS、XLSX、CSV 以及其他試算表格式。

**Q: 如何將產生的 HTML 嵌入 Spring MVC 視圖？**  
A: 將輸出資料夾作為靜態資源提供，並在 Thymeleaf 或 JSP 模板中引用產生的 `page_0.html`、`page_1.html` 等檔案。

**Q: 商業部署需要什麼授權？**  
A: 必須購買 GroupDocs 的完整正式授權；試用授權僅供評估使用。

## 資源
- **文件說明**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 參考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **下載**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **購買**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **免費試用**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **暫時授權**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **支援**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-06-15  
**測試環境：** GroupDocs Viewer 25.2 for Java  
**作者：** GroupDocs  

## 相關教學

- [在 Java 試算表中使用 GroupDocs.Viewer 渲染隱藏列與欄](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [在 Java 中使用 GroupDocs.Viewer 跳過渲染空白列：效能指南](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [完整指南：使用 GroupDocs.Viewer Java 將 Excel 2003 XML 轉換為 HTML/JPG/PNG/PDF](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)