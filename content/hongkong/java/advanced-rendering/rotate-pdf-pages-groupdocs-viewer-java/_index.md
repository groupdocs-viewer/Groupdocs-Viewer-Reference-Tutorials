---
date: '2026-01-18'
description: 了解如何使用 GroupDocs.Viewer for Java 旋轉 PDF 頁面。本分步教學涵蓋 Maven 設定、頁面旋轉（包括將
  PDF 旋轉 90 度）以及故障排除。
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: 如何在 Java 中使用 GroupDocs.Viewer 旋轉 PDF 頁面 – 完整指南
type: docs
url: /zh-hant/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs.Viewer 在 Java 中旋轉 PDF 頁面

在 PDF 中旋轉特定頁面對於對齊文件或調整簡報投影片非常重要。**在本指南中您將學習如何使用 GroupDocs.Viewer 以程式方式旋轉 pdf** 頁面，無論是需要將 pdf 旋轉 90 度、翻轉整個區段，或在一次呼叫中處理多個頁面。

![使用 GroupDocs.Viewer for Java 旋轉特定 PDF 頁面](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**您將學到的內容：**
- 在 Java 專案中設定 GroupDocs.Viewer（包括 Maven GroupDocs Viewer 配置）
- 以程式方式旋轉特定 PDF 頁面（rotate pdf 90 degrees、180 degrees 等）
- 最佳使用的關鍵配置
- 實作過程中常見問題的故障排除

## 快速答案
- **哪個程式庫可以在 Java 中旋轉 PDF 頁面？** GroupDocs.Viewer for Java。  
- **我可以將單一頁面旋轉 90 度嗎？** 可以，使用 `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`。  
- **開發時需要授權嗎？** 可取得免費試用的臨時授權。  
- **是否必須使用 Maven？** 建議使用 Maven 來管理 GroupDocs 相依性。  
- **如何呈現旋轉後的頁面？** 使用 `HtmlViewOptions` 並呼叫 `viewer.view(...)`。

## 前置條件

### 必要的程式庫與相依性

開始之前，請確保您已具備：
- 已在機器上安裝 Java Development Kit (JDK) 8 版或更新版本。  
- 一個整合開發環境 (IDE)，如 IntelliJ IDEA 或 Eclipse。  
- 用於管理專案相依性的 Maven。

### 環境設定需求

1. **Maven 設定**：在 `pom.xml` 中加入必要的儲存庫與相依性，以將 GroupDocs.Viewer 加入您的 Maven 專案。  
2. **授權取得**：從 GroupDocs 取得臨時授權，讓您在開發期間無限制探索所有功能。請前往 [GroupDocs 免費試用](https://releases.groupdocs.com/viewer/java/) 或在 [GroupDocs 臨時授權頁面](https://purchase.groupdocs.com/temporary-license/) 申請臨時授權。

## 設定 GroupDocs.Viewer for Java

要使用 Maven 將 GroupDocs.Viewer 整合至您的 Java 專案，請更新 `pom.xml`：

**Maven 配置**  
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

使用以下程式碼指定文件目錄與輸出路徑，以初始化 GroupDocs.Viewer：

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## 實作指南

### 使用 GroupDocs.Viewer 旋轉特定頁面

**概述：** 旋轉特定 PDF 頁面以提升文件呈現效果。

#### 步驟 1：設定頁面旋轉

使用 `HtmlViewOptions` 將第一頁旋轉 90 度、第二頁旋轉 180 度：

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### 步驟 2：初始化 Viewer 並渲染

建立 `Viewer` 實例並渲染指定頁面：

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### 參數與配置

- **Rotation**：使用 `rotatePage` 搭配頁碼與旋轉角度。可用的旋轉值有 `ON_90_DEGREE`、`ON_180_DEGREE`、`ON_270_DEGREE`。  
- **HtmlViewOptions**：設定 PDF 轉 HTML 的轉換行為，確保嵌入資源被包含。  
- **pdf to html java**：`HtmlViewOptions` 類別在執行 PDF‑to‑HTML 轉換時會保留版面配置。

#### 故障排除技巧（troubleshoot pdf rotation）

- 核對文件與輸出目錄的路徑是否正確。  
- 檢查是否缺少相依性或使用了錯誤的程式庫版本。  
- 若在試用期間出現功能受限，請確認已正確套用授權。  
- 若出現記憶體激增情況，建議將頁面分批渲染（逐步 rotate multiple pdf pages）。

## 實務應用

### 真實案例
1. **文件對齊** – 旋轉掃描文件以取得正確的數位方向。  
2. **簡報調整** – 在分享前調整 PDF 內的簡報投影片。  
3. **檔案保存工作流程** – 在數位化歷史文件時自動校正方向。

### 整合可能性
將 GroupDocs.Viewer 與基於 Java 的文件管理系統、內容平台或需要動態檢視功能的企業客製解決方案結合。

## 效能考量

- **資源管理**：使用完畢後關閉 `Viewer` 實例以釋放資源。  
- **Java 記憶體管理**：渲染大型文件時監控記憶體使用，並採用高效資料結構。  
- **最佳實踐**：對常用文件或頁面使用快取機制。

## 結論

本教學說明了 **如何使用 GroupDocs.Viewer 在 Java 中旋轉 pdf** 頁面，涵蓋環境設定到實務應用。您可進一步嘗試加入浮水印或將文件轉換為其他格式等功能。

**後續步驟：** 探索更多 GroupDocs.Viewer 功能，以提升文件處理能力。

## FAQ 章節

### 常見問題
1. **旋轉問題的故障排除**：確認頁碼與旋轉參數正確。  
2. **處理大型 PDF 檔案**：使用適當的資源管理方式有效處理。  
3. **授權需求**：開發階段使用臨時授權，上線後購買正式授權。  
4. **一次旋轉多個頁面**：對不同頁碼與角度多次呼叫 `rotatePage`。  
5. **與 Java 程式庫的整合**：可無縫將 GroupDocs.Viewer 嵌入更大型的應用或框架。

## 常見問答

**Q: 我可以一次旋轉 PDF 的所有頁面嗎？**  
A: 可以。遍歷頁碼並對每一頁呼叫 `rotatePage(page, Rotation.ON_90_DEGREE)`。

**Q: 旋轉會影響原始 PDF 檔案嗎？**  
A: 不會。旋轉僅在渲染過程中套用，來源 PDF 保持不變。

**Q: 若 PDF 設有密碼該怎麼辦？**  
A: 建立 `Viewer` 實例時提供密碼，例如 `new Viewer(path, password)`。

**Q: 設定 HtmlViewOptions 時出現 “null pointer” 錯誤要如何除錯？**  
A: 確認輸出目錄已存在，且 `pageFilePathFormat` 能正確解析。

**Q: 轉換成其他格式（如 PNG）時能否同時旋轉頁面？**  
A: 可以，使用相同的 `rotatePage` 設定，只需搭配目標格式的檢視選項。

## 資源
- **文件說明**： [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 參考**： [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下載**： [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **購買**： [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **免費試用**： [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **臨時授權**： [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **支援**： [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-01-18  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs