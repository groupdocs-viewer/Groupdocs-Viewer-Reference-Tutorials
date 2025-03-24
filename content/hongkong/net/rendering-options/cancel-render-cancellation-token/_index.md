---
title: 使用取消令牌取消渲染
linktitle: 使用取消令牌取消渲染
second_title: GroupDocs.Viewer .NET API
description: 將 Groupdocs.Viewer for .NET 無縫整合到您的 .NET 專案中，以實現高效的文件檢視。
weight: 11
url: /zh-hant/net/rendering-options/cancel-render-cancellation-token/
---

# 使用取消令牌取消渲染

## 介紹
Groupdocs.Viewer for .NET 是一款功能強大的工具，旨在簡化 .NET 應用程式中的文件檢視和處理。無論您處理的是 PDF、Microsoft Office 文件還是其他常見格式，該程式庫都提供了強大的功能，可將文件檢視功能無縫整合到您的 .NET 專案中。
## 先決條件
在深入研究 Groupdocs.Viewer for .NET 的整合之前，請確保滿足以下先決條件：
1. 安裝：從提供的下載並安裝 Groupdocs.Viewer for .NET 函式庫[下載連結](https://releases.groupdocs.com/viewer/net/).
   
2. 許可證： 取得許可證[群組文件](https://purchase.groupdocs.com/buy)釋放圖書館的全部潛能。或者，您可以使用以下方式開始免費試用：[臨時執照](https://purchase.groupdocs.com/temporary-license/).
   
3. 開發環境：確保您設定了相容的開發環境，包括 Visual Studio 或您選擇的任何其他 .NET IDE。

## 導入命名空間
為了有效地利用 Groupdocs.Viewer for .NET，您需要將必要的命名空間匯入到您的專案中。按著這些次序：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

現在，讓我們將提供的範例分解為多個步驟，以便更好地理解和實現：
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
此步驟設定將儲存渲染的文件頁面的目錄。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
在這裡，我們定義各個文件頁面的文件路徑的格式。
## 步驟3：初始化CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource 用於產生可用於取消非同步操作的 CancellationToken 實例。
## 第四步：取得CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
此步驟從 CancellationTokenSource 檢索令牌，該令牌將用於取消渲染操作。
## 第 5 步：渲染文檔頁面
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
在這裡，我們使用 Task.Run() 非同步啟動文件頁面的渲染。 Viewer 實例是使用指定的文件檔案 (SAMPLE_DOCX) 建立的，並配置了呈現選項。然後使用 Viewer 類別的 View 方法開始渲染過程。
## 第 6 步：設定渲染超時
```csharp
cancellationTokenSource.CancelAfter(10);
```
此步驟為渲染操作設定 10 毫秒的逾時。如果操作超過這個逾時時間，就會自動取消。
## 步驟7：顯示成功訊息
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後，會顯示成功訊息，表示文件已成功呈現。

## 結論
在本教程中，我們介紹了將 Groupdocs.Viewer for .NET 整合到專案中的基礎知識。透過執行上述步驟，您可以將文件檢視功能無縫合併到 .NET 應用程式中，從而增強使用者體驗和工作效率。
## 常見問題解答
### Groupdocs.Viewer for .NET 是否與所有文件格式相容？
Groupdocs.Viewer for .NET 支援多種文件格式，包括 PDF、Microsoft Office 文件、影像等。
### 我可以自訂渲染文件頁面的外觀嗎？
是的，您可以自訂渲染過程的各個方面，包括頁面大小、品質、浮水印等等。
### Groupdocs.Viewer for .NET 是否需要網路連線？
不需要，Groupdocs.Viewer for .NET 在您的 .NET 環境中本地運行，並且不需要 Internet 連接即可查看文件。
### Groupdocs.Viewer for .NET 是否提供技術支援？
是的，可以透過以下方式獲得技術支持[群組文檔論壇](https://forum.groupdocs.com/c/viewer/9)，您可以在其中提問、報告問題以及與社區互動。
### 我可以在購買前試用 Groupdocs.Viewer for .NET 嗎？
是的，您可以使用提供的免費試用版開始[試用版](https://releases.groupdocs.com/).