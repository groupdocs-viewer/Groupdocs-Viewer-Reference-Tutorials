---
"description": "了解如何使用 GroupDocs.Viewer for .NET 渲染具有原始頁面大小的 PDF。按照我們的逐步指南操作，即可無縫整合此功能。"
"linktitle": "使用原始頁面大小渲染 PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "使用原始頁面大小渲染 PDF"
"url": "/zh-hant/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# 使用原始頁面大小渲染 PDF

## 介紹
在 .NET 開發領域，GroupDocs.Viewer 是一款功能強大的工具，可用於渲染各種文件格式，包括 PDF。文件處理中的一個常見需求是在渲染 PDF 的同時保留其原始頁面大小。要無縫地完成此任務，需要全面了解 GroupDocs.Viewer for .NET 及其功能。

![使用 GroupDocs.Viewer .NET 渲染具有原始頁面大小的 PDF](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## 先決條件
在使用 GroupDocs.Viewer for .NET 渲染具有原始頁面大小的 PDF 之前，請確保您已滿足以下先決條件：
### 1. 安裝 GroupDocs.Viewer for .NET
首先從網站下載 GroupDocs.Viewer 庫。您可以從提供的 [下載連結](https://releases.groupdocs.com/viewer/net/)依照文件中提供的安裝說明，將其有效地整合到您的.NET專案中。
### 2. 設定開發環境
確保已設定好 .NET 開發的開發環境。這包括安裝相容的 IDE（例如 Visual Studio），以及對 C# 程式設計有基本的了解。
### 3. 取得 PDF 文檔
您需要一個範例 PDF 文件來使用 GroupDocs.Viewer 進行渲染。您可以使用任何 PDF 文件進行測試。如果您沒有，可以從各種線上資源下載範例 PDF。

## 導入命名空間
在繼續渲染 PDF 之前，必須將必要的命名空間匯入到您的 C# 專案中。此步驟可讓您從 GroupDocs.Viewer 庫存取所需的類別和方法。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在您已經滿足了先決條件並導入了必要的命名空間，讓我們將使用 GroupDocs.Viewer for .NET 呈現具有原始頁面大小的 PDF 的過程分解為簡單的步驟：
## 步驟 1：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
確保指定要儲存渲染頁面的目錄。替換 `"Your Document Directory"` 使用您所需目錄的路徑。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
設定渲染頁面檔案的命名格式。在本例中，頁面將儲存為 PNG 圖像，檔案名稱格式如下： `"page_1.png"`， `"page_2.png"`， 等等。
## 步驟 3：使用原始頁面大小渲染 PDF
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
實例化 `Viewer` 對象，其中包含 PDF 文件的路徑。然後，創建 `PngViewOptions` 使用指定的頁面檔案路徑格式。設定 `RenderOriginalPageSize` 財產 `true` 在渲染時保留原始頁面大小。
## 步驟 4：顯示渲染文件位置
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
列印一條指示渲染成功的訊息並提供渲染頁面的儲存目錄。

## 結論
按照本教學中概述的步驟操作，使用 GroupDocs.Viewer for .NET 渲染具有原始頁面大小的 PDF 非常簡單。透過匯入必要的命名空間並遵循逐步指南，您可以將此功能無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### GroupDocs.Viewer 除了 PDF 之外還能呈現其他文件格式嗎？
是的，GroupDocs.Viewer 支援呈現各種文件格式，包括 Word、Excel、PowerPoint 等。
### GroupDocs.Viewer 是否與 .NET Core 相容？
是的，GroupDocs.Viewer 與 .NET Framework 和 .NET Core 環境相容。
### 我可以自訂渲染頁面的輸出格式嗎？
是的，您可以透過調整 GroupDocs.Viewer 提供的選項來自訂輸出格式，例如設定不同的影像格式或指定自訂渲染選項。
### GroupDocs.Viewer 是否支援基於雲端的文檔渲染？
是的，GroupDocs.Viewer 提供基於雲端的文檔渲染 API，可讓您直接從雲端儲存提供者渲染文件。
### GroupDocs.Viewer 有免費試用版嗎？
是的，您可以訪問提供的 [關聯](https://releases。groupdocs.com/).