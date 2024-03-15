---
title: 載入受密碼保護的文檔
linktitle: 載入受密碼保護的文檔
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 輕鬆地將受密碼保護的文件檢視整合到 .NET 應用程式中。按照我們的逐步教學進行無縫操作。
type: docs
weight: 12
url: /zh-hant/net/advanced-loading/load-password-protected-document/
---
## 介紹
在當今的數位時代，無縫管理和查看各種文件格式對於許多企業和個人來說都是必需的。幸運的是，GroupDocs.Viewer for .NET 為 .NET 開發人員提供了全面的解決方案，可以輕鬆地將文件檢視功能整合到他們的應用程式中。在本教學中，我們將深入研究 GroupDocs.Viewer 的基本功能之一：載入受密碼保護的文件。我們將逐步分解該過程，確保開發人員可以輕鬆遵循並將此功能實現到他們的專案中。
## 先決條件
在我們深入學習本教學之前，請確保您已設定以下先決條件：
### 1. 安裝適用於.NET的GroupDocs.Viewer
確保您的開發環境中安裝了 GroupDocs.Viewer for .NET。您可以從[網站](https://releases.groupdocs.com/viewer/net/).
### 2. 取得受密碼保護的文檔
出於測試目的，請準備一份受密碼保護的文件。這將使我們能夠有效地演示加載過程。

## 導入命名空間
在繼續本教學之前，讓我們將必要的命名空間匯入到我們的專案中：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 第 1 步：定義輸出目錄
首先，指定要儲存渲染輸出的目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`與您所需目錄的路徑。
## 步驟2：定義頁面檔案路徑格式
接下來，定義每個渲染頁面的檔案路徑的格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
這種格式將產生檔案路徑，例如`"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`， 等等。
## 步驟 3：配置載入選項
配置受密碼保護文件的載入選項，包括密碼：
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
代替`"12345"`使用您文件的實際密碼。
## 第 4 步：初始化檢視器
使用文件和載入選項初始化 GroupDocs.Viewer：
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    //用於查看選項的程式碼將在下一步中新增。
}
```
代替`"Path_to_your_document"`以及受密碼保護的文件的路徑。
## 步驟 5：配置 HTML 視圖選項
配置 HTML 視圖選項以呈現具有嵌入資源的文件：
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 第 6 步：渲染文檔
使用配置的檢視器和視圖選項渲染文件：
```csharp
viewer.View(options);
```
## 步驟7：顯示成功訊息
通知使用者文件已成功呈現：
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
在本教學中，我們探討如何使用 GroupDocs.Viewer for .NET 載入受密碼保護的文件。透過遵循逐步指南，開發人員可以將此功能無縫整合到他們的 .NET 應用程式中，使用戶能夠輕鬆查看受保護的文件。
## 常見問題解答
### 除了受密碼保護的文件之外，GroupDocs.Viewer 還可以處理其他文件格式嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer 與 .NET Core 相容嗎？
是的，GroupDocs.Viewer 提供與 .NET Framework 和 .NET Core 環境的兼容性。
### 我可以自訂文件的渲染選項嗎？
絕對地！ GroupDocs.Viewer提供了各種渲染選項，讓開發人員可以根據自己的要求自訂查看體驗。
### GroupDocs.Viewer是否支援文件註解？
是的，GroupDocs.Viewer 支援文件註釋，使用戶能夠為文件添加註釋、突出顯示和其他註釋。
### GroupDocs.Viewer 是否有試用版？
是的，您可以從 GroupDocs.Viewer 取得免費試用版[網站](https://releases.groupdocs.com/).