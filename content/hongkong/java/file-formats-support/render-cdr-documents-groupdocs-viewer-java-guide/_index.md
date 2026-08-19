---
date: '2026-08-19'
description: 了解如何使用 GroupDocs.Viewer for Java 將 cdr 轉換為 html，以及 jpg、png、pdf。包括 setup、code
  examples 和 performance tips。
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: 了解如何使用 GroupDocs.Viewer for Java 將 cdr 轉換為 html、jpg、png、pdf。逐步指南，包含
  setup、code snippets 和 performance best practices。
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: 使用 GroupDocs.Viewer Java 將 cdr 轉換為 html、jpg、png、pdf
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: 使用 GroupDocs.Viewer Java 將 cdr 轉換為 html、jpg、png、pdf
type: docs
url: /zh-hant/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# 將 cdr 轉換為 html、jpg、png、pdf（使用 GroupDocs.Viewer Java）

如果您需要快速且可靠地 **convert cdr to html**（或轉換為 JPG、PNG 和 PDF），您已來到正確的教學。本指南將帶您逐步了解所需的一切——從安裝 GroupDocs.Viewer for Java 到將 CorelDRAW（CDR）檔案渲染為適合網頁的 HTML 頁面、高品質影像以及通用可讀的 PDF。完成後，您只需幾行程式碼即可將這些轉換整合到任何 Java 應用程式中。

![使用 GroupDocs.Viewer for Java 渲染 CDR 檔案](/viewer/file-formats-support/render-cdr-files.png)

[使用 GroupDocs.Viewer for Java 渲染 CDR 檔案](/viewer/file-formats-support/render-cdr-files.png)

## 快速答案
- **哪個函式庫可將 CDR 轉換為 HTML？** GroupDocs.Viewer for Java。  
- **我也可以將 CDR 轉換為 JPG、PNG 和 PDF 嗎？** 是的——使用相同的 Viewer API 並搭配不同的檢視選項。  
- **我需要授權嗎？** 測試時可使用免費試用或臨時授權；正式環境則需完整授權。  
- **需要哪個 Java 版本？** JDK 8 或更新版本。  
- **支援批次轉換嗎？** 當然可以——只需使用相同的 Viewer 實例遍歷檔案即可。

## 「convert cdr to html」是什麼？
將 cdr 轉換為 html 意味著將 CorelDRAW 向量檔案轉換為標準 HTML 標記，並可選擇性地嵌入圖像和樣式，使設計能直接在網頁瀏覽器中檢視，而無需原始設計軟體。此過程會保留原始的版面配置、顏色與向量形狀，透過轉換為可縮放的 SVG 元素或嵌入於 HTML 中的點陣圖像，實現跨瀏覽器的精確視覺呈現，同時保持檔案大小低。

## 為什麼要將 cdr 轉換為 html、jpg、png 或 pdf？
您可以將單一 CDR 檔案渲染為四種廣泛支援的格式，每種格式都有其特定用途：HTML 用於即時網頁預覽，JPG/PNG 用於點陣圖像，PDF 用於可列印、可存檔的文件。此彈性讓您能針對不同客戶提供最佳檔案類型，減少儲存重複，並使資產具備未來相容性。

## 前置條件

1. **函式庫與相依性** – 已在 Maven 專案中加入 GroupDocs.Viewer。  
2. **Java Development Kit (JDK)** – 已安裝 8 版或更新的版本。  
3. **基本的 Java 知識** – 以便了解程式碼範例。

### 必要的函式庫、版本與相依性

將以下 Maven 設定加入您的 `pom.xml`（與原始教學相同）：

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

### 取得授權步驟

GroupDocs.Viewer 提供免費試用、測試用臨時授權或完整購買選項：

- **免費試用** – 從 [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/) 下載。  
- **臨時授權** – 前往 [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) 申請。  
- **購買** – 透過 [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) 取得永久授權。

## 設定 GroupDocs.Viewer for Java

Viewer 是核心類別，用於載入文件並提供所有支援輸出格式的渲染方法。

### 使用 Maven 安裝
上述的 Maven 片段會自動下載所有必要的 JAR。儲存檔案後執行 `mvn clean install` 即可。

### 授權初始化
`Viewer` 是核心類別，用於載入文件並提供所有支援輸出格式的渲染方法。在渲染任何文件之前先初始化授權：

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## 實作指南

以下提供每種輸出格式的逐步範例。程式碼區塊與原始教學相同，我們僅在其周圍加入說明文字。

### 如何使用 GroupDocs.Viewer 將 cdr 轉換為 html

載入 CDR 檔案並呼叫 HTML 渲染 API——這就是產生網頁就緒標記所需的一切。此過程需要設定檔案路徑、建立 `HtmlViewOptions` 實例，並呼叫 `viewer.view()`。此兩步驟模式適用於任何文件大小，且能保留向量精度。

#### 將 cdr 文件渲染為 HTML
**概述：** 將您的 CDR 檔案轉換為適合網頁分享的 HTML。

**步驟 1 – 設定檔案路徑**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**步驟 2 – 初始化 viewer 並渲染**

HtmlViewOptions 用於設定 HTML 渲染，可選擇嵌入資源或分別儲存。以下程式碼將每頁渲染為單獨的 HTML 檔，同時以 Base64 字串嵌入圖像。

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### 如何使用 GroupDocs.Viewer 將 cdr 轉換為 jpg

您只需兩行程式碼即可從 CDR 來源產生高品質 JPEG 影像。首先，以所需品質設定 `JpgViewOptions`，然後呼叫 `viewer.view()`。此方法非常適合縮圖、電子郵件附件或任何需要緊湊點陣圖的情境。

#### 將 cdr 文件渲染為 JPG
**概述：** 從您的 CDR 來源產生高品質 JPEG 影像。

**步驟 1 – 設定檔案路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**步驟 2 – 初始化 viewer 並渲染**

JpgViewOptions 定義 JPEG 渲染設定，例如壓縮品質與輸出命名。以下範例將每頁儲存為單獨的 JPEG 檔。

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### 如何使用 GroupDocs.Viewer 將 cdr 轉換為 png

PNG 輸出提供無損點陣圖，適合存檔或進一步的圖形處理。使用 `PngViewOptions` 保持每個像素完整，然後逐頁渲染文件。

#### 將 cdr 文件渲染為 PNG
**概述：** 產生無損 PNG 影像，用於存檔或設計用途。

**步驟 1 – 設定檔案路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**步驟 2 – 初始化 viewer 並渲染**

PngViewOptions 指定 PNG 渲染參數，包括支援透明背景。程式碼會自動為每頁建立 PNG。

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### 如何使用 GroupDocs.Viewer 將 cdr 轉換為 pdf

將 CDR 檔案轉換為 PDF 可獲得通用可讀、可列印的文件。`PdfViewOptions` 內部處理向量到點陣的轉換，保留版面與字型，無需 Adobe Illustrator。

#### 將 cdr 文件渲染為 PDF
**概述：** 將您的 CDR 檔案轉換為通用可讀的 PDF。

**步驟 1 – 設定檔案路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**步驟 2 – 初始化 viewer 並渲染**

PdfViewOptions 控制 PDF 產生，支援字型嵌入與頁面版面自訂。此程式碼片段會產生包含所有頁面的單一 PDF。

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## 實務應用

- **Web portals：** 使用 HTML 轉換直接在網站上嵌入 CDR 設計。  
- **Image galleries：** 部署 JPG/PNG 輸出以建立快速載入的圖庫或產品目錄。  
- **Document sharing：** 為需要可列印、唯讀版本的客戶提供 PDF。  
- **Archiving：** 儲存多種格式以確保未來即使軟體變更仍能存取。  
- **Cross‑platform integration：** 將產生的檔案輸入後續服務，如 OCR、分析或數位資產管理系統。  

## 效能考量

- **盡快釋放 Viewer 實例**（如使用 try‑with‑resources 示範），以釋放記憶體。  
- **批次處理：** 使用相同的 Viewer 設定遍歷 CDR 檔案集合，以減少開銷。  
- **資源配置：** GroupDocs.Viewer 可在不將整個檔案載入記憶體的情況下渲染最多 500 頁的文件，但極為複雜的圖形可能需要增加堆積大小。大型轉換時請監控 CPU 與記憶體使用情況。  

## 常見陷阱與除錯技巧

- **缺少字型：** 若輸出外觀不同，請確保伺服器上有所需字型，或透過 `PdfViewOptions` 嵌入字型。  
- **大型檔案：** 若 CDR 檔案超過 200 MB，建議逐頁處理以避免 `OutOfMemoryError`。  
- **影像品質不佳：** 若 JPEG 壓縮過度，請調整 `JpgViewOptions` 中的 `setQuality` 值。  
- **授權錯誤：** 請確認授權檔案路徑正確，且授權版本與 Viewer 函式庫版本相符。  

## 結論

我們已示範如何使用 GroupDocs.Viewer for Java **將 cdr 轉換為 html**，以及轉換為 JPG、PNG 與 PDF。遵循簡潔的程式碼片段與最佳實踐提示，您即可將這些轉換嵌入任何基於 Java 的工作流程，為使用者提供彈性且高品質的輸出。

### 後續步驟
- 嘗試使用進階渲染選項，例如自訂頁面尺寸或浮水印。  
- 將轉換流程與 REST API 結合，提供即時檔案轉換服務。  
- 加入社群並在 [GroupDocs Forum](https://forum.groupdocs.com/c/viewer) 提問。  

## 常見問題

**Q: 我可以轉換受密碼保護的 CDR 檔案嗎？**  
A: 是的。使用接受密碼參數的 `Viewer` 實例載入檔案（請參閱 API 文件）。

**Q: 一次可以轉換的頁數有上限嗎？**  
A: 沒有硬性上限，但非常大的檔案可能需要更多記憶體；建議逐頁處理。

**Q: HTML 輸出會包含嵌入字型嗎？**  
A: 使用 `HtmlViewOptions.forEmbeddedResources` 時，字型會以 Base64 形式嵌入，確保在各瀏覽器間一致渲染。

**Q: 如何控制 JPEG 品質？**  
A: `JpgViewOptions` 提供 `setQuality(int)` 方法，可指定 1‑100 的數值。

**Q: 我可以在 Linux 伺服器上轉換 CDR 檔案嗎？**  
A: 當然可以——只要安裝 JDK，GroupDocs.Viewer 即可跨平台使用。

---

**最後更新：** 2026-08-19  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

## 相關教學

- [如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML、JPG、PNG 與 PDF](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [如何使用 GroupDocs.Viewer for Java 將 CF2 轉換為 PDF、HTML、JPG、PNG](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)
- [如何在 Java 中使用 GroupDocs.Viewer 將 pdf 轉換為 html 並優化影像品質](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)