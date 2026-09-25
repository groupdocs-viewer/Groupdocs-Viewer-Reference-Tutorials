---
date: '2026-09-25'
description: 了解如何使用 GroupDocs Viewer for Java 建立 html view mpp，透過時間間隔渲染專案文件，並提供逐步程式碼說明。
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: 使用 GroupDocs Viewer for Java 建立 html view mpp，以特定時間間隔渲染 Microsoft
  Project 檔案。遵循逐步設定、授權與程式碼片段，以精確呈現時間軸。
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: 使用 GroupDocs Viewer for Java 建立 html view mpp
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: 使用 GroupDocs Viewer（Java）建立 html view mpp
type: docs
url: /zh-hant/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# 如何在 Java 中使用 GroupDocs Viewer 按時間間隔渲染專案文件

在本教學中，您將學習如何使用 GroupDocs Viewer for Java **create html view mpp**，讓您僅渲染位於特定開始日期與結束日期範圍內的 Microsoft Project 檔案部分。我們將逐步說明 Maven 設定、授權，以及嵌入精確時間軸視圖至應用程式所需的 API 呼叫。

![使用 GroupDocs.Viewer for Java 按時間間隔渲染專案文件](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

欲預覽，請參閱 [使用 GroupDocs.Viewer for Java 按時間間隔渲染專案文件](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)。

## 快速解答
- **此功能的作用是什麼？** 它僅渲染位於開始日期與結束日期之間的 Microsoft Project 檔案部分。  
- **使用哪種輸出格式？** 使用嵌入資源的 HTML，適合網頁整合。  
- **需要授權嗎？** 免費試用可用於評估；正式環境需購買完整授權。  
- **可以在執行時變更日期範圍嗎？** 可以——在渲染選項中調整 `setStartDate` 和 `setEndDate` 的值。  
- **此功能支援所有 Java 版本嗎？** 只要使用 GroupDocs.Viewer 25.2 或更新版本，即可在 Java 8 以上運行。

## 什麼是 create html view mpp？
`create html view mpp` 是將 Microsoft Project 檔案（`.mpp` 或 `.mpt`）轉換為一組呈現排程的 HTML 頁面的過程。GroupDocs Viewer 在伺服器端執行轉換，讓您無需安裝 Microsoft Project，即可在任何瀏覽器中顯示時間軸。

## 為什麼要按時間間隔渲染專案文件？
僅渲染所需的時間間隔可減少產生的 HTML 大小、加快頁面載入，並讓您專注於需要分析的特定專案階段。此目標化視圖非常適合儀表板、狀態報告，或嵌入自訂專案管理工具中，避免完整專案資料過於龐大。

## 先決條件

- **GroupDocs.Viewer for Java** 版本 25.2 或以上。  
- Java Development Kit (JDK) 8 或更新版本。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 基本的 Maven 知識。  

## 設定 GroupDocs.Viewer for Java

### Maven 依賴

將以下儲存庫與依賴項加入您的 `pom.xml`：

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

1. **免費試用** – 從 [GroupDocs 下載頁面](https://releases.groupdocs.com/viewer/java/) 下載試用版。  
2. **臨時授權** – 透過 [temporary‑license 頁面](https://purchase.groupdocs.com/temporary-license/) 取得延長測試的臨時授權。  
3. **購買** – 若需無限制的正式環境使用，請於 [GroupDocs 購買頁面](https://purchase.groupdocs.com/buy) 購買授權。

## 基本檢視器初始化

`Viewer` 是 GroupDocs.Viewer for Java 中的主要類別，用於載入文件並提供渲染功能。

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## 取得專案檔案的檢視資訊

`ProjectManagementViewInfo` 提供 Microsoft Project 檔案的中繼資料，包括整體排程的開始與結束日期。

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## 設定 HTML 渲染選項（從專案產生 HTML）

`HtmlViewOptions` 設定 GroupDocs 渲染 HTML 的方式，讓您可以設定日期範圍、嵌入資源以及自訂外觀。

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## 執行渲染程序

`viewer.render` 依據提供的選項執行轉換，並將產生的 HTML 檔案寫入目標資料夾。

```java
viewer.view(viewOptions);
```

## 常見問題與故障排除

- **檔案路徑不正確** – 請再次確認來源 `.mpp` 檔案與輸出目錄皆存在。  
- **不支援的檔案類型** – 確認文件為支援的 Project 格式（例如 `.mpp`、`.mpt`）。  
- **授權錯誤** – 試用授權可能有限制渲染次數；若需無限制使用，請改為完整授權。  

## 實務應用

1. **專案時間軸分析** – 僅向利害關係人展示當前階段。  
2. **自動化報告** – 產生具時間限制的 HTML 報告，用於每週狀態更新。  
3. **與儀表板整合** – 將渲染頁面嵌入 BI 工具或自訂入口網站。  
4. **歸檔** – 保存專案排程的網頁友好快照，以供未來參考。  

## 效能建議

- 使用 *嵌入資源* 選項，使每個 HTML 頁面自包含，減少 HTTP 請求。  
- 對於極大型專案，建議將渲染分成較小的日期區段，以降低記憶體使用。將一年區間渲染可將 HTML 大小縮減至完整專案匯出的 80 % 左右，將載入時間從數秒縮短至一般伺服器上一秒以內。  
- 服務完畢後清除暫存檔案，以防磁碟空間膨脹。  

## 結論

您現在已了解 **如何使用 GroupDocs** Viewer 在特定時間間隔內渲染專案文件，並在 Java 中 **從專案資料產生 HTML**。此功能簡化時間軸視覺化、提升報告效率，且能順利整合至現代 Web 應用程式。

### 下一步
- 探索其他 Viewer 功能，如浮水印、密碼保護或自訂 CSS 樣式。  
- 將此渲染流程與 REST API 結合，以提供即時時間軸視圖。  

## 常見問題

**Q: GroupDocs.Viewer 支援哪些檔案格式？**  
A: GroupDocs.Viewer 支援超過 100 種輸入格式，包括 PDF、DOCX、XLSX、PPTX 以及 Microsoft Project 檔案，實現通用文件可視化。

**Q: 如何開始使用 GroupDocs.Viewer 的免費試用？**  
A: 您可從 [GroupDocs Viewer Java 下載頁面](https://releases.groupdocs.com/viewer/java/) 下載試用版。

**Q: 可以在不嵌入資源的情況下渲染文件嗎？**  
A: 可以，您可選擇引用外部資源的其他 HTML 檢視選項，而非嵌入資源。

**Q: 若文件過大無法渲染該怎麼辦？**  
A: 可將文件拆分為較小的區段，或僅渲染所需的日期範圍，如上所示。

**Q: 如何處理渲染錯誤？**  
A: 請檢查所有設定、確認授權有效，並參考 GroupDocs 文件以取得錯誤代碼說明。

## 資源
- **文件**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 參考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下載**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **購買**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **免費試用**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **臨時授權**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **支援**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-09-25  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 將 MS Project 檔案渲染為 HTML、JPG、PNG 與 PDF（含註解）](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [MS Project HTML 匯出：透過 GroupDocs Java 調整時間單位](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [GroupDocs Viewer Java 響應式 HTML 渲染](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)