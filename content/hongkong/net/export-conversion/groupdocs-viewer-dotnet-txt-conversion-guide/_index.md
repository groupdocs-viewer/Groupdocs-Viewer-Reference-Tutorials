---
"date": "2025-04-25"
"description": "透過本綜合指南了解如何使用 GroupDocs.Viewer for .NET 將 TXT 檔案轉換為 HTML、JPG、PNG 和 PDF 等多種格式。"
"title": "使用 GroupDocs.Viewer .NET 將 TXT 轉換為 HTML、JPG、PNG、PDF 完整指南"
"url": "/zh-hant/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# 使用 GroupDocs.Viewer .NET 將 TXT 轉換為多種格式

## 介紹

想要輕鬆地將文字文件轉換為 HTML、JPG、PNG 或 PDF 等各種格式？管理文件轉換可能頗具挑戰性，尤其是在處理多頁文件或特定格式要求時。 **適用於 .NET 的 GroupDocs.Viewer** 簡化了將 TXT 檔案呈現為多種輸出格式的過程，確保您的資料可存取且具有視覺吸引力。

![使用 GroupDocs.Viewer for .NET 將 TXT 轉換為 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

在本指南中，我們將探索如何使用 GroupDocs.Viewer for .NET 將 TXT 文件轉換為多頁 HTML、單頁 HTML、JPG、PNG 和 PDF。最終，您將掌握：
- 使用 C# 和 GroupDocs.Viewer 轉換 TXT 文件
- 根據您的需求實現不同的渲染選項
- 優化轉換期間的效能

讓我們深入研究解決您的文件轉換難題。

## 先決條件

在開始之前，請確保您已準備好以下內容：
- **開發環境**：Visual Studio 2019 或更高版本。
- **.NET 框架**：版本 4.6.1 或更高版本。
- **GroupDocs.Viewer for .NET 函式庫**：
  - 透過 NuGet 套件管理器控制台： `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - 使用 .NET CLI： `dotnet add package GroupDocs.Viewer --version 25.3.0`

建議熟悉 C# 程式設計和 .NET 中的基本檔案操作，以便輕鬆跟進。

## 為 .NET 設定 GroupDocs.Viewer

### 安裝

首先，安裝 **GroupDocs.檢視器** 使用您首選的套件管理器的庫：

#### NuGet 套件管理器控制台
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 授權

你可以從 **免費試用** 或獲得 **臨時執照** 探索 GroupDocs.Viewer for .NET 的全部功能，不受評估限制：
- 免費試用： [點此下載](https://releases.groupdocs.com/viewer/net/)
- 臨時執照： [點擊此處請求](https://purchase.groupdocs.com/temporary-license/)

如需繼續使用，請考慮直接從 [群組文檔](https://purchase。groupdocs.com/buy).

### 基本初始化

要在您的專案中設定 GroupDocs.Viewer：

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// 使用 TXT 檔案路徑初始化 Viewer 物件。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 您的渲染程式碼將放在這裡。
}
```

## 實施指南

現在，讓我們深入研究每個功能並看看如何實現它們。

### 將 TXT 文件渲染為多頁 HTML

#### 概述
此功能示範如何將 TXT 文件轉換為多頁 HTML 格式。文字檔案的每一頁都會呈現為包含嵌入資源的單獨 HTML 檔案。

#### 步驟 1：設定檢視器

創建一個 `Viewer` 來源 TXT 檔案的物件：

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// 使用範例文字檔案初始化檢視器。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 繼續步驟 2...
```

#### 步驟 2：配置 HTML 視圖選項

設定 `HtmlViewOptions` 分別渲染每個頁面：

```csharp
// 設定多頁渲染的 HTML 視圖選項。
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// 將文件呈現為多頁 HTML。
viewer.View(options);
}
```

**解釋**： 這 `ForEmbeddedResources()` 方法確保圖像和样式等資源直接嵌入 HTML 文件中，方便共享。

### 將 TXT 文件渲染為單頁 HTML

#### 概述
將 TXT 文件轉換為單一 HTML 頁面，非常適合需要顯示為一個連續網頁的文件。

#### 步驟 1：設定檢視器

初始化 `Viewer` 目的：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// 為不同的文字檔案初始化一個新的檢視器實例。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // 繼續步驟 2...
```

#### 步驟 2：設定單頁 HTML 選項

配置 `HtmlViewOptions` 啟用單頁設定：

```csharp
// 設定渲染到單一 HTML 頁面的選項。
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// 呈現為單一 HTML 頁面。
viewer.View(options);
}
```

**解釋**： 這 `RenderToSinglePage` 屬性確保整個內容在一個頁面上呈現。

### 將 TXT 文件渲染為 JPG

#### 概述
此功能可讓您將文字文件轉換為 JPEG 影像，這對於視覺演示或存檔目的很有用。

#### 步驟 1：設定檢視器

準備你的 `Viewer` 目的：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// 使用範例檔案初始化檢視器。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 繼續步驟 2...
```

#### 步驟2：配置JPG視圖選項

設定 `JpgViewOptions` 用於影像渲染：

```csharp
// 設定渲染為 JPG 影像的選項。
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// 將文檔呈現為 JPEG 文件。
viewer.View(options);
}
```

**解釋**： 這 `JpgViewOptions` 該類別指定如何以 JPEG 格式呈現和儲存文件的每一頁。

### 將 TXT 文件渲染為 PNG

#### 概述
將文字文件轉換為 PNG 格式，提供具有透明度支援的高品質影像輸出。

#### 步驟 1：設定檢視器

初始化 `Viewer` 目的：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// 為您的 TXT 檔案建立一個檢視器實例。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 繼續步驟 2...
```

#### 步驟 2：設定 PNG 視圖選項

設定 `PngViewOptions`：

```csharp
// 設定渲染為 PNG 影像的視圖選項。
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// 以 PNG 格式呈現文件。
viewer.View(options);
}
```

**解釋**： 這 `PngViewOptions` 類別允許每個頁面以透明度呈現，使其適合分層圖形。

### 將 TXT 文件渲染為 PDF

#### 概述
此功能非常適合將文字文件轉換為通用的 PDF 格式。

#### 步驟 1：設定檢視器

準備你的 `Viewer` 目的：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// 為您的範例文字檔案初始化檢視器實例。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 繼續步驟 2...
```

#### 步驟 2：設定 PDF 檢視選項

設定 `PdfViewOptions`：

```csharp
// 設定呈現為 PDF 文件的視圖選項。
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// 將文件渲染為 PDF 檔案。
viewer.View(options);
}
```

**解釋**： 這 `PdfViewOptions` 類別指定如何將 TXT 檔案轉換並儲存為 PDF 文件。

## 結論

使用 GroupDocs.Viewer for .NET，將文字文件轉換為各種格式非常簡單。本指南介紹如何使用 C# 將 TXT 檔案轉換為多頁 HTML、單頁 HTML、JPG、PNG 和 PDF。無論您是想增強文件的可訪問性還是相容性，這些方法都能提供強大的解決方案。

如需進一步協助或更多進階功能，請參閱 [官方 GroupDocs.Viewer 文檔](https://docs.groupdocs.com/viewer/net/)編碼愉快！