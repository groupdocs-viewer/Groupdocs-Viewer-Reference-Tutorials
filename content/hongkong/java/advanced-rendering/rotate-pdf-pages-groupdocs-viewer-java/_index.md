---
date: '2026-04-04'
description: 學習如何使用 GroupDocs.Viewer for Java 旋轉特定的 PDF 頁面。本分步指南涵蓋 Maven 設定、PDF 旋轉
  90 度以及故障排除。
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: 如何使用 GroupDocs.Viewer for Java 旋轉特定的 PDF 頁面
type: docs
url: /zh-hant/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs.Viewer for Java 旋轉特定 PDF 頁面

在 PDF 中旋轉特定頁面對於對齊文件、修正掃描圖像或微調簡報投影片可能是必要的。**在本指南中，您將學習如何使用 GroupDocs.Viewer 以程式方式旋轉特定 PDF 頁面**，無論您需要將 PDF 旋轉 90 度、翻轉整個區段，或在一次呼叫中處理多個頁面。

![使用 GroupDocs.Viewer for Java 旋轉特定 PDF 頁面](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**您將學習**
- 在您的 Java 專案中設定 GroupDocs.Viewer（包括 Maven GroupDocs Viewer 配置）
- 以程式方式旋轉特定 PDF 頁面（旋轉 PDF 90 度、180 度等）
- 最佳使用的關鍵配置
- 實作過程中常見問題的排除

## 快速解答
- **哪個程式庫可以在 Java 中旋轉 PDF 頁面？** GroupDocs.Viewer for Java.  
- **我可以將單一頁面旋轉 90 度嗎？** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **開發時需要授權嗎？** 可取得臨時授權供免費試用。  
- **是否需要 Maven？** Maven 是管理 GroupDocs 相依性的推薦方式。  
- **如何渲染已旋轉的頁面？** 使用 `HtmlViewOptions` 並呼叫 `viewer.view(...)`.

## 前置條件

### 必要的函式庫與相依性
- Java Development Kit (JDK) 8 或更新版本。  
- IntelliJ IDEA 或 Eclipse 等 IDE。  
- 用於相依性管理的 Maven。

### 環境設定需求
1. **Maven 配置** – 將 GroupDocs.Viewer 加入您的 `pom.xml`。  
2. **授權取得** – 從 GroupDocs 獲取臨時授權。請造訪 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 或在 [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) 申請臨時授權。

## 設定 GroupDocs.Viewer for Java

要使用 Maven 將 GroupDocs.Viewer 整合至您的 Java 專案，請更新您的 `pom.xml`：

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

### 基本初始化與設定
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## 如何使用 GroupDocs.Viewer 旋轉特定 PDF 頁面
### 概觀
旋轉特定 PDF 頁面可讓您在不更改原始檔案的情況下，細緻地控制文件的呈現方式。

### 步驟 1：設定頁面旋轉
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### 步驟 2：初始化 Viewer 並渲染
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### 參數與設定
- **Rotation** – `rotatePage(pageNumber, Rotation.*)`，其中旋轉選項為 `ON_90_DEGREE`、`ON_180_DEGREE`、`ON_270_DEGREE`。  
- **HtmlViewOptions** – 處理 PDF 轉 HTML 的轉換，同時保留版面配置與嵌入資源。  
- **pdf to html java** – 此類別屬於相同 API，確保忠實的視覺呈現。

## 為何要旋轉特定 PDF 頁面？
- **文件對齊** – 校正掃描合約或發票的正確方向。  
- **簡報微調** – 調整以 PDF 匯出的投影片。  
- **歸檔一致性** – 在大量數位化過程中統一頁面方向。

## 常見問題與解決方案（排除 PDF 旋轉問題）
- **路徑錯誤** – 確認 `YOUR_DOCUMENT_DIRECTORY` 與 `YOUR_OUTPUT_DIRECTORY` 存在且可存取。  
- **缺少相依性** – 確保 Maven 坐標對應最新的 GroupDocs.Viewer 版本。  
- **授權限制** – 正確套用臨時授權，否則部分功能可能被停用。  
- **記憶體激增** – 將大型 PDF 分批渲染或增大 JVM 堆積大小。

## 實務應用

### 真實案例應用
1. **文件對齊** – 旋轉掃描文件以獲得正確的數位方向。  
2. **簡報調整** – 在分享前修改 PDF 內的簡報投影片。  
3. **歸檔工作流程** – 在數位化過程中自動調整歷史文件的方向。

### 整合可能性
將 GroupDocs.Viewer 與基於 Java 的內容管理系統、企業入口網站或需要即時檢視 PDF 的自訂 API 結合。

## 效能考量
- **資源管理** – 必須隨時關閉 `Viewer` 實例，以釋放檔案句柄與記憶體。  
- **Java 記憶體管理** – 處理大型 PDF 時監控堆積使用情況；可考慮串流頁面而非一次載入整個檔案。  
- **最佳實踐** – 為常存取的文件快取已渲染的 HTML，以減少處理時間。

## 結論
本教學說明了 **如何在 Java 中使用 GroupDocs.Viewer 旋轉特定 PDF 頁面**，涵蓋從 Maven 設定到渲染已旋轉頁面以及處理常見陷阱。可嘗試其他功能，如加水印、格式轉換或批次處理，以進一步擴充文件工作流程。

**下一步：**深入了解其他 GroupDocs.Viewer 功能，例如將 PDF 轉換為 PNG、加入水印，或與雲端儲存服務整合。

## 常見問答區
- **排除旋轉問題** – 確認頁碼與旋轉參數正確。  
- **處理大型 PDF 檔案** – 分批處理頁面並監控記憶體使用。  
- **授權需求** – 開發時使用臨時授權；生產環境請購買正式授權。  
- **旋轉多頁** – 針對不同頁碼與角度重複呼叫 `rotatePage`。  
- **與 Java 函式庫整合** – GroupDocs.Viewer 可無縫搭配 Spring Boot、Jakarta EE 及其他 Java 框架。

## 常見問題

**Q: 我可以一次旋轉 PDF 的所有頁面嗎？**  
A: 可以。遍歷頁碼，對每一頁呼叫 `rotatePage(page, Rotation.ON_90_DEGREE)`。

**Q: 旋轉會影響原始 PDF 檔案嗎？**  
A: 不會。旋轉僅在渲染過程中套用，來源 PDF 保持不變。

**Q: 如果 PDF 受密碼保護該怎麼辦？**  
A: 在建立 `Viewer` 實例時提供密碼：`new Viewer(path, password)`。

**Q: 設定 HtmlViewOptions 時遇到 “null pointer” 錯誤該如何除錯？**  
A: 確認輸出目錄存在，且 `pageFilePathFormat` 正確解析。

**Q: 轉換為其他格式（例如 PNG）時能否旋轉頁面？**  
A: 可以。使用相同的 `rotatePage` 設定，搭配目標格式的相應檢視選項。

## 資源
- **文件說明**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 參考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下載**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **購買**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **免費試用**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **臨時授權**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **支援**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-04-04  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs