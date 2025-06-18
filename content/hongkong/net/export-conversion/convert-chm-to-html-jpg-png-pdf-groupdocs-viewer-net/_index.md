---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer .NET 輕鬆將 CHM 檔案轉換為 HTML、JPEG、PNG 和 PDF 格式。增強項目中文件的可存取性和分發能力。"
"title": "使用 GroupDocs.Viewer .NET 將 CHM 轉換為 HTML、JPG、PNG、PDF 綜合指南"
"url": "/zh-hant/net/export-conversion/convert-chm-to-html-jpg-png-pdf-groupdocs-viewer-net/"
"weight": 1
---

# 使用 GroupDocs.Viewer .NET 將 CHM 檔案轉換為 HTML、JPG、PNG 和 PDF

## 介紹

由於 CHM 文件相容性有限，您在查看或分享其內容時是否遇到了困難？將這些文件轉換為更易於存取的格式（例如 HTML、JPEG、PNG 或 PDF）可以解決此問題，使資訊更易於分發。在本指南中，我們將向您展示如何使用 **GroupDocs.Viewer .NET** 輕鬆將 CHM 檔案轉換為各種常用格式。您將學習如何精準有效率地處理文件渲染。

![使用 GroupDocs.Viewer for .NET 將 CHM 轉換為 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-chm-html-jpg-png-pdf.png)

### 您將學到什麼
- 將 CHM 檔案轉換為 HTML 以實現網頁相容性。
- 將 CHM 內容渲染為 JPEG 影像以進行視覺分享。
- 將 CHM 頁面轉換為 PNG 格式以獲得高品質的圖形。
- 將整個 CHM 文件匯出為 PDF，以獲得通用可讀的格式。

讀完本指南後，您將掌握這些轉換技巧，並準備將它們整合到您的專案中。讓我們從設定環境開始！

## 先決條件

在開始之前，請確保所有設定均正確：

- **GroupDocs.Viewer .NET** 版本 25.3.0 或更高版本。
- 類似 Visual Studio 的 C# 開發環境。
- 對 C# 中的文件處理和目錄管理有基本的了解。

### 環境設定要求
若要使用 GroupDocs.Viewer，請使用 NuGet 套件管理器控制台或 .NET CLI 安裝程式庫：

**NuGet 套件管理器控制台**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**\.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 許可證取得步驟

GroupDocs 提供免費試用，您也可以在購買前取得臨時授權進行測試。訪問 [購買頁面](https://purchase.groupdocs.com/buy) 探索許可證選項。

## 為 .NET 設定 GroupDocs.Viewer

要開始使用 GroupDocs.Viewer，請確保它已按照上述說明安裝在您的專案中。您可以依照以下步驟設定基本環境：

1. **初始化檢視器**：將您的 CHM 檔案載入到檢視器中。
2. **配置輸出目錄**：設定轉換後文件的儲存位置。

以下是初始化 GroupDocs.Viewer 以轉換 CHM 檔案的範例程式碼片段：
```csharp
using GroupDocs.Viewer;
using System.IO;

string chmFilePath = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.chm");
using (Viewer viewer = new Viewer(chmFilePath))
{
    // 進一步的配置和轉換將在這裡進行。
}
```

## 實施指南

### 將 CHM 渲染為 HTML

將 CHM 文件轉換為 HTML 格式後，可以在任何 Web 瀏覽器中查看該文件，從而增強可存取性。

#### 步驟 1：設定輸出目錄
為輸出 HTML 檔案建立一個目錄：
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "HTML");
Directory.CreateDirectory(outputDirectory);
```

#### 步驟 2：設定檢視器選項
使用 `HtmlViewOptions` 定義如何呈現 CHM 內容：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer(chmFilePath))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // 可選：將所有頁面渲染成單一 HTML 頁面
    viewer.View(options); 
}
```

### 將 CHM 渲染為 JPG

為了以視覺方式共享特定內容，將 CHM 檔案轉換為 JPEG 影像非常有用。

#### 步驟 1：設定影像的輸出目錄
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "JPG");
Directory.CreateDirectory(outputDirectory);
```

#### 步驟 2：設定 JPG 檢視器選項
將特定頁面渲染為 JPEG：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer(chmFilePath))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options, 1, 2, 3); // 僅將前三頁轉換為 JPEG 格式
}
```

### 將 CHM 渲染為 PNG

為了在轉換過程中保持高品質的圖形，請將 CHM 檔案渲染為 PNG 影像。

#### 步驟 1：設定 PNG 檔案的輸出目錄
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "PNG");
Directory.CreateDirectory(outputDirectory);
```

#### 步驟 2：設定 PNG 的檢視器選項
將特定頁面轉換為 PNG 格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer(chmFilePath))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options, 1, 2, 3); // 將前三頁轉換為 PNG 格式
}
```

### 將 CHM 渲染為 PDF

將 CHM 檔案轉換為 PDF 文件可實現跨裝置的通用可讀性。

#### 步驟 1：設定 PDF 檔案的輸出目錄
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "PDF");
Directory.CreateDirectory(outputDirectory);
```

#### 步驟 2：設定 PDF 轉換的檢視器選項
將整個 CHM 檔案渲染為 PDF：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer(chmFilePath))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options); // 將所有頁面轉換為 PDF 格式
}
```

## 實際應用

- **文件共享**：將 CHM 檔案轉換為 HTML 以用於線上文件。
- **檔案用途**：將內容儲存為 JPEG 或 PNG 影像，以便於存檔。
- **報告生成**：將技術手冊匯出為 PDF 以供官方報告。

與其他 .NET 系統的整合可增強檔案自動批次等功能，使此轉換流程在業務工作流程中無縫銜接。

## 性能考慮

為了優化使用 GroupDocs.Viewer 時的效能：
- 透過正確處理物件來確保高效的記憶體管理。
- 限制一次轉換的頁面數量，以防止資源耗盡。
- 使用嵌入式資源進行 HTML 轉換以減少外部依賴。

遵循這些最佳實務將確保文件轉換操作順利、有效率。

## 結論

現在，您已經掌握如何使用 GroupDocs.Viewer .NET 將 CHM 檔案轉換為各種格式。無論是將內容渲染為網頁友善的 HTML、JPEG 或 PNG 等圖像格式，還是通用的 PDF，此工具都能滿足您的文件處理需求。您可以考慮探索 API 的其他功能，並將其整合到更大的專案中。

## 常見問題部分

**問題 1：GroupDocs.Viewer 支援哪些版本的 .NET？**
A1：GroupDocs.Viewer 支援各種 .NET 框架，包括 .NET Framework 4.6.1 及更高版本以及 .NET Core 2.0+。

**Q2：如何有效率地處理大型 CHM 檔案？**
A2：將轉換過程分解為較小的批次以有效管理記憶體使用。

**Q3：GroupDocs.Viewer 也可以轉換其他文件格式嗎？**
A3：是的，它支援多種格式，包括 PDF、Word、Excel 等。

**Q4：使用 GroupDocs.Viewer 的系統需求為何？**
A4：需要基於 Windows 且支援 .NET 的環境。請確保您的開發設定符合以下條件。

**Q5：如何解決轉換過程中的錯誤？**
A5：檢查檔案權限，確保路徑設定正確，如果問題仍然存在，請查閱文件或支援論壇。

## 資源
- [文件](https://docs.groupdocs.com/viewer/net/)
- [API 參考](https://reference.groupdocs.com/viewer/net/)
- [下載 GroupDocs.Viewer for .NET](https://releases.groupdocs.com/viewer/net/)
- [購買 GroupDocs.Viewer](https://purchase.groupdocs.com/buy)
- [GroupDocs 支援論壇](https://forum.groupdocs.com/c/viewer)