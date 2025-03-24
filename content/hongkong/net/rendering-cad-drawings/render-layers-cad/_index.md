---
title: CAD 工程圖中的渲染圖層
linktitle: CAD 工程圖中的渲染圖層
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 在 .NET 應用程式中無縫渲染 CAD 繪圖。探索渲染選項、自訂圖層等。
weight: 13
url: /zh-hant/net/rendering-cad-drawings/render-layers-cad/
---
## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的工具，使開發人員能夠將文件呈現功能無縫整合到他們的 .NET 應用程式中。無論您需要渲染 CAD 繪圖、PDF、Microsoft Office 文件或其他文檔，GroupDocs.Viewer 都能提供全面的解決方案。
## 先決條件
在深入使用 GroupDocs.Viewer for .NET 之前，請確保您符合以下先決條件：
- 對 C# 程式語言有基本了解。
- 在您的電腦上設定.NET 開發環境。
- 安裝了適用於 .NET 的 GroupDocs.Viewer。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).
- 造訪 GroupDocs.Viewer for .NET 文件以供參考，可找到[這裡](https://tutorials.groupdocs.com/viewer/net/).

## 導入命名空間
若要開始使用 GroupDocs.Viewer for .NET，您需要在專案中匯入所需的命名空間。按著這些次序：

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

讓我們將提供的範例分解為多個步驟：
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 3 步：初始化檢視器對象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    //代碼塊繼續...
}
```
## 第 4 步：設定 HTML 視圖選項
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 第 5 步：定義 CAD 圖層
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## 第 6 步：渲染文檔
```csharp
viewer.View(options);
```
## 第7步：輸出渲染文檔位置
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
透過 GroupDocs.Viewer for .NET，在 .NET 應用程式中渲染 CAD 繪圖成為一個無縫過程。透過遵循本指南中概述的步驟，您可以輕鬆地將文件渲染功能整合到您的專案中。
## 常見問題解答
### GroupDocs.Viewer 是否與所有類型的 CAD 繪圖相容？
是的，GroupDocs.Viewer 支援渲染多種 CAD 繪圖格式，包括 DWG 和 DXF。
### 我可以自訂 CAD 工程圖的渲染選項嗎？
當然，GroupDocs.Viewer 提供了各種自訂選項，例如指定要渲染的圖層或設定輸出格式。
### GroupDocs.Viewer 是否需要網路連線來呈現文件？
不需要，GroupDocs.Viewer 在本地執行渲染，無需網路連線。
### GroupDocs.Viewer for .NET 是否有免費試用版？
是的，您可以免費試用 GroupDocs.Viewer for .NET[這裡](https://releases.groupdocs.com/).
### 在哪裡可以獲得 GroupDocs.Viewer for .NET 的支援？
如需任何技術協助或疑問，您可以造訪 GroupDocs.Viewer 論壇[這裡](https://forum.groupdocs.com/c/viewer/9).