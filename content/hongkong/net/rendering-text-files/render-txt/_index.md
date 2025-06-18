---
"description": "探索使用 GroupDocs.Viewer for .NET 將文字檔案無縫轉換為多種格式。輕鬆增強您的文件管理能力。"
"linktitle": "渲染文字檔（.txt）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染文字檔（.txt）"
"url": "/zh-hant/net/rendering-text-files/render-txt/"
"weight": 10
---

# 渲染文字檔（.txt）

## 介紹
在文件管理和操作領域，GroupDocs.Viewer for .NET 是一款功能強大的工具，它提供了豐富的功能，可以有效地渲染各種文件格式。本文深入探討如何使用 GroupDocs.Viewer for .NET 將文字檔案 (.txt) 渲染為多種格式。無論您是想將文字檔案轉換為 HTML、JPG、PNG 或 PDF，GroupDocs.Viewer 都能為您提供必要的工具，讓您無縫地完成這些任務。
## 先決條件
在深入研究轉換過程之前，請確保您已滿足以下先決條件：
### 1. 安裝 GroupDocs.Viewer for .NET
確保您的開發環境中已安裝 GroupDocs.Viewer for .NET。您可以從 [網站](https://releases。groupdocs.com/viewer/net/).
### 2. 熟悉.NET Framework
熟悉 .NET 框架的基礎知識，包括如何設定專案以及如何利用程式碼庫中的程式庫。
### 3. 範例文字文件
準備要轉換的範例文字檔 (.txt)。這些文件將作為轉換過程的輸入。

## 導入命名空間
在深入轉換過程之前，請確保將必要的命名空間匯入到您的專案中。這樣您就可以無縫存取 GroupDocs.Viewer for .NET 提供的功能。
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
我們將每個範例分解為多個步驟，以有效地引導您完成轉換過程：

## 步驟 1：定義 HTML 輸出路徑
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
指定 HTML 輸出檔案的完整路徑。
## 步驟 2：將文字檔案渲染為多頁 HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
實例化 `Viewer` 帶有文字檔案路徑的物件。配置 `HtmlViewOptions` 用於嵌入資源並將文字檔案呈現為多頁 HTML。
## 步驟3：定義單頁HTML輸出路徑
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
指定單頁 HTML 輸出檔案的完整路徑。
## 步驟 4：將文字檔案渲染為單頁 HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
實例化 `Viewer` 帶有文字檔案路徑的物件。配置 `HtmlViewOptions` 用於嵌入資源並設置 `RenderToSinglePage` 為 true。將文字檔案渲染為單頁 HTML。
## 步驟5：定義JPG輸出路徑
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
指定 JPG 輸出檔的完整路徑。
## 步驟6：將文字檔渲染為JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
實例化 `Viewer` 帶有文字檔案路徑的物件。配置 `JpgViewOptions` 作為輸出路徑並將文字檔案渲染為 JPG 格式。
## 步驟 7：定義 PNG 輸出路徑
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
指定 PNG 輸出檔的完整路徑。
## 步驟 8：將文字檔案渲染為 PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
實例化 `Viewer` 帶有文字檔案路徑的物件。配置 `PngViewOptions` 作為輸出路徑並將文字檔案渲染為 PNG 格式。
## 步驟9：定義PDF輸出路徑
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
指定 PDF 輸出檔案的完整路徑。
## 步驟 10：將文字檔渲染為 PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
實例化 `Viewer` 帶有文字檔案路徑的物件。配置 `PdfViewOptions` 作為輸出路徑並將文字檔案呈現為 PDF 格式。

## 結論
總而言之，GroupDocs.Viewer for .NET 使開發人員能夠輕鬆地將文字檔案渲染為各種格式，包括 HTML、JPG、PNG 和 PDF。按照本文概述的逐步指南，您可以將 GroupDocs.Viewer 無縫整合到您的 .NET 應用程式中，從而增強文件管理功能。
## 常見問題解答
### Q：GroupDocs.Viewer for .NET 是否與所有版本的 .NET 框架相容？
是的，GroupDocs.Viewer for .NET 設計為與各種 .NET 框架版本相容，確保開發的多功能性和靈活性。
### Q：我可以自訂渲染文件的輸出外觀嗎？
當然！ GroupDocs.Viewer 提供了豐富的自訂選項，可讓開發人員根據自己的教學和需求自訂渲染文件的外觀。
### Q：GroupDocs.Viewer for .NET 有試用版嗎？
是的，您可以透過造訪以下網站提供的免費試用版來探索 GroupDocs.Viewer for .NET 的功能 [網站]( https://releases。groupdocs.com/).
### Q：如何獲得 GroupDocs.Viewer for .NET 的支援或尋求協助？
對於有關 GroupDocs.Viewer for .NET 的任何問題、支援或協助，您可以存取專門的支援論壇 [這裡](https://forum。groupdocs.com/c/viewer/9).
### Q：我可以購買 GroupDocs.Viewer for .NET 的臨時授權嗎？
是的，可以購買臨時許可證，為使用者在特定期限內使用 GroupDocs.Viewer for .NET 提供彈性和便利性。