---
"description": "了解如何使用 GroupDocs.Viewer for .NET 調整 CAD 圖紙的輸出影像大小。輕鬆提升可視性和可用性。"
"linktitle": "調整 CAD 繪圖的輸出影像大小"
"second_title": "GroupDocs.Viewer .NET API"
"title": "調整 CAD 繪圖的輸出影像大小"
"url": "/zh-hant/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# 調整 CAD 繪圖的輸出影像大小

## 介紹
CAD 圖紙通常需要進行特定調整才能獲得最佳的檢視和呈現效果。 GroupDocs.Viewer for .NET 提供了一套強大的工具集來管理和自訂 CAD 圖紙輸出。在本教學中，我們將逐步指導您調整 CAD 圖紙的輸出影像大小。
## 先決條件
在開始之前，請確保您符合以下先決條件：
1. GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET [這裡](https://releases。groupdocs.com/viewer/net/).
2. 文件目錄：準備您的文件所在的目錄。
3. 基本理解：熟悉.NET 程式設計的基本概念。

## 導入命名空間
首先，請確保匯入必要的命名空間以存取 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟1：設定輸出目錄
定義要儲存 CAD 圖紙輸出影像的目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
設定頁面檔案路徑的格式。此格式將用於命名各個頁面並將其儲存為 HTML 檔案：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步驟3：調整影像大小
在檢視器物件的使用區塊內，透過設定適當的選項來調整 CAD 繪圖的影像大小：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 步驟4：顯示輸出目錄
渲染文件後，顯示一條指示渲染成功的訊息並提供輸出目錄的位置：
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
調整 CAD 圖紙的輸出影像大小對於增強其視覺性和可用性至關重要。使用 GroupDocs.Viewer for .NET，此流程變得精簡高效，讓您能夠根據特定需求自訂輸出。
## 常見問題解答
### 除了 CAD 圖紙之外，我還可以調整其他類型文件的輸出影像大小嗎？
是的，GroupDocs.Viewer for .NET 支援各種文件類型，您可以調整大多數文件格式的輸出圖片大小。
### GroupDocs.Viewer for .NET 是否與不同版本的 .NET 框架相容？
是的，GroupDocs.Viewer for .NET 與 .NET 框架的多個版本相容，確保在不同環境中的靈活性和可用性。
### GroupDocs.Viewer for .NET 是否有任何可用的授權選項？
是的，您可以探索不同的許可選項，包括臨時許可和商業許可，以滿足您的需求。
### 我可以自訂渲染文檔的輸出格式嗎？
當然，GroupDocs.Viewer for .NET 提供了各種自訂選項，可讓您根據教學自訂輸出格式。
### 在哪裡可以找到更多關於 GroupDocs.Viewer for .NET 的支援或協助？
您可以造訪 GroupDocs.Viewer 論壇 [這裡](https://forum.groupdocs.com/c/viewer/9) 獲得支持、提出問題並與社區互動。