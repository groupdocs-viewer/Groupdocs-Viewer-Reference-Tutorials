---
title: 調整 PDF 中的影像質量
linktitle: 調整 PDF 中的影像質量
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 調整 PDF 文件中的影像品質。請按照我們的逐步教學進行無縫整合。
weight: 10
url: /zh-hant/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的程式庫，可讓開發人員輕鬆地將文件呈現功能整合到他們的 .NET 應用程式中。該庫的主要功能之一是能夠在渲染 PDF 文件時調整影像品質。在本教學中，我們將引導您使用 GroupDocs.Viewer for .NET 逐步完成調整影像品質的過程。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. C# 程式設計基礎知識。
2. Visual Studio 安裝在您的系統上。
3. 下載並安裝了 .NET 函式庫的 GroupDocs.Viewer。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).

## 導入命名空間
首先，您需要匯入必要的命名空間以使用 GroupDocs.Viewer for .NET：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`以及要儲存渲染的 HTML 頁面的路徑。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
此行定義每個呈現的 HTML 頁面的文件路徑的格式。`{0}`是頁碼的佔位符。
## 步驟 3：調整影像質量
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
代替`"Your PDF File Path"`以及 PDF 文件的路徑。
## 第四步：顯示輸出路徑
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
該行顯示已儲存渲染的 HTML 頁面的路徑。

## 結論
在本教學中，我們學習如何在使用 GroupDocs.Viewer for .NET 渲染 PDF 文件時調整影像品質。透過執行上述簡單步驟，您可以根據您的要求輕鬆自訂影像品質。
## 常見問題解答
### 我可以調整 PDF 以外的其他文件格式的影像品質嗎？
是的，GroupDocs.Viewer for .NET 支援各種文件格式，您可以調整大多數文件格式的影像品質。
### 有哪些可用的影像品質選項？
GroupDocs.Viewer for .NET 提供低、中、高影像品質選項。
### 有沒有辦法在使用調整後的影像品質渲染文件之前預覽文件？
是的，您可以使用 GroupDocs.Viewer for .NET 產生具有不同影像品質設定的文件預覽。
### GroupDocs.Viewer for .NET 是否需要商業用途授權？
是的，您需要獲得商業使用許可。您可以從以下位置購買許可證[這裡](https://purchase.groupdocs.com/buy).
### 在哪裡可以獲得 GroupDocs.Viewer for .NET 的支援？
您可以從 GroupDocs.Viewer 論壇獲得支持[這裡](https://forum.groupdocs.com/c/viewer/9).