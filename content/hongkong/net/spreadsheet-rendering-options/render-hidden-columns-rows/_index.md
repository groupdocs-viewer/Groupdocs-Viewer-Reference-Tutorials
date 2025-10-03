---
"description": "使用 GroupDocs.Viewer for .NET 輕鬆解鎖電子表格中的隱藏資料。按照我們的逐步指南，顯示隱藏的列和行。"
"linktitle": "渲染隱藏的列和列"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染隱藏的列和列"
"url": "/zh-hant/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
type: docs
---
# 渲染隱藏的列和列

## 介紹
在文件視覺化領域，GroupDocs.Viewer for .NET 是一款功能強大的工具，能夠無縫呈現各種文件格式。其中一個引人入勝的功能是能夠顯示電子表格中隱藏的列和行。在本教程中，我們將深入探討解鎖此功能的步驟，並釋放資料的潛力。
## 先決條件
在踏上這趟旅程之前，請確保您已滿足以下先決條件：
- GroupDocs.Viewer for .NET：請確保您已安裝最新版本。如果沒有，您可以從 [官方網站](https://releases。groupdocs.com/viewer/net/).
- 文件檔案：準備電子表格格式的範例文件（例如，SAMPLE.XLSX）來試驗隱藏的列和行。
- 開發環境：設定工作環境，最好使用 Visual Studio 或任何其他適合 .NET 開發的 IDE。
## 導入命名空間
在您的 .NET 專案中，匯入必要的命名空間以有效利用 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟 1：設定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
定義渲染後的 HTML 頁面的輸出目錄。請相應地調整文件路徑格式。
## 步驟 2：初始化檢視器並配置選項
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
透過提供電子表格文件的路徑來建立檢視器實例。配置 HTML 視圖選項以嵌入資源並啟用隱藏列和行的渲染。
## 步驟3：執行渲染流程
```csharp
    viewer.View(options);
}
```
呼叫檢視器物件上的 View 方法，並傳遞已配置的選項。這將啟動渲染過程。
## 步驟 4：檢查輸出
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
驗證來源文件是否成功呈現並將輸出定位在指定的目錄中。
## 結論
使用 GroupDocs.Viewer for .NET，輕鬆解鎖電子表格中隱藏的列和行。本教學將指導您如何揭示隱藏數據，從而更全面地查看文件。
## 常見問題
### 除了電子表格之外，我可以在其它文件格式中呈現隱藏的列和行嗎？
是的，除了電子表格之外，GroupDocs.Viewer 還支援各種文件格式，包括 Word、PDF 和 PowerPoint。
### 可渲染的隱藏列和隱藏行的數量是否有限制？
GroupDocs.Viewer 可以有效率地處理各種隱藏列和行的渲染。然而，在極端情況下，如果隱藏資料量過大，可能會影響效能。
### 我可以自訂渲染資料的輸出格式嗎？
當然！ GroupDocs.Viewer 提供了靈活的選項來自訂輸出，讓您可以根據特定需求自訂渲染的資料。
### 使用 GroupDocs.Viewer 是否有任何授權注意事項？
是的，請確保您擁有適合您用途的許可證。探索許可選項，請訪問 [GroupDocs 購買](https://purchase.groupdocs.com/buy) 或獲得 [臨時執照](https://purchase.groupdocs.com/temporary-license/) 用於測試。
### 我可以在哪裡尋求協助或聯繫 GroupDocs 社群以獲得支援？
訪問 [GroupDocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9) 以獲得支持、討論和社區互動。