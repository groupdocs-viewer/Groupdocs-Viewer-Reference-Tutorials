---
"description": "探索 Groupdocs.Viewer for .NET 的強大功能，無縫渲染 Numbers 檔案。輕鬆轉換為 HTML、JPG、PNG 和 PDF。"
"linktitle": "渲染數位"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染數位"
"url": "/zh-hant/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# 渲染數位

## 介紹
歡迎學習本教學課程，了解如何使用 Groupdocs.Viewer for .NET 渲染 Numbers 檔案。無論您是經驗豐富的開發人員還是初學者，本指南都將引導您完成將 Numbers 文件轉換為各種格式的過程。 Groupdocs.Viewer for .NET 是一款功能強大的工具，可讓您將文件檢視功能無縫整合到您的 .NET 應用程式中。
## 先決條件
在深入學習本教程之前，請確保您已滿足以下先決條件：
- 具備 C# 和 .NET 開發的工作知識。
- Groupdocs.Viewer for .NET 程式庫已安裝。您可以下載 [這裡](https://releases。groupdocs.com/viewer/net/).
- 儲存輸出檔案的文檔目錄路徑。
## 導入命名空間
在您的 C# 專案中，請確保匯入必要的命名空間以使用 Groupdocs.Viewer 庫：
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟 1：設定輸出目錄
在開始渲染之前，請定義轉換後檔案儲存的輸出目錄。將“您的文件目錄”替換為實際路徑：
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟 2：渲染為多頁 HTML
使用以下程式碼將 Numbers 檔案轉換為多頁 HTML：
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 步驟3：渲染為JPG
使用以下程式碼將 Numbers 檔案轉換為 JPG 格式：
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步驟 4：渲染為 PNG
使用以下程式碼將 Numbers 檔案轉換為 PNG 格式：
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步驟 5：渲染為 PDF
最後，使用以下程式碼將 Numbers 檔案轉換為 PDF 格式：
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
恭喜！您已成功使用 Groupdocs.Viewer for .NET 將 Numbers 檔案渲染為各種格式。
## 結論
在本教程中，我們介紹了使用 Groupdocs.Viewer for .NET 渲染 Numbers 檔案的基礎知識。這個強大的程式庫提供了無縫集成，可在 .NET 應用程式中檢視和轉換文件。
## 常見問題解答
### 我可以將 Groupdocs.Viewer for .NET 與其他文件類型一起使用嗎？
是的，Groupdocs.Viewer 支援多種文件格式，包括 Word、Excel、PDF 等。
### 是否有可用於測試目的的臨時許可證？
是的，您可以獲得臨時駕照 [這裡](https://purchase.groupdocs.com/temporary-license/) 用於測試。
### 在哪裡可以找到對 Groupdocs.Viewer for .NET 的支援？
訪問 [Groupdocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9) 尋求幫助和討論。
### 如何購買 Groupdocs.Viewer for .NET 的完整版本？
您可以購買完整版 [這裡](https://purchase。groupdocs.com/buy).
### 有免費試用版嗎？
是的，您可以探索免費試用版 [這裡](https://releases。groupdocs.com/).