---
title: 渲染 CHM 文件
linktitle: 渲染 CHM 文件
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer 在 .NET 中呈現 CHM 檔案。輕鬆將 CHM 轉換為 HTML、JPG、PNG 和 PDF 格式。
weight: 10
url: /zh-hant/net/rendering-web-documents/render-chm/
---
## 介紹
在本教學中，我們將探討如何使用 GroupDocs.Viewer for .NET 呈現 CHM（編譯的 HTML 說明）檔案。 GroupDocs.Viewer for .NET 是一個功能強大的文件呈現 API，允許開發人員在其 .NET 應用程式中顯示 170 多種文件類型，而無需安裝任何外部軟體。

## 先決條件

在我們深入研究渲染 CHM 檔案之前，請確保您符合以下先決條件：

### 安裝適用於 .NET 的 GroupDocs.Viewer

首先，您需要安裝 GroupDocs.Viewer for .NET。您可以從以下位置下載該程式庫[集團文件網站](https://releases.groupdocs.com/viewer/net/)或透過 NuGet 套件管理器在套件管理器控制台中執行以下命令來安裝它：

```bash
Install-Package GroupDocs.Viewer
```

## 導入命名空間

確保將必要的命名空間匯入到您的專案中：

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在讓我們將渲染過程分解為多個步驟：

## 第 1 步：定義輸出目錄

定義要儲存渲染檔案的目錄：

```csharp
string outputDirectory = "Your Document Directory";
```

## 第 2 步：渲染為 HTML

若要將 CHM 檔案呈現為 HTML，請使用下列程式碼片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; //設定為 true 將所有 CHM 內容轉換為單一頁面

    viewer.View(options); //轉換所有頁面
}
```

## 第 3 步：渲染為 JPG

若要將 CHM 檔案渲染為 JPG 影像，請使用下列程式碼片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); //僅轉換第 1、2、3 頁
}
```

## 第 4 步：渲染為 PNG

若要將 CHM 檔案渲染為 PNG 影像，請使用下列程式碼片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); //僅轉換第 1、2、3 頁
}
```

## 第 5 步：渲染為 PDF

若要將 CHM 文件呈現為 PDF 文檔，請使用以下程式碼片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //轉換所有頁面
}
```

## 第 6 步：檢查輸出

渲染過程完成後，檢查渲染檔案的指定輸出目錄：

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

使用 GroupDocs.Viewer for .NET 呈現 CHM 檔案是一個簡單的過程。透過遵循本教學中概述的步驟，您可以在 .NET 應用程式中有效地將 CHM 文件轉換為各種格式，例如 HTML、圖像（JPG、PNG）和 PDF。

## 常見問題解答

### Q1：GroupDocs.Viewer 可以渲染 CHM 之外的其他文件格式嗎？

A1：是的，GroupDocs.Viewer 支援渲染 170 多種文件格式，包括 PDF、DOCX、XLSX、PPTX 等。

### Q2：GroupDocs.Viewer 與 .NET Core 相容嗎？

A2：是的，GroupDocs.Viewer 除了傳統的 .NET Framework 之外也支援 .NET Core。

### Q3：我可以自訂不同輸出格式的渲染選項嗎？

A3：是的，GroupDocs.Viewer 提供了各種自訂渲染過程的選項，例如指定頁碼、設定影像品質和配置輸出路徑。

### Q4：GroupDocs.Viewer 渲染文件需要任何外部依賴嗎？

A4：不需要，GroupDocs.Viewer 是一個獨立的函式庫，不需要任何外部相依性或第三方軟體安裝。

### Q5：GroupDocs.Viewer 有免費試用版嗎？

 A5：是的，您可以透過造訪 GroupDocs.Viewer 免費試用[網站](https://releases.groupdocs.com/).