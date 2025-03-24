---
title: 渲染 CAD 工程圖中的所有佈局
linktitle: 渲染 CAD 工程圖中的所有佈局
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 渲染 CAD 繪圖中的所有佈局。請遵循我們的無縫整合綜合教程。
weight: 11
url: /zh-hant/net/rendering-cad-drawings/render-all-layouts-cad/
---
## 介紹
在文件管理和視覺化領域，GroupDocs.Viewer for .NET 作為多功能解決方案脫穎而出，使開發人員能夠在其 .NET 應用程式中輕鬆呈現各種文件類型。其眾多功能包括高效渲染 CAD 繪圖的能力，包括它們所需的複雜佈局。在本教程中，我們將深入研究利用 GroupDocs.Viewer for .NET 渲染 CAD 繪圖中存在的所有佈局的過程。 
## 先決條件
在開始本教學之前，請確保您具備以下先決條件：
1. 對 .NET 開發的基本了解：熟悉 .NET 開發基礎知識將有助於理解本教程中概述的實作步驟。
2. 安裝 GroupDocs.Viewer for .NET：確保您已安裝 GroupDocs.Viewer for .NET 程式庫。您可以從[網站](https://releases.groupdocs.com/viewer/net/).
3. CAD 繪圖檔：取得您想要渲染的 CAD 圖面檔案。其中可能包括具有多種佈局的 DWG 檔案。
4. 開發環境：使用必要的工具和相依性設定您首選的開發環境。

## 導入命名空間
首先，確保將所需的命名空間匯入到 .NET 專案中。這些命名空間提供對使用 GroupDocs.Viewer 渲染 CAD 繪圖所需的功能的存取。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟2：導入System.IO命名空間
```csharp
using System.IO;
```
## 第 1 步：指定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
定義要儲存渲染輸出的目錄。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
設定渲染頁面的檔案路徑的格式。在這種情況下，頁面將儲存為 HTML 檔案。
## 第 3 步：實例化檢視器對象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
建立 Viewer 類別的實例，並將 CAD 繪圖檔案的路徑作為參數傳遞。
## 步驟 4：配置 HTML 視圖選項
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
配置 HTML 視圖選項，指定應為 CAD 工程圖呈現佈局。
## 第 5 步：渲染 CAD 繪圖
```csharp
viewer.View(options);
```
呼叫 Viewer 物件的 View 方法，傳遞配置的選項來渲染 CAD 繪圖。
## 步驟6：顯示輸出目錄
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
通知使用者渲染成功以及輸出目錄的位置。

## 結論
在本教學中，我們探討如何利用 GroupDocs.Viewer for .NET 呈現 CAD 繪圖中存在的所有版面。透過遵循逐步指南並實現提供的程式碼片段，您可以將此功能無縫整合到您的 .NET 應用程式中，從而增強文件視覺化功能。
## 常見問題解答
### GroupDocs.Viewer 是否與各種 CAD 格式相容？
是的，GroupDocs.Viewer 支援以 DWG 和 DXF 等格式渲染 CAD 繪圖。
### 我可以根據應用程式的要求自訂渲染輸出嗎？
當然，GroupDocs.Viewer 提供了多種自訂渲染輸出的選項，包括影像品質、頁面大小等。
### GroupDocs.Viewer 是否需要任何額外的商業用途授權？
是的，對於商業用途，您可能需要獲得許可證。您可以獲得用於測試目的的臨時許可證或從網站購買商業許可證。
### 我可以使用 GroupDocs.Viewer 非同步渲染 CAD 繪圖嗎？
是的，GroupDocs.Viewer 提供非同步渲染功能，允許在不阻塞主執行緒的情況下高效處理大型 CAD 繪圖。
### GroupDocs.Viewer 是否提供故障排除和技術協助支援？
當然，您可以從 GroupDocs.Viewer 社群論壇尋求支援和協助，可造訪[這裡](https://forum.groupdocs.com/c/viewer/9).