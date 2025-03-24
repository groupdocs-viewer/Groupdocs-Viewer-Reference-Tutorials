---
title: 渲染追蹤更改
linktitle: 渲染追蹤更改
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 輕鬆呈現文件中的追蹤變更。提高您的文件管理效率。
weight: 10
url: /zh-hant/net/rendering-word-processing-documents/render-tracked-changes/
---

# 渲染追蹤更改

## 介紹
在當今的數位時代，有效管理和查看文件對於企業和個人都至關重要。隨著先進技術的出現，GroupDocs.Viewer for .NET 等解決方案徹底改變了我們與各種文件格式（包括 Word 文件、PDF 等）互動的方式。在本綜合指南中，我們將深入研究如何利用 GroupDocs.Viewer for .NET 無縫呈現文件中的追蹤變更。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. GroupDocs.Viewer for .NET 安裝：從下列位置下載並安裝 GroupDocs.Viewer for .NET[網站](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework：確保您的系統上安裝了 .NET Framework。
3. 文件目錄：準備一個用於儲存文件的目錄。

## 導入命名空間
首先，將必要的命名空間匯入到您的專案中。這些命名空間對於有效利用 GroupDocs.Viewer 功能至關重要。
## 腳步：
1. 開啟您的 IDE：啟動您首選的整合開發環境 (IDE)，例如 Visual Studio。
2. 建立或開啟您的專案：開始一個新專案或開啟您打算使用 GroupDocs.Viewer 的現有專案。
3. 匯入命名空間：在專案檔案或程式碼檔案中，新增以下命名空間：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在，讓我們將提供的範例分解為多個步驟，以指導您使用 GroupDocs.Viewer for .NET 呈現追蹤的變更。
## 第1步：設定輸出目錄
首先，定義要儲存渲染輸出的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`以及您所需目錄的路徑。
## 步驟2：定義頁面檔案路徑格式
指定頁面檔案路徑的格式。此格式將決定呈現的頁面的命名和儲存方式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
這裡，`"page_{0}.html"`表示頁面將被命名為`page_1.html`, `page_2.html`， 等等。
## 第 3 步：初始化檢視器對象
初始化一個`Viewer`透過將文件的路徑作為參數傳遞來取得物件。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    //程式碼繼續下一步...
}
```
確保更換`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES`以及您的文件的路徑。
## 步驟 4：配置 HTML 視圖選項
配置 HTML 視圖選項以自訂呈現設置，例如呈現追蹤變更。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
此步驟允許在輸出 HTML 中呈現追蹤的變更。
## 第5步：渲染文檔
使用配置的選項渲染文件。
```csharp
viewer.View(options);
```
此命令根據提供的設定啟動渲染過程。
## 步驟6：顯示輸出目錄
告知使用者渲染輸出的儲存位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
此訊息通知使用者渲染成功以及在哪裡可以找到輸出檔案。

## 結論
總之，GroupDocs.Viewer for .NET 提供了一個強大的解決方案，可以輕鬆呈現文件中追蹤的變更。透過遵循本文概述的逐步指南，您可以將此功能無縫整合到您的 .NET 應用程式中，從而提高文件管理效率。
## 常見問題解答
### 我可以使用 GroupDocs.Viewer for .NET 以各種文件格式呈現追蹤的變更嗎？
是的，GroupDocs.Viewer 支援以多種格式呈現追蹤的更改，包括 DOCX、PDF 等。
### GroupDocs.Viewer for .NET 是否與所有 .NET Framework 版本相容？
是的，GroupDocs.Viewer for .NET 與各種版本的 .NET Framework 相容，確保廣泛的兼容性。
### GroupDocs.Viewer 是否提供任何用於測試目的的免費試用版？
是的，您可以在做出購買決定之前免費試用 GroupDocs.Viewer 以探索其功能。
### 我可以自訂渲染設定以滿足特定要求嗎？
當然，GroupDocs.Viewer 提供了廣泛的自訂選項，可讓您根據需要自訂渲染流程。
### 如果我遇到任何問題或對 GroupDocs.Viewer 有疑問，可以在哪裡尋求協助？
如需支援和社群協助，您可以造訪 GroupDocs.Viewer 論壇：[這個連結](https://forum.groupdocs.com/c/viewer/9).