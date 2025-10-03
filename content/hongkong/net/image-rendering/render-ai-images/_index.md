---
"description": "了解如何使用 GroupDocs.Viewer for .NET 在 .NET 應用程式中輕鬆渲染 AI 影像。按照我們的逐步教程，實現無縫整合。"
"linktitle": "渲染 AI 影像"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 AI 影像"
"url": "/zh-hant/net/image-rendering/render-ai-images/"
"weight": 10
type: docs
---
# 渲染 AI 影像

## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的程式庫，使開發人員能夠輕鬆地在其 .NET 應用程式中渲染各種文件格式。無論您需要顯示 AI 影像、PDF 或其他文件類型，GroupDocs.Viewer 都能簡化流程，提供多種輸出格式，以便無縫整合到您的專案中。本教學將引導您使用 GroupDocs.Viewer for .NET 逐步渲染 AI 影像。

![使用 GroupDocs.Viewer for .NET 渲染 AI 影像](/viewer/image-rendering/render-ai-images.png)

## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
1. Visual Studio：在您的系統上安裝 Visual Studio IDE。
2. GroupDocs.Viewer for .NET：從 [網站](https://releases。groupdocs.com/viewer/net/).
3. C# 基礎知識：需要熟悉 C# 程式語言才能理解程式碼範例。

## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以存取 .NET 的 GroupDocs.Viewer 的功能。

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

使用 GroupDocs.Viewer for .NET 渲染 AI 影像涉及多個步驟，每個步驟都對應特定的輸出格式。為了清晰起見，我們將該過程分解為各個步驟。
## 步驟 1：指定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟 2：渲染為 HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 步驟3：渲染為JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 步驟4：渲染為PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 步驟5：渲染為PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 結論
GroupDocs.Viewer for .NET 提供了一個無縫的解決方案，用於在 .NET 應用程式中渲染 AI 映像和各種文件格式。透過遵循本教學提供的逐步指南，開發人員可以輕鬆地將文件渲染功能整合到他們的專案中。
## 常見問題解答
### 渲染 AI 影像時我可以自訂輸出外觀嗎？
是的，GroupDocs.Viewer for .NET 提供了各種自訂輸出外觀的選項，包括頁面大小、影像品質等。
### 是否有可供測試的試用版？
是的，您可以從 GroupDocs 下載免費試用版 [網站](https://releases.groupdocs.com/viewer/net/) 在購買之前評估圖書館的功能。
### GroupDocs.Viewer 是否支援渲染加密的 AI 影像？
是的，GroupDocs.Viewer for .NET 支援使用提供的適當解密金鑰渲染加密的 AI 影像。
### 我可以直接從 URL 渲染 AI 圖像嗎？
是的，GroupDocs.Viewer for .NET 允許透過指定 URL 路徑而不是本機檔案路徑來從 URL 呈現 AI 影像。
### GroupDocs.Viewer for .NET 是否提供技術支援？
是的，可以透過 GroupDocs 獲得技術支持 [論壇](https://forum.groupdocs.com/c/viewer/9)，您可以在這裡提問、報告問題並尋求社區的幫助。