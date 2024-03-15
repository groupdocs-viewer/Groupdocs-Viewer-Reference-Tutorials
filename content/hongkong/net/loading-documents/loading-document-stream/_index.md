---
title: 從串流載入文檔
linktitle: 從串流載入文檔
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 從流程無縫載入文件。透過強大的文件檢視功能增強您的 .NET 應用程式。
type: docs
weight: 12
url: /zh-hant/net/loading-documents/loading-document-stream/
---
## 介紹
在 .NET 開發領域，有效管理和檢視文件至關重要。隨著高階工具和函式庫的出現，曾經看似艱鉅的任務現在變得簡單了。在這些工具中，GroupDocs.Viewer for .NET 作為無縫處理各種文件格式的多功能解決方案脫穎而出。在本綜合指南中，我們深入研究了使用 GroupDocs.Viewer for .NET 從流程載入文件的複雜性。無論您是經驗豐富的開發人員還是新手，本教學都將為您提供有效利用 GroupDocs.Viewer 功能的知識。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. 對 C# 和 .NET 框架的基本了解：熟悉 C# 程式語言和 .NET 框架將有助於理解所討論的概念。
   
2. 安裝 GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET[網站](https://releases.groupdocs.com/viewer/net/).
3. IDE：安裝 Visual Studio 等整合開發環境 (IDE)，用於編碼和測試。
4. 文檔流程：準備要載入的文檔流程。這可以是文件流或任何其他相容的流源。

## 導入命名空間
在實作從流程載入文件的程式碼之前，請確保匯入必要的命名空間：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
設定保存渲染文檔的目錄路徑。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
定義每個頁面的文件路徑的格式。此處，「{0}」將替換為頁碼。
## 步驟3：取得文檔流
```csharp
Stream stream = GetFileStream();
```
從所需來源取得文檔流。這可以是檔案流、記憶體流或任何其他相容的流。
## 步驟 4：使用檢視器載入文檔
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
使用文檔流初始化 Viewer 類別的新實例。然後，配置 HTML 視圖選項並呈現文件。
## 步驟5：顯示輸出目錄
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
通知使用者文件已成功渲染並提供保存輸出的位置。

## 結論
總而言之，GroupDocs.Viewer for .NET 提供了一個強大的解決方案，可以輕鬆地從流中載入和查看文件。透過遵循本教學中概述的步驟，您可以將文件檢視功能無縫整合到 .NET 應用程式中，從而增強使用者體驗和工作效率。
## 常見問題解答
### GroupDocs.Viewer for .NET 可以處理不同的文件格式嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer for .NET 是否同時適用於 Web 和桌面應用程式？
絕對地！ GroupDocs.Viewer 可以無縫整合到使用 .NET 開發的 Web 和桌面應用程式中。
### GroupDocs.Viewer 是否提供文件呈現的自訂選項？
是的，您可以根據您的要求自訂文件呈現的各個方面，例如浮水印、頁面旋轉和縮放等級。
### 我可以在商業專案中使用 GroupDocs.Viewer for .NET 嗎？
是的，GroupDocs.Viewer 提供適合商業專案的授權選項。您可以從官方購買許可證[網站](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET 是否提供技術支援？
是的，您可以從以下公司提供的專門支援論壇尋求技術協助和指導：[群組文檔檢視器](https://forum.groupdocs.com/c/viewer/9).