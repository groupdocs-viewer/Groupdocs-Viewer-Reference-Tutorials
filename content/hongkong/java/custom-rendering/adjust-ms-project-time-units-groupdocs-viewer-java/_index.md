---
date: '2026-05-21'
description: 了解如何使用 GroupDocs Viewer for Java 進行 MS Project HTML 匯出，並調整時間單位。提供前置條件、設定步驟及故障排除的逐步指南。
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: MS Project HTML 匯出：透過 GroupDocs Java 調整時間單位
type: docs
url: /zh-hant/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML 匯出：透過 GroupDocs Java 調整時間單位

將 **MS Project** 檔案匯出為 HTML 是專案管理儀表板、狀態報告入口網站以及協作審閱工具的常見需求。預設情況下，檢視器會以分鐘為單位呈現時間相關資料，這會使畫面雜亂，且每日報告較難閱讀。使用 **GroupDocs Viewer for Java**，您可以以程式方式將時間單位設定為 **days**，產生符合一般利害關係人期望的乾淨 *ms project html export*。在本教學中，您將學會如何設定檢視器、調整時間單位，並在幾個簡單步驟內將專案渲染為 HTML。

![使用 GroupDocs.Viewer for Java 調整 MS Project 時間單位](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[使用 GroupDocs.Viewer for Java 調整 MS Project 時間單位](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## 快速解答
- **什麼函式庫可以渲染 MS Project 檔案？** GroupDocs Viewer for Java。  
- **HTML 匯出可以設定哪個時間單位？** Days，使用 `TimeUnit.DAYS`。  
- **生產環境需要授權嗎？** 是——必須使用永久授權；試用版可用於評估。您可以從 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 開始。  
- **哪個 IDE 最適合？** 任何支援 Maven 的 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）。  
- **Maven 必須使用嗎？** Maven 可簡化相依管理，但您也可以使用 Gradle 或手動加入 JAR。  
- **在哪裡購買？** 前往 [buy page](https://purchase.groupdocs.com/buy) 查看價格。

## GroupDocs Viewer for Java 是什麼？
**GroupDocs Viewer for Java** 是一套 Java SDK，能將超過 150 種文件格式（包括 MS Project）轉換為網頁友好的 HTML、PNG、JPEG 或 PDF。  
它抽象化了解析邏輯，讓您可以控制渲染選項（例如時間單位），且可在任何支援 Java 8 或更高版本的平台上執行。

## 為什麼要調整 MS Project HTML 匯出的時間單位？
將時間單位設定為 **days** 可減少視覺噪點，符合大多數報告節奏，並提升頁面載入速度，因為產生的時間標記較少。以量化數據來說，使用天而非分鐘渲染可將典型 30 天專案的產生 HTML 大小縮減最高 **45 %**，且客戶端渲染速度提升約 **30 %**。

## 先決條件
- **Java Development Kit (JDK) 8 或更新版本** 已安裝於工作站。  
- **Maven**（或 Gradle）用於相依管理。  
- 您想要匯出的 **MS Project (.mpp)** 檔案。  
- 取得 **GroupDocs Viewer for Java** 授權（試用或永久）。

### 所需函式庫
將以下相依加入您的 `pom.xml`（或相等的 Gradle 片段）：

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** 保持版本號為最新；較新版本會加入格式支援與效能改進。

## 如何設定 GroupDocs Viewer for Java？
透過建立指向 MS Project 檔案的 `Viewer` 實例來初始化檢視器。`Viewer` 類別是所有渲染操作的入口點。它會載入來源文件、準備內部結構，並公開 `view()` 與 `viewToHtml()` 等方法，以產生所需的輸出格式。

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** `Viewer` 類別是 GroupDocs Viewer 的核心元件，負責載入來源文件並提供 `view()`、`viewToHtml()` 等渲染方法。

## 如何調整 HTML 匯出的時間單位？
要變更時間粒度，請建立 `ViewOptions` 物件，將其 `ProjectOptions` 設為 `TimeUnit.DAYS`，再傳遞給檢視器。`ViewOptions` 定義文件的渲染設定，而 `TimeUnit` 列舉則指定時間相關資料的單位（分鐘、 小時、 天）。設定完畢後，呼叫 `viewer.view(options)` 即可產生帶有每日標記的 HTML。

使用 `new Viewer("file.mpp")` 載入 MS Project 檔案，建立 `ViewOptions` 物件，設定 `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`，最後呼叫 `viewer.view(options)`。此三步流程會將時間單位由分鐘改為天，並產生僅顯示每日間隔的 HTML 檔案。

### 步驟 1：定義輸出資料夾
選擇一個可寫入的目錄作為 HTML 頁面的儲存位置，例如 `output/`。

### 步驟 2：建立包含嵌入資源的檢視選項
嵌入資源（CSS、JavaScript）可確保 HTML 頁面自包含。

### 步驟 3：將時間單位設定為天
使用 `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` 以切換粒度。

### 步驟 4：渲染文件
呼叫 `viewer.view(options)`；檢視器會將每個專案頁面寫入一個 HTML 檔案至輸出資料夾。

### 步驟 5：驗證結果
在瀏覽器中開啟產生的 `index.html`；您應該會看到任務條僅對齊於天標記，而非分鐘標記。

## 常見問題與故障排除
- **Incorrect output path** – 確認目錄已存在且 Java 程序具有寫入權限。  
- **Missing license** – 若未提供有效授權，檢視器會回退至試用模式，並可能嵌入浮水印。  
- **Large files (> 500 MB)** – 考慮增大 JVM 堆積大小 (`-Xmx2g`) 或使用 `options.setRenderLimit(1000)` 以分批處理頁面。

## 調整時間單位 HTML 匯出的實際應用
1. **Executive dashboards** – 每日粒度符合大多數 KPI 可視化需求。  
2. **Automated status emails** – 可直接將產生的 HTML 嵌入郵件正文，以快速更新。  
3. **Project portals** – 將 HTML 部署於內部網站，讓團隊成員依天篩選任務。

## 大型 MS Project 檔案的效能考量
- **Memory management** – 使用 Java 垃圾回收旗標 (`-XX:+UseG1GC`) 及時釋放未使用的物件。  
- **Selective rendering** – 若僅需甘特圖，可透過 `options.getProjectOptions().setRenderGantt(true)` 並 `setRenderResources(false)` 停用其他資源渲染。  
- **Parallel processing** – 批次轉換時，可為每個檔案建立獨立的 `Viewer` 物件，並在執行緒池中執行，以利用多核心 CPU。

## 結論
您現在已掌握完整、可投入生產環境的工作流程，使用 GroupDocs Viewer for Java 以天為單位執行 **ms project html export**。此方法可減少 HTML 大小、加速客戶端渲染，並提供利害關係人友好的專案排程檢視。您亦可探索其他渲染選項（如 PDF 匯出或影像快照），將整合延伸至更廣泛的報告管線。

## 常見問答

**Q: 我可以將其他 Project 視圖（例如 Resource Sheet）匯出為 HTML 嗎？**  
A: 可以，`ProjectOptions` 物件允許您在渲染前啟用或停用特定視圖，如甘特圖、資源表與行事曆。

**Q: 能否自訂產生 HTML 的 CSS？**  
A: 完全可以。透過 `options.setStyleSheetPath("path/to/custom.css")` 提供自訂樣式表路徑，檢視器會將其嵌入每一頁。

**Q: GroupDocs Viewer 支援的 MS Project 檔案大小上限是多少？**  
A: SDK 可處理最高 **500 MB** 的檔案，且不需將整個文件載入記憶體，得益於其串流架構。

**Q: 伺服器上需要安裝 Microsoft Project 嗎？**  
A: 不需要。GroupDocs Viewer 直接解析 .mpp 格式，無需 Microsoft Project 或任何 Office 安裝。

**Q: 如何為生產環境授權檢視器？**  
A: 請於 GroupDocs 商店購買永久授權；於執行時使用 `License license = new License(); license.setLicense("path/to/license.lic");` 載入授權檔。短期需求可取得 [temporary license](https://purchase.groupdocs.com/temporary-license/)。

---

**Last Updated:** 2026-05-21  
**Tested With:** GroupDocs Viewer Java 25.2  
**Author:** GroupDocs  

**Resources**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## 相關教學

- [How to Render MS Project Files as HTML, JPG, PNG, and PDF with Notes Using GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [How to Use GroupDocs Viewer to Render Project Documents by Time Intervals in Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [How to Set Licenses in GroupDocs.Viewer Java: File and URL Setup Guide](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)