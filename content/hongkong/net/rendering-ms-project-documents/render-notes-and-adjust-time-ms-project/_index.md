---
"description": "使用 GroupDocs.Viewer for .NET 輕鬆渲染 MS Project 文件。輕鬆渲染註解、調整時間單位並探索各種輸出格式。"
"linktitle": "渲染註解並調整時間單位（MS Project）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染註解並調整時間單位（MS Project）"
"url": "/zh-hant/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# 渲染註解並調整時間單位（MS Project）

## 介紹
GroupDocs.Viewer for .NET 是一款功能強大的文件渲染 API，可讓開發人員在其 .NET 應用程式中查看和操作各種文件格式。在本教程中，我們將重點介紹如何渲染註解並調整 MS Project 文件的時間單位。
## 先決條件
在開始之前，請確保您符合以下先決條件：
1. GroupDocs.Viewer for .NET：確保您已下載並安裝了 GroupDocs.Viewer for .NET 程式庫。您可以從 [這裡](https://releases。groupdocs.com/viewer/net/).
2. 開發環境：設定具有 .NET 支援的首選開發環境。
3. MS Project 文件：準備好一個 MS Project 範例文件以供測試。
## 導入命名空間
首先，讓我們匯入必要的命名空間以開始渲染 MS Project 文件：
## 步驟 1：導入命名空間
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
現在我們已經導入了所需的命名空間，讓我們將每個範例分解為多個步驟，以便全面理解。
## 將 MS Project 文件渲染為 HTML
若要將 MS Project 文件呈現為包含註解的 HTML 格式，請依照下列步驟操作：
### 第 2 步：設定輸出目錄和檔案格式
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 步驟3：初始化檢視器物件並設定選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 步驟 4：將文件渲染為 HTML
```csharp
viewer.View(options);
```
## 將 MS Project 文件渲染為影像格式
您也可以將 MS Project 文件渲染為 JPG 和 PNG 等影像格式。操作方法如下：
### 步驟5：設定JPG的輸出目錄和檔案格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 步驟6：初始化檢視器物件並設定JPG選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 步驟 7：將文件渲染為 JPG
```csharp
viewer.View(options);
```
重複類似步驟以渲染為 PNG 和其他影像格式。
## 將 MS Project 文件渲染為 PDF
若要將 MS Project 文件呈現為 PDF 格式，請依下列步驟操作：
### 步驟8：設定PDF的輸出目錄和檔案格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 步驟 9：初始化檢視器物件並設定 PDF 選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 步驟 10：將文件渲染為 PDF
```csharp
viewer.View(options);
```

## 結論
恭喜！您已成功學習如何使用 GroupDocs.Viewer for .NET 渲染 MS Project 文件並調整時間單位。請將這些知識運用到您的專案中，以增強文件檢視功能。
## 常見問題解答
### 我可以將 MS Project 文件渲染為 HTML、圖像和 PDF 以外的其他格式嗎？
是的，GroupDocs.Viewer for .NET 支援渲染為各種格式，例如 DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer for .NET 有試用版嗎？
是的，你可以從 [這裡](https://releases。groupdocs.com/).
### 如何取得 GroupDocs.Viewer for .NET 的臨時許可？
訪問 [此連結](https://purchase.groupdocs.com/temporary-license/) 取得臨時執照。
### 在哪裡可以找到 GroupDocs.Viewer for .NET 的文檔？
請參閱文檔 [這裡](https://tutorials。groupdocs.com/viewer/net/).
### 我可以在哪裡尋求支援或詢問與 GroupDocs.Viewer for .NET 相關的問題？
您可以造訪支援論壇 [這裡](https://forum。groupdocs.com/c/viewer/9).