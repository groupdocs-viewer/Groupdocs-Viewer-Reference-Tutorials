---
title: 渲染 EMZ 和 EMF 影像
linktitle: 渲染 EMZ 和 EMF 影像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 將 EMZ 和 EMF 影像呈現為各種格式。面向開發人員的易於理解的教程。
weight: 14
url: /zh-hant/net/image-rendering/render-emz-emf-images/
---
## 介紹

GroupDocs.Viewer for .NET 是一個強大的文件呈現API，允許開發人員在其.NET 應用程式中顯示各種文件類型，包括EMZ（增強型Windows 圖元文件）和EMF（增強型圖元文件）圖像。在本教學中，我們將探索如何使用 GroupDocs.Viewer for .NET 將 EMZ 和 EMF 影像渲染為不同的格式，例如 HTML、JPG、PNG 和 PDF。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1.  GroupDocs.Viewer for .NET：您可以從以下位置下載程式庫：[這裡](https://releases.groupdocs.com/viewer/net/).
2. 開發環境：確保您為 .NET 開發設定了相容的開發環境。
3. 範例 EMZ/EMF 影像：具有可用於渲染的範例 EMZ 和 EMF 影像。

## 導入命名空間

在深入研究程式碼之前，讓我們先導入必要的名稱空間：

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

現在，讓我們以逐步指南的形式將每個範例分解為多個步驟：

## 將 EMZ/EMF 影像渲染為 HTML

### 第1步：設定輸出目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`以及要儲存渲染的 HTML 檔案的路徑。

### 步驟2：定義頁面檔案路徑格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
這將指定渲染的 HTML 檔案的檔案路徑格式。

### 第 3 步：渲染為 HTML：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
此程式碼初始化`Viewer`物件與範例 EMZ 映像並使用指定選項將其呈現為 HTML 格式。

## 將 EMZ/EMF 影像渲染為 JPG、PNG 和 PDF

重複以下步驟渲染為 JPG、PNG 和 PDF 格式：

### 步驟1：定義頁面檔案路徑格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
根據所需的輸出格式調整檔案名稱和副檔名（`jpg`, `png` ， 或者`pdf`）。

### 第 2 步：渲染為對應格式：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    //根據輸出格式（Jpg、Png、Pdf）調整選項
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
代替`JpgViewOptions`和`PngViewOptions`或者`PdfViewOptions`基於所需的輸出格式。

## 結論

總而言之，GroupDocs.Viewer for .NET 提供了一個無縫解決方案，可在 .NET 應用程式中將 EMZ 和 EMF 影像呈現為各種格式。透過遵循本教程中概述的步驟，開發人員可以輕鬆地將文件渲染功能整合到他們的應用程式中。

## 常見問題解答

### Q：GroupDocs.Viewer 能否呈現 EMZ 和 EMF 影像之外的其他文件格式？
答：是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、DOCX、PPTX、XLSX 等。

### Q：GroupDocs.Viewer for .NET 是否有免費試用版？
答：是的，您可以免費試用[這裡](https://releases.groupdocs.com/).

### Q：GroupDocs.Viewer 是否為開發人員提供支援？
答：是的，GroupDocs 透過其[論壇](https://forum.groupdocs.com/c/viewer/9)開發人員可以在這裡提出問題並尋求協助。

### Q：我可以購買 GroupDocs.Viewer for .NET 的臨時授權嗎？
答：是的，可以購買臨時許可證[這裡](https://purchase.groupdocs.com/temporary-license/).

### Q：在哪裡可以找到 GroupDocs.Viewer for .NET 的詳細文件？
答：可以參考文檔[這裡](https://tutorials.groupdocs.com/viewer/net/)有關使用 API 的全面指導。