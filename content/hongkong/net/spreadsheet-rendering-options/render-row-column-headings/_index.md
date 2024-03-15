---
title: 渲染行和列標題
linktitle: 渲染行和列標題
second_title: GroupDocs.Viewer .NET API
description: 增強 .NET 中的文件檢視功能！了解使用 GroupDocs.Viewer for .NET 呈現行標題和列標題。探索 HTML、JPG、PNG 和 PDF 輸出。
type: docs
weight: 18
url: /zh-hant/net/spreadsheet-rendering-options/render-row-column-headings/
---
## 介紹
您是否希望增強 .NET 應用程式中的文件檢視體驗？透過 GroupDocs.Viewer for .NET，您可以無縫地呈現電子表格檔案中的行標題和列標題。在本教學中，我們將引導您完成使用不同輸出格式（例如 HTML、JPG、PNG 和 PDF）呈現行標題和列標題的過程。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 為 .NET 程式庫安裝了 GroupDocs.Viewer。
- 用於測試目的的範例 XLSX 檔案。
- 具備 C# 和 .NET 開發的實用知識。
## 導入命名空間
在 C# 程式碼中，請確保匯入必要的命名空間以使用 GroupDocs.Viewer：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. 設定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. 渲染為 HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3.渲染為JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4.渲染為PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. 渲染為PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 結論
恭喜！您已使用 GroupDocs.Viewer for .NET 成功呈現電子表格中的行標題和列標題。嘗試不同的輸出格式以滿足您的應用程式的需求。
## 經常問的問題
### Q：我可以自訂渲染文檔的輸出目錄嗎？
 A：是的，您可以在程式碼中設定您想要的輸出目錄`outputDirectory`變數被定義。
### Q：GroupDocs.Viewer 是否與其他電子表格格式相容？
答：是的，GroupDocs.Viewer 支援各種電子表格格式，包括 XLS、XLSX、CSV 等。
### Q：渲染過程中出現異常如何處理？
答：您可以實作 try-catch 區塊來處理異常並記錄或向使用者顯示適當的訊息。
### Q：在我的應用程式中使用 GroupDocs.Viewer 是否有任何授權要求？
答：是的，您需要有效的許可證。您可以獲得用於測試目的的臨時許可證或購買用於生產的完整許可證。
### Q：我可以在哪裡找到其他支持或社區討論？
答：訪問[GroupDocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9)以尋求支持和討論。