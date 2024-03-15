---
title: 渲染註解並調整時間單位 (MS Project)
linktitle: 渲染註解並調整時間單位 (MS Project)
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 掌握 MS Project 文件的渲染。輕鬆渲染註解、調整時間單位並探索各種輸出格式。
type: docs
weight: 11
url: /zh-hant/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的文件呈現 API，可讓開發人員在其 .NET 應用程式中檢視和操作各種文件格式。在本教程中，我們將重點放在專門針對 MS Project 文件渲染註解和調整時間單位。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. GroupDocs.Viewer for .NET：確保您已下載並安裝 GroupDocs.Viewer for .NET 程式庫。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).
2. 開發環境：設定您首選的具有 .NET 支援的開發環境。
3. MS 專案文件：準備好範例 MS 專案文件以供測試。
## 導入命名空間
首先，讓我們匯入必要的命名空間以開始渲染 MS Project 文件：
## 第 1 步：導入命名空間
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
現在我們已經導入了所需的命名空間，讓我們將每個範例分解為多個步驟以便全面理解。
## 將 MS Project 文件渲染為 HTML
若要將 MS Project 文件呈現為包含註解的 HTML 格式，請依照下列步驟操作：
### 步驟2：設定輸出目錄和檔案格式
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 第 3 步：初始化檢視器物件並設定選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 第 4 步：將文件渲染為 HTML
```csharp
viewer.View(options);
```
## 將 MS Project 文件渲染為影像格式
您也可以將 MS Project 文件渲染為 JPG 和 PNG 等影像格式。就是這樣：
### 步驟5：設定JPG的輸出目錄和檔案格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 第 6 步：初始化檢視器物件並設定 JPG 選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 第 7 步：將文件渲染為 JPG
```csharp
viewer.View(options);
```
重複類似的步驟以渲染為 PNG 和其他影像格式。
## 將 MS 專案文件渲染為 PDF
若要將 MS Project 文件呈現為 PDF 格式，請依照下列步驟操作：
### 步驟8：設定PDF的輸出目錄和檔案格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 第 9 步：初始化檢視器物件並設定 PDF 選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 第 10 步：將文件渲染為 PDF
```csharp
viewer.View(options);
```

## 結論
恭喜！您已成功學習如何使用 GroupDocs.Viewer for .NET 呈現 MS Project 文件並調整時間單位。將這些知識融入您的專案中以增強文件檢視功能。
## 常見問題解答
### 我可以將 MS Project 文件呈現為除 HTML、圖像和 PDF 之外的其他格式嗎？
是的，GroupDocs.Viewer for .NET 支援呈現為各種格式，例如 DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer for .NET 是否有試用版？
是的，您可以從以下位置獲得免費試用[這裡](https://releases.groupdocs.com/).
### 如何取得 GroupDocs.Viewer for .NET 的臨時許可？
訪問[這個連結](https://purchase.groupdocs.com/temporary-license/)獲得臨時許可證。
### 在哪裡可以找到 GroupDocs.Viewer for .NET 的文檔？
參考文檔[這裡](https://reference.groupdocs.com/viewer/net/).
### 我可以在哪裡尋求與 GroupDocs.Viewer for .NET 相關的支援或提出問題？
您可以造訪支援論壇[這裡](https://forum.groupdocs.com/c/viewer/9).