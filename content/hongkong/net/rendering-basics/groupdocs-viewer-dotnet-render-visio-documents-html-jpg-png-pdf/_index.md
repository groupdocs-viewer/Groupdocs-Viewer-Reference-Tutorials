---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer for .NET 輕鬆將 Microsoft Visio 檔案轉換為多種格式。增強文件可存取性，實現 Web 整合。"
"title": "如何使用 GroupDocs.Viewer 在 .NET 中將 Visio 文件呈現為 HTML、JPG、PNG 和 PDF"
"url": "/zh-hant/net/rendering-basics/groupdocs-viewer-dotnet-render-visio-documents-html-jpg-png-pdf/"
"weight": 1
type: docs
---
# 如何使用 .NET 中的 GroupDocs.Viewer 將 Visio 文件呈現為 HTML、JPG、PNG 和 PDF

## 介紹

您是否正在尋找一款多功能工具，將 Microsoft Visio 圖表轉換為 HTML、JPG、PNG 或 PDF 等格式？本教程將指導您使用 **適用於 .NET 的 GroupDocs.Viewer**，一個旨在簡化文件轉換的強大庫。閱讀本文後，您將了解如何有效地將 Visio 檔案轉換為不同的格式，從而提高可存取性和可用性。

**您將學到什麼：**
- 如何在 .NET 環境中設定 GroupDocs.Viewer
- 將圖表渲染為 HTML、JPG、PNG 和 PDF 的逐步說明
- 獲得最佳結果的關鍵配置選項
- 實際應用和整合可能性

讓我們先介紹一下先決條件。

## 先決條件

在深入研究 GroupDocs.Viewer for .NET 之前，請確保您已：

### 所需的函式庫、版本和相依性
- **適用於 .NET 的 GroupDocs.Viewer**：建議使用25.3.0或更高版本。
- 相容的 .NET 開發環境（例如 Visual Studio）。

### 環境設定要求
- 您的系統應該支援.NET Framework 或 .NET Core/5+。

### 知識前提
- 對 C# 和 .NET 專案結構有基本的了解。

## 為 .NET 設定 GroupDocs.Viewer

首先，安裝 **GroupDocs.檢視器** 使用 NuGet 套件管理器控制台或 .NET CLI 程式庫：

**NuGet 套件管理器控制台**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 許可證取得步驟
- **免費試用**：從免費試用開始探索其功能。
- **臨時執照**：取得臨時許可證以進行延長測試。
- **購買**：如果需要長期使用，請考慮購買。

### 基本初始化和設定

透過確保您的專案正確引用庫來初始化 GroupDocs.Viewer：

```csharp
using GroupDocs.Viewer;
// 使用文檔路徑初始化檢視器對象
using (Viewer viewer = new Viewer("path/to/your/document.vsd"))
{
    // 根據需要配置選項
}
```

## 實施指南

我們將逐步介紹如何將 Visio 文件呈現為不同的格式。

### 將 Visio 文件呈現為 HTML

**概述**：將圖表轉換為 HTML 可以輕鬆嵌入網頁，增強可訪問性和互動性。

#### 步驟 1：設定 HTML 視圖選項

配置 `HtmlViewOptions` 對於嵌入式資源：

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // 配置圖形寬度
    viewer.View(options); // 渲染並儲存為 HTML
}
```

**金鑰配置**： 
- `RenderFiguresOnly`：僅渲染圖形。
- `FigureWidth`：設定每個圖形的寬度（以像素為單位）。

### 將 Visio 文件渲染為 JPG

**概述**：將圖表轉換為 JPEG 影像有助於跨平台共享，無需專門的軟體。

#### 步驟2：設定JpgViewOptions

設定適合將圖形渲染為影像的選項：

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // 調整圖形寬度
    viewer.View(options); // 渲染並儲存為 JPG
}
```

**故障排除提示**：如果輸出影像不清楚，請驗證 `FigureWidth` 符合您預期的顯示尺寸。

### 將 Visio 文件渲染為 PNG

**概述**：PNG 格式提供無損壓縮的高品質影像，非常適合詳細圖表。

#### 步驟3：定義PngViewOptions

專門配置渲染為 PNG 的選項：

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // 設定圖形寬度
    viewer.View(options); // 渲染並儲存為 PNG
}
```

### 將 Visio 文件渲染為 PDF

**概述**：將圖表轉換為 PDF 格式非常適合分發和存檔，並提供通用的文件視圖。

#### 步驟 4：設定 PdfViewOptions

配置以 PDF 格式渲染圖形的選項：

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // 定義圖形寬度
    viewer.View(options); // 渲染並儲存為 PDF
}
```

## 實際應用

GroupDocs.Viewer 可以增強各種系統中的文件管理：
1. **入口網站**：將渲染的 HTML 圖形直接嵌入網頁中以取得動態內容。
2. **文件管理系統（DMS）**：使用 JPG、PNG 或 PDF 格式，以便在 DMS 平台內輕鬆共享和儲存。
3. **商業報告工具**：產生嵌入不同格式圖表的報告以滿足演示需求。

## 性能考慮

使用 GroupDocs.Viewer 時優化效能至關重要：
- **資源使用情況**：監控渲染期間的記憶體使用情況以避免瓶頸。
- **最佳實踐**：盡可能利用非同步操作來提高反應能力。
- **記憶體管理**：使用後及時處置檢視器物件以釋放資源。

## 結論

在本教學中，您學習如何利用 GroupDocs.Viewer for .NET 將 Visio 文件渲染為 HTML、JPG、PNG 和 PDF 格式。借助這些技能，您可以增強文件的可訪問性，並將多種渲染功能整合到您的應用程式中。

**後續步驟**：查看 GroupDocs.Viewer 的其他功能 [API 參考](https://reference.groupdocs.com/viewer/net/) 或嘗試不同的渲染選項以滿足您的特定需求。

## 常見問題部分

1. **我可以在沒有許可證的情況下呈現 Visio 文件嗎？**
   - 是的，您可以使用免費試用許可證的 GroupDocs.Viewer 來初步探索其功能。
2. **除了 Visio 之外，GroupDocs.Viewer 還支援哪些文件格式？**
   - 它支援多種格式，包括 PDF、Word、Excel 等。
3. **是否可以自訂渲染圖形的輸出尺寸？**
   - 絕對！調整 `FigureWidth` 在渲染選項中控制輸出尺寸。
4. **如何使用 GroupDocs.Viewer 處理大型文件？**
   - 透過配置記憶體使用設定並在適當的情況下使用非同步進程來優化效能。