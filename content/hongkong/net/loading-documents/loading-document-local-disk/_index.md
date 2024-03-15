---
title: 從本機磁碟載入文檔
linktitle: 從本機磁碟載入文檔
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 Groupdocs.Viewer for .NET 從本機磁碟無縫呈現文件。使用高效的文件增強您的 .NET 應用程式。
type: docs
weight: 10
url: /zh-hant/net/loading-documents/loading-document-local-disk/
---
## 介紹
在當今的數位時代，高效的文件渲染對於各種應用程式至關重要。 Groupdocs.Viewer for .NET 提供了一個強大的解決方案，可以直接從本機磁碟呈現文件。在本教學中，我們將引導您完成使用 Groupdocs.Viewer for .NET 從本機磁碟載入文件的過程。無論您是經驗豐富的開發人員還是新手，本逐步指南都將幫助您將文件呈現無縫整合到 .NET 應用程式中。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  Groupdocs.Viewer for .NET：從下列位置下載並安裝最新版本[這裡](https://releases.groupdocs.com/viewer/net/).
2. .NET 開發環境：確保您的系統上設定了有效的 .NET 開發環境。
3. 本機文件：將要渲染的文件儲存在本機磁碟上。

## 導入命名空間
首先，讓我們匯入必要的命名空間來存取 Groupdocs.Viewer for .NET 的功能。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟一：從本機磁碟載入文檔
首先設定將保存渲染的 HTML 頁面的輸出目錄。
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 2 步：初始化檢視器並渲染文檔
使用文件的路徑初始化 Viewer 對象，並使用 HTML 視圖選項呈現它。
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 3 步：顯示輸出
渲染完成後，將顯示一則訊息，指示來源文件的渲染成功以及輸出檔案的位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
恭喜！您已成功學習如何使用 Groupdocs.Viewer for .NET 從本機磁碟載入文件。這個強大的工具為您的 .NET 應用程式中的文件渲染開啟了無限可能。
## 常見問題解答
### 我可以使用 Groupdocs.Viewer for .NET 呈現不同格式的文件嗎？
是的，Groupdocs.Viewer for .NET 支援多種文件格式，包括 DOCX、PDF、XLSX、PPTX 等。
### Groupdocs.Viewer for .NET 是否與所有 .NET 框架相容？
Groupdocs.Viewer for .NET 與大多數 .NET 框架相容，包括 .NET Core、.NET Framework 和 .NET Standard。
### 我可以自訂文件的渲染選項嗎？
絕對地！ Groupdocs.Viewer for .NET 提供了廣泛的自訂選項，可讓您根據您的特定要求自訂渲染流程。
### Groupdocs.Viewer for .NET 是否有試用版？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.groupdocs.com/).
### 在哪裡可以找到 Groupdocs.Viewer for .NET 的支援或其他資源？
如需支援和其他資源，請造訪 Groupdocs.Viewer for .NET[論壇](https://forum.groupdocs.com/c/viewer/9).