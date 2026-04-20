---
date: '2026-02-28'
description: 學習如何使用 GroupDocs.Viewer for Java 將 CDR 檔案轉換為 HTML、JPG、PNG 及 PDF。包括設定、程式碼範例與效能技巧。
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: 使用 GroupDocs.Viewer Java 將 CDR 轉換為 HTML、JPG、PNG、PDF
type: docs
url: /zh-hant/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# 轉換 CDR 為 HTML、JPG、PNG、PDF（使用 GroupDocs.Viewer Java）

如果您需要 **將 CDR 轉換為 HTML**（或 JPG、PNG、PDF）且要求快速且可靠，您已來到正確的教學。本指南將一步步說明從安裝 GroupDocs.Viewer for Java 到將 CorelDRAW（CDR）檔案渲染成適合網頁的 HTML 頁面、高品質影像以及通用的 PDF。完成後，您只需幾行程式碼即可在任何 Java 應用程式中整合這些轉換功能。

![Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## 快速解答
- **哪個函式庫可以將 CDR 轉換為 HTML？** GroupDocs.Viewer for Java。  
- **我也可以將 CDR 轉換為 JPG、PNG、PDF 嗎？** 可以——使用相同的 Viewer API，只需更換不同的檢視選項。  
- **需要授權嗎？** 測試時可使用免費試用或臨時授權；正式上線則需正式授權。  
- **需要哪個版本的 Java？** JDK 8 或更新版本。  
- **支援批次轉換嗎？** 完全支援——只要在同一個 Viewer 實例中迴圈處理檔案即可。

## 什麼是「convert CDR to HTML」？
將 CDR 轉換為 HTML 意指把 CorelDRAW 向量檔案轉換成標準的 HTML 標記，必要時會內嵌圖片與樣式，讓設計直接在瀏覽器中顯示，無需原始設計軟體。

## 為什麼要將 CDR 轉換為 HTML、JPG、PNG 或 PDF？
- **HTML** 可讓您在網站入口嵌入圖形，立即分享。  
- **JPG** 與 **PNG** 為光柵圖像，適合相簿、縮圖或電子郵件附件。  
- **PDF** 提供可列印、跨平台的版本，適用於歸檔或文件共享系統。  

同時擁有這四種格式，您可以依不同受眾提供最合適的檔案類型，提升效能並確保資產未來可用。

## 前置條件

在開始之前，請確保您已具備：

1. **函式庫與相依性** – 已在 Maven 專案中加入 GroupDocs.Viewer。  
2. **Java 開發工具包 (JDK)** – 已安裝 8 版或更新版本。  
3. **基本的 Java 知識** – 以便了解程式碼片段。

### 必要的函式庫、版本與相依性

將以下 Maven 設定加入您的 `pom.xml`（與原教學完全相同）：

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

### 授權取得步驟

GroupDocs.Viewer 提供免費試用、測試用臨時授權或正式購買選項：

- **免費試用** – 從 [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/) 下載。  
- **臨時授權** – 前往 [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) 申請。  
- **購買** – 於 [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) 取得永久授權。

## 設定 GroupDocs.Viewer for Java

### 使用 Maven 安裝
上述的 Maven 片段會自動下載所有必要的 JAR。儲存檔案後執行 `mvn clean install` 即可。

### 授權初始化
在渲染任何文件之前先初始化授權：

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## 實作指南

以下提供每種輸出格式的逐步範例。程式碼區塊與原教學完全相同，我們僅在其前後加入說明文字。

### 如何使用 GroupDocs.Viewer 將 CDR 轉換為 HTML

#### 渲染 CDR 文件為 HTML
**概述：** 將 CDR 檔案轉換成適合網頁的 HTML，方便分享。

**步驟 1 – 設定檔案路徑**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**步驟 2 – 初始化 Viewer 並渲染**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### 如何使用 GroupDocs.Viewer 將 CDR 轉換為 JPG

#### 渲染 CDR 文件為 JPG
**概述：** 從 CDR 原始檔產生高品質 JPEG 影像。

**步驟 1 – 設定檔案路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**步驟 2 – 初始化 Viewer 並渲染**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### 如何使用 GroupDocs.Viewer 將 CDR 轉換為 PNG

#### 渲染 CDR 文件為 PNG
**概述：** 產生無損 PNG 影像，適合存檔或設計用途。

**步驟 1 – 設定檔案路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**步驟 2 – 初始化 Viewer 並渲染**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### 如何使用 GroupDocs.Viewer 將 CDR 轉換為 PDF

#### 渲染 CDR 文件為 PDF
**概述：** 將 CDR 檔案轉成通用的 PDF 格式。

**步驟 1 – 設定檔案路徑**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**步驟 2 – 初始化 Viewer 並渲染**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## 實務應用

- **網站入口**：使用 HTML 轉換直接在網站嵌入 CDR 設計。  
- **影像相簿**：部署 JPG/PNG 輸出以加速相簿載入。  
- **文件共享**：提供 PDF 給需要可列印、唯讀版本的客戶。  
- **歸檔**：同時保存多種格式，以確保未來可存取。  
- **跨平台整合**：將產生的檔案輸入其他服務（如 OCR、分析）中。

## 效能考量

- **即時釋放 Viewer 實例**（如示範的 try‑with‑resources）以釋放記憶體。  
- **批次處理**：使用相同的 Viewer 設定迴圈處理多個 CDR 檔，可減少開銷。  
- **資源配置**：大型或複雜的 CDR 檔案需足夠的 CPU / RAM，建議使用監控工具微調。

## 結論

我們已示範如何使用 GroupDocs.Viewer for Java **將 CDR 轉換為 HTML**，以及 JPG、PNG、PDF。依照簡潔的程式碼範例與最佳實踐，您可以將這些轉換功能整合至任何基於 Java 的工作流程，為使用者提供彈性且高品質的輸出。

### 後續步驟
- 嘗試進階渲染選項，如自訂頁面大小或浮水印。  
- 結合轉換管線與 REST API，提供即時檔案轉換服務。  
- 加入社群，於 [GroupDocs Forum](https://forum.groupdocs.com/c/viewer) 提問交流。

## 常見問題

**Q: 可以轉換有密碼保護的 CDR 檔案嗎？**  
A: 可以。使用接受密碼參數的 `Viewer` 實例載入檔案（請參閱 API 文件）。

**Q: 同時轉換的頁數有上限嗎？**  
A: 沒有硬性上限，但極大型檔案可能需要更多記憶體，建議分頁處理。

**Q: HTML 輸出會包含嵌入字型嗎？**  
A: 使用 `HtmlViewOptions.forEmbeddedResources` 時，字型會以 Base64 形式嵌入，確保渲染一致。

**Q: 如何控制 JPEG 的品質？**  
A: `JpgViewOptions` 提供 `setQuality(int)` 方法，可設定 1‑100 的品質值。

**Q: 能在 Linux 伺服器上轉換 CDR 檔案嗎？**  
A: 完全可以——只要安裝 JDK，GroupDocs.Viewer 即可跨平台運作。

---

**最後更新：** 2026-02-28  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs