---
date: '2026-06-05'
description: 了解如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML、JPG、PNG 和 PDF。本分步指南涵蓋設定、渲染選項以及實際應用案例。
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: 如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML、JPG、PNG 和 PDF
type: docs
url: /zh-hant/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# 如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML、JPG、PNG 和 PDF

將 Excel 轉換為 HTML 是在網頁上顯示試算表資料且保留列與欄標題的常見需求。在本教學中，您將了解 GroupDocs.Viewer for Java 如何簡化 **convert excel to html**，以及如何將相同的工作簿渲染為 JPG、PNG 和 PDF 格式。我們將逐步說明前置條件、函式庫設定以及每個渲染情境，並提供清晰、可直接投入生產的程式碼範例。

## 快速解答
- **GroupDocs.Viewer 能否將 Excel 渲染為多種格式？** 是的——HTML、JPG、PNG 和 PDF 均已內建支援。  
- **開發時是否需要授權？** 免費試用可用於測試；正式環境需購買永久授權。  
- **列與欄標題會被保留嗎？** 在 view options 上設定 `setRenderHeadings(true)` 即可包含它們。  
- **需要哪個版本的 Java？** Java 8 或以上；函式庫相容於 Java 11、17 及更高版本。  
- **大型工作簿的轉換速度快嗎？** GroupDocs.Viewer 可在一般伺服器硬體上於一秒內處理 200 頁的試算表。

## 「convert excel to html」是什麼？
**Convert excel to html** 指將 Excel 工作簿轉換為可在網頁上使用的 HTML 文件，同時保留原始版面、公式與標頭。這讓您能在不需要使用者安裝 Excel 的情況下，將試算表無縫嵌入網頁或入口網站。

## 為何使用 GroupDocs.Viewer Java 進行 Excel 渲染？
GroupDocs.Viewer Java 支援 **50+ 輸入與輸出格式**，包括 DOCX、XLSX、PPTX、HTML、JPG、PNG 與 PDF。它能在不將整個檔案載入記憶體的情況下處理數百頁的工作簿，轉換速度比許多開源方案快 **10 倍**。此外，函式庫還提供對渲染選項的精細控制，例如標頭可見性、頁面大小與影像品質。

## 前置條件

- **Java Development Kit (JDK) 8+** 已安裝並在您的 IDE（IntelliJ IDEA、Eclipse 等）中設定。  
- **Maven** 用於相依性管理。  
- 具備基本的 Java 語法與 Maven `pom.xml` 的認識。  
- 具備有效的 **GroupDocs.Viewer Java** 授權（試用或永久）。

### 必要的函式庫與相依性
將 GroupDocs.Viewer Java 相依性加入您的 `pom.xml`：

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

### 環境設定
- 確認 `java -version` 回傳 1.8 或更新版本。  
- 開啟您喜愛的 IDE，建立 Maven 專案。

在深入實作之前，讓我們先完成前置條件的設定。

![convert Excel files into HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## 設定 GroupDocs.Viewer Java

### 安裝資訊
在專案的 `pom.xml` 中加入上述 Maven 相依性。執行 `mvn clean install` 後，函式庫即會加入您的 classpath。

### 取得授權步驟
1. **Free Trial（免費試用）：** 從 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 下載試用版。  
2. **Temporary License（暫時授權）：** 從 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 取得延長測試的暫時授權。  
3. **Purchase（購買）：** 前往 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 取得正式授權以供生產使用。

### 基本初始化
`Viewer` 類別是所有渲染操作的入口。初始化相當簡單：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

此程式碼會建立一個與本機授權檔案綁定的 `Viewer` 實例，準備好處理 Excel 檔案。

## 實作指南

以下說明每個渲染目標。對於每種格式，我們會先 **匯入所需類別**，接著 **設定輸出目錄**，最後 **配置 view options**，使用 `setRenderHeadings(true)` 以保留列與欄的標頭。

### 渲染試算表為 HTML
**如何使用 GroupDocs.Viewer Java 將 Excel 工作簿轉換為 HTML？**  
要將 Excel 工作簿轉換為 HTML，先使用 Viewer 載入檔案，建立 HtmlViewOptions 實例，啟用標頭渲染，然後呼叫 view 方法。此過程會將每個工作表寫入獨立的 HTML 檔案，保留儲存格格式、公式與原始版面，以確保在網頁上的正確顯示。

#### 步驟實作
**1. 匯入必要的函式庫**  
HtmlViewOptions 設定工作簿渲染為 HTML 的方式，允許自訂標頭、樣式與頁面版面配置。  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. 設定輸出目錄**  
指定產生的 HTML 頁面將寫入的資料夾。  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. 初始化 Viewer 並配置選項**  
建立 `Viewer` 實例，設定 `setRenderHeadings(true)`，然後呼叫 `view`。  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**說明：** `HtmlViewOptions` 控制 HTML 輸出。啟用 `setRenderHeadings(true)` 可確保第一列與第一欄（通常為標頭）出現在產生的 HTML 中，使資料即時易於理解。

### 渲染試算表為 JPG
**如何將 Excel 工作表渲染為包含標頭的 JPG 影像？**  
將 Excel 工作表渲染為 JPG 需要使用 Viewer 載入工作簿，建立 JpgViewOptions 物件，將 renderHeadings 設為 true，然後呼叫 view。函式庫會以指定的 DPI 光柵化每頁，產生高解析度的 JPG 檔案，保留試算表的視覺結構與標頭。

#### 步驟實作
**1. 匯入必要的函式庫**  
JpgViewOptions 定義將工作表渲染為 JPG 影像的設定，包括 DPI、品質與標頭可見性。  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. 設定輸出目錄**  
定義 JPG 檔案的儲存位置。  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. 初始化 Viewer 並配置選項**  
建立 Viewer，設定標頭渲染，並執行轉換。  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**說明：** `JpgViewOptions` 讓您控制 DPI 與品質。使用 `setRenderHeadings(true)`，產生的影像會保留試算表的標頭列與欄，對於報告與簡報相當重要。

### 渲染試算表為 PNG
**將 Excel 轉換為 PNG 並保留欄標題的流程是什麼？**  
要從 Excel 檔案產生 PNG 影像，使用 Viewer 開啟工作簿，建立 PngViewOptions 實例，啟用標頭渲染，然後執行 view。PNG 輸出提供無損品質，保留所有儲存格樣式與標頭列，適合存檔或進一步的影像處理。

#### 步驟實作
**1. 匯入必要的函式庫**  
PngViewOptions 控制工作表渲染為 PNG 影像，提供無損壓縮與標頭選項。  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. 設定輸出目錄**  
選擇 PNG 輸出的資料夾。  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. 初始化 Viewer 並配置選項**  
建立 Viewer，啟用標頭渲染，並呼叫 `view`。  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**說明：** 透過呼叫 `setRenderHeadings(true)`，PNG 檔案會包含原始試算表的標頭列與欄，保留後續使用者的上下文資訊。

### 渲染試算表為 PDF
**如何將 Excel 檔案轉換為 PDF 並顯示列與欄標頭？**  
將 Excel 轉換為 PDF 非常簡單：以來源檔案建立 Viewer，設定 PdfViewOptions 以渲染標頭，然後呼叫 view。產生的 PDF 會忠實呈現工作簿的版面，包含列與欄標頭，且支援向量圖形，確保列印與分發時的清晰度。

#### 步驟實作
**1. 匯入必要的函式庫**  
PdfViewOptions 指定 PDF 產生的參數，如頁面大小、邊距與標頭渲染。  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. 設定輸出目錄**  
指定 PDF 文件的目標資料夾。  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. 初始化 Viewer 並配置選項**  
建立 `Viewer`，啟用標頭渲染，並執行轉換。  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**說明：** 在 `PdfViewOptions` 上設定 `setRenderHeadings(true)` 可保證第一列/欄出現在最終 PDF 中，使文件可直接列印或存檔。

## 實務應用
在以下實務情境中，**convert excel to html**、**excel to pdf java** 或 **convert spreadsheet to image** 都非常有價值：

1. **Business Reporting（商業報告）：** 從財務模型產生 HTML 儀表板或 PDF 報告，無需手動複製貼上。  
2. **Data Visualization（資料視覺化）：** 在簡報中嵌入 JPG/PNG 試算表快照，確保標頭即時提供觀眾上下文。  
3. **Document Archiving（文件存檔）：** 將 Excel 工作簿存為 PDF 以符合法規要求，同時保留原始版面與標頭。  
4. **Web Portals（網站入口）：** 直接在瀏覽器提供試算表的 HTML 版本，並可使用 JavaScript 進行互動篩選。

## 常見問題

**Q: 我可以轉換受密碼保護的 Excel 檔案嗎？**  
**A: 可以。將密碼傳入 `Viewer` 建構子，函式庫會在渲染前解密工作簿。**

**Q: GroupDocs.Viewer 是否支援含巨集的工作簿 (.xlsm)？**  
**A: 當然支援。Viewer 會將巨集視為資料，在渲染時會忽略，確保轉換安全。**

**Q: 支援的最大檔案大小是多少？**  
**A: 透過串流架構，函式庫可處理最高 **2 GB** 的檔案，且不需將整個文件載入記憶體。**

**Q: 能否只渲染特定的工作表？**  
**A: 可以。使用 `ViewOptions.setPageNumber(pageIndex)` 在產生 HTML、JPG、PNG 或 PDF 時指定單一工作表。**

**Q: 如何控制 JPG 輸出的影像品質？**  
**A: 設定 `JpgViewOptions.setQuality(90)`（值介於 0‑100）即可在檔案大小與影像品質之間取得平衡。

## 結論
現在您已擁有一套完整、可直接投入生產的指南，說明如何使用 GroupDocs.Viewer Java **convert excel to html**、**excel to pdf java** 與 **convert spreadsheet to image**。依照上述步驟，您即可將試算表渲染整合至任何 Java 後端，自動產出保留標頭的 HTML 報表、高解析度影像或存檔用 PDF。

---

**最後更新：** 2026-06-05  
**測試環境：** GroupDocs.Viewer Java 23.12  
**作者：** GroupDocs

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 將 DOCX 轉換為 HTML：一步步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer for Java 的響應式 HTML 渲染：完整指南](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – 使用 GroupDocs.Viewer for Java 將 ODF 轉換為 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)