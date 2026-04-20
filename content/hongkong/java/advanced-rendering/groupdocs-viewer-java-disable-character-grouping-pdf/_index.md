---
date: '2026-03-22'
description: 了解如何使用 GroupDocs Viewer for Java 從 PDF 產生 HTML，並停用字元分組，以實現精確的文字呈現。
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: 從 PDF 產生 HTML 並停用分組 – GroupDocs Java
type: docs
url: /zh-hant/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# 從 PDF 產生 HTML 並停用分組 – 使用 GroupDocs Viewer for Java

在許多專案中，您需要 **從 PDF 產生 HTML**，同時確保每個字形都精確地位於原本的位置。這在處理複雜文字、古代語言或法律文件時尤為重要，因為一個錯位的字元就可能改變含義。本教學將帶您完整了解如何使用 GroupDocs Viewer for Java 將 PDF 轉換為 HTML，並說明 **如何停用分組**，讓每個字元皆被視為獨立元素。

![精確渲染技術與 GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 快速解答
- **「停用分組」會做什麼？** 它會強制渲染器將每個字元視為獨立元素，保留精確的版面配置。  
- **哪個 API 選項控制此功能？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **需要授權嗎？** 試用版可用於測試，但正式環境必須購買完整授權。  
- **可以同時產生 PDF 的 HTML 嗎？** 可以——使用 `HtmlViewOptions` 產生 HTML 輸出，同時停用分組。  
- **此功能僅限於 PDF 嗎？** 主要針對 PDF，但 Viewer 支援多種其他格式。

## 介紹

在處理 PDF 文件時，渲染的精確度至關重要——尤其是面對象形文字或需要精確字元呈現的語言時。「字元分組」功能常會錯誤地將字元合併，導致文件內容被誤讀。對於需要完整復製文件文字版面的使用者而言，這會造成嚴重問題。

### 前置條件

在開始編寫程式碼之前，請確保符合以下需求：
- **函式庫與相依性**：需要 GroupDocs.Viewer for Java 版本 25.2 以上。  
- **環境設定**：請安裝 Java Development Kit (JDK)，並將 IDE 設定為可使用 Maven 專案。  
- **知識前提**：具備基本的 Java 程式設計概念，尤其是檔案路徑處理與外部函式庫的使用。

## 如何使用 GroupDocs Viewer 產生 PDF 的 HTML

產生 HTML 從 PDF 是兩步驟的流程：先設定 Viewer，然後渲染文件。關鍵在於渲染前先關閉字元分組，讓 HTML 輸出能逐字元對應原始 PDF 版面。

### 設定 GroupDocs.Viewer for Java

#### 透過 Maven 安裝

首先，將必要的函式庫整合至您的專案。於 `pom.xml` 中加入以下設定：

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

#### 授權取得

為了完整使用 GroupDocs.Viewer，建議取得授權：
- **免費試用**：先使用免費試用版測試功能。  
- **臨時授權**：若需要更長的測試時間，可申請臨時授權。  
- **購買授權**：長期專案建議直接購買授權。

#### 基本初始化與設定

以下是一段可直接執行的程式碼範例，展示完整工作流程——從設定輸出資料夾到在停用字元分組的情況下將 PDF 渲染為 HTML：

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

以下我們逐行說明範例程式碼，讓您了解 **為什麼** 這樣做以及 **如何** 讓產生的 HTML 不會出現不必要的字元合併。

##### 步驟 1：定義輸出目錄  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**為什麼？** 這確保渲染出的 HTML 檔案會存放在專屬資料夾中，方便日後查找與管理。

##### 步驟 2：設定檔案路徑格式  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**為什麼？** 使用佔位符 (`{0}`) 可讓 Viewer 為每一頁 PDF 建立獨立的 HTML 檔案，保持輸出有序。

##### 步驟 3：初始化 HTML View Options  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**為什麼？** 嵌入式資源會將圖片、字型與 CSS 直接打包於每個 HTML 頁面，適合網頁檢視器或 e‑learning 平台使用。

##### 步驟 4：停用字元分組  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**為什麼？** 這行程式碼是關鍵，告訴渲染引擎 **不要** 合併相鄰字元，確保產生的 HTML 完全對應原始 PDF 中的字形位置。

##### 步驟 5：渲染文件  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**為什麼？** 將 `Viewer` 包在 try‑with‑resources 區塊中，可自動釋放所有原生資源，避免長時間執行的應用程式發生記憶體洩漏。

### 產生不分組的 Java HTML 從 PDF

`HtmlViewOptions` 類別讓您在保持每個字元獨立的前提下 **產生 HTML 從 PDF**。當您需要將渲染頁面嵌入網站入口或 e‑learning 平台，且字形位置必須精確時，這個功能特別實用。

### 常見問題與解決方案

- **FileNotFoundException** – 請再次確認傳入 `new Viewer(...)` 的路徑。建議使用絕對路徑或 `Path.of(...)` 以提升可讀性。  
- **寫入權限** – 確認輸出資料夾對 Java 程序具有寫入權限；在 Linux 上可能需要調整資料夾權限 (`chmod 775`)。  
- **版本不符** – `setDisableCharsGrouping` 選項自 25.2 版起提供。請確認 `pom.xml` 中的版本號正確。

### 實務應用

1. **語言保存** – 適用於中文、日文、阿拉伯文或古代文字等，字元間距對意義至關重要的文件。  
2. **法律與金融文件** – 確保文字完全復製，以符合嚴格的合規要求。  
3. **教育資源** – 完美支援包含複雜圖表、註解或多語言內容的教科書。

### 效能考量

- **最佳化資源使用** – 大型 PDF 可能佔用大量記憶體。建議分批處理頁面，並及時釋放 `Viewer` 實例。  
- **Java 記憶體管理** – 若預計處理數百頁的 PDF，請調整 JVM 堆積大小（如 `-Xmx2g` 或更高）。  
- **平行渲染** – 大量轉換時，可為每個執行緒建立獨立的 `Viewer` 實例，以利用多核心 CPU。

## 常見問答

**Q:** *為什麼需要停用字元分組？*  
**A:** 停用分組可防止渲染器將屬於不同字形的字元合併，這對於字元間距與順序傳遞意義的文字系統至關重要。

**Q:** *`setDisableCharsGrouping` 設定僅適用於 HTML 輸出嗎？*  
**A:** 否，它會影響底層的 PDF 渲染引擎，因此任何輸出格式（HTML、PNG、JPEG 等）都會反映此變更。

**Q:** *可以將此設定與自訂字型結合使用嗎？*  
**A:** 可以——在初始化 `Viewer` 之前載入自訂字型，分組規則仍會生效。

**Q:** *停用分組會影響效能嗎？*  
**A:** 會略微增加負擔，因為引擎需要逐一處理每個字元，但對大多數文件而言影響甚微。

**Q:** *是否能在單頁上切換分組設定？*  
**A:** 目前此選項僅能於 `PdfOptions` 實例全域設定；若需不同頁面使用不同設定，必須為每個頁面建立獨立的 `Viewer` 實例。

## 資源

- [GroupDocs 文件說明](https://docs.groupdocs.com/viewer/java/)
- [API 參考文件](https://reference.groupdocs.com/viewer/java/)
- [下載 GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [購買授權](https://purchase.groupdocs.com/buy)
- [免費試用版](https://releases.groupdocs.com/viewer/java/)
- [臨時授權申請](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 支援論壇](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-03-22  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs