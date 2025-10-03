---
"description": "了解如何使用 GroupDocs.Viewer for .NET 將 EMZ 和 EMF 影像渲染為各種格式。這是一個面向開發人員的簡單易懂的教學。"
"linktitle": "渲染 EMZ 和 EMF 影像"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 EMZ 和 EMF 影像"
"url": "/zh-hant/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# 渲染 EMZ 和 EMF 影像

## 介紹

GroupDocs.Viewer for .NET 是一個功能強大的文件渲染 API，可讓開發人員在其 .NET 應用程式中顯示各種文件類型，包括 EMZ（增強型 Windows 圖元檔案）和 EMF（增強圖元檔案）影像。在本教學中，我們將探討如何使用 GroupDocs.Viewer for .NET 將 EMZ 和 EMF 影像渲染為 HTML、JPG、PNG 和 PDF 等不同格式。

![使用 GroupDocs.Viewer for .NET 渲染 EMZ 和 EMF 影像](/viewer/image-rendering/render-emz-and-emf-images.png)

## 先決條件

在開始之前，請確保您符合以下先決條件：

1. GroupDocs.Viewer for .NET：您可以從 [這裡](https://releases。groupdocs.com/viewer/net/).
2. 開發環境：確保您已為 .NET 開發設定了相容的開發環境。
3. 樣本 EMZ/EMF 影像：提供樣本 EMZ 和 EMF 影像以供渲染。

## 導入命名空間

在深入研究程式碼之前，讓我們先導入必要的命名空間：

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

現在，讓我們按照逐步指南的格式將每個範例分解為多個步驟：

## 將 EMZ/EMF 影像渲染為 HTML

### 步驟1：設定輸出目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
代替 `"Your Document Directory"` 替換為您想要儲存渲染的 HTML 檔案的路徑。

### 步驟2：定義頁面檔案路徑格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
這將指定呈現的 HTML 檔案的檔案路徑格式。

### 步驟 3：渲染為 HTML：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
此程式碼初始化 `Viewer` 物件與範例 EMZ 圖像一起使用，並使用指定的選項將其呈現為 HTML 格式。

## 將 EMZ/EMF 影像渲染為 JPG、PNG 和 PDF

重複以下步驟以渲染為 JPG、PNG 和 PDF 格式：

### 步驟1：定義頁面檔案路徑格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
根據所需的輸出格式調整檔案名稱和副檔名（`jpg`， `png`， 或者 `pdf`）。

### 步驟 2：渲染為對應格式：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // 根據輸出格式調整選項（Jpg、Png、Pdf）
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
代替 `JpgViewOptions` 和 `PngViewOptions` 或者 `PdfViewOptions` 根據所需的輸出格式。

## 結論

總而言之，GroupDocs.Viewer for .NET 提供了一個無縫的解決方案，用於在 .NET 應用程式中將 EMZ 和 EMF 映像渲染為各種格式。透過遵循本教程中概述的步驟，開發人員可以輕鬆地將文件渲染功能整合到他們的應用程式中。

## 常見問題解答

### Q：GroupDocs.Viewer 除了可以呈現 EMZ 和 EMF 影像之外，還可以呈現其他文件格式嗎？
答：是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、DOCX、PPTX、XLSX 等。

### Q：GroupDocs.Viewer for .NET 有免費試用版嗎？
答：是的，您可以免費試用 [這裡](https://releases。groupdocs.com/).

### Q：GroupDocs.Viewer 是否為開發人員提供支援？
答：是的，GroupDocs 透過其 [論壇](https://forum.groupdocs.com/c/viewer/9) 開發人員可以在這裡提出問題並尋求協助。

### Q：我可以購買 GroupDocs.Viewer for .NET 的臨時授權嗎？
答：是的，可以購買臨時許可證 [這裡](https://purchase。groupdocs.com/temporary-license/).

### Q：在哪裡可以找到 GroupDocs.Viewer for .NET 的詳細文件？
答：您可以參考文檔 [這裡](https://tutorials.groupdocs.com/viewer/net/) 以獲得有關使用 API 的全面指導。