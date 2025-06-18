---
"description": "了解如何使用 Groupdocs.Viewer for .NET 將特定 CAD 格式（如 CF2）呈現為 HTML、JPG、PNG 和 PDF。"
"linktitle": "渲染特定 CAD 格式 (CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染特定 CAD 格式 (CF2)"
"url": "/zh-hant/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# 渲染特定 CAD 格式 (CF2)

## 介紹
在本教學中，我們將探索如何使用 Groupdocs.Viewer for .NET 渲染特定的 CAD 格式。 Groupdocs.Viewer 是一個強大的文件檢視器 API，可讓開發人員在其應用程式中顯示超過 170 種文件類型，而無需安裝任何外部軟體。具體來說，我們將重點介紹如何將 CAD 格式（例如 CF2）渲染為各種輸出格式，例如 HTML、JPG、PNG 和 PDF。
## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
- 您的系統上安裝了 Visual Studio。
- Groupdocs.Viewer for .NET SDK。您可以從 [這裡](https://releases。groupdocs.com/viewer/net/).
- C# 程式語言的基本知識。
## 導入命名空間
首先，讓我們匯入渲染 CAD 格式所需的必要命名空間。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
現在，讓我們將每個範例分解為多個步驟：
## 將 CF2 渲染為 HTML
### 步驟 1：定義將儲存渲染的 HTML 的輸出目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
### 第 2 步：定義 HTML 輸出的檔案路徑格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### 步驟3：初始化Viewer物件並指定輸入的CF2檔案。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // 如果需要，設定其他渲染選項
    // 選項.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## 將 CF2 渲染為 JPG
### 步驟 1：定義 JPG 輸出的檔案路徑格式。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### 步驟2：初始化Viewer物件並指定輸入的CF2檔案。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // 如果需要，設定其他渲染選項
    // 選項.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## 將 CF2 渲染為 PNG

### 步驟 1：定義 PNG 輸出的檔案路徑格式。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### 步驟2：初始化Viewer物件並指定輸入的CF2檔案。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // 如果需要，設定其他渲染選項
    // 選項.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## 將 CF2 渲染為 PDF
### 步驟 1：定義 PDF 輸出的文件路徑格式。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### 步驟2：初始化Viewer物件並指定輸入的CF2檔案。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // 如果需要，設定其他渲染選項
    // 選項.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## 結論
在本教學中，我們學習如何使用 Groupdocs.Viewer for .NET 渲染特定的 CAD 格式（例如 CF2）。按照逐步指南操作，您可以輕鬆地將文件渲染功能整合到您的 .NET 應用程式中。
## 常見問題解答
### Groupdocs.Viewer 除了 CF2 之外還能渲染其他 CAD 格式嗎？
是的，Groupdocs.Viewer 支援多種 CAD 格式，包括 DWG、DXF、DGN 等。
### Groupdocs.Viewer 是否適合在 Web 應用程式中呈現文件？
當然，Groupdocs.Viewer 可以無縫整合到 Web 應用程式中，以便直接在瀏覽器中呈現文件。
### Groupdocs.Viewer 是否需要任何外部相依性來進行渲染？
不，Groupdocs.Viewer 是一個獨立的 API，不需要任何外部依賴或軟體安裝。
### 我可以根據自己的要求自訂渲染選項嗎？
是的，Groupdocs.Viewer 提供了各種可自訂的渲染選項來滿足您的特定需求。
### Groupdocs.Viewer 有試用版嗎？
是的，您可以從以下網址取得 Groupdocs.Viewer 的免費試用版 [這裡](https://releases。groupdocs.com/).