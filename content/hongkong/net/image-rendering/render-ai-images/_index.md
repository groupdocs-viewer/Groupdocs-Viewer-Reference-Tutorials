---
title: 渲染 AI 影像
linktitle: 渲染 AI 影像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 在 .NET 應用程式中輕鬆渲染 AI 影像。請按照我們的逐步教學進行無縫整合。
weight: 10
url: /zh-hant/net/image-rendering/render-ai-images/
---

# 渲染 AI 影像

## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中輕鬆呈現各種文件格式。無論您需要顯示 AI 影像、PDF 或其他文件類型，GroupDocs.Viewer 都能簡化流程，提供多種輸出格式，以便無縫整合到您的專案中。本教學將引導您使用 GroupDocs.Viewer for .NET 逐步渲染 AI 影像。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Visual Studio：在您的系統上安裝 Visual Studio IDE。
2.  GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET[網站](https://releases.groupdocs.com/viewer/net/).
3. C# 基礎知識：需要熟悉 C# 程式語言才能理解程式碼範例。

## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以存取 GroupDocs.Viewer for .NET 的功能。

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

使用 GroupDocs.Viewer for .NET 渲染 AI 影像涉及多個步驟，每個步驟都適合特定的輸出格式。為了清楚起見，下面我們將把這個過程分解為單獨的步驟。
## 第 1 步：指定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
## 第 2 步：渲染為 HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 3 步：渲染為 JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 4 步：渲染為 PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 5 步：渲染為 PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 結論
GroupDocs.Viewer for .NET 提供了一個無縫解決方案，用於在 .NET 應用程式中渲染 AI 映像和各種文件格式。透過遵循本教學中提供的逐步指南，開發人員可以輕鬆地將文件渲染功能整合到他們的專案中。
## 常見問題解答
### 渲染 AI 影像時可以自訂輸出外觀嗎？
是的，GroupDocs.Viewer for .NET 提供了自訂輸出外觀的各種選項，包括頁面大小、影像品質等。
### 是否有可用於測試目的的試用版？
是的，您可以從 GroupDocs 下載免費試用版[網站](https://releases.groupdocs.com/viewer/net/)在購買之前評估圖書館的功能。
### GroupDocs.Viewer是否支援渲染加密的AI影像？
是的，GroupDocs.Viewer for .NET 支援使用提供的適當解密金鑰渲染加密的 AI 影像。
### 我可以直接從 URL 渲染 AI 圖像嗎？
是的，GroupDocs.Viewer for .NET 允許透過指定 URL 路徑而不是本機檔案路徑來從 URL 渲染 AI 影像。
### GroupDocs.Viewer for .NET 是否提供技術支援？
是的，可以透過 GroupDocs 獲得技術支持[論壇](https://forum.groupdocs.com/c/viewer/9)，您可以在其中提問、報告問題以及尋求社區幫助。