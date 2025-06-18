---
"description": "了解如何使用 GroupDocs.Viewer for .NET 在 CAD 圖紙中渲染單一佈局。輕鬆實現與 .NET 應用程式的無縫整合。"
"linktitle": "在 CAD 圖紙中渲染單一佈局"
"second_title": "GroupDocs.Viewer .NET API"
"title": "在 CAD 圖紙中渲染單一佈局"
"url": "/zh-hant/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# 在 CAD 圖紙中渲染單一佈局

## 介紹
在 .NET 開發領域，處理和檢視 CAD 圖紙是一項常見的需求。 GroupDocs.Viewer for .NET 透過提供在 .NET 應用程式中渲染 CAD 圖紙的全面解決方案，簡化了這項任務。在本教程中，我們將深入研究如何使用 GroupDocs.Viewer for .NET 在 CAD 圖紙中渲染單一佈局。
## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
- 對 C# 程式語言和 .NET 架構有基本的了解。
- 您的系統上安裝了 Visual Studio。
- 已下載 GroupDocs.Viewer for .NET 函式庫，並將 tutorialsd 新增至您的專案。您可以從 [這裡](https://releases。groupdocs.com/viewer/net/).
- 熟悉 CAD 檔案格式及其結構。

## 導入命名空間
首先，將必要的命名空間匯入到您的 C# 程式碼中以存取 GroupDocs.Viewer 功能。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 步驟 1：定義輸出目錄
指定要儲存渲染輸出的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
定義每個渲染頁面的檔案路徑的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步驟3：實例化檢視器對象
建立 GroupDocs.Viewer 提供的 Viewer 類別的實例。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 步驟 4：配置 HTML 視圖選項
配置使用嵌入資源呈現 HTML 輸出的選項。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 步驟5：指定CAD佈局名稱
指定要渲染的 CAD 佈局的名稱。
```csharp
options.CadOptions.LayoutName = "Model";
```
## 步驟6：渲染CAD圖紙
使用指定的選項呼叫 Viewer 物件的 View 方法。
```csharp
viewer.View(options);
```
## 步驟 7：顯示成功訊息
通知使用者來源文件已成功呈現。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
渲染 CAD 圖紙，尤其是在處理佈局時，可能是一項艱鉅的任務。但是，使用 GroupDocs.Viewer for .NET，流程變得無縫且有效率。按照本教學中概述的步驟，您可以毫不費力地在 .NET 應用程式中渲染 CAD 圖紙中的單一佈局。
## 常見問題解答
### 我可以使用 GroupDocs.Viewer for .NET 同時渲染多個佈局嗎？
是的，GroupDocs.Viewer for .NET 支援從 CAD 圖紙渲染多種佈局。
### GroupDocs.Viewer 是否相容於不同的 CAD 檔案格式？
當然，GroupDocs.Viewer 支援多種 CAD 檔案格式，包括 DWG、DXF、DGN 等。
### 我可以自訂 CAD 圖紙的渲染選項嗎？
是的，GroupDocs.Viewer 提供了廣泛的選項來根據您的要求自訂渲染設定。
### GroupDocs.Viewer for .NET 有免費試用版嗎？
是的，您可以透過免費試用探索 GroupDocs.Viewer 的功能 [這裡](https://releases。groupdocs.com/).
### 在哪裡可以獲得 GroupDocs.Viewer for .NET 的支援？
如有任何疑問或需要協助，您可以造訪 GroupDocs.Viewer 論壇 [這裡](https://forum。groupdocs.com/c/viewer/9).