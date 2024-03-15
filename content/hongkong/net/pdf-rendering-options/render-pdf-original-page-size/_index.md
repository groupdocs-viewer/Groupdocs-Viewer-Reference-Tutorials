---
title: 使用原始頁面大小渲染 PDF
linktitle: 使用原始頁面大小渲染 PDF
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 以原始頁面大小呈現 PDF。按照我們的逐步指南無縫整合此功能。
type: docs
weight: 17
url: /zh-hant/net/pdf-rendering-options/render-pdf-original-page-size/
---
## 介紹
在 .NET 開發領域，GroupDocs.Viewer 作為渲染各種文件格式（包括 PDF）的強大工具而脫穎而出。文件處理中的一個常見要求是渲染 PDF，同時保留其原始頁面大小。要無縫地完成此任務，需要全面了解 GroupDocs.Viewer for .NET 及其功能。
## 先決條件
在深入使用 GroupDocs.Viewer for .NET 以原始頁面大小渲染 PDF 之前，請確保符合以下先決條件：
### 1. 安裝適用於.NET的GroupDocs.Viewer
首先從網站下載 GroupDocs.Viewer 庫。您可以從提供的庫中取得該庫[下載連結](https://releases.groupdocs.com/viewer/net/)。請依照文件中提供的安裝說明將其有效地整合到您的 .NET 專案中。
### 2. 建構開發環境
確保您已設定用於 .NET 開發的開發環境。這包括安裝相容的 IDE（例如 Visual Studio）以及對 C# 程式設計的基本了解。
### 3. 取得PDF文檔
您需要一個範例 PDF 文件才能使用 GroupDocs.Viewer 進行呈現。您可以使用任何 PDF 文件進行測試。如果您沒有，可以從各種線上資源下載 PDF 範例。

## 導入命名空間
在繼續渲染 PDF 之前，必須將必要的命名空間匯入到您的 C# 專案中。此步驟可讓您從 GroupDocs.Viewer 庫存取所需的類別和方法。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在您已經具備了先決條件並導入了必要的命名空間，讓我們將使用 GroupDocs.Viewer for .NET 以原始頁面大小渲染 PDF 的過程分解為簡單的步驟：
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
確保指定要儲存渲染頁面的目錄。代替`"Your Document Directory"`與您所需目錄的路徑。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
設定渲染頁面檔案的命名格式。在此範例中，頁面將儲存為 PNG 圖像，檔案名稱格式為`"page_1.png"`, `"page_2.png"`， 等等。
## 第 3 步：使用原始頁面大小渲染 PDF
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
實例化一個`Viewer`包含 PDF 檔案路徑的物件。然後，創建`PngViewOptions`具有指定的頁面文件路徑格式。放`RenderOriginalPageSize`財產給`true`在渲染時保留原始頁面大小。
## 第 4 步：顯示渲染文檔位置
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
列印一條指示渲染成功的訊息，並提供儲存渲染頁面的目錄。

## 結論
當您按照本教學中概述的步驟操作時，使用 GroupDocs.Viewer for .NET 呈現原始頁面大小的 PDF 是一個簡單的過程。透過匯入必要的命名空間並遵循逐步指南，您可以將此功能無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### GroupDocs.Viewer 可以呈現 PDF 以外的其他文件格式嗎？
是的，GroupDocs.Viewer 支援渲染各種文件格式，包括 Word、Excel、PowerPoint 等。
### GroupDocs.Viewer 與 .NET Core 相容嗎？
是的，GroupDocs.Viewer 與 .NET Framework 和 .NET Core 環境相容。
### 我可以自訂渲染頁面的輸出格式嗎？
是的，您可以透過調整 GroupDocs.Viewer 提供的選項來自訂輸出格式，例如設定不同的影像格式或指定自訂渲染選項。
### GroupDocs.Viewer 是否提供對基於雲端的文檔呈現的支援？
是的，GroupDocs.Viewer 提供用於基於雲端的文檔渲染的 API，可讓您直接從雲端儲存提供者渲染文件。
### GroupDocs.Viewer 是否有免費試用版？
是的，您可以透過造訪提供的免費試用版來探索 GroupDocs.Viewer[關聯](https://releases.groupdocs.com/).