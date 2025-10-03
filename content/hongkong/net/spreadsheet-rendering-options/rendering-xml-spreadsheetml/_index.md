---
"description": "探索使用 GroupDocs.Viewer for .NET 無縫渲染各種格式的 XML SpreadSheetML 檔案。輕鬆整合到您的應用程式中。"
"linktitle": "渲染 XML SpreadSheetML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 XML SpreadSheetML"
"url": "/zh-hant/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# 渲染 XML SpreadSheetML

## 介紹
歡迎來到 GroupDocs.Viewer for .NET 的世界！在本教學中，我們將指導您使用功能強大的 .NET 函式庫 GroupDocs.Viewer 輕鬆渲染 XML SpreadSheetML 檔案。無論您是經驗豐富的開發人員還是剛入門，本逐步指南都能幫助您輕鬆地將 XML SpreadSheetML 渲染功能整合到您的應用程式中。
## 先決條件
在深入學習本教程之前，請確保您已滿足以下先決條件：
- 支援.NET 的開發環境。
- 已安裝 GroupDocs.Viewer for .NET 程式庫。您可以下載 [這裡](https://releases。groupdocs.com/viewer/net/).
- 對 C# 程式設計有基本的了解。
## 導入命名空間
首先將必要的命名空間匯入到您的 C# 專案中。這可確保您能夠存取 GroupDocs.Viewer 提供的功能。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 步驟 1：設定文檔目錄
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
明確指定文件類型為 Excel 2003 XML SpreadSheetML 以便準確呈現它。
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 步驟 4：渲染為多頁 HTML
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
## 步驟6：渲染為PNG
類似地，使用指定的選項將檔案渲染為 PNG 映像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步驟 7：渲染為 PDF
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
恭喜！您已成功學習如何使用 GroupDocs.Viewer for .NET 渲染 XML SpreadSheetML 檔案。探索這個多功能庫提供的更多功能和選項，提升您的文件檢視能力。
## 常見問題解答
### GroupDocs.Viewer 是否與其他檔案格式相容？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、Word、Excel 等。
### 我可以自訂渲染文件的外觀嗎？
當然！ GroupDocs.Viewer 提供各種自訂選項，讓您可以根據特定需求自訂輸出。
### 我可以在哪裡找到額外的支援和資源？
訪問 [GroupDocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9) 尋求社區支持並探索 [文件](https://tutorials.groupdocs.com/viewer/net/) 了解詳細資訊。
### 有免費試用嗎？
是的，您可以免費試用 [這裡](https://releases。groupdocs.com/).
### 如何取得臨時執照？
您可以獲得臨時駕照 [這裡](https://purchase。groupdocs.com/temporary-license/).