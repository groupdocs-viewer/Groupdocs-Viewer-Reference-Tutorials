---
title: 在 CAD 工程圖中渲染單一佈局
linktitle: 在 CAD 工程圖中渲染單一佈局
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 在 CAD 繪圖中渲染單一佈局。在 .NET 應用程式中無縫整合的簡單步驟。
type: docs
weight: 14
url: /zh-hant/net/rendering-cad-drawings/render-single-layout-cad/
---
## 介紹
在 .NET 開發領域，處理和檢視 CAD 繪圖是一項常見需求。 GroupDocs.Viewer for .NET 透過提供在 .NET 應用程式中渲染 CAD 繪圖的全面解決方案來簡化此任務。在本教程中，我們將深入研究使用 GroupDocs.Viewer for .NET 在 CAD 繪圖中渲染單一佈局。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 對 C# 程式語言和 .NET 架構有基本了解。
- Visual Studio 安裝在您的系統上。
- 下載並在專案中引用的 .NET 程式庫的 GroupDocs.Viewer。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).
- 熟悉 CAD 檔案格式及其結構。

## 導入命名空間
首先，將必要的命名空間匯入到 C# 程式碼中以存取 GroupDocs.Viewer 功能。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 第 1 步：定義輸出目錄
指定要儲存渲染輸出的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
定義每個呈現頁面的文件路徑的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 3 步：實例化檢視器對象
建立 GroupDocs.Viewer 提供的 Viewer 類別的實例。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 步驟 4：配置 HTML 視圖選項
配置用於使用嵌入資源呈現 HTML 輸出的選項。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 步驟 5：指定 CAD 佈局名稱
指定要渲染的 CAD 佈局的名稱。
```csharp
options.CadOptions.LayoutName = "Model";
```
## 第 6 步：渲染 CAD 繪圖
使用指定選項呼叫 Viewer 物件的 View 方法。
```csharp
viewer.View(options);
```
## 步驟7：顯示成功訊息
通知使用者來源文件已成功呈現。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
渲染 CAD 工程圖，尤其是在處理佈局時，可能是一項艱鉅的任務。然而，使用 GroupDocs.Viewer for .NET，流程變得無縫且有效率。透過遵循本教學中概述的步驟，您可以輕鬆地在 .NET 應用程式中渲染 CAD 繪圖中的單一佈局。
## 常見問題解答
### 我可以使用 GroupDocs.Viewer for .NET 同時渲染多個佈局嗎？
是的，GroupDocs.Viewer for .NET 支援從 CAD 繪圖渲染多個佈局。
### GroupDocs.Viewer 是否與不同的 CAD 檔案格式相容？
當然，GroupDocs.Viewer 支援多種 CAD 檔案格式，包括 DWG、DXF、DGN 等。
### 我可以自訂 CAD 工程圖的渲染選項嗎？
是的，GroupDocs.Viewer 提供了廣泛的選項來根據您的要求自訂渲染設定。
### GroupDocs.Viewer for .NET 是否有免費試用版？
是的，您可以透過免費試用來探索 GroupDocs.Viewer 的功能[這裡](https://releases.groupdocs.com/).
### 在哪裡可以獲得 GroupDocs.Viewer for .NET 的支援？
如有任何疑問或協助，您可以造訪 GroupDocs.Viewer 論壇[這裡](https://forum.groupdocs.com/c/viewer/9).