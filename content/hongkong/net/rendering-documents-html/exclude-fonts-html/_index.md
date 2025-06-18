---
"description": "了解如何使用 GroupDocs.Viewer for .NET 從渲染的 HTML 中排除字體。請按照此逐步指南操作，即可實現無縫文件顯示。"
"linktitle": "從渲染的 HTML 中排除字體"
"second_title": "GroupDocs.Viewer .NET API"
"title": "從渲染的 HTML 中排除字體"
"url": "/zh-hant/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# 從渲染的 HTML 中排除字體

## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的文件渲染庫，它允許開發人員在其 .NET 應用程式中顯示 50 多種文件格式，而無需任何外部相依性。在本教程中，我們將重點介紹 GroupDocs.Viewer 的一項特定功能：從渲染的 HTML 輸出中排除字體。 
## 先決條件
在開始之前，請確保您已準備好以下內容：
1. 對 C# 和 .NET 開發有基本的了解。
2. 已安裝 GroupDocs.Viewer for .NET。您可以從 [這裡](https://releases。groupdocs.com/viewer/net/).
3. Visual Studio 或任何其他用於 C# 開發的 IDE。

## 導入命名空間
在您的 C# 程式碼中，確保包含必要的命名空間：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 步驟 1：定義輸出目錄
設定您想要儲存渲染的 HTML 檔案的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
指定所呈現文件的各個頁面的文件路徑的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步驟3：初始化檢視器對象
使用您想要呈現的文檔實例化 Viewer 物件。
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // 您的程式碼在此處
}
```
## 步驟 4：設定 HTML 視圖選項
定義 HTML 渲染的選項，包括嵌入資源的格式和要排除的字體。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 步驟5：渲染文檔
將 HTML 視圖選項傳遞給 Viewer 物件以呈現文件。
```csharp
viewer.View(options);
```
## 步驟6：輸出渲染文檔位置
告知使用者渲染後的 HTML 檔案的儲存位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
在本教程中，我們學習如何使用 GroupDocs.Viewer for .NET 從渲染的 HTML 輸出中排除字體。按照上面概述的步驟，您可以自訂渲染過程以滿足您的特定需求，確保在應用程式中以最佳方式顯示文件。
## 常見問題解答
### 我可以從呈現的 HTML 中排除多種字體嗎？
是的，您可以新增多個字體名稱到 `FontsToExclude` HTML 視圖選項中的清單。
### GroupDocs.Viewer 是否與所有 .NET 框架相容？
是的，GroupDocs.Viewer 支援 .NET Framework 4.6.1 及更高版本。
### 我可以從遠端儲存位置呈現文件嗎？
是的，GroupDocs.Viewer 支援從本機儲存以及遠端儲存位置和串流呈現文件。
### GroupDocs.Viewer 是否支援 HTML 輸出的響應式設計？
是的，您可以透過相應地調整 HTML 視圖選項來啟用響應式渲染。
### GroupDocs.Viewer 是否提供技術支援？
是的，您可以尋求協助並參與討論 [GroupDocs.Viewer 論壇](https://forum。groupdocs.com/c/viewer/9).