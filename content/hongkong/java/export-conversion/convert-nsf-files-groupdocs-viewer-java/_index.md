---
date: '2026-05-26'
description: 了解如何使用 GroupDocs.Viewer for Java 將 NSF 轉換為 PDF 以及其他格式（HTML、JPG、PNG）。逐步指南與最佳實踐技巧。
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: 使用 GroupDocs.Viewer for Java 將 NSF 轉換為 PDF
type: docs
url: /zh-hant/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer for Java 將 NSF 檔案轉換為多種格式

在本完整指南中，您將學習 **如何將 nsf 轉換為 pdf**，以及使用 GroupDocs.Viewer for Java 將 NSF 檔案渲染為 HTML、JPG 和 PNG。無論您是需要歸檔 Lotus Notes 資料庫、在瀏覽器中顯示，或產生圖像預覽，本教學都會一步步說明——從環境設定到程式碼層面的細節——讓您在數分鐘內完成轉換。

![使用 GroupDocs.Viewer for Java 將 NSF 檔案轉換為 HTML、JPG、PNG 與 PDF](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[使用 GroupDocs.Viewer for Java 將 NSF 檔案轉換為 HTML、JPG、PNG 與 PDF](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## 快速答案
- **主要使用情境是什麼？** 將 NSF 檔案渲染為 PDF、HTML、JPG 或 PNG，以供網路、歸檔或分享使用。  
- **哪個函式庫負責轉換？** GroupDocs.Viewer for Java。  
- **我需要授權嗎？** 提供免費試用版；正式環境需購買完整授權。  
- **需要哪個 Java 版本？** JDK 8 或更新版本。  
- **我可以批次處理多個 NSF 檔案嗎？** 可以——將渲染邏輯包在迴圈中，並使用 try‑with‑resources 管理資源。  

## 什麼是「convert nsf to pdf」？
將 NSF（Lotus Notes 資料庫）檔案轉換為 PDF，會產生一個靜態、可在任何平台閱讀的文件，保留原始的版面配置、字型與圖形，且不需要 Notes 客戶端。此格式非常適合法律歸檔、安全分發與長期保存，因為 PDF 檔案可在任何作業系統或裝置上開啟。

## 為何將 NSF 轉換為 PDF 及其他格式？
將 NSF 檔案轉換為 PDF、HTML、JPG 或 PNG，可實現跨平台存取、保留視覺完整性，並能與現代 Web 與行動應用程式無縫整合。PDF 保持精確的頁面版面，HTML 提供即時的瀏覽器內檢視，JPG/PNG 則提供高解析度的圖像快照，可用於縮圖或嵌入。

## 前置條件
- **Java Development Kit (JDK) 8+** – 建議使用 JDK 11 或更新版本，以獲得更佳的垃圾回收效能。  
- **Maven** – 用於相依性管理。  
- **GroupDocs.Viewer for Java** – 試用版或授權版。  
- 具備 Java 檔案 I/O 與 Maven 專案結構的基本認識。  

## 設定 GroupDocs.Viewer for Java
### Maven 設定
將 GroupDocs.Viewer 相依性加入 `pom.xml`。此操作會自動下載所有必要的二進位檔與傳遞相依性。

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
若要解鎖完整功能，您可以：
- **免費試用：** 在未提供授權金鑰的情況下評估核心功能。  
- **臨時授權：** 申請限時金鑰以進行測試。  
- **完整購買：** 取得正式授權以無限制使用。  

### 基本初始化
`Viewer` 為核心類別，用於將文件渲染為目標輸出格式。請在 try‑with‑resources 區塊中以授權與檔案路徑初始化，以確保正確釋放資源。

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## 如何將 NSF 轉換為 PDF
要將 NSF 文件轉換為 PDF，首先建立指向來源檔案的 `Viewer` 實例。接著設定 `PdfViewOptions`，定義輸出特性，如頁面尺寸、壓縮等級以及是否嵌入字型。最後，呼叫 `viewer.view(pdfOptions)`，即可將整個文件渲染為單一 PDF 檔，供發佈使用。

`PdfViewOptions` 指定 PDF 專屬設定，例如頁面尺寸與壓縮。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## 將 NSF 渲染為 HTML
### 概觀
將 NSF 文件轉換為自包含的 HTML 頁面，嵌入圖像與 CSS，以確保螢幕上呈現的準確性。  

### 步驟說明
#### 1. 設定輸出目錄與檔案路徑
定義儲存 HTML 檔案的資料夾。

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. 設定載入選項
`LoadOptions` 讓您微調資源載入，例如為外部資產設定逾時時間。

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. 初始化 Viewer 並渲染
`Viewer` 處理 NSF 並將 HTML 檔寫入目標目錄。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## 將 NSF 渲染為 JPG
### 概觀
從 NSF 文件的每一頁產生高品質 JPG 圖像，適用於預覽或嵌入以圖像為主的工作流程。  

#### 1. 定義輸出路徑
指定命名模式，例如 `output_page_{0}.jpg`，其中 `{0}` 為頁碼。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. 設定並渲染
`JpgViewOptions` 定義 JPEG 圖像輸出的設定，包括解析度與品質。建立 `JpgViewOptions`，設定所需 DPI，然後呼叫 `viewer.view(options)`。

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## 將 NSF 渲染為 PNG
### 概觀
產生無失真的 PNG 圖像，保留原始 NSF 頁面的所有細節。  

#### 1. 設定輸出路徑
使用類似 `nsf_page_{0}.png` 的模板，以自動分頁。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. 渲染文件
`PngViewOptions` 設定 PNG 輸出參數，如解析度與色深。配置 `PngViewOptions`（例如 `setResolution(300)`），然後渲染。

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## 實務應用
1. **基於 Web 的文件分享：** 將 NSF 轉換為 HTML，以便在瀏覽器中即時檢視，無需安裝 Notes。  
2. **圖像歸檔：** 以頁面為單位儲存 JPG/PNG 快照，用於縮圖畫廊或 OCR 流程。  
3. **通用存取：** 使用 PDF 轉換提供單一安全檔案，可在任何裝置上開啟，符合合規需求。  

## 效能考量
- **資源載入：** 根據網路延遲調整 `setResourceLoadingTimeout`，以避免卡住。  
- **記憶體管理：** 為 `Viewer` 實例使用 try‑with‑resources，會自動釋放原生資源。  
- **批次處理：** 大量批次時，可順序或平行串流處理檔案，並監控堆積使用量，確保不超過 JVM 記憶體上限。  

## 常見問答
**什麼是轉換 NSF 文件的最佳格式？**  
- 取決於後續使用情境：Web 入口使用 HTML，通用分發使用 PDF，圖像導向工作流程使用 JPG/PNG。  

**如何有效處理大型 NSF 檔案？**  
- 調整 `LoadOptions`（例如提升 `setResourceLoadingTimeout`），將檔案分成較小批次處理，並在可能時重複使用單一 `Viewer` 實例。  

**我可以自訂圖像格式的輸出品質嗎？**  
- 可以。於渲染前透過 `JpgViewOptions` 或 `PngViewOptions` 設定 DPI、壓縮等級與色深。  

**如果轉換失敗該怎麼辦？**  
- 核對檔案路徑，確保 NSF 檔案未損毀，並檢查 GroupDocs.Viewer 日誌以取得錯誤代碼。升級至最新函式庫版本通常可解決相容性問題。  

**是否支援批次轉換？**  
- 當然支援。將渲染邏輯包在 `for` 迴圈或 Java Stream 中，即可自動處理多個 NSF 檔案。  

## 常見問題
**Q: 如何在不遺失註解的情況下將 NSF 檔案轉換為 PDF？**  
A: `PdfViewOptions` 會自動保留大多數註解；只要使用此選項渲染文件，產生的 PDF 即會與原始版面相同。  

**Q: 我可以轉換受密碼保護的 NSF 檔案嗎？**  
A: 可以。於建立 `Viewer` 實例前，透過 `LoadOptions` 提供認證資訊。  

**Q: 哪個 Java 版本效能最佳？**  
A: JDK 11 或更新版本提供更佳的垃圾回收與併發效能，可加速批次轉換。  

**Q: 能否為 JPG/PNG 輸出設定自訂 DPI？**  
A: 在呼叫 `viewer.view(options)` 前，設定 `JpgViewOptions.setResolution(int dpi)` 或 `PngViewOptions.setResolution(int dpi)`。  

**Q: GroupDocs.Viewer 是否支援將輸出直接串流至 HTTP 回應？**  
A: 支援。使用 view options 的 `Stream` 重載，直接寫入 `HttpServletResponse.getOutputStream()`。  

## 結論
您現在已掌握使用 GroupDocs.Viewer for Java **convert nsf to pdf** 以及將 NSF 檔案渲染為 HTML、JPG、PNG 的完整路線圖。依照上述步驟，即可將強大的文件轉換功能整合至任何 Java 應用程式，實現批次作業自動化，並以最符合使用者需求的格式提供內容。可進一步探索 Viewer 的其他功能，如浮水印、自訂字型與多頁處理，以豐富您的解決方案。

---

**最後更新：** 2026-05-26  
**測試環境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs  

## 相關教學
- [groupdocs viewer java：將文件轉換為 PDF – 完整指南](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – 使用 GroupDocs.Viewer for Java 將 ODF 轉換為 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [將 PST 轉換為 HTML、JPG、PNG、PDF – 使用 GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)