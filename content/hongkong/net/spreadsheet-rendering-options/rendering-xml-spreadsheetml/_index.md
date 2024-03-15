---
title: 呈現 XML SpreadSheetML
linktitle: 呈現 XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 探索各種格式的 XML SpreadSheetML 檔案的無縫呈現。輕鬆整合到您的應用程式中。
type: docs
weight: 16
url: /zh-hant/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## 介紹
歡迎來到 GroupDocs.Viewer for .NET 的世界！在本教學中，我們將引導您使用強大的 .NET 函式庫 GroupDocs.Viewer 輕鬆渲染 XML SpreadSheetML 檔案。無論您是經驗豐富的開發人員還是新手，本逐步指南都將幫助您輕鬆地將 XML SpreadSheetML 渲染整合到您的應用程式中。
## 先決條件
在深入學習本教學之前，請確保您已設定以下先決條件：
- 具有 .NET 支援的開發環境。
- 安裝了 .NET 函式庫的 GroupDocs.Viewer。你可以下載它[這裡](https://releases.groupdocs.com/viewer/net/).
- 對 C# 程式設計有基本了解。
## 導入命名空間
首先將必要的命名空間匯入到您的 C# 專案中。這可確保您能夠存取 GroupDocs.Viewer 提供的功能。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 第 1 步：設定您的文件目錄
定義儲存輸出的文檔目錄的路徑。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟 2：指定輸出檔案路徑
設定 HTML、JPG、PNG 和 PDF 輸出檔的完整路徑。
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## 步驟 3：指定載入選項
將文件類型明確指定為 Excel 2003 XML SpreadSheetML 以準確呈現它。
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 第 4 步：渲染為多頁 HTML
利用 HTML 視圖選項將 XML SpreadSheetML 檔案呈現為多頁 HTML 文件。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 步驟5：渲染為JPG
使用指定的選項將 XML SpreadSheetML 檔案渲染為 JPG 映像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 第 6 步：渲染為 PNG
同樣，使用指定的選項將檔案渲染為 PNG 影像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 第 7 步：渲染為 PDF
最後，使用指定的選項將 XML SpreadSheetML 檔案呈現為 PDF 文件。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 結論
恭喜！您已成功學習如何使用 GroupDocs.Viewer for .NET 呈現 XML SpreadSheetML 檔案。透過探索這個多功能庫提供的更多功能和選項來增強您的文件檢視能力。
## 常見問題解答
### GroupDocs.Viewer 是否與其他檔案格式相容？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、Word、Excel 等。
### 我可以自訂渲染文件的外觀嗎？
絕對地！ GroupDocs.Viewer 提供各種自訂選項，可讓您根據您的特定需求自訂輸出。
### 我可以在哪裡找到額外的支援和資源？
參觀[GroupDocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9)尋求社區支持並探索[文件](https://reference.groupdocs.com/viewer/net/)獲取詳細資訊。
### 有免費試用嗎？
是的，您可以免費試用[這裡](https://releases.groupdocs.com/).
### 如何獲得臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.groupdocs.com/temporary-license/).