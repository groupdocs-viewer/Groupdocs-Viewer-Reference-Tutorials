---
title: 在 PDF 中啟用分層渲染
linktitle: 在 PDF 中啟用分層渲染
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 在 PDF 文件中啟用分層渲染。輕鬆增強文件檢視體驗。
weight: 15
url: /zh-hant/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## 介紹
在本教學中，我們將深入研究使用 GroupDocs.Viewer for .NET 在 PDF 文件中啟用分層渲染的過程。分層渲染可以增強文件顯示和操作，為使用者提供更具互動性的檢視體驗。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. GroupDocs.Viewer for .NET：確保您已安裝在專案中使用 GroupDocs.Viewer for .NET 所需的套件或程式庫。
2. Visual Studio：您應該在系統上安裝 Visual Studio 來編碼和執行提供的範例。
3. C# 的基本了解：本教學假設您熟悉 C# 程式語言語法和概念。

## 導入命名空間
首先將所需的命名空間匯入到您的專案中：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
確保指定要儲存渲染輸出的目錄路徑。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
此步驟設定渲染輸出中各頁面的檔案路徑的格式。`{0}`是頁碼的佔位符。
## 第 3 步：啟用分層渲染
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
在這裡，我們創建一個`Viewer`對象並指定要處理的 PDF 文件。然後我們配置`HtmlViewOptions`具有定義的頁面文件路徑格式。透過設定`EnableLayeredRendering`財產給`true`在`PdfOptions`，我們為 PDF 文件啟用分層渲染。
## 步驟4：顯示輸出目錄
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後，我們列印一則訊息，指示來源文件渲染成功，並提示使用者檢查指定目錄中的輸出。

## 結論
使用 GroupDocs.Viewer for .NET 在 PDF 文件中啟用分層渲染可增強文件檢視功能，為使用者提供更豐富、更具互動性的體驗。透過遵循本教學中概述的步驟，您可以將此功能無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### 什麼是PDF文件中的分層渲染？
分層渲染允許分離和操作 PDF 文件中的不同元件，從而實現互動式檢視並增強使用者體驗。
### 我可以自訂渲染文檔的輸出目錄嗎？
是的，您可以根據您的要求指定輸出的任何目錄路徑。
### GroupDocs.Viewer 是否支援 PDF 以外的其他文件格式？
是的，GroupDocs.Viewer 支援多種文件格式，包括 Word、Excel、PowerPoint 等。
### GroupDocs.Viewer 與 .NET Core 相容嗎？
是的，GroupDocs.Viewer 與 .NET Framework 和 .NET Core 環境相容。
### 我可以在哪裡找到額外的支援或協助？
您可以造訪 GroupDocs.Viewer 論壇，以獲取有關檢視器庫的任何問題或協助。