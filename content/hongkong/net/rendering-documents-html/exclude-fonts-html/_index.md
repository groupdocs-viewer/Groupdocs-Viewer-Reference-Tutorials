---
title: 從渲染的 HTML 中排除字體
linktitle: 從渲染的 HTML 中排除字體
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 從呈現的 HTML 中排除字體。請按照此逐步指南進行無縫文件顯示。
weight: 10
url: /zh-hant/net/rendering-documents-html/exclude-fonts-html/
---
## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的文件呈現庫，允許開發人員在其 .NET 應用程式中顯示 50 多種文件格式，而無需外部相依性。在本教程中，我們將重點介紹 GroupDocs.Viewer 的一個特定功能：從渲染的 HTML 輸出中排除字體。 
## 先決條件
在開始之前，請確保您具備以下條件：
1. 對 C# 和 .NET 開發有基本了解。
2. 安裝了適用於 .NET 的 GroupDocs.Viewer。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio 或任何其他用於 C# 開發的 IDE。

## 導入命名空間
在您的 C# 程式碼中，確保包含必要的命名空間：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 第 1 步：定義輸出目錄
設定要儲存渲染的 HTML 檔案的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
指定所呈現文件的各個頁面的文件路徑的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 3 步：初始化檢視器對象
使用要呈現的文檔實例化 Viewer 物件。
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    //你的程式碼放在這裡
}
```
## 第 4 步：設定 HTML 視圖選項
定義 HTML 呈現的選項，包括嵌入資源的格式和要排除的字型。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 第5步：渲染文檔
將 HTML 視圖選項傳遞給 Viewer 物件以呈現文件。
```csharp
viewer.View(options);
```
## 第 6 步：輸出渲染文檔位置
告知使用者渲染的 HTML 檔案的儲存位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 從呈現的 HTML 輸出中排除字型。透過執行上述步驟，您可以自訂渲染過程以滿足您的特定要求，確保文件在應用程式中的最佳顯示。
## 常見問題解答
### 我可以從渲染的 HTML 中排除多種字體嗎？
是的，您可以將多個字體名稱新增至`FontsToExclude`HTML 視圖選項中的清單。
### GroupDocs.Viewer 是否與所有 .NET 框架相容？
是的，GroupDocs.Viewer 支援 .NET Framework 4.6.1 及更高版本。
### 我可以從遠端儲存位置渲染文件嗎？
是的，GroupDocs.Viewer 支援從本機儲存以及遠端儲存位置和串流呈現文件。
### GroupDocs.Viewer 是否支援 HTML 輸出的響應式設計？
是的，您可以透過相應調整 HTML 視圖選項來啟用響應式渲染。
### GroupDocs.Viewer 是否提供技術支援？
是的，您可以尋求協助並參與相關討論[GroupDocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9).