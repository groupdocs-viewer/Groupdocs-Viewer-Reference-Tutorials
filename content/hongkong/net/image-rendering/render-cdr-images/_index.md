---
"description": "學習如何使用 GroupDocs.Viewer for .NET 將 CDR 影像渲染為 HTML、JPG、PNG 和 PDF。本教學將幫助您輕鬆轉換 CorelDRAW 檔案。"
"linktitle": "渲染 CDR 影像"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 CDR 影像"
"url": "/zh-hant/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# 渲染 CDR 影像

## 介紹
在本教學中，我們將指導您使用 GroupDocs.Viewer for .NET 渲染 CDR（CorelDRAW）影像。 CDR 是一種主要與向量圖形編輯器 CorelDRAW 相關的檔案格式。使用 GroupDocs.Viewer，您可以輕鬆地將 CDR 檔案轉換為各種格式，例如 HTML、JPG、PNG 和 PDF。

![使用 GroupDocs.Viewer for .NET 渲染 CDR 影像](/viewer/image-rendering/render-cdr-images.png)

## 先決條件
在開始之前，請確保您符合以下先決條件：
1. GroupDocs.Viewer for .NET：請確保您已安裝 GroupDocs.Viewer for .NET。您可以從以下網址下載： [這裡](https://releases。groupdocs.com/viewer/net/).
2. 文件目錄：準備一個要儲存渲染影像的目錄。
3. C# 基礎知識：熟悉 C# 程式語言對於理解程式碼範例是必要的。
## 導入命名空間
在深入研究程式碼範例之前，請在 C# 檔案中匯入必要的命名空間：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
現在，讓我們將每個範例分解為多個步驟：
## 渲染為 HTML
1. 定義要儲存渲染的 HTML 檔案的輸出目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
2. 指定 HTML 文件的文件路徑格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. 使用 Viewer 類別將 CDR 檔案呈現為 HTML：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## 渲染為 JPG
1. 定義JPG檔案的檔案路徑格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. 使用Viewer類別將CDR檔案渲染為JPG：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## 渲染為 PNG
1. 定義 PNG 檔案的檔案路徑格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. 使用 Viewer 類別將 CDR 檔案渲染為 PNG：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## 渲染為 PDF
1. 定義PDF的檔案路徑格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. 使用 Viewer 類別將 CDR 檔案渲染為 PDF：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. （可選）您可以透過向 `viewer.View()` 方法。
## 結論
使用 GroupDocs.Viewer for .NET 將 CDR 圖像渲染為 HTML、JPG、PNG 和 PDF 等各種格式非常簡單。按照本教學中概述的步驟，您可以根據需求有效地將 CDR 檔案轉換為不同的格式。
## 常見問題解答
### GroupDocs.Viewer for .NET 是否與所有版本的 CDR 檔案相容？
GroupDocs.Viewer for .NET 支援渲染不同版本的 CorelDRAW 所建立的 CDR 檔案。
### 我可以自訂渲染檔案的輸出嗎？
是的，GroupDocs.Viewer for .NET 提供了各種選項來自訂輸出，例如調整影像品質、設定浮水印等。
### GroupDocs.Viewer for .NET 是否需要任何外部依賴？
不，GroupDocs.Viewer for .NET 是一個獨立函式庫，不需要任何外部依賴來呈現文件。
### GroupDocs.Viewer for .NET 有試用版嗎？
是的，您可以從以下網址下載 GroupDocs.Viewer for .NET 的免費試用版 [這裡](https://releases。groupdocs.com/).
### 在哪裡可以獲得 GroupDocs.Viewer for .NET 的支援？
您可以從 GroupDocs.Viewer 社群論壇獲得支持 [這裡](https://forum。groupdocs.com/c/viewer/9).