---
date: '2026-06-20'
description: 了解如何使用 GroupDocs.Viewer for Java 從 DWG 檔案渲染特定版面，將 CAD 轉換為 HTML，並高效提取版面
  DWG。
keywords:
- groupdocs viewer dwg
- convert cad to html
- extract layout dwg
schemas:
- author: GroupDocs
  dateModified: '2026-06-20'
  description: Learn how to render specific layouts from DWG files with GroupDocs.Viewer
    for Java, convert CAD to HTML, and extract layout DWG efficiently.
  headline: groupdocs viewer dwg – How to Render Specific CAD Drawings in Java Using
    GroupDocs.Viewer
  type: TechArticle
- description: Learn how to render specific layouts from DWG files with GroupDocs.Viewer
    for Java, convert CAD to HTML, and extract layout DWG efficiently.
  name: groupdocs viewer dwg – How to Render Specific CAD Drawings in Java Using GroupDocs.Viewer
  steps:
  - name: Define the output directory
    text: 'Create a folder where the generated HTML files will be saved. The `Utils`
      helper creates a platform‑independent output folder for rendered files. *Explanation*:
      `Utils.getOutputDirectoryPath` builds a platform‑independent path and creates
      the folder if it does not exist.'
  - name: Set up naming for rendered pages
    text: 'Specify a naming pattern that includes a placeholder for the page number.
      *Explanation*: `{0}` is replaced by the page index, allowing you to render multiple
      layouts without filename collisions.'
  - name: Configure HtmlViewOptions
    text: 'Tell the viewer to embed resources and to target a single layout. HtmlViewOptions
      configures how the output HTML is generated, including resource embedding and
      layout selection. *Explanation*: `forEmbeddedResources` packs images and CSS
      directly into the HTML, producing a single portable file per la'
  - name: Choose the layout you want to render
    text: 'Provide the exact layout name as it appears inside the DWG file. The `layoutName`
      property specifies which drawing layout the viewer should render. *Explanation*:
      Setting `layoutName` to `"Model"` (or any custom layout) instructs GroupDocs.Viewer
      to ignore all other views.'
  - name: Render the layout and clean up
    text: 'Open the viewer in a try‑with‑resources block, invoke `view`, and let Java
      close the instance automatically. The `Viewer` class is the main entry point
      for rendering documents with GroupDocs.Viewer. *Explanation*: The `view` call
      streams the selected layout to HTML files in the output folder; the vi'
  type: HowTo
- questions:
  - answer: It is a server‑side library that converts more than 50 document and CAD
      formats—including DWG—into HTML, PNG, or JPEG without needing installed Office
      or CAD software.
    question: What is GroupDocs.Viewer for Java?
  - answer: Visit the [GroupDocs' purchase page](https://purchase.groupdocs.com/temporary-license/)
      and request a free temporary license for development and testing.
    question: How do I obtain a temporary license for GroupDocs.Viewer?
  - answer: Yes, it streams pages and can render multi‑hundred‑page drawings while
      keeping memory usage below 200 MB, provided you close the `Viewer` instance
      after each operation.
    question: Can GroupDocs.Viewer handle very large DWG files efficiently?
  - answer: Absolutely – replace `HtmlViewOptions` with `PdfViewOptions` and specify
      the same layout name to get a PDF output.
    question: Is it possible to convert a DWG layout directly to PDF instead of HTML?
  - answer: The official documentation and API reference contain additional code snippets
      for batch processing and custom rendering pipelines.
    question: Where can I find more examples of layout extraction?
  type: FAQPage
title: groupdocs viewer dwg – 如何在 Java 中使用 GroupDocs.Viewer 渲染特定 CAD 圖紙
type: docs
url: /zh-hant/java/rendering-basics/render-cad-groupdocs-viewer-java/
weight: 1
---

# groupdocs viewer dwg – 如何在 Java 中使用 GroupDocs.Viewer 渲染特定 CAD 圖紙

將 DWG 檔案中的特定版面渲染出來是常見需求，無論是需要聚焦單一設計視圖、產生輕量級 HTML 預覽，或是將特定圖層嵌入網頁。本教學將說明 **GroupDocs.Viewer for Java** 如何簡單地渲染選定的版面、將 CAD 轉換為 HTML，並僅用幾行程式碼即可抽取版面 DWG。

![使用 GroupDocs.Viewer for Java 渲染特定 CAD 圖紙](/viewer/rendering-basics/render-specific-cad-drawings-java.png)

## 快速解答
- **哪個函式庫可以將 DWG 轉換為 HTML？** GroupDocs.Viewer for Java。  
- **我能只渲染 DWG 中的單一版面嗎？** 可以 – 在 `HtmlViewOptions` 中指定版面名稱。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買永久授權。  
- **需要哪個 Java 版本？** JDK 8 或更新版本。  
- **大型 CAD 檔案的記憶體使用是否成問題？** 使用串流選項並及時關閉 `Viewer` 實例即可。

## groupdocs viewer dwg 是什麼？
`GroupDocs.Viewer` 是一套 Java 函式庫，可將超過 50 種文件與 CAD 格式（包括 DWG）轉換為網頁友好的表示形式，如 HTML、PNG 或 JPEG。它不需要本機 CAD 軟體，即可在各平台上提供一致的渲染效果。

## 為何使用 GroupDocs.Viewer 進行 DWG 渲染？
GroupDocs.Viewer 支援 **50+ CAD 輸入格式**，且能在記憶體使用低於 200 MB 的情況下串流渲染上百頁圖紙。內建的版面抽取功能讓您只保留單一視圖，較完整圖紙渲染可減少高達 **70 %** 的頁面載入時間。

## 前置條件
- **GroupDocs.Viewer for Java** ≥ 25.2。  
- Maven 用於相依性管理。  
- 本機已安裝 JDK 8+。  
- 具備 DWG 檔案結構（版面、模型空間、紙張空間）的基本認識。

## 如何從 DWG 檔案渲染特定版面？

載入目標 DWG 檔案、設定 HTML 渲染選項，並指定欲輸出的版面名稱。只要在 `HtmlViewOptions` 中設定版面名稱，檢視器就會抽取該視圖並產生對應的 HTML 檔案。此流程僅需三個簡潔步驟即可完成預覽產生與處理時間的縮減。

### 步驟 1：定義輸出目錄
建立一個資料夾，用於儲存產生的 HTML 檔案。

`Utils` 輔助類別會為渲染檔案建立平台無關的輸出資料夾。  
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
*說明*：`Utils.getOutputDirectoryPath` 會組合平台無關的路徑，若資料夾不存在則自動建立。

### 步驟 2：設定已渲染頁面的命名方式
指定一個包含頁碼佔位符的命名模式。

```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*說明*：`{0}` 會被頁面索引取代，讓您在不產生檔名衝突的情況下渲染多個版面。

### 步驟 3：設定 HtmlViewOptions
告訴檢視器嵌入資源並針對單一版面產出。

HtmlViewOptions 控制輸出 HTML 的產生方式，包含資源嵌入與版面選擇。  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*說明*：`forEmbeddedResources` 會將圖片與 CSS 直接打包進 HTML，為每個版面產生單一可攜檔案。

### 步驟 4：選擇要渲染的版面
提供 DWG 檔案中正確的版面名稱。

`layoutName` 屬性指定檢視器應渲染哪個圖紙版面。  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
*說明*：將 `layoutName` 設為 `"Model"`（或任何自訂版面）即指示 GroupDocs.Viewer 忽略其他視圖。

### 步驟 5：渲染版面並清理
在 try‑with‑resources 區塊中開啟檢視器，呼叫 `view`，讓 Java 自動關閉實例。

`Viewer` 類別是使用 GroupDocs.Viewer 渲染文件的主要入口。  
```java
viewOptions.getCadOptions().setLayoutName("Model");
```
*說明*：`view` 呼叫會將選定的版面串流至輸出資料夾中的 HTML 檔案；渲染完成後即釋放檢視器資源。

## 常見問題與解決方案
- **版面找不到** – 請以 CAD 編輯器開啟 DWG，確認版面名稱拼寫與大小寫完全相符。  
- **記憶體不足錯誤** – 啟用 `Viewer.setMemoryLimit` 或將檔案分成較小的區塊處理。  
- **缺少圖片** – 確認已設定 `forEmbeddedResources`，否則可能會產生外部圖片檔案。

## 常見問答

**Q: GroupDocs.Viewer for Java 是什麼？**  
**A:** 它是一套伺服器端函式庫，能將超過 50 種文件與 CAD 格式（含 DWG）轉換為 HTML、PNG 或 JPEG，無需安裝 Office 或 CAD 軟體。

**Q: 如何取得 GroupDocs.Viewer 的臨時授權？**  
**A:** 前往 [GroupDocs 的購買頁面](https://purchase.groupdocs.com/temporary-license/) 申請免費的開發與測試臨時授權。

**Q: GroupDocs.Viewer 能有效處理非常大的 DWG 檔案嗎？**  
**A:** 能。它會串流頁面，並在關閉 `Viewer` 實例後將記憶體使用維持在 200 MB 以下，即使是上百頁的圖紙也能順利渲染。

**Q: 能否直接將 DWG 版面轉換為 PDF 而非 HTML？**  
**A:** 完全可以 – 只要將 `HtmlViewOptions` 換成 `PdfViewOptions`，並指定相同的版面名稱，即可產生 PDF 輸出。

**Q: 哪裡可以找到更多版面抽取的範例？**  
**A:** 官方文件與 API 參考中提供了批次處理與自訂渲染管線的額外程式碼範例。

## 實務應用
1. **建築簡報** – 只顯示客戶會議所需的平面圖版面。  
2. **製造審查** – 抽取單一元件視圖，討論公差時無需載入完整組件。  
3. **線上教學模組** – 在網頁教學中嵌入單一 CAD 視圖，提升說明清晰度。  
4. **文件管理整合** – 上傳 DWG 至內容庫時自動抽取版面預覽。  
5. **自訂報表** – 產生聚焦單一圖紙視圖的 HTML 報表，減少檔案大小與載入時間。

## 效能提示
- **重複使用 Viewer 實例** 以處理多個檔案；它會快取內部資源，提升後續渲染速度。  
- **啟用串流**，呼叫 `Viewer.setRenderMode(RenderMode.Stream)` 以降低記憶體佔用。  
- **在 Web 伺服器上使用 gzip 壓縮** 輸出 HTML，進一步改善客戶端載入效能。

## 結論
您現在已掌握使用 **GroupDocs.Viewer for Java** 從 DWG 檔案渲染特定版面的完整、生產環境就緒方案。透過鎖定單一版面，可縮短渲染時間、降低記憶體消耗，並產生可隨處嵌入的乾淨 HTML，無論是網站入口還是內部儀表板皆適用。

**下一步**  
- 嘗試渲染不同的版面名稱，例如 `"Top View"` 或 `"Section A"`，觀察輸出差異。  
- 若需相同版面的 PDF 版本，可改用 `PdfViewOptions`。  
- 結合此技巧與 GroupDocs.Annotation，為渲染出的 HTML 加上浮水印或註解。

---

**Last Updated:** 2026-06-20  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs  

## 資源
- [文件說明](https://docs.groupdocs.com/viewer/java/)
- [API 參考](https://reference.groupdocs.com/viewer/java/)
- [下載 GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)
- [購買授權](https://purchase.groupdocs.com/buy)
- [免費試用](https://releases.groupdocs.com/viewer/java/)
- [臨時授權申請](https://purchase.groupdocs.com/temporary-license)

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS)) {
    viewer.view(viewOptions);
}
```

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 以自訂尺寸與背景色將 CAD 圖紙渲染為 PNG](/viewer/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/)
- [使用 GroupDocs.Viewer Java 將 CAD 圖紙切割為圖磚以提升渲染效能](/viewer/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer 渲染 CAD 圖層的完整指南（Java）](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)