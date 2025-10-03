---
"description": "了解如何使用 GroupDocs.Viewer for .NET 呈現 Visio 圖形，並增強 .NET 應用程式中的文件檢視功能。"
"linktitle": "渲染 Visio 圖形"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 Visio 圖形"
"url": "/zh-hant/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
type: docs
---
# 渲染 Visio 圖形

## 介紹
在當今的數位時代，文件渲染在各種應用程式中都扮演著至關重要的角色。無論是在網站上顯示文檔，還是將其轉換為不同的格式，高效的渲染都至關重要。 GroupDocs.Viewer for .NET 為在 .NET 應用程式中檢視和操作文件提供了一個強大的解決方案。在本教程中，我們將深入研究如何使用 GroupDocs.Viewer for .NET 渲染 Visio 圖形，並將流程分解為幾個簡單的步驟。
## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
1. 環境設定：確保您有一個用於 .NET 開發的工作環境。
2. GroupDocs.Viewer for .NET：從 [下載連結](https://releases。groupdocs.com/viewer/net/).
3. C# 基本了解：熟悉 C# 程式語言基礎。
4. 範例 Visio 文件：準備好要呈現的範例 Visio 文件。

## 導入命名空間
在您的 C# 專案中，首先匯入必要的命名空間：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1.渲染為HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 輸出目錄：定義保存渲染的 HTML 的目錄。
- 頁面檔案路徑格式：指定 HTML 頁面的路徑格式。
- 檢視器初始化：使用 Visio 文件的路徑初始化檢視器物件。
- HTML 視圖選項：配置呈現 HTML 的選項。
- Visio 渲染選項：設定特定於 Visio 渲染的選項，例如僅渲染圖形和圖形寬度。
## 2.渲染為JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 與渲染為 HTML 類似，配置渲染為 JPG 格式的選項。
## 3.渲染為PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 渲染為 PNG 格式的配置遵循與 JPG 渲染類似的模式。
## 4.渲染為PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 若要渲染為 PDF，請配置特定於 PDF 格式的選項。

## 結論
在本教學中，我們探討如何使用 GroupDocs.Viewer for .NET 渲染 Visio 圖形。按照逐步指南操作，您可以將文件渲染功能無縫整合到 .NET 應用程式中，從而增強使用者體驗和工作效率。
## 常見問題解答
### 我可以自訂 Visio 圖形的渲染選項嗎？
是的，GroupDocs.Viewer for .NET 提供了大量自訂渲染選項，包括圖形寬度、僅渲染圖形等。
### GroupDocs.Viewer for .NET 是否適合大規模文件渲染？
當然，GroupDocs.Viewer for .NET 針對高效處理大規模文件渲染進行了最佳化。
### GroupDocs.Viewer 除了支援 Visio 之外還支援其他文件格式嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、Microsoft Office、AutoCAD 等。
### 我可以將 GroupDocs.Viewer 整合到 Web 應用程式中嗎？
是的，GroupDocs.Viewer 可以無縫整合到 Web 應用程式中以檢視和操作文件。
### 購買前是否有可供測試的試用版？
是的，你可以從 [網站](https://releases.groupdocs.com/) 測試 GroupDocs.Viewer for .NET 的功能。