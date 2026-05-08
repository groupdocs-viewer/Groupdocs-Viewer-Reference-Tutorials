---
date: '2026-02-13'
description: 學習如何使用 GroupDocs.Viewer for Java 將 nsf 轉換為 pdf 以及其他格式（HTML、JPG、PNG）。本分步指南展示了如何高效轉換
  nsf 檔案。
keywords:
- GroupDocs.Viewer Java
- NSF Document Conversion
- Convert NSF Files
title: 使用 GroupDocs.Viewer for Java 將 NSF 轉換為 PDF、HTML、JPG、PNG
type: docs
url: /zh-hant/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer for Java 轉換 NSF 檔案為多種格式

使用 Java 將 NSF 文件轉換為 HTML、JPG、PNG 或 PDF 等不同格式，透過 GroupDocs.Viewer for Java 可輕鬆完成。**本教學示範如何將 nsf 轉換為 pdf** 以及其他實用格式，並逐步說明設定、實作與最佳實踐技巧。

![使用 GroupDocs.Viewer for Java 將 NSF 檔案轉換為 HTML、JPG、PNG 及 PDF](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## 快速解答
- **主要使用情境是什麼？** 將 NSF 檔案渲染為 PDF、HTML、JPG 或 PNG，以供網站、歸檔或分享使用。  
- **哪個函式庫負責轉換？** GroupDocs.Viewer for Java。  
- **需要授權嗎？** 可使用免費試用版；正式環境需購買完整授權。  
- **需要哪個 Java 版本？** JDK 8 或更新版本。  
- **可以批次處理多個 NSF 檔案嗎？** 可以 — 將渲染邏輯放入迴圈，並使用 try‑with‑resources 管理資源。

## 「convert nsf to pdf」是什麼？

將 NSF（Lotus Notes 資料庫）檔案轉換為 PDF，可產生一個靜態且廣受支援的文件，任何裝置皆可開啟，無需原始的 Notes 客戶端。此轉換對於歸檔、法律合規以及便捷分發皆相當有用。

## 為何要將 NSF 轉換為 PDF 及其他格式？

- **通用存取**：PDF、HTML、JPG 與 PNG 幾乎在所有平台皆可閱讀。  
- **保留版面**：PDF 能維持原始頁面布局、字型與圖形。  
- **網頁整合**：HTML 可在瀏覽器中快速檢視，無需額外外掛。  
- **影像擷取**：JPG/PNG 非常適合作為縮圖、預覽圖或嵌入其他應用程式。

## 前置條件

在實作 GroupDocs.Viewer for Java 之前，請確保具備以下條件：

1. **函式庫與相依性：**  
   - Maven（用於相依性管理）  
   - 系統已安裝 JDK 8 或更新版本。  

2. **環境設定：**  
   - 具備 Java 程式設計的基本概念  
   - 熟悉 Maven 以建立專案。  

3. **知識前置：**  
   - Java 檔案處理基礎  
   - 文件轉換概念。  

## 設定 GroupDocs.Viewer for Java

### Maven 設定

將 GroupDocs.Viewer 加入您的 Java 專案，於 `pom.xml` 中加入以下設定：

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

使用 GroupDocs.Viewer 時，您可以：

- **免費試用**：取得基本功能以評估本工具。  
- **臨時授權**：取得臨時授權以使用完整功能。  
- **購買**：考慮在正式環境購買授權。  

### 基本初始化

以下方式初始化 GroupDocs.Viewer：

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## 如何將 NSF 轉換為 PDF

以下章節示範如何將 NSF 檔案渲染為 HTML、JPG、PNG、**以及 PDF**。PDF 範例直接滿足主要關鍵字「convert nsf to pdf」。

### 渲染 NSF 為 HTML

#### 概觀
將 NSF 文件轉換為 HTML 格式，並將資源嵌入 HTML 內，方便網頁檢視。

#### 步驟說明

**1. 設定輸出目錄與檔案路徑**  
定義輸出 HTML 檔案的存放位置。

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

**2. 設定載入選項**  
使用特定選項（如資源載入逾時）自訂載入過程。

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

**3. 初始化 Viewer 並渲染**  
使用 Viewer 類別將文件渲染為 HTML 格式。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

### 渲染 NSF 為 JPG

#### 概觀
將 NSF 文件轉換為高品質 JPG 影像，以供分享或整合至影像系統。

**1. 定義輸出路徑**  
設定儲存渲染後 JPG 的檔案路徑格式。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

**2. 設定並渲染**  
設定 Viewer 並將文件渲染為 JPEG 影像。

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

### 渲染 NSF 為 PNG

#### 概觀
將文件渲染為 PNG 格式，具無損壓縮與高解析度特性。

**1. 設定輸出路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

**2. 渲染文件**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

### 渲染 NSF 為 PDF

#### 概觀
將 NSF 文件轉換為 PDF 格式，為通用接受的文件標準。

**1. 定義輸出路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```

**2. 渲染為 PDF**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## 實務應用

1. **基於網頁的文件分享**：將 NSF 檔案渲染為 HTML，以便在網路平台上輕鬆分享。  
2. **影像歸檔**：以 JPG 或 PNG 格式儲存文件的高品質影像。  
3. **通用文件存取**：使用 PDF 轉換，確保在各種裝置上皆能相容。  

## 效能考量

- **優化資源載入**：根據系統能力調整 `setResourceLoadingTimeout`。  
- **記憶體管理**：透過正確使用 try‑with‑resources 管理 Viewer 實例，以確保記憶體使用效率。  
- **批次處理**：針對大規模轉換，考慮以批次方式處理文件，以管理資源使用。  

## 常見問題

1. **什麼是轉換 NSF 文件的最佳格式？**  
   - 依需求而定：網頁檢視選 HTML，通用存取選 PDF，影像需求選 JPG/PNG。  

2. **如何有效處理大型 NSF 檔案？**  
   - 考慮優化載入選項並以批次方式處理。  

3. **能否自訂影像格式的輸出品質？**  
   - 可以，設定 `JpgViewOptions` 或 `PngViewOptions` 時調整解析度等參數。  

4. **轉換失敗時該怎麼辦？**  
   - 檢查檔案路徑、確保 Viewer 實例正確設定，並參考 GroupDocs 文件中的故障排除說明。  

5. **有沒有辦法在批次程序中自動化這些轉換？**  
   - 當然可以！在多個文件上使用迴圈即可有效自動化此流程。  

## 常見問答

**Q: 如何在不遺失註解的情況下將 NSF 檔案轉換為 PDF？**  
A: GroupDocs.Viewer 會在 `PdfViewOptions` 渲染階段保留大多數註解，確保 PDF 與原始版面相同。

**Q: 能否轉換受密碼保護的 NSF 檔案？**  
A: 可以。於初始化 Viewer 前，透過 `LoadOptions` 提供相應的認證資訊。

**Q: 推薦使用哪個 Java 版本以獲得最佳效能？**  
A: 建議使用 JDK 11 或更新版本，因其提供更佳的垃圾回收與併發處理，對批次轉換有助益。

**Q: 能否為 JPG/PNG 輸出設定自訂 DPI？**  
A: 可以，在呼叫 `viewer.view(options)` 前，透過設定 `JpgViewOptions` 或 `PngViewOptions` 的 DPI 參數來調整。

**Q: GroupDocs.Viewer 是否支援直接將輸出串流至 Web 回應？**  
A: 支援。您可以使用 view options 的 `Stream` 重載版本，將結果直接寫入 HTTP 回應，而非寫入檔案路徑。

## 結論

本指南探討了如何使用 GroupDocs.Viewer for Java **將 nsf 轉換為 pdf** 及其他格式。依循上述步驟，即可將文件轉換功能順利整合至您的應用程式中。建議進一步探索 GroupDocs.Viewer 的其他功能，並考慮將其納入專案，以提升文件處理的完整度。

---

**Last Updated:** 2026-02-13  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs