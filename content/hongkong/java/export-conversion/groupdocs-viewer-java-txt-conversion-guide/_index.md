---
"date": "2025-04-24"
"description": "學習如何使用 GroupDocs.Viewer for Java 將 TXT 檔案有效率地轉換為 HTML、JPG、PNG 和 PDF 等多種格式。請遵循本逐步指南。"
"title": "使用 GroupDocs.Viewer for Java 將 TXT 檔案轉換為 HTML、JPG、PNG 和 PDF"
"url": "/zh-hant/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/"
"weight": 1
---

# 使用 GroupDocs.Viewer for Java 轉換 TXT 檔案：綜合指南

## 介紹

在當今的數位世界中，高效的文件管理對企業和個人都至關重要。無論您需要在網路上顯示文字文檔，還是需要以各種格式存檔文件，轉換文字 (TXT) 文件都是常見的需求。 **GroupDocs.Viewer for Java** 提供高效的解決方案，輕鬆將 TXT 檔案渲染為 HTML、JPG、PNG 和 PDF 等多種格式。本指南將指導您如何使用這個多功能函式庫實現無縫轉換。

### 您將學到什麼：
- 在 Java 環境中設定 GroupDocs.Viewer
- 將 TXT 檔案轉換為多頁和單頁 HTML
- 將 TXT 文件渲染為影像格式（JPG、PNG）
- 將TXT內容轉換為PDF格式

讓我們探討一下開始實施之前所需的先決條件。

## 先決條件

在深入研究 GroupDocs.Viewer for Java 之前，請確保您已：

### 所需的庫和相依性：
- **GroupDocs.Viewer for Java** 版本 25.2 或更高版本。
  
### 環境設定要求：
- 您的系統上安裝了相容的 Java 開發工具包 (JDK)（建議使用 Java 8+）。
- 整合開發環境 (IDE)，如 IntelliJ IDEA、Eclipse 或 NetBeans。

### 知識前提：
- 對 Java 程式設計和文件處理有基本的了解。
- 熟悉 Maven 的依賴管理很有幫助。

## 為 Java 設定 GroupDocs.Viewer

開始使用 **GroupDocs.檢視器**，透過 Maven 將其包含在您的專案中，如下所示：

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

### 許可證取得步驟：
- 從 **免費試用** 或獲得 **臨時執照** 探索 GroupDocs.Viewer 的全部功能。
- 考慮透過其官方管道購買許可證 [購買頁面](https://purchase.groupdocs.com/buy) 可供長期使用。

### 基本初始化和設定：
1. 將 Maven 依賴項新增至您的專案。
2. 確保您已使用 JDK 和 IDE 設定了環境。

現在，讓我們來探索如何實現 GroupDocs.Viewer 的不同功能，將 TXT 檔案轉換為各種格式。

## 實施指南

### 功能 1：將 TXT 渲染為多頁 HTML

#### 概述：
此功能將 TXT 文件轉換為多頁 HTML 格式，從而保留多個網頁上的文字結構。

##### 步驟：

**導入所需庫**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**設定路徑和檢視器**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // 配置使用嵌入資源進行渲染的選項
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // 使用這些選項將文件渲染為 HTML
    viewer.view(options);
}
```

**解釋：**
- `HtmlViewOptions.forEmbeddedResources` 在這裡使用以確保所有資源都嵌入在輸出檔案中，使它們自成一體。

### 功能 2：將 TXT 渲染為單頁 HTML

#### 概述：
此功能將您的整個文字文件壓縮為單一 HTML 頁面，非常適合快速預覽或摘要。

##### 步驟：

**導入所需庫**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**設定路徑和檢視器**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // 配置使用嵌入資源進行渲染的選項
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // 設定選項以呈現為單頁 HTML
    options.setRenderToSinglePage(true);
    
    // 使用這些選項渲染文檔
    viewer.view(options);
}
```

**解釋：**
這 `setRenderToSinglePage(true)` 方法將所有文字壓縮到一個網頁中。

### 功能3：將TXT渲染為JPG

#### 概述：
將您的 TXT 檔案轉換為高品質的 JPEG 影像，適合共享或列印目的。

##### 步驟：

**導入所需庫**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**設定路徑和檢視器**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // 配置渲染為 JPEG 影像的選項
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // 使用這些選項將文件渲染為 JPG
    viewer.view(options);
}
```

**解釋：**
- `JpgViewOptions` 允許您指定針對影像轉換客製化的輸出路徑和渲染設定。

### 功能 4：將 TXT 渲染為 PNG

#### 概述：
將文字文件轉換為便攜式網路圖形 (PNG) 格式，提供無損壓縮的高品質圖片。

##### 步驟：

**導入所需庫**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**設定路徑和檢視器**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // 配置渲染為 PNG 影像的選項
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // 使用這些選項將文件渲染為 PNG
    viewer.view(options);
}
```

**解釋：**
- `PngViewOptions` 在這裡使用，類似於 `JpgViewOptions`，但具有 PNG 格式特有的優勢。

### 功能 5：將 TXT 轉換為 PDF

#### 概述：
從文字文件產生 PDF 文件，非常適合以普遍接受的格式分發或存檔。

##### 步驟：

**導入所需庫**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**設定路徑和檢視器**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // 配置渲染為 PDF 的選項
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // 使用這些選項將文件渲染為 PDF
    viewer.view(options);
}
```

**解釋：**
- `PdfViewOptions` 提供特定於 PDF 轉換的設置，包括頁面設定和資源嵌入。

## 實際應用

GroupDocs.Viewer for Java 的功能擴展到幾個實際用例：

1. **文件管理系統：** 自動將基於文字的文件轉換為適合內部入口網站的網路友善格式。
2. **發布平台：** 將作者提交的內容從 TXT 轉換為 HTML，以便無縫整合到內容管理系統。
3. **歸檔解決方案：** 以現代、易於存取的 PDF 或圖像格式儲存舊文字檔案。
4. **與雲端儲存整合：** 自動跨雲端平台轉換和儲存文檔，以實現更好的可存取性。