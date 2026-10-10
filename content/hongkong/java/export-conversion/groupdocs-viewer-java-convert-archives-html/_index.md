---
date: '2026-10-10'
description: 了解如何使用 GroupDocs.Viewer Java 將 zip 轉換為 html、設定每頁項目數、嵌入資源 html，並高效批量轉換壓縮檔案。
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: 了解如何使用 GroupDocs.Viewer Java 將 zip 轉換為 html、嵌入資源、設定每頁項目數，並批量處理壓縮檔案，以實現快速、可攜式的網頁預覽。
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: 使用 GroupDocs.Viewer Java 轉換 zip 為 HTML 並加入分頁功能
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: 使用 GroupDocs.Viewer Java 將 zip 轉換為 html 並設定每頁項目數
type: docs
url: /zh-hant/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 zip 轉換為 html 並設定每頁項目數量，使用 GroupDocs.Viewer Java

在許多 Web 應用程式中，您需要直接在瀏覽器中顯示 ZIP 或 RAR 壓縮檔的內容。**如何將 zip 轉換** 為 HTML 是常見需求，且該函式庫允許您嵌入圖片、CSS 與字型，使最終產出為單一、可攜帶的頁面。本教學將帶您逐步完成所有步驟——從 Maven 設定到多頁面渲染——同時說明每個選項對效能與可用性的影響。

![使用 GroupDocs.Viewer for Java 將壓縮檔轉換為 HTML](/viewer/export-conversion/convert-archives-to-html-java.png)

## 快速解答
- **「set items per page」控制什麼？** 它決定每個產生的 HTML 頁面上會顯示多少個來自壓縮檔的檔案或資料夾。  
- **我可以直接在 HTML 中嵌入圖片和 CSS 嗎？** 是 – 使用 `forEmbeddedResources` 選項將資源嵌入 HTML。  
- **是否支援批次轉換？** 當然可以；您可以遍歷一系列壓縮檔，並以相同設定渲染每個檔案。  
- **使用 GroupDocs.Viewer 是否需要 Maven？** 是，請如以下示範加入 `groupdocs-viewer` Maven 依賴。  
- **支援哪些輸出格式？** 單頁 HTML 與多頁 HTML 均可使用，且函式庫支援超過 50 種輸入壓縮檔類型。

## 「set items per page」在 GroupDocs.Viewer 中的意義
它告訴檢視器在產生多頁文件時，每個 HTML 頁面應顯示多少個壓縮檔條目（檔案或資料夾）。調整此數值可協助您在大型壓縮檔中平衡頁面大小與導覽速度，透過限制每頁載入的資料量來減少最終使用者的渲染時間。

## 為什麼要嵌入資源 HTML？
將資源（圖片、CSS、字型）直接嵌入 HTML 檔案中，可產生單一、可攜帶的文件，無需外部檔案即可開啟。這對於電子郵件附件、離線檢視或將輸出嵌入其他網頁非常理想，同時也免除管理外部資產路徑的需求。

## 前置條件

- **必要的函式庫：** 包含 GroupDocs.Viewer 版本 25.2 或更新版本。  
- **環境：** 已安裝並配置 Java Development Kit（JDK）。  
- **知識需求：** 基本的 Java 與 Maven 依賴管理。  

## Maven GroupDocs Viewer 設定

將 GroupDocs 倉庫與檢視器依賴加入您的 `pom.xml`：

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
GroupDocs.Viewer 提供 **免費試用連結**、臨時授權或完整購買選項。請選擇最符合您專案時程的方案。

## 基本初始化
`Viewer` 類別是渲染文件與壓縮檔的入口點。完成 Maven 設定後，將檢視器引入程式碼中：

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 如何將壓縮檔渲染為單頁 HTML
`HtmlViewOptions` 類別定義 HTML 輸出的設定，例如嵌入資源。載入壓縮檔、設定 HTML 選項以嵌入資源，並將所有內容渲染至單一自包含頁面。這會產生一個包含所有檔案、圖片、CSS 與字型的單一 HTML 檔案，可供離線使用或作為電子郵件附件。

**直接答案：** 為 ZIP 檔建立 `Viewer` 實例，呼叫 `HtmlViewOptions.forEmbeddedResources()`，並執行 `viewer.view(documentPath, options)`。此操作會產生一個包含所有檔案、圖片、CSS 與字型的單一 HTML 檔案，可供離線使用或作為電子郵件附件。

### 步驟 1：定義輸出目錄
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步驟 2：設定單頁輸出的檔名
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 步驟 3：初始化檢視器
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 步驟 4：設定渲染選項（嵌入資源 HTML）
`HtmlViewOptions` 類別定義 HTML 輸出的設定，例如嵌入資源。使用 `forEmbeddedResources()` 可將所有內容打包成單一檔案。

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步驟 5：渲染為單一頁面
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 如何將壓縮檔渲染為多頁 HTML 並設定每頁項目數量
`HtmlViewOptions` 類別亦支援分頁。透過呼叫 `options.setItemsPerPage(N)`，您可指示檢視器將壓縮檔分割為多個 HTML 檔案，每個檔案顯示最多 **N** 個條目。此方式可提升大型壓縮檔的導覽速度，同時保持每頁輕量。

**直接答案：** 使用 `HtmlViewOptions.forEmbeddedResources()`，呼叫 `options.setItemsPerPage(N)`，然後渲染壓縮檔。檢視器會產生多個 HTML 檔案——每頁一個——每個檔案包含最多 **N** 個條目，從而加快大型壓縮檔的導覽速度。

### 步驟 1：重用輸出目錄
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步驟 2：定義多頁檔名格式
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 步驟 3：再次初始化檢視器
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 步驟 4：設定多頁選項（嵌入資源 HTML）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步驟 5：設定每頁項目數量（主要關鍵字）
`options.setItemsPerPage(20); // how to convert zip archives with 20 entries per page`
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 實務應用

- **文件管理系統：** 在不安裝額外檢視器的情況下加入壓縮檔預覽功能。  
- **Web 入口網站：** 為使用者提供快速、免下載的方式來瀏覽打包文件。  
- **協作工具：** 讓團隊直接在瀏覽器中檢視共享的壓縮檔。  

## 效能考量

- **資源管理：** 透過串流處理壓縮檔以降低記憶體使用量；檢視器可處理高達 500 MB 的壓縮檔，且無需將整個檔案載入記憶體。  
- **批次轉換壓縮檔：** 遍歷壓縮檔清單，呼叫相同的渲染邏輯以提升吞吐量。  
- **快取策略：** 若同一壓縮檔被頻繁存取，將渲染後的 HTML 存入快取，可將重複處理時間降低至 70 % 以內。  

## 常見問題

**Q: 什麼是 GroupDocs.Viewer Java？**  
**A:** GroupDocs.Viewer Java 是一個伺服器端函式庫，可將超過 50 種文件與壓縮檔格式（包括 ZIP 與 RAR）渲染為 HTML、PDF 或影像檔，且不需外部應用程式。

**Q: 如何取得 GroupDocs.Viewer 的免費試用？**  
**A:** 前往 [free trial link](https://releases.groupdocs.com/viewer/java/) 下載並測試。

**Q: 我可以轉換除壓縮檔外的其他文件類型嗎？**  
**A:** 可以，檢視器支援 PDF、Word、Excel、PowerPoint 以及超過 35 種其他格式。

**Q: 若渲染速度緩慢該怎麼辦？**  
**A:** 減少每頁項目數量、啟用串流，或將壓縮檔分成較小批次處理，以提升速度。

**Q: 我可以從哪裡取得協助或支援？**  
**A:** 透過 [support forum](https://forum.groupdocs.com/c/viewer/9) 聯繫我們。

**Q: 是否可以直接在 HTML 中嵌入 CSS 與圖片？**  
**A:** 當然可以——如範例所示，使用 `HtmlViewOptions.forEmbeddedResources`。

**Q: 如何批次轉換一個資料夾中的壓縮檔？**  
**A:** 使用 `for` 迴圈遍歷每個檔案，對每次迭代套用相同的 `Viewer` 與 `HtmlViewOptions` 設定。

**Q: 我可以在哪裡與其他使用者討論問題？**  
**A:** 前往 [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) 參與社群討論。

## 資源

- **文件說明：** 深入了解功能，請參閱 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)。  
- **API 參考：** 在 [GroupDocs API](https://reference.groupdocs.com/viewer/java/) 查看完整 API。  
- **下載：** 從 [download page](https://releases.groupdocs.com/viewer/java/) 取得最新二進位檔。  
- **購買與授權：** 在 [purchase page](https://purchase.groupdocs.com/buy) 檢視選項。  
- **支援與社群：** 在 [support forum](https://forum.groupdocs.com/c/viewer/9) 參與討論。  
- **GroupDocs 論壇：** 於 [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) 獲取社群協助。

---

**最後更新：** 2026-10-10  
**測試環境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs

## 相關教學

- [如何將 zip 轉換為 HTML 並在 Java 中使用 GroupDocs.Viewer 渲染 zip 資料夾](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer Java 將 zip 轉換為 PDF - 自訂檔名](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [如何使用 GroupDocs.Viewer for Java 將 DOCX 轉換為 HTML：逐步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}