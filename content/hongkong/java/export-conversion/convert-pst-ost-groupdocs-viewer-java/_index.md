---
"date": "2025-04-24"
"description": "了解如何使用 GroupDocs.Viewer for Java 輕鬆將 Outlook PST/OST 檔案轉換為 HTML、JPG、PNG 或 PDF 等可存取格式。本指南涵蓋所有步驟和所需配置。"
"title": "使用 GroupDocs.Viewer for Java 將 PST/OST 轉換為 HTML、JPG、PNG、PDF | 匯出和轉換指南"
"url": "/zh-hant/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/"
"weight": 1
---

# 使用 GroupDocs.Viewer for Java 將 PST/OST 轉換為 HTML、JPG、PNG、PDF

## 介紹

您是否希望將 Outlook PST 或 OST 檔案轉換為更易於存取的格式，例如 HTML、JPG、PNG 或 PDF？透過強大的 GroupDocs.Viewer for Java 函式庫，這項任務變得簡單且有效率。本教學將指導您使用 GroupDocs.Viewer for Java 渲染 PST/OST 文檔，從而實現跨平台輕鬆共享和檢視。

**您將學到什麼：**
- 如何使用 GroupDocs.Viewer for Java 設定您的環境。
- 將 PST/OST 檔案轉換為 HTML、JPG、PNG 和 PDF 格式的逐步說明。
- 關鍵配置選項可最佳化您的文件轉換流程。

首先讓我們回顧一下開始之前所需的先決條件。

## 先決條件

要繼續本教程，請確保您具備以下條件：

### 所需的庫和依賴項
- **GroupDocs.Viewer for Java**：您需要 25.2 或更高版本。
- **Java 開發工具包 (JDK)**：需要 JDK 8 或更高版本才能編譯和執行您的應用程式。

### 環境設定要求
- 相容的整合開發環境 (IDE)，如 IntelliJ IDEA、Eclipse 或 NetBeans。
- 您的系統上安裝了 Maven 來管理依賴項。

### 知識前提
- 對 Java 程式設計有基本的了解。
- 熟悉使用 Maven 進行依賴管理。

有了先決條件後，讓我們繼續為 Java 設定 GroupDocs.Viewer。

## 為 Java 設定 GroupDocs.Viewer

要使用 GroupDocs.Viewer for Java，您需要將其新增為專案的依賴項。如果您使用的是 Maven，請依照下列步驟操作：

**Maven配置：**

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

### 許可證取得步驟
- **免費試用**：您可以先免費試用，探索其功能。
- **臨時執照**：如果您需要更多時間進行評估，請申請臨時許可證。
- **購買**：購買長期使用的許可證。

### 基本初始化和設定

一旦 Maven 配置完成，請在 Java 應用程式中初始化 GroupDocs.Viewer：

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // 使用範例 PST 檔案路徑初始化檢視器
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

設定完成後，讓我們繼續實作渲染功能。

## 實施指南

本節根據您想要將 PST/OST 文件呈現為的格式分為幾個邏輯步驟：HTML、JPG、PNG 和 PDF。

### 將 PST/OST 文件渲染為 HTML

**概述：**
將 PST/OST 檔案渲染為 HTML，使其能夠在 Web 瀏覽器中輕鬆查看。此功能將資源直接嵌入 HTML 文件中，以實現無縫檢視。

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

**解釋**：定義 HTML 檔案的儲存位置。 `Paths` 類別有助於有效地管理檔案路徑。

#### 步驟 2：配置載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**解釋**：設定資源載入的超時時間，以防止渲染過程中出現延遲。

#### 步驟 3：初始化檢視器並渲染 HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

**解釋**：使用 `HtmlViewOptions` 在 HTML 文件中嵌入資源。 `view()` 方法執行渲染。

### 將 PST/OST 文件渲染為 JPG

**概述：**
將您的 PST/OST 檔案的每一頁轉換為單獨的 JPG 映像，以便於共享和檢視。

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

**解釋**：指定輸出 JPG 檔案的目錄和檔案名稱模式。

#### 步驟 2：配置載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**解釋**：與HTML渲染類似，設定資源載入的逾時時間。

#### 步驟3：初始化檢視器並渲染JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**解釋**： 使用 `JpgViewOptions` 將每個頁面呈現為單獨的 JPG 檔案。

### 將 PST/OST 文件渲染為 PNG

**概述：**
將您的 PST/OST 檔案轉換為 PNG 影像，這對於高品質的演示和列印輸出來說是理想的。

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

**解釋**：定義 PNG 檔案的目錄和檔案名稱模式。

#### 步驟 2：配置載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**解釋**：設定資源載入超時以有效管理渲染時間。

#### 步驟3：初始化檢視器並渲染PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**解釋**： 使用 `PngViewOptions` 將每個頁面渲染為單獨的 PNG 檔案。

### 將 PST/OST 文件渲染為 PDF

**概述：**
將整個 PST/OST 文件轉換為單一 PDF 文件，以便於分發和存檔。

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

**解釋**：指定輸出 PDF 檔案的目錄和檔案名稱。

#### 步驟 2：配置載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**解釋**：設定超時以確保渲染順利無延遲。

#### 步驟 3：初始化檢視器並渲染 PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**解釋**： 使用 `PdfViewOptions` 將整個文件呈現為單一 PDF 文件。

## 實際應用

以下是渲染 PST/OST 文件的一些實際用例：

1. **電子郵件歸檔：** 將電子郵件檔案轉換為 HTML 或 PDF，以便於存取和分享。
2. **文件管理系統：** 與需要文檔轉換才能儲存和檢索的系統整合。
3. **協作工具：** 在 Slack 或 Microsoft Teams 等協作工具中共用轉換後的文件。
4. **法律文件：** 透過將法律文件轉換為通用格式來準備法律文件。
5. **備份解決方案：** 以各種格式建立重要電子郵件和附件的備份。

## 性能考慮

為了優化使用 GroupDocs.Viewer for Java 時的效能，請考慮以下提示：
- 確保渲染過程中有效率的資源管理。
- 監控記憶體使用情況並根據需要調整配置以防止瓶頸。
- 如果您的應用程式環境支援非同步處理，請利用非同步處理來提高回應能力。

透過遵循本指南，您可以使用 GroupDocs.Viewer for Java 有效地將 PST/OST 檔案轉換為各種格式，從而增強跨不同平台的可存取性和可用性。