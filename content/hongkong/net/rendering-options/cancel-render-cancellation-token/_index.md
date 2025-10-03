---
"description": "將 Groupdocs.Viewer for .NET 無縫整合到您的 .NET 專案中，以實現高效的文件檢視。"
"linktitle": "使用取消令牌取消渲染"
"second_title": "GroupDocs.Viewer .NET API"
"title": "使用取消令牌取消渲染"
"url": "/zh-hant/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# 使用取消令牌取消渲染

## 介紹
Groupdocs.Viewer for .NET 是一款功能強大的工具，旨在簡化 .NET 應用程式中的文件檢視和處理。無論您處理的是 PDF、Microsoft Office 文件或其他常見格式，此程式庫都能提供強大的功能，將文件檢視功能無縫整合到您的 .NET 專案中。
## 先決條件
在深入研究 Groupdocs.Viewer for .NET 的整合之前，請確保您已滿足以下先決條件：
1. 安裝：從提供的下載並安裝 Groupdocs.Viewer for .NET 函式庫 [下載連結](https://releases。groupdocs.com/viewer/net/).
   
2. 許可證：從 [群組文檔](https://purchase.groupdocs.com/buy) 充分發揮圖書館的潛能。或者，您也可以使用 [臨時執照](https://purchase。groupdocs.com/temporary-license/).
   
3. 開發環境：確保您已設定相容的開發環境，包括 Visual Studio 或您選擇的任何其他 .NET IDE。

## 導入命名空間
為了有效地利用 Groupdocs.Viewer for .NET，您需要將必要的命名空間匯入到您的專案中。請依照以下步驟操作：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

現在，讓我們將提供的範例分解為多個步驟，以便更好地理解和實施：
## 步驟 1：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
此步驟設定儲存渲染的文件頁面的目錄。
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
## 步驟4：取得CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
此步驟從 CancellationTokenSource 中檢索令牌，該令牌將用於取消渲染操作。
## 步驟5：渲染文件頁面
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
這裡，我們使用 Task.Run() 非同步啟動文件頁面的渲染。使用指定的文件檔案 (SAMPLE_DOCX) 建立 Viewer 實例，並配置渲染選項。然後使用 Viewer 類別的 View 方法啟動渲染過程。
## 步驟 6：設定渲染超時
```csharp
cancellationTokenSource.CancelAfter(10);
```
此步驟為渲染操作設定 10 毫秒的逾時時間。如果操作超過此逾時時間，則會自動取消。
## 步驟 7：顯示成功訊息
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後，顯示成功訊息，表示文件已成功呈現。

## 結論
在本教程中，我們介紹了將 Groupdocs.Viewer for .NET 整合到專案中的基礎知識。請依照上述步驟，您可以將文件檢視功能無縫整合到 .NET 應用程式中，從而提升使用者體驗和工作效率。
## 常見問題解答
### Groupdocs.Viewer for .NET 是否相容於所有文件格式？
Groupdocs.Viewer for .NET 支援多種文件格式，包括 PDF、Microsoft Office 文件、影像等。
### 我可以自訂呈現的文件頁面的外觀嗎？
是的，您可以自訂渲染過程的各個方面，包括頁面大小、品質、浮水印等。
### Groupdocs.Viewer for .NET 是否需要網路連線？
否，Groupdocs.Viewer for .NET 在您的 .NET 環境中本機運行，不需要網路連線即可查看文件。
### Groupdocs.Viewer for .NET 是否提供技術支援？
是的，可以透過以下方式獲得技術支持 [Groupdocs 論壇](https://forum.groupdocs.com/c/viewer/9)，您可以在此提問、回報問題並與社群互動。
### 我可以在購買之前試用 Groupdocs.Viewer for .NET 嗎？
是的，你可以使用提供的免費試用版開始試用 [試用版](https://releases。groupdocs.com/).