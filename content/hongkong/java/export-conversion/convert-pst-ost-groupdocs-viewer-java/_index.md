---
date: '2026-07-19'
description: 了解如何使用 GroupDocs.Viewer for Java 將 PST 轉換為 HTML 以及 JPG、PNG、PDF 等其他格式。本指南涵蓋所有必要的步驟與設定。
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: 使用 GroupDocs.Viewer for Java 快速將 PST 轉換為 HTML。一步一步學習如何在可投入生產的指南中同時匯出為
  JPG、PNG 與 PDF。
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: 使用 GroupDocs.Viewer for Java 將 PST 轉換為 HTML – 快速電郵匯出
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: 使用 GroupDocs.Viewer for Java 將 PST 轉換為 HTML、JPG、PNG、PDF
type: docs
url: /zh-hant/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# 將 PST 轉換為 HTML、JPG、PNG、PDF（使用 GroupDocs.Viewer for Java）

您是否想要 **convert pst to html** 或其他格式如 JPG、PNG 或 PDF？使用功能強大的 GroupDocs.Viewer for Java 函式庫，這項工作既簡單又高效。在本教學中，您將學習如何將 Outlook PST/OST 檔案轉換為適合網頁的 HTML、影像檔或單一 PDF，讓您的電子郵件存檔更易於分享與保存。

![使用 GroupDocs.Viewer for Java 將 PST/OST 轉換為 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[使用 GroupDocs.Viewer for Java 將 PST/OST 轉換為 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**您將學習**
- 如何在 Maven 專案中設定 GroupDocs.Viewer for Java。  
- 逐步說明如何 **java convert pst** 檔案轉換為 HTML、JPG、PNG 與 PDF。  
- 最佳化效能與常見陷阱的設定技巧。

## 快速解答
- **哪個函式庫處理 PST 轉換？** GroupDocs.Viewer for Java。  
- **我可以直接將 PST 轉換為 PDF 嗎？** 可以，使用 `PdfViewOptions`。  
- **生產環境是否需要授權？** 需要有效的 GroupDocs 授權。  
- **支援哪個 Java 版本？** JDK 8 或更高。  
- **我需要手動提取附件嗎？** 不需要，檢視器會自動渲染附件。

## 什麼是 GroupDocs.Viewer for Java？
GroupDocs.Viewer for Java 是一個伺服器端 API，能載入超過 100 種文件與電子郵件格式，並將它們渲染為 HTML、影像或 PDF 輸出，無需外部軟體。它可處理高達 2 GB 的 PST 檔案，同時將記憶體使用量控制在 200 MB 以下。

## 如何使用 GroupDocs.Viewer for Java 將 pst 轉換為 html？
使用 `new Viewer("source.pst")` 載入 PST 檔案，設定 `HtmlViewOptions` 指向輸出資料夾，然後呼叫 `viewer.view(htmlOptions)`。此 API 會提取每封電子郵件，保留格式、附件與中繼資料，並為每則訊息寫入單獨的 HTML 頁面——全部在一次方法呼叫中完成。

### 為什麼選擇 GroupDocs.Viewer？
- **高保真度渲染** – 99.9 % 的電子郵件內容（包括富文字內容、表格與嵌入圖像）均能精確再現。  
- **多種輸出格式** – 一次 API 呼叫即可產生 HTML、JPG、PNG 或 PDF，涵蓋 50 多種匯出選項。  
- **零外部相依性** – 無需 Outlook、Exchange Server 或第三方轉換器；所有操作皆在您的 Java 執行環境內完成。

## 前置條件

- **GroupDocs.Viewer for Java** – 版本 25.2 或更新。  
- **Java Development Kit (JDK)** – 8 或更新。  
- Maven 用於相依管理。  
- 具備基本的 Java 知識與 Maven 使用經驗。

## 設定 GroupDocs.Viewer for Java

`Viewer` 是 GroupDocs.Viewer for Java 的核心類別，用於載入文件並將其渲染為選定的格式。將 GroupDocs 儲存庫與相依性加入您的 `pom.xml`：

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
- **Free trial** – 無償試用，探索所有功能。  
- **Temporary license** – 如有需要，可延長評估時間。  
- **Full license** – 生產環境部署必須取得完整授權。

### 基本初始化

`Viewer` 實例重量輕；您可以重複使用同一個實例處理多個檔案，以減少物件建立的開銷。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## 實作指南

以下各節將逐步說明如何將 PST/OST 檔案渲染為每種支援的格式。

### 將 PST/OST 文件渲染為 HTML

#### 步驟 1：設定輸出目錄
定義一個資料夾以寫入 HTML 頁面。GroupDocs 會為每封電子郵件建立子資料夾，以保持資源有序。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 步驟 2：設定載入選項
`LoadOptions` 允許您指定密碼處理、資源載入逾時以及選擇性頁面渲染。將逾時設定為 30 秒在大多數伺服器環境中表現良好。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 3：定義 HTML 檢視選項
`HtmlViewOptions` 指定輸出資料夾、資源處理方式，以及 HTML 轉換的可選 CSS 設定。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### 步驟 4：初始化 Viewer 並渲染 HTML
建立 `Viewer` 物件，傳入 PST 檔案路徑，並使用 `HtmlViewOptions` 呼叫 `view`。API 會自動遍歷 PST 中的所有訊息，產生整齊的 HTML 結構。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### 將 PST/OST 文件渲染為 JPG

#### 步驟 1：設定輸出目錄
建立專用的資料夾以存放 JPG 快照；每封電子郵件會根據長度產生一或多個影像檔。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 2：設定載入選項
可重複使用 HTML 所用的 `LoadOptions`，確保在不同格式間保持一致的密碼處理。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 步驟 3：定義 JPG 檢視選項
`JpgViewOptions` 控制影像解析度、品質，以及 JPEG 轉換的輸出資料夾。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 步驟 4：初始化 Viewer 並渲染 JPG
使用 `viewer.view(jpgOptions)` 產生高品質的 JPEG 檔案，供網頁預覽使用。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### 將 PST/OST 文件渲染為 PNG

#### 步驟 1：設定輸出目錄
當需要無損品質以供存檔或 OCR 處理時，PNG 輸出相當有用。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 步驟 2：設定載入選項
除密碼與逾時設定外，無需其他額外設定。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 步驟 3：定義 PNG 檢視選項
`PngViewOptions` 允許您設定透明背景與無損 PNG 圖片的輸出資料夾。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 4：初始化 Viewer 並渲染 PNG
實例化 `viewer.view(pngOptions)` 以產生每封電子郵件的 PNG 快照。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 將 PST/OST 文件渲染為 PDF

#### 步驟 1：設定輸出目錄
每個 PST 產生單一 PDF 檔，可簡化法律審查流程並降低儲存負擔。

CODE_BLOCK_PLACEHOLDER_14_END

#### 步驟 2：設定載入選項
轉換為 PDF 時，您可能需要啟用 `setEmbedFonts(true)`，以確保在任何機器上皆能保持視覺一致性。

CODE_BLOCK_PLACEHOLDER_15_END

#### 步驟 3：定義 PDF 檢視選項
`PdfViewOptions` 允許您選擇壓縮等級、嵌入字型，並設定 PDF 轉換的輸出檔名。

CODE_BLOCK_PLACEHOLDER_16_END

#### 步驟 4：初始化 Viewer 並渲染 PDF
建立 `PdfViewOptions`，可選擇壓縮等級，然後呼叫 `viewer.view(pdfOptions)`。API 會將所有電子郵件合併為一個可搜尋的 PDF 文件。

CODE_BLOCK_PLACEHOLDER_17_END

## 實務應用

- **電子郵件存檔：** 將大型 PST 存檔轉換為可搜尋的 HTML 或 PDF，以符合合規需求。  
- **文件管理系統：** 將轉換後的檔案儲存於僅接受 PDF、PNG 或 JPG 的系統中。  
- **協作平台：** 在 Slack 或 Teams 中以影像形式分享轉換後的電子郵件。  
- **法律審查：** 向法院提供電子郵件證據的 PDF 版本。  
- **備份策略：** 保留關鍵訊息的輕量 PNG 或 JPG 快照。

## 效能考量

- **資源管理：** 在處理多個檔案時重複使用 `Viewer` 實例，以減少開銷。  
- **記憶體調校：** 根據伺服器容量調整 `loadOptions.setResourceLoadingTimeout`。  
- **非同步處理：** 將轉換工作移至背景執行緒，以提升 UI 響應性。  

## 常見問題

**Q: 我如何 **convert pst to pdf** 使用相同的程式碼基礎？**  
A: 使用 `PdfViewOptions` 如 PDF 渲染章節所示；其餘程式碼保持相同。

**Q: GroupDocs.Viewer 能處理加密的 PST 檔案嗎？**  
A: 可以，在渲染前透過 `LoadOptions.setPassword("yourPassword")` 提供密碼。

**Q: **java convert pst** 轉換為 PNG 與 JPG 有何差異？**  
A: PNG 保持無損品質，適合截圖；JPG 檔案較小，適合電子郵件預覽。

**Q: 有沒有方法可以 **how to convert pst** 批次處理檔案？**  
A: 將渲染邏輯包在迴圈中，遍歷 PST 檔案目錄；對每個檔案重複使用相同的 `Viewer` 設定。

**Q: API 是否支援轉換大於 1 GB 的 PST 檔案？**  
A: 是，GroupDocs.Viewer 以串流方式處理資料，最高可處理 2 GB 檔案，且不會將整個封存載入記憶體。

## 結論

您現在擁有一套完整、可投入生產的指南，使用 GroupDocs.Viewer for Java **convert pst to html**、JPG、PNG 與 PDF。依照上述步驟，您即可將電子郵件轉換整合至任何基於 Java 的工作流程，提升可存取性，並符合合規需求。

---

**最後更新:** 2026-07-19  
**測試環境:** GroupDocs.Viewer for Java 25.2  
**作者:** GroupDocs

## 相關教學

- [使用 GroupDocs.Viewer for Java 將 NSF 轉換為 PDF、HTML、JPG、PNG](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – 使用 GroupDocs.Viewer for Java 將 ODF 轉換為 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [如何使用 GroupDocs.Viewer for Java 將 DOCX 轉換為 HTML：一步一步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)