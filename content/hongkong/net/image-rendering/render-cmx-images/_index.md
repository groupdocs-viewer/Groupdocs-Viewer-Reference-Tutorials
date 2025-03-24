---
title: 渲染 CMX 影像
linktitle: 渲染 CMX 影像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 輕鬆將 CMX 影像渲染為各種格式。增強您的文件管理。
weight: 13
url: /zh-hant/net/image-rendering/render-cmx-images/
---

# 渲染 CMX 影像

## 介紹
在文件管理和操作領域，渲染各種格式的圖像是一項關鍵任務。 GroupDocs.Viewer for .NET 透過提供將 CMX 圖像渲染為不同格式（例如 HTML、JPG、PNG 和 PDF）的全面功能，簡化了此過程。本教學將引導您完成使用 GroupDocs.Viewer for .NET 渲染 CMX 影像的逐步流程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  GroupDocs.Viewer for .NET 函式庫：從下列位置下載並安裝 GroupDocs.Viewer for .NET 函式庫[這裡](https://releases.groupdocs.com/viewer/net/).
2. 開發環境：擁有一個使用.NET框架設定的工作開發環境。
3. CMX 圖像檔案：取得您想要渲染的 CMX 圖像檔案。

## 導入命名空間
在繼續之前，請確保匯入必要的命名空間以存取 .NET 應用程式中的 GroupDocs.Viewer 功能：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## 渲染為 HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- 定義輸出目錄：設定要儲存渲染的 HTML 檔案的目錄。
- 指定文件路徑格式：定義輸出 HTML 文件的格式。
- 實例化 Viewer 物件：使用 CMX 映像檔建立 Viewer 類別的實例。
- HTML 呈現選項：設定 HTML 呈現選項，例如嵌入資源。
- 將 CMX 渲染為 HTML：呼叫檢視器物件的 View 方法將 CMX 影像渲染為 HTML。
## 渲染為 JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- 定義輸出目錄：設定儲存渲染的 JPG 檔案的目錄。
- 指定檔案路徑格式：定義輸出 JPG 檔案的格式。
- 實例化 Viewer 物件：使用 CMX 映像檔建立 Viewer 類別的實例。
- JPG 渲染選項：配置 JPG 渲染選項。
- 將 CMX 渲染為 JPG：呼叫檢視器物件的 View 方法將 CMX 影像渲染為 JPG。
## 渲染為 PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 定義輸出目錄：設定用於儲存渲染的 PNG 檔案的目錄。
- 指定檔案路徑格式：定義輸出 PNG 檔案的格式。
- 實例化 Viewer 物件：使用 CMX 映像檔建立 Viewer 類別的實例。
- PNG 渲染選項：配置 PNG 渲染選項。
- 將 CMX 渲染為 PNG：呼叫檢視器物件的 View 方法將 CMX 影像渲染為 PNG。
## 渲染為 PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 定義輸出目錄：設定用於儲存渲染的 PDF 檔案的目錄。
- 指定文件路徑格式：定義輸出 PDF 檔案的格式。
- 實例化 Viewer 物件：使用 CMX 映像檔建立 Viewer 類別的實例。
- PDF 渲染選項：配置 PDF 渲染選項。
- 將 CMX 渲染為 PDF：呼叫檢視器物件的 View 方法將 CMX 影像渲染為 PDF。

## 結論
總之，GroupDocs.Viewer for .NET 提供了一個強大的解決方案，可以將 CMX 影像無縫呈現為各種格式。透過遵循本教學中概述的步驟，您可以輕鬆地將 CMX 影像渲染功能整合到您的 .NET 應用程式中，從而提高文件管理效率。
## 常見問題解答
### 我可以渲染 CMX 圖像的特定頁面嗎？
是的，您可以透過在渲染選項中指定頁碼來渲染特定頁面。
### GroupDocs.Viewer for .NET 是否與所有 .NET 框架相容？
是的，GroupDocs.Viewer for .NET 與多個 .NET 框架相容，包括 .NET Core 和 .NET Framework。
### GroupDocs.Viewer 是否支援渲染加密的 CMX 影像？
是的，GroupDocs.Viewer 支援使用適當的解密金鑰渲染加密的 CMX 影像。
### 我可以為不同的輸出格式自訂渲染選項嗎？
當然，GroupDocs.Viewer 提供了廣泛的選項，可根據您的要求自訂渲染參數。
### 是否有提供 GroupDocs.Viewer 支援的社群論壇？
是的，您可以在支援論壇上尋求協助並與 GroupDocs.Viewer 社群互動[這裡](https://forum.groupdocs.com/c/viewer/9).