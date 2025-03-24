---
title: 載入文檔時指定文件類型
linktitle: 載入文檔時指定文件類型
second_title: GroupDocs.Viewer .NET API
description: 了解如何在使用 GroupDocs.Viewer for .NET 載入文件時指定文件類型。在 .NET 應用程式中準確呈現各種格式。
weight: 10
url: /zh-hant/net/advanced-loading/specify-file-type/
---
## 介紹
GroupDocs.Viewer for .NET 是一種多功能文件渲染 API，支援多種文件格式，包括 DOCX、PDF、PPTX 等。透過在載入文件時指定文件類型，您可以確保準確的渲染和使用者流暢的檢視體驗。
## 先決條件
在開始之前，請確保您具備以下先決條件：
- C# 和 .NET 架構的基礎知識。
- Visual Studio 安裝在您的系統上。
- GroupDocs.Viewer for .NET 安裝在您的專案中。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).
##
## 導入命名空間
首先，您需要將必要的命名空間匯入到 C# 程式碼中。這些命名空間提供對文件呈現所需的類別和方法的存取。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：設定輸出目錄
定義要儲存渲染文檔頁面的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
指定文件每個頁面的輸出 HTML 文件的命名格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步驟 3：指定載入選項
建立一個實例`LoadOptions`類別並設定所需的文件類型。
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## 第 4 步：載入文件並渲染
使用`Viewer`類別來載入文件並將其呈現為 HTML 格式。
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 步驟5：顯示成功訊息
通知使用者文件已成功呈現並指定輸出文件的位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 在載入文件時指定文件類型。透過執行這些簡單的步驟，您可以確保在 .NET 應用程式中準確呈現各種文件格式。
## 常見問題解答
### 我可以使用 GroupDocs.Viewer for .NET 呈現 DOCX 以外的文件嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、PPTX、XLSX 等。
### GroupDocs.Viewer for .NET 是否與 .NET Core 相容？
是的，GroupDocs.Viewer for .NET 與 .NET Framework 和 .NET Core 相容。
### 我可以自訂 GroupDocs.Viewer 產生的輸出 HTML 檔案嗎？
是的，您可以使用 API 提供的各種選項自訂 HTML 輸出。
### GroupDocs.Viewer for .NET 是否需要任何外部相依性？
不需要，GroupDocs.Viewer for .NET 是一個獨立的函式庫，不需要任何外部相依性。
### GroupDocs.Viewer for .NET 是否有試用版？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.groupdocs.com/viewer/net/).