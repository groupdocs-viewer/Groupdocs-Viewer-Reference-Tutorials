---
"description": "了解如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 影像。輕鬆將向量圖形轉換為 HTML、JPG、PNG 和 PDF。"
"linktitle": "渲染 SVG 和 SVGZ 影像"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 SVG 和 SVGZ 影像"
"url": "/zh-hant/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# 渲染 SVG 和 SVGZ 影像

## 介紹
在本教學中，我們將指導您使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 圖像。 GroupDocs.Viewer for .NET 是一個強大的文件渲染 API，使開發人員能夠在其 .NET 應用程式中渲染各種文件格式。 SVG 和 SVGZ 是用於向量圖形的常用圖像格式，使用 GroupDocs.Viewer for .NET，您可以輕鬆地將它們渲染為不同的輸出格式，例如 HTML、JPG、PNG 和 PDF。

![使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 影像](/viewer/image-rendering/render-svg-and-svgz-images.png)

## 先決條件
在開始之前，請確保您已安裝並設定以下先決條件：
1. GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET [這裡](https://releases。groupdocs.com/viewer/net/).
2. 開發環境：確保您有一個適用於 .NET 開發的開發環境，例如 Visual Studio。
3. 範例 SVGZ 檔案：準備好範例 SVGZ 檔案以供測試。

## 導入命名空間
在深入研究程式碼之前，讓我們先導入必要的命名空間：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 步驟 1：將 SVGZ 渲染為 HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 步驟2：將SVGZ渲染為JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 步驟3：將SVGZ渲染為PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 步驟 4：將 SVGZ 渲染為 PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 影像。只需幾個簡單的步驟，您就可以將 SVGZ 映像轉換為各種輸出格式，例如 HTML、JPG、PNG 和 PDF，從而可以在不同的環境中存取和查看它們。
## 常見問題解答
### GroupDocs.Viewer 可以呈現其他影像格式嗎？
是的，GroupDocs.Viewer 支援渲染各種影像格式，包括 PNG、JPEG、BMP、TIFF、GIF 等。
### GroupDocs.Viewer 是否與 .NET Core 相容？
是的，GroupDocs.Viewer 與 .NET Framework 和 .NET Core 相容。
### 我可以自訂渲染選項嗎？
是的，GroupDocs.Viewer 提供了廣泛的渲染選項，可讓您根據自己的要求自訂輸出。
### GroupDocs.Viewer 是否需要任何第三方相依性？
不，GroupDocs.Viewer 是一個獨立的 API，不需要任何第三方依賴來呈現文件。
### 是否有可供測試的試用版？
是的，您可以從以下網址下載 GroupDocs.Viewer 的免費試用版 [這裡](https://releases.groupdocs.com/) 在購買之前評估其功能。