---
title: 渲染 RAR 檔案
linktitle: 渲染 RAR 檔案
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 將 RAR 檔案呈現為 HTML、JPG、PNG 或 PDF 格式。輕鬆檢視和分享 RAR 存檔的內容。
weight: 13
url: /zh-hant/net/rendering-archive-files/render-rar/
---

# 渲染 RAR 檔案

## 介紹
RAR 檔案是一種流行的格式，用於將多個檔案和資料夾壓縮並儲存到單一容器中。將 RAR 檔案呈現為各種格式（例如 HTML、JPG、PNG 或 PDF）對於查看或分享這些存檔的內容至關重要。在本教學中，我們將探討如何使用 GroupDocs.Viewer for .NET 呈現 RAR 檔案。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. GroupDocs.Viewer for .NET：從下列位置安裝 GroupDocs.Viewer for .NET 程式庫[下載連結](https://releases.groupdocs.com/viewer/net/).
2. 範例 RAR 存檔：準備好範例 RAR 存檔以供渲染。

## 導入命名空間
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
## 第 2 步：渲染為 HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 3 步：渲染為 JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 4 步：渲染為 PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 5 步：渲染為 PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 結論
使用 GroupDocs.Viewer for .NET 將 RAR 檔案呈現為各種格式變得非常簡單。透過遵循本教學中概述的步驟，您可以輕鬆地將 RAR 檔案轉換為 HTML、JPG、PNG 或 PDF 格式，從而輕鬆查看和分享其內容。
## 常見問題解答
### GroupDocs.Viewer for .NET 可以處理加密的 RAR 存檔嗎？
是的，GroupDocs.Viewer for .NET 支援渲染加密的 RAR 存檔，前提是在渲染過程中提供必要的密碼。
### 是否可以自訂渲染文件的輸出外觀？
絕對地！ GroupDocs.Viewer for .NET 提供了廣泛的自訂選項，讓使用者可以根據自己的喜好自訂呈現文件的外觀。
### GroupDocs.Viewer for .NET 是否支援呈現 RAR 以外的其他存檔格式？
是的，GroupDocs.Viewer for .NET 支援呈現各種存檔格式，包括 ZIP、TAR、7z 等。
### 我可以將 GroupDocs.Viewer for .NET 整合到我的 Web 應用程式中嗎？
當然！ GroupDocs.Viewer for .NET 提供適合整合到桌面和 Web 應用程式中的 API。
### GroupDocs.Viewer for .NET 是否有試用版？
是的，您可以從以下網站免費試用 GroupDocs.Viewer for .NET[網站](https://releases.groupdocs.com/).