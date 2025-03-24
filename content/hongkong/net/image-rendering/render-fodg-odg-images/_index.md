---
title: 渲染 FODG 和 ODG 影像
linktitle: 渲染 FODG 和 ODG 影像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 將 FODG 和 ODG 圖片渲染為 HTML、JPG、PNG 和 PDF。增強您的文件處理能力。
weight: 15
url: /zh-hant/net/image-rendering/render-fodg-odg-images/
---

# 渲染 FODG 和 ODG 影像

## 介紹
在軟體開發領域，有效處理文件格式至關重要。 GroupDocs.Viewer for .NET 是一款功能強大的工具，旨在簡化在 .NET 應用程式中渲染 FODG 和 ODG 影像的過程。本教學將引導您完成使用 GroupDocs.Viewer for .NET 將這些圖片呈現為各種格式（例如 HTML、JPG、PNG 和 PDF）所需的步驟。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET[這裡](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework：確保您的系統上安裝了 .NET Framework。
3. C# 基礎知識：熟悉 C# 程式語言會有幫助。

## 導入命名空間
在開始實施之前，導入必要的命名空間：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 第1步：設定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`與要儲存渲染影像的目錄路徑。
## 第 2 步：渲染為 HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
此步驟將 FODG 圖像呈現為 HTML 格式。
## 第 3 步：渲染為 JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
此處，FODG 影像被渲染為 JPG 格式。
## 第 4 步：渲染為 PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
此步驟將 FODG 影像轉換為 PNG 格式。
## 第 5 步：渲染為 PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
最後，FODG 影像被渲染為 PDF 格式。

## 結論
在本教程中，我們探討如何使用 GroupDocs.Viewer for .NET 將 FODG 和 ODG 影像渲染為各種格式。透過執行這些步驟，您可以將文件呈現功能無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### GroupDocs.Viewer for .NET 是否與所有版本的 .NET Framework 相容？
GroupDocs.Viewer for .NET 與各種 .NET Framework 版本相容，包括最新版本。
### 我可以使用 GroupDocs.Viewer for .NET 非同步呈現文件嗎？
是的，GroupDocs.Viewer for .NET 提供非同步渲染功能以提高效能。
### GroupDocs.Viewer for .NET 支援渲染加密文件嗎？
是的，GroupDocs.Viewer for .NET 支援使用適當的解密金鑰呈現加密文件。
### 是否可以使用 GroupDocs.Viewer for .NET 自訂渲染輸出？
當然，GroupDocs.Viewer for .NET 提供了各種自訂選項，可根據您的要求自訂渲染輸出。
### 我可以使用 GroupDocs.Viewer for .NET 從遠端儲存位置呈現文件嗎？
是的，GroupDocs.Viewer for .NET 支援從本機和遠端儲存位置呈現文件。