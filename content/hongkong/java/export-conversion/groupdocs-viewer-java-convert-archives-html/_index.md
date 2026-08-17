---
date: '2026-08-03'
description: 了解如何使用 GroupDocs.Viewer Java 將 zip 轉換為 html、設定每頁項目數、嵌入資源 html，並高效批量轉換壓縮檔。
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: 了解如何使用 GroupDocs.Viewer Java 將 zip 轉換為 html、設定每頁項目數、嵌入資源 html，並高效批量轉換壓縮檔。遵循逐步程式碼與效能技巧。
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: 使用 GroupDocs.Viewer Java 將 zip 轉換為 html 並設定每頁項目數
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
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

# 使用 GroupDocs.Viewer Java 將 zip 轉換為 html 並設定每頁項目數量

在許多網頁應用程式中，您需要直接在瀏覽器中顯示 ZIP 或 RAR 壓縮檔的內容。使用 GroupDocs.Viewer for Java，您可以在單一步驟中 **將 zip 轉換為 html**，控制每個頁面顯示的壓縮檔條目數量，嵌入所有相關的圖片和 CSS，甚至批次處理數十個壓縮檔。本教學將帶您完整了解工作流程，從 Maven 設定到多頁面渲染，並說明每個設定對效能與可用性的影響。

![使用 GroupDocs.Viewer for Java 將壓縮檔轉換為 HTML](/viewer/export-conversion/convert-archives-to-html-java.png)

## 快速解答
- **「set items per page」控制什麼？** 它決定每個產生的 HTML 頁面上會顯示多少個壓縮檔中的檔案或資料夾。  
- **我可以直接在 HTML 中嵌入圖片和 CSS 嗎？** 可以 – 使用 `forEmbeddedResources` 選項將資源嵌入 HTML。  
- **是否支援批次轉換？** 當然可以；您可以遍歷壓縮檔集合，使用相同設定渲染每個檔案。  
- **使用 GroupDocs.Viewer 是否需要 Maven？** 需要，請如以下示範加入 `groupdocs-viewer` Maven 依賴。  
- **支援哪些輸出格式？** 單頁 HTML 與多頁 HTML 均可使用，且此函式庫支援超過 50 種輸入壓縮檔類型。

## GroupDocs.Viewer 中的「set items per page」是什麼？
**set items per page** 設定屬於壓縮檔渲染選項。它告訴檢視器在產生多頁 HTML 文件時，每個 HTML 頁面應顯示多少個壓縮檔條目（檔案或資料夾）。調整此數值可協助您在頁面大小與導覽速度之間取得平衡，特別是針對大型壓縮檔。

## 為什麼要嵌入資源 HTML？
將資源（圖片、CSS、字型）直接嵌入 HTML 檔案中，可產生單一且可攜帶的文件，無需外部檔案即可開啟。這對於電子郵件附件、離線檢視或將輸出嵌入其他網頁特別適合。此方式亦簡化部署，因為不必管理外部資產路徑。

## 前置條件
- **必要函式庫：** 包含 GroupDocs.Viewer 版本 25.2 或更新版本。  
- **環境：** 已安裝並設定 Java Development Kit (JDK)。  
- **知識需求：** 基本的 Java 與 Maven 依賴管理。  

## Maven GroupDocs Viewer 設定
將 GroupDocs 儲存庫與 viewer 依賴加入您的 `pom.xml`：

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
GroupDocs.Viewer 提供 **免費試用連結**、臨時授權或完整購買方案。請依您的專案時程選擇合適的方案。

### 基本初始化
完成 Maven 設定後，將 viewer 引入程式碼中：

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 如何將壓縮檔渲染為單頁 html
Viewer 是用於載入文件或壓縮檔以進行渲染的核心類別。

若要產生包含整個壓縮檔的單一 HTML 檔案，請為 ZIP 檔建立 `Viewer` 實例，並使用 `HtmlViewOptions.forEmbeddedResources()` 來嵌入所有圖片、CSS 與字型。使用此選項渲染壓縮檔會產生一個自包含的頁面，適合用於電子郵件或離線使用。

### 步驟 1：定義輸出目錄
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步驟 2：設定單頁輸出的檔名
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 步驟 3：初始化 viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 步驟 4：設定渲染選項（嵌入資源 HTML）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步驟 5：渲染為單一頁面
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 如何將壓縮檔渲染為多頁 html 並設定每頁項目數量
`HtmlViewOptions` 設定 viewer 渲染 HTML 輸出的方式，包含分頁與資源嵌入。

若要將壓縮檔分割為多個頁面，請建立 `HtmlViewOptions.forEmbeddedResources()`，並使用 `options.setItemsPerPage(20)` 設定每頁的項目數量。viewer 會產生多個 HTML 檔案，每個檔案顯示最多指定數量的條目，這可提升大型壓縮檔的導覽體驗並加快載入速度。

### 步驟 1：重複使用輸出目錄
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步驟 2：定義多頁檔名格式
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 步驟 3：再次初始化 viewer
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
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 實務應用
- **文件管理系統：** 在不安裝額外檢視器的情況下加入壓縮檔預覽功能。  
- **Web 入口網站：** 為使用者提供快速、免下載的方式來瀏覽打包文件。  
- **協作工具：** 讓團隊直接在瀏覽器中檢查共享的壓縮檔。  

## 效能考量
- **資源管理：** 透過串流處理壓縮檔以降低記憶體使用量；viewer 可處理高達 500 MB 的壓縮檔，且無需將整個檔案載入記憶體。  
- **批次轉換壓縮檔：** 迭代壓縮檔清單，呼叫相同的渲染邏輯以提升吞吐量。  
- **快取策略：** 若同一壓縮檔被頻繁存取，將渲染後的 HTML 存入快取，可將重複處理時間降低至 70 % 以內。  

## 常見問題
**Q: GroupDocs.Viewer Java 是什麼？**  
A: GroupDocs.Viewer Java 是一套伺服器端函式庫，可將超過 50 種文件與壓縮檔格式（包括 ZIP 與 RAR）渲染為 HTML、PDF 或影像檔，且不需外部應用程式。

**Q: 如何取得 GroupDocs.Viewer 的免費試用？**  
A: 前往 [free trial link](https://releases.groupdocs.com/viewer/java/) 下載並測試。

**Q: 除了壓縮檔，我可以轉換其他文件類型嗎？**  
A: 可以，viewer 支援 PDF、Word、Excel、PowerPoint 以及超過 35 種其他格式。

**Q: 若渲染速度緩慢該怎麼辦？**  
A: 減少每頁項目數量、啟用串流，或將壓縮檔分成較小批次處理，以提升速度。

**Q: 我可以在哪裡取得協助或支援？**  
A: 透過 [support forum](https://forum.groupdocs.com/c/viewer/9) 聯繫我們。

**Q: 是否可以直接在 HTML 中嵌入 CSS 與圖片？**  
A: 完全可以——如範例所示，使用 `HtmlViewOptions.forEmbeddedResources`。

**Q: 如何批次轉換資料夾中的壓縮檔？**  
A: 使用 `for` 迴圈遍歷每個檔案，對每次迭代套用相同的 `Viewer` 與 `HtmlViewOptions` 設定。

## 資源
- **文件說明：** 透過 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) 深入了解功能。  
- **API 參考：** 前往 [GroupDocs API](https://reference.groupdocs.com/viewer/java/) 探索完整 API。  
- **下載：** 從 [download page](https://releases.groupdocs.com/viewer/java/) 取得最新二進位檔。  
- **購買與授權：** 在 [purchase page](https://purchase.groupdocs.com/buy) 查看方案。  
- **支援與社群：** 於 [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) 參與討論。  

---

**最後更新：** 2026-08-03  
**測試環境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs

## 相關教學
- [如何將 zip 轉換為 HTML 並在 Java 中使用 GroupDocs.Viewer 渲染 zip 資料夾](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer Java 將 zip 轉換為 pdf - 自訂檔名](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [如何使用 GroupDocs.Viewer for Java 將 DOCX 轉換為 HTML：逐步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)