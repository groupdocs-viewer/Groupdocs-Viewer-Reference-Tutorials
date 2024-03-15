---
title: 渲染隱藏的列和列
linktitle: 渲染隱藏的列和列
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 輕鬆解鎖電子表格中的隱藏資料。按照我們的逐步指南來揭示隱藏的列和行。
type: docs
weight: 13
url: /zh-hant/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## 介紹
在文件視覺化領域，GroupDocs.Viewer for .NET 是一款強大的工具，可促進各種文件格式的無縫呈現。一個有趣的功能是能夠顯示電子表格中隱藏的列和行。在本教程中，我們將深入探討解鎖此功能並釋放資料潛力的步驟。
## 先決條件
在開始此旅程之前，請確保您具備以下先決條件：
- GroupDocs.Viewer for .NET：確保您安裝了最新版本。如果沒有，您可以從以下位置下載[官方網站](https://releases.groupdocs.com/viewer/net/).
- 文件檔案：準備電子表格格式的範例文件（例如，SAMPLE.XLSX）以試驗隱藏的列和行。
- 開發環境：設定工作環境，最好使用 Visual Studio 或任何其他適合 .NET 開發的 IDE。
## 導入命名空間
在您的 .NET 專案中，匯入必要的命名空間以有效利用 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：設定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
定義將儲存渲染的 HTML 頁面的輸出目錄。相應地調整文件路徑格式。
## 步驟 2：初始化檢視器並配置選項
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
透過提供電子表格文件的路徑來建立檢視器實例。配置 HTML 視圖選項以嵌入資源並啟用隱藏列和行的呈現。
## 第三步：執行渲染流程
```csharp
    viewer.View(options);
}
```
呼叫檢視器物件上的 View 方法，傳遞配置的選項。這將啟動渲染過程。
## 第 4 步：檢查輸出
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
驗證來源文件是否成功呈現並在指定目錄中找到輸出。
## 結論
使用 GroupDocs.Viewer for .NET 解鎖電子表格中的隱藏列和行變得輕而易舉。本教學為您提供了揭示隱藏資料的基本步驟，從而提供更全面的文件視圖。
## 經常問的問題
### 除了電子表格之外，我還可以以其他文件格式呈現隱藏的列和行嗎？
是的，GroupDocs.Viewer 除了電子表格之外還支援各種文件格式，包括 Word、PDF 和 PowerPoint。
### 可以呈現的隱藏列和行的數量是否有限制？
GroupDocs.Viewer 可以有效處理各種隱藏列和行的渲染。然而，具有大量隱藏資料的極端情況可能會影響效能。
### 我可以自訂渲染資料的輸出格式嗎？
絕對地！ GroupDocs.Viewer 提供了靈活的選項來自訂輸出，可讓您根據您的特定需求自訂呈現的資料。
### 使用 GroupDocs.Viewer 是否有任何授權注意事項？
是的，請確保您擁有適合您的使用的許可證。探索授權選項：[集團文件購買](https://purchase.groupdocs.com/buy)或獲得[臨時執照](https://purchase.groupdocs.com/temporary-license/)供測試用。
### 我可以在哪裡尋求協助或聯繫 GroupDocs 社群以獲得支援？
參觀[GroupDocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9)支持、討論和社區互動。