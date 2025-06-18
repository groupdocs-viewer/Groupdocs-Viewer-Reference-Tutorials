---
"description": "了解如何使用 Groupdocs.Viewer for .NET 從本機磁碟無縫渲染文件。使用高效的文件功能增強您的 .NET 應用程式。"
"linktitle": "從本機磁碟載入文檔"
"second_title": "GroupDocs.Viewer .NET API"
"title": "從本機磁碟載入文檔"
"url": "/zh-hant/net/loading-documents/loading-document-local-disk/"
"weight": 10
---

# 從本機磁碟載入文檔

## 介紹
在當今的數位時代，高效的文件渲染對於各種應用程式至關重要。 Groupdocs.Viewer for .NET 提供了一個強大的解決方案，可直接從本機磁碟渲染文件。在本教學中，我們將指導您使用 Groupdocs.Viewer for .NET 從本機磁碟載入文件的過程。無論您是經驗豐富的開發人員還是剛剛入門，本逐步指南都將幫助您將文件渲染無縫整合到您的 .NET 應用程式中。

![使用 GroupDocs.Viewer .NET 從本機磁碟載入文檔](/viewer/loading-documents/load-documents-from-local-disk.png)

## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
1. Groupdocs.Viewer for .NET：從下載並安裝最新版本 [這裡](https://releases。groupdocs.com/viewer/net/).
2. .NET 開發環境：確保您的系統上已設定可用的 .NET 開發環境。
3. 本機文件：將您想要渲染的文件儲存在本機磁碟上。

## 導入命名空間
首先，讓我們匯入必要的命名空間來存取 .NET 的 Groupdocs.Viewer 的功能。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟 1：從本機磁碟載入文檔
首先設定將保存呈現的 HTML 頁面的輸出目錄。
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 2 步：初始化檢視器並渲染文檔
使用文件的路徑初始化檢視器物件並使用 HTML 視圖選項呈現它。
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 步驟3：顯示輸出
一旦渲染完成，將顯示一則訊息，表示來源文件渲染成功以及輸出檔案的位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
恭喜！您已成功學習如何使用 Groupdocs.Viewer for .NET 從本機磁碟載入文件。這款強大的工具為您的 .NET 應用程式的文件渲染開啟了無限可能。
## 常見問題解答
### 我可以使用 Groupdocs.Viewer for .NET 呈現不同格式的文件嗎？
是的，Groupdocs.Viewer for .NET 支援多種文件格式，包括 DOCX、PDF、XLSX、PPTX 等。
### Groupdocs.Viewer for .NET 是否與所有 .NET 框架相容？
Groupdocs.Viewer for .NET 與大多數 .NET 框架相容，包括 .NET Core、.NET Framework 和 .NET Standard。
### 我可以自訂文件的渲染選項嗎？
當然！ Groupdocs.Viewer for .NET 提供了豐富的自訂選項，讓您可以根據特定需求自訂渲染流程。
### Groupdocs.Viewer for .NET 有試用版嗎？
是的，您可以從下載免費試用版 [這裡](https://releases。groupdocs.com/).
### 在哪裡可以找到 Groupdocs.Viewer for .NET 的支援或其他資源？
如需支援和其他資源，請造訪 Groupdocs.Viewer for .NET [論壇](https://forum。groupdocs.com/c/viewer/9).