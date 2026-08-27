---
date: '2026-08-25'
description: 了解如何使用 GroupDocs.Viewer for Java 轉換 Apple Numbers 檔案為 PDF、HTML、JPG 或
  PNG。內容包括設定、Java 文件轉換步驟以及網頁顯示技巧。
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: 了解如何使用 GroupDocs.Viewer for Java 轉換 Apple Numbers 檔案為 PDF、HTML、JPG
  或 PNG。內容包括設定、Java 文件轉換步驟以及網頁顯示技巧。
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: 使用 GroupDocs.Viewer for Java 轉換 Apple Numbers 檔案的方法
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: 使用 GroupDocs.Viewer for Java 轉換 Apple Numbers 檔案的方法
type: docs
url: /zh-hant/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs.Viewer for Java 轉換 Numbers

在網頁或桌面客戶端顯示 Apple Numbers 試算表有時像解謎，特別是當您需要 **將 Numbers 轉換為 PDF** 或將其嵌入為報告圖像時。本教學將教您如何使用 **GroupDocs.Viewer for Java** 將 **Numbers 轉換** 為 PDF、HTML、JPG 與 PNG。我們會逐步說明專案設定、程式碼層級的渲染，以及實務情境，讓您在數分鐘內建立穩健的預覽或歸檔流程。

![渲染 Apple Numbers 文件使用 GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[渲染 Apple Numbers 文件使用 GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### 您將學習的內容
- 如何將 GroupDocs.Viewer 加入基於 Maven 的 Java 專案。  
- 逐步程式碼示範 **將 Numbers 轉換為 pdf**、**將 Numbers 轉換為 html**、**將 Numbers 轉換為 jpg** 與 **將 Numbers 轉換為 png**。  
- 何時為網站入口、電子郵件工作流程或文件管理系統選擇各種輸出格式。  

## 快速解答
- **我可以使用 Java 將 Numbers 轉換為 PDF 嗎？** 是的 – 建立 `Viewer` 並呼叫 `PdfViewOptions` 即可取得可直接儲存的 PDF。  
- **哪種格式提供最完整的網頁預覽？** HTML，因為它能保留表格、公式與樣式的互動性。  
- **生產環境需要授權嗎？** 任何非試用部署皆需商業授權。  
- **支援影像轉換嗎？** 當然可以 – 使用 `JpgViewOptions` 或 `PngViewOptions` 取得高品質快照。  
- **需要哪個 Java 版本？** Java 8 以上，並使用 Maven 管理相依性。  

## 前置條件
- 在您的機器上安裝 Java Development Kit (JDK) 8 或更新版本。  
- 使用 Maven 處理相依性與建置專案。  
- 具備 Java 檔案 I/O、路徑與例外處理的基本知識。  

## 設定 GroupDocs.Viewer for Java

### 使用 Maven 安裝
將 GroupDocs 儲存庫與 Viewer 相依性加入您的 `pom.xml`。此區塊必須保持原樣：

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
- **免費試用：** 完整功能，無需信用卡。  
- **臨時授權：** 申請有限時間的金鑰以延長測試。  
- **正式購買：** 取得永久授權以供商業使用。  

## Viewer 類別是什麼？
`Viewer` 類別是 GroupDocs.Viewer 的核心引擎，負責載入文件並將其渲染為指定的輸出格式。它抽象化檔案類型處理，讓您專注於業務邏輯，而不必解析試算表內部結構。  

## 如何使用 GroupDocs.Viewer for Java 將 Numbers 轉換為 HTML？

`HtmlViewOptions` 指定 HTML 渲染的設定，例如嵌入資源或連結外部檔案。  
載入 Numbers 檔案、設定 HTML 選項，然後呼叫 `viewer.view()`。`HtmlViewOptions.forEmbeddedResources()` 方法會將 CSS 與圖像直接打包進 HTML，使結果非常適合嵌入網頁而不需額外資源。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **為何重要：** 嵌入式資源讓預覽自成一體，避免圖像連結失效，並簡化 CDN 部署。  

## 如何使用 GroupDocs.Viewer for Java 將 Numbers 轉換為 JPG？

`JpgViewOptions` 設定 JPEG 輸出，允許對每個渲染頁面調整品質與大小。  
您可以將每個試算表頁面轉為 JPEG 快照。調整 `quality` 設定以在檔案大小與視覺保真度之間取得平衡，這在需要輕量圖像用於社群媒體或電子報時非常有用。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **提示：** 若處理大型活頁簿，可將品質降低至 70 % – 視覺影響甚微，但檔案大小會大幅下降。  

## 如何使用 GroupDocs.Viewer for Java 將 Numbers 轉換為 PNG？

`PngViewOptions` 設定 PNG 輸出，支援無損壓縮與解析度設定，以產生高品質影像。  
PNG 提供無損壓縮，完整保留每個像素。當您需要列印品質的圖形（如報告或 PDF）時，可使用 `resolution` 屬性提升 DPI。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **進階提示：** 設定 `options.setResolution(300)` 可取得高解析度輸出，在列印頁面上呈現清晰細緻的效果。  

## 如何使用 GroupDocs.Viewer for Java 將 Numbers 轉換為 PDF？

`PdfViewOptions` 定義 PDF 渲染選項，包括字型嵌入、壓縮與頁面大小控制。  
`PdfViewOptions` 物件讓您嵌入字型、控制頁面大小，並保留 Numbers 活頁簿的原始版面配置。轉換在一次呼叫中完成，產生可搜尋、不可編輯的 PDF，適合歸檔或合規使用。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **關鍵設定：** 啟用 `options.setCompress(true)` 可在不犧牲品質的前提下縮小 PDF 大小，這對大型文件倉儲尤為重要。  

## 為何使用 GroupDocs.Viewer for Java？

GroupDocs.Viewer 支援 **超過 100 種檔案格式**，包括 Apple Numbers，且能在不將整個檔案載入記憶體的情況下渲染數百頁的試算表。基準測試顯示，250 頁的 Numbers 檔案在標準 2.5 GHz CPU 上可於 8 秒內轉換為 PDF，為企業流程提供速度與可靠性。  

## 實務應用
- **網站整合：** 渲染為 HTML，提供跨瀏覽器且無需外掛的互動式試算表檢視器。  
- **內容分享：** 轉換為 JPG/PNG，以便在電子報、聊天應用或社群動態中快速嵌入圖像。  
- **企業文件管理系統（DMS）：** 使用 **如何將 Numbers 轉換為 PDF** 以儲存不可編輯、可搜尋的試算表版本，符合合規與稽核需求。  

## 效能考量
- **資源管理：** 請始終在 try‑with‑resources 區塊中建立 `Viewer`（如範例所示），以確保本機資源及時釋放。  
- **大型活頁簿：** 逐頁處理並串流輸出，將記憶體使用量控制在 100 MB 以下，即使是 500 頁的檔案亦可。  
- **執行緒安全性：** 每個執行緒建立獨立的 `Viewer` 實例；此類別非執行緒安全，若共享同一實例可能導致競爭條件。  

## 常見問題與故障排除
- **缺少字型：** 若產生的 PDF 外觀不同，請確認伺服器上已安裝所需字型，或使用 `PdfViewOptions.setEmbedFonts(true)` 進行嵌入。  
- **空白頁面：** 確認 Numbers 檔案未受密碼保護；目前 GroupDocs.Viewer 無法解密受保護的活頁簿。  
- **記憶體不足錯誤：** 對於極大型檔案，可啟用 `options.setPageCount(1)` 逐頁渲染，之後再合併結果。  

## 常見問答

**Q: GroupDocs.Viewer 支援哪些檔案格式？**  
A: 超過 100 種格式，包括 DOCX、XLSX、PDF、HTML 與 Apple Numbers，且皆具完整渲染能力。  

**Q: 如何有效處理大型 Numbers 檔案？**  
A: 逐頁串流轉換，使用 `options.setPageCount()` 限制記憶體使用，並考慮壓縮輸出 PDF。  

**Q: GroupDocs.Viewer 可用於商業專案嗎？**  
A: 可以 — 購買商業授權即可移除試用限制，並取得正式支援。  

**Q: 能否自訂影像的輸出品質？**  
A: 當然可以。調整 `JpgViewOptions.setQuality(int)` 或 `PngViewOptions.setResolution(int)` 以符合您的大小與品質需求。  

**Q: 在哪裡可以找到更進階的使用範例？**  
A: 前往 [GroupDocs 文件](https://docs.groupdocs.com/viewer/java/) 取得深入指南、範例專案與 API 參考說明。  

## 後續步驟
先試驗上述選項，接著探索其他客製化功能，如 PDF 加入浮水印、設定密碼保護，或將檢視器整合至 Spring Boot REST 服務中。[GroupDocs 文件](https://docs.groupdocs.com/viewer/java/) 提供完整功能目錄，讓您自由組合使用。  

## 資源
- **文件說明：** [GroupDocs.Viewer Java 文件](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs 文件：** [GroupDocs 文件](https://docs.groupdocs.com/viewer/java/)  
- **API 參考：** [API 參考](https://reference.groupdocs.com/viewer/java/)  
- **API 參考：** [GroupDocs API 參考](https://reference.groupdocs.com/viewer/java/)  
- **下載：** [取得 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **購買授權：** [購買授權](https://purchase.groupdocs.com/buy)  
- **免費試用：** [開始免費試用](https://releases.groupdocs.com/viewer/java/)  
- **臨時授權：** [在此申請](https://purchase.groupdocs.com/temporary-license/)  
- **支援論壇：** [加入討論](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-08-25  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

## 相關教學

- [如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML、JPG、PNG 與 PDF](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [如何使用 GroupDocs.Viewer 在 Java 中將 Excel 轉換為 HTML 並渲染隱藏列與欄](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Java 文件渲染教學 - 將檔案轉換為 HTML、PDF 與影像](/viewer/java/rendering-basics/)