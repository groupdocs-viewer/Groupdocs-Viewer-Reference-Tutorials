---
title: 將檔案渲染到單一或多個 HTML 頁面
linktitle: 將檔案渲染到單一或多個 HTML 頁面
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 將檔案呈現為 HTML 頁面。輕鬆地將文件檢視功能整合到您的 .NET 應用程式中。
weight: 12
url: /zh-hant/net/rendering-archive-files/render-archives-html/
---
## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的文件呈現庫，可讓開發人員輕鬆地將文件檢視功能整合到他們的 .NET 應用程式中。無論您需要將檔案呈現為單一還是多個 HTML 頁面，本教學都會逐步引導您完成流程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  GroupDocs.Viewer for .NET：確保您的專案中安裝了該程式庫。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).
2. 開發環境：為 .NET 開發設定一個工作開發環境。
3. 文檔目錄：準備一個儲存文檔的目錄。
4. C# 的基本了解：熟悉 C# 程式語言基礎。

## 導入命名空間
在您的 C# 程式碼中，確保導入必要的命名空間：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

請依照下列步驟使用 GroupDocs.Viewer for .NET 將檔案呈現到單一或多個 HTML 頁面：
## 第1步：設定輸出目錄
定義要儲存渲染的 HTML 頁面的目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
## 第2步：定義檔路徑格式
指定 HTML 頁面的文件路徑格式。對於單頁渲染：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
對於多頁面渲染：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## 第 3 步：渲染為單頁 HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## 步驟 4： 渲染為多個 HTML 頁面
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; //設定每頁的項目
    viewer.View(options);
}
```
## 第 5 步：檢查輸出
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
使用 GroupDocs.Viewer for .NET 將檔案呈現為 HTML 頁面是一個簡單的過程。透過遵循本教學中概述的步驟，您可以將文件檢視功能無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### 除了檔案之外，我還可以渲染其他文件格式嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer 是否適用於桌面和 Web 應用程式？
當然，GroupDocs.Viewer 可以在桌面和 Web 應用程式中無縫使用。
### GroupDocs.Viewer 是否提供檢視器介面的自訂選項？
是的，您可以根據您的要求自訂檢視器介面。
### 我可以使用 GroupDocs.Viewer 非同步呈現文件嗎？
是的，GroupDocs.Viewer 提供非同步渲染功能以提高效能。
### GroupDocs.Viewer是否支援文件註解？
是的，GroupDocs.Viewer 允許使用者有效率地檢視和管理文件註解。