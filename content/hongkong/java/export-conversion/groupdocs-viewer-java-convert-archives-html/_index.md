---
date: '2026-02-23'
description: 了解如何設定每頁項目數、嵌入資源 HTML，並使用 GroupDocs.Viewer Java 批量將壓縮檔轉換為單頁或多頁 HTML。
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 設定每頁項目數：使用 GroupDocs.Viewer Java 將壓縮檔轉換為 HTML
type: docs
url: /zh-hant/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

Docs"

Make sure to keep formatting.

Now produce final content with translations, preserving placeholders.

Let's construct final answer.# 設定每頁項目數：使用 GroupDocs.Viewer Java 轉換壓縮檔為 HTML

將 ZIP 或 RAR 等壓縮檔轉換為適合在瀏覽器中直接分享或檢閱的 HTML 是常見需求。在本指南中，你將學習**如何設定每頁項目數**、如何將資源嵌入 HTML 以產生自包含的輸出，以及如何使用 GroupDocs.Viewer Java 高效批次轉換壓縮檔。

![使用 GroupDocs.Viewer for Java 轉換壓縮檔為 HTML](/viewer/export-conversion/convert-archives-to-html-java.png)

## 快速解答
- **「設定每頁項目數」控制什麼？** 它決定壓縮檔中有多少檔案或資料夾會顯示在每個產生的 HTML 頁面上。  
- **我可以直接在 HTML 中嵌入圖片和 CSS 嗎？** 可以 – 使用 `forEmbeddedResources` 選項即可嵌入資源 HTML。  
- **是否支援批次轉換？** 當然可以；你可以遍歷一系列壓縮檔，並以相同設定渲染每個檔案。  
- **使用 GroupDocs.Viewer 是否需要 Maven？** 需要，請依下方示範加入 `maven groupdocs viewer` 依賴。  
- **支援哪些輸出格式？** 提供單頁 HTML Java 與多頁 HTML Java 兩種格式。

## GroupDocs.Viewer 中的「設定每頁項目數」是什麼？
**設定每頁項目數** 屬於壓縮檔渲染選項。它告訴檢視器在產生多頁 HTML 文件時，每個 HTML 頁面應顯示多少個壓縮檔條目（檔案或資料夾）。調整此數值可協助在大型壓縮檔中平衡頁面大小與導覽速度。

## 為什麼要嵌入資源 HTML？
將資源（圖片、CSS、字型）直接嵌入 HTML 檔案，可產生單一、可攜帶的文件，無需外部檔案即可開啟。這對於電子郵件附件、離線檢視，或將輸出嵌入其他網頁特別適用。

## 前置條件

- **必要函式庫：** 包含 GroupDocs.Viewer 版本 25.2 或更新版本。  
- **環境：** 已安裝並設定 Java Development Kit（JDK）。  
- **知識需求：** 基本的 Java 與 Maven 依賴管理。  

## Maven GroupDocs Viewer 設定

將 GroupDocs 儲存庫與 Viewer 依賴加入你的 `pom.xml`：

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
GroupDocs.Viewer 提供 **免費試用連結**、臨時授權或完整購買方案。請依專案時程選擇合適的方案。

### 基本初始化
完成 Maven 設定後，將 Viewer 引入程式碼中：

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 如何將壓縮檔渲染為單頁 HTML

### 步驟 1：定義輸出目錄
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步驟 2：設定單頁輸出的檔名
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 步驟 3：初始化 Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 步驟 4：設定渲染選項（嵌入資源 HTML）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步驟 5：渲染為單頁
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 如何將壓縮檔渲染為多頁 HTML 並設定每頁項目數

### 步驟 1：重複使用輸出目錄
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步驟 2：設定多頁檔名格式
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 步驟 3：再次初始化 Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 步驟 4：設定多頁選項（嵌入資源 HTML）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步驟 5：設定每頁項目數（主要關鍵字）
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 實務應用

- **文件管理系統：** 在不安裝額外檢視器的情況下加入壓縮檔預覽功能。  
- **網站入口：** 為使用者提供快速、免下載的方式瀏覽打包文件。  
- **協作工具：** 讓團隊直接在瀏覽器中檢視共享的壓縮檔。  

## 效能考量

- **資源管理：** 留意記憶體使用情況；對於大量批次可考慮調整 JVM 的垃圾回收器。  
- **批次轉換壓縮檔：** 迭代壓縮檔清單，呼叫相同的渲染邏輯以提升吞吐量。  
- **快取策略：** 若同一壓縮檔被頻繁存取，可將渲染後的 HTML 存入快取。  

## 常見問題

**Q: 什麼是 GroupDocs.Viewer Java？**  
A: 一個多功能的函式庫，可將文件（包括壓縮檔）渲染成 HTML、PDF、圖片等格式。

**Q: 如何取得 GroupDocs.Viewer 的免費試用？**  
A: 前往 [免費試用連結](https://releases.groupdocs.com/viewer/java/) 下載並測試。

**Q: 除了壓縮檔，我可以轉換其他文件類型嗎？**  
A: 可以，Viewer 支援 PDF、Word、Excel 等多種格式。

**Q: 若渲染速度緩慢該怎麼辦？**  
A: 減少每頁項目數、啟用串流，或將壓縮檔分成較小批次處理。

**Q: 我該向哪裡尋求協助或支援？**  
A: 可透過 [支援論壇](https://forum.groupdocs.com/c/viewer/9) 聯絡我們。

**Q: 是否可以直接在 HTML 中嵌入 CSS 與圖片？**  
A: 完全可以——如範例所示，使用 `HtmlViewOptions.forEmbeddedResources`。

**Q: 如何批次轉換資料夾內的壓縮檔？**  
A: 使用 `for` 迴圈遍歷每個檔案，對每次迭代套用相同的 `Viewer` 與 `HtmlViewOptions` 設定。

## 資源

- **文件說明：** 透過 [GroupDocs 文件說明](https://docs.groupdocs.com/viewer/java/) 深入了解功能。  
- **API 參考：** 前往 [GroupDocs API](https://reference.groupdocs.com/viewer/java/) 探索完整 API。  
- **下載：** 從 [下載頁面](https://releases.groupdocs.com/viewer/java/) 取得最新二進位檔。  
- **購買與授權：** 在 [購買頁面](https://purchase.groupdocs.com/buy) 查看方案。  
- **支援與社群：** 於 [GroupDocs 論壇](https://forum.groupdocs.com/c/viewer/9) 參與討論。

---

**最後更新：** 2026-02-23  
**測試環境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs