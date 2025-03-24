---
title: 渲染 SVG 和 SVGZ 影像
linktitle: 渲染 SVG 和 SVGZ 影像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 影像。輕鬆將向量圖形轉換為 HTML、JPG、PNG 和 PDF。
weight: 16
url: /zh-hant/net/image-rendering/render-svg-svgz-images/
---

# 渲染 SVG 和 SVGZ 影像

## 介紹
在本教學中，我們將引導您完成使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 影像的過程。 GroupDocs.Viewer for .NET 是一個功能強大的文件呈現 API，使開發人員能夠在其 .NET 應用程式中呈現各種文件格式。 SVG 和 SVGZ 是用於向量圖形的流行圖像格式，透過 GroupDocs.Viewer for .NET，您可以輕鬆將它們渲染為不同的輸出格式，例如 HTML、JPG、PNG 和 PDF。
## 先決條件
在開始之前，請確保您已安裝並設定以下先決條件：
1.  GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET[這裡](https://releases.groupdocs.com/viewer/net/).
2. 開發環境：確保您擁有用於 .NET 開發的有效開發環境，例如 Visual Studio。
3. 範例 SVGZ 檔案：準備好範例 SVGZ 檔案以供測試。

## 導入命名空間
在深入研究程式碼之前，讓我們先導入必要的名稱空間：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 第 1 步：將 SVGZ 渲染為 HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 第 2 步：將 SVGZ 渲染為 JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 步驟 3：將 SVGZ 渲染為 PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 第 4 步：將 SVGZ 渲染為 PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 影像。只需幾個簡單的步驟，您就可以將 SVGZ 映像轉換為各種輸出格式，如 HTML、JPG、PNG 和 PDF，從而使它們在不同的環境中均可存取和檢視。
## 常見問題解答
### GroupDocs.Viewer 可以渲染其他影像格式嗎？
是的，GroupDocs.Viewer 支援渲染各種影像格式，包括 PNG、JPEG、BMP、TIFF、GIF 等。
### GroupDocs.Viewer 與 .NET Core 相容嗎？
是的，GroupDocs.Viewer 與 .NET Framework 和 .NET Core 相容。
### 我可以自訂渲染選項嗎？
是的，GroupDocs.Viewer 提供了廣泛的渲染選項，可讓您根據您的要求自訂輸出。
### GroupDocs.Viewer 是否需要任何第三方相依性？
不需要，GroupDocs.Viewer 是一個獨立的 API，不需要任何第三方依賴項即可呈現文件。
### 有試用版可供測試嗎？
是的，您可以從以下位置下載 GroupDocs.Viewer 的免費試用版：[這裡](https://releases.groupdocs.com/)在購買之前評估其功能。