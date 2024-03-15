---
title: 取得 CAD 工程圖的檢視信息
linktitle: 取得 CAD 工程圖的檢視信息
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 擷取 CAD 工程圖的檢視資訊。透過無縫 CAD 檔案處理增強您的 .NET 應用程式。
type: docs
weight: 10
url: /zh-hant/net/rendering-cad-drawings/get-view-info-cad-drawing/
---
## 介紹
在軟體開發領域，有效處理 CAD 繪圖至關重要。無論您是為建築師、工程師還是設計師建立應用程序，為 CAD 檔案提供無縫的檢視體驗都可以大大提高使用者滿意度。 GroupDocs.Viewer for .NET 提供了一個強大的解決方案，可以輕鬆地將 CAD 檔案檢視功能整合到您的 .NET 應用程式中。在本教學中，我們將引導您完成使用 GroupDocs.Viewer for .NET 取得 CAD 繪圖視圖資訊的流程。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
### 1. 安裝適用於.NET的GroupDocs.Viewer
首先，您需要在開發環境中安裝 GroupDocs.Viewer for .NET。您可以從以下位置下載最新版本[集團文件網站](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework 的基本了解
熟悉 .NET 框架和 C# 程式語言對於學習本教程至關重要。
### 3.搭建開發環境
確保您擁有使用 Visual Studio 或任何其他 .NET 相容 IDE 設定的開發環境。

## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以利用 GroupDocs.Viewer 功能。

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

## 第 1 步：定義查看資訊選項
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
```
在這一步驟中，我們初始化一個實例`ViewInfoOptions`指定檢索視圖資訊的選項。我們用`ForHtmlView()`方法來指示我們要檢索 HTML 視圖的資訊。
## 步驟 2：配置 CAD 渲染選項
```csharp
viewInfoOptions.CadOptions.RenderLayouts = true;
```
在這裡，我們設定`RenderLayouts`財產給`true`包括所有佈局。這可確保渲染 CAD 檔案中的所有佈局。
## 步驟 3：檢索 CAD 視圖訊息
```csharp
CadViewInfo info = viewer.GetViewInfo(viewInfoOptions) as CadViewInfo;
```
我們稱之為`GetViewInfo()`檢視器物件上的方法，傳遞`viewInfoOptions`作為檢索 CAD 文件視圖資訊的參數。我們投射返回的`ViewInfo`反對`CadViewInfo`類型。
## 步驟 4：顯示文件類型和頁數
```csharp
Console.WriteLine("Document type is: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```
在此步驟中，我們將 CAD 檔案中的文件類型和總頁數列印到控制台。
## 第 5 步：顯示佈局和圖層
```csharp
Console.WriteLine("\nLayouts:");
foreach (Layout layout in info.Layouts)
    Console.WriteLine(layout);
Console.WriteLine("\nLayers:");
foreach (Layer layer in info.Layers)
    Console.WriteLine(layer);
```
最後，我們迭代從 CAD 檔案檢索的佈局和圖層並將它們列印到控制台。

## 結論
透過學習本教學課程，您已了解如何利用 GroupDocs.Viewer for .NET 無縫取得 CAD 工程圖的視圖資訊。將此功能整合到您的 .NET 應用程式中可以顯著增強使用者體驗並簡化 CAD 檔案處理。
## 常見問題解答
### Q：GroupDocs.Viewer for .NET 是否與所有 CAD 檔案格式相容？
GroupDocs.Viewer for .NET 支援各種 CAD 檔案格式，包括 DWG、DXF、DWF 等。
### Q：我可以自訂 CAD 檔案的渲染選項嗎？
是的，您可以根據您的要求自訂渲染選項，例如佈局、圖層和輸出格式。
### Q：GroupDocs.Viewer for .NET 是否有免費試用版？
是的，您可以在購買前從網站訪問 GroupDocs.Viewer for .NET 免費試用版，以探索其功能。
### Q：GroupDocs.Viewer for .NET 的更新發布頻率如何？
GroupDocs 定期發布更新和增強功能，以確保與最新 CAD 檔案格式的相容性並提高整體效能。
### Q：我可以在哪裡尋求有關 GroupDocs.Viewer for .NET 的支援或協助？
您可以造訪 GroupDocs.Viewer 論壇或聯絡支援人員以取得任何疑問、技術協助或故障排除。