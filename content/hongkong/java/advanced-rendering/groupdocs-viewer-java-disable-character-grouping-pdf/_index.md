---
date: '2025-12-21'
description: 了解如何在使用 GroupDocs.Viewer for Java 時，透過 PDF 渲染選項中的 Java HTML 來停用 PDF 的分組功能，以確保文字呈現精確。
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: 如何使用 GroupDocs.Viewer for Java 停用 PDF 的分組
type: docs
url: /zh-hant/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# 如何在 PDF 中使用 GroupDocs.Viewer for Java 停用分組

當您在渲染 PDF 時需要 **停用分組**，尤其是處理複雜文字或古老語言時，精確的字元位置至關重要。預設的 *Character Grouping* 功能可能會錯誤地合併字元，導致內容被誤解。本指南將逐步示範如何使用 GroupDocs.Viewer for Java 停用分組，確保每個字形都精確地位於正確位置。

![使用 GroupDocs.Viewer for Java 的精確渲染技術](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 快速解答
- **「停用分組」的作用是什麼？** 它會強制渲染器將每個字元視為獨立元素，保留精確的版面配置。  
- **哪個 API 選項控制此功能？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **我需要授權嗎？** 試用版可用於測試，但正式環境需要完整授權。  
- **我可以同時從 PDF 產生 Java HTML 嗎？** 可以——使用 `HtmlViewOptions` 在停用分組的同時產生 HTML 輸出。  
- **此功能僅限於 PDF 嗎？** 主要針對 PDF，但 Viewer 支援多種其他格式。  

## 介紹

在處理 PDF 文件時，渲染的精確度至關重要——尤其是面對像象形文字或需要精確字元呈現的語言時。"Character Grouping" 功能常因錯誤地將字元分組而導致問題，進而使文件內容被誤解。對於需要精確複製文件文字版面的使用者而言，這尤其成為困擾。

### 前置條件

- **Libraries & Dependencies**：您需要 GroupDocs.Viewer for Java 版本 25.2 或更新版本。  
- **Environment Setup**：確保已安裝 Java Development Kit (JDK)，且 IDE 已設定好可使用 Maven 專案。  
- **Knowledge Prerequisites**：具備 Java 程式基礎，特別是檔案路徑處理與使用外部函式庫的知識。  

## 如何在 PDF 渲染中停用分組

### 設定 GroupDocs.Viewer for Java

#### 透過 Maven 安裝

首先，將所需函式庫整合至您的專案。於 `pom.xml` 中加入以下設定：

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

#### 取得授權

若要完整使用 GroupDocs.Viewer，請考慮取得授權：

- **Free Trial**：使用免費試用版測試功能。  
- **Temporary License**：若需要更長時間，可申請臨時授權。  
- **Purchase**：對於長期專案，建議購買授權。  

#### 基本初始化與設定

先設定您的專案環境：

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### 實作指南

#### 功能：停用字元分組

##### 步驟 1：定義輸出目錄

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**為什麼？** 確保輸出檔案有條理且易於存取。

##### 步驟 2：設定檔案路徑格式

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**為什麼？** 有助於系統化地整理 PDF 文件的各頁。

##### 步驟 3：初始化 HTML View Options

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**為什麼？** 嵌入式資源可確保每頁的 HTML 檔案中包含所有必要資產。

##### 步驟 4：停用字元分組

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**為什麼？** 確保字元單獨渲染，保留其預期的版面與意義。

##### 步驟 5：渲染文件

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**為什麼？** 確保所有資源正確關閉，避免記憶體洩漏。

### 從 PDF 產生不分組的 Java HTML

`HtmlViewOptions` 類別允許您在保持每個字元分離的同時產生 **java html from pdf**。當您需要將渲染後的頁面嵌入網站入口或 e‑learning 平台，且字形位置必須精確時，這特別方便。

### 疑難排解技巧

- 確認文件路徑正確，以避免 `FileNotFoundException`。  
- 確認輸出目錄具寫入權限。  
- 再次確認您使用的 GroupDocs.Viewer for Java 版本相容。  

## 實務應用

1. **語言保存**：適用於渲染中文、日文或古代文字等對字元精度有要求的文件。  
2. **法律與金融文件**：確保需精確文字呈現以符合合規要求的文件之準確性。  
3. **教育資源**：適合包含複雜圖表或註釋的教科書與學術論文。  

## 效能考量

- **優化資源使用**：確保伺服器具備足夠資源以處理大型 PDF 檔案。  
- **Java 記憶體管理**：使用高效資料結構與垃圾回收策略，以有效管理記憶體。  
- **批次處理**：渲染多個文件時，採用批次方式以提升吞吐量。  

## 結論

您現在已掌握在使用 GroupDocs.Viewer for Java 進行 PDF 渲染時 **停用分組** 的方法。此功能對於需要精確文字呈現的應用程式至關重要。接下來可嘗試將此功能整合至其他文件管理系統，或探索更多渲染選項。

接下來的步驟包括探索 GroupDocs.Viewer 的進階功能，並針對大規模部署進行效能微調。

## 常見問題

**Q:** *為什麼需要停用字元分組？*  
**A:** 停用分組可防止渲染器合併屬於不同字形的字元，對於間距與順序傳遞意義的文字系統而言至關重要。

**Q:** *`setDisableCharsGrouping` 設定僅適用於 HTML 輸出嗎？*  
**A:** 不是，它會影響底層的 PDF 渲染引擎，因此任何輸出格式（HTML、PNG 等）皆會套用此變更。

**Q:** *我可以將此設定與自訂字型結合使用嗎？*  
**A:** 可以——只要在初始化 `Viewer` 前載入自訂字型，分組規則仍會生效。

**Q:** *停用分組會影響效能嗎？*  
**A:** 會稍微降低效能，因為引擎會逐一處理每個字元，但對大多數文件的影響有限。

**Q:** *是否能在每頁單獨切換分組？*  
**A:** 目前此選項是針對每個 `PdfOptions` 實例全域設定；若需不同頁面有不同設定，需建立不同的 `Viewer` 實例。

## 資源

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2025-12-21  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs