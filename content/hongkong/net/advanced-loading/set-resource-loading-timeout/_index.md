---
"description": "了解如何在 GroupDocs.Viewer for .NET 中有效地配置資源載入逾時。掌握精準穩定的文件渲染。"
"linktitle": "設定資源載入超時（進階）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "設定資源載入超時（進階）"
"url": "/zh-hant/net/advanced-loading/set-resource-loading-timeout/"
"weight": 13
---

# 設定資源載入超時（進階）

## 介紹
在 .NET 開發領域，GroupDocs.Viewer 提供了一套強大的工具集，可以精確且有效率地渲染文件和影像。要充分利用其功能，需要了解其複雜性，包括設定資源載入逾時。在本教學中，我們將深入探討如何在 GroupDocs.Viewer for .NET 中設定資源載入逾時。

![在 GroupDocs.Viewer for .NET 中設定資源載入逾時（進階）](/viewer/advanced-loading/set-resource-loading-timeout-img.png)

## 先決條件
在開始本教學之前，請確保您符合以下先決條件：
1. .NET 開發基礎知識：熟悉 C# 程式設計和 .NET 框架基礎至關重要。
2. 安裝 GroupDocs.Viewer for .NET：從下載並安裝 GroupDocs.Viewer for .NET 程式庫 [下載頁面](https://releases。groupdocs.com/viewer/net/).
3. 整合開發環境 (IDE)：在您的系統上安裝一個 IDE，例如 Visual Studio。

## 導入命名空間
在深入編碼過程之前，請先匯入必要的命名空間：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 步驟 1：定義輸出目錄
首先，定義渲染文檔的保存目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
代替 `"Your Document Directory"` 與您想要儲存渲染文檔的路徑。
## 步驟2：定義頁面檔案路徑格式
定義各頁面的文件路徑的格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
此格式將產生以下檔案名 `page_1.html`， `page_2.html`等，在指定的輸出目錄內。
## 步驟 3：配置載入選項
配置載入選項，包括資源載入逾時：
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
本例設定資源載入的超時時間為5秒。
## 步驟4：初始化檢視器對象
初始化 `Viewer` 具有要呈現的文檔和定義的載入選項的物件：
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
代替 `TestFiles.WITH_EXTERNAL_IMAGE_DOC` 使用您想要呈現的文檔的路徑。
## 步驟 5：配置 HTML 視圖選項
配置嵌入資源的 HTML 視圖選項：
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
此配置可確保嵌入的資源（如圖片）包含在呈現的 HTML 中。
## 步驟 6：渲染文檔
使用配置的選項呈現文件：
```csharp
viewer.View(options);
```
此步驟啟動渲染程序。
## 步驟 7：顯示輸出目錄
顯示表示渲染成功的訊息和輸出目錄的位置：
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
掌握 GroupDocs.Viewer for .NET 中的資源載入逾時對於確保文件渲染過程的流暢性至關重要。透過學習本教學課程，您將了解如何有效地配置逾時，從而提升您的 .NET 開發能力。
## 常見問題解答
### 設定資源載入超時有什麼意義？
設定資源載入逾時可確保渲染過程不會無限期掛起，進而增強應用程式的穩定性。
### 可以根據文檔類型自訂資源載入逾時嗎？
是的，可以根據所呈現文件的複雜性和大小來調整資源載入逾時。
### 設定較短的超時時間會對效能產生什麼影響嗎？
如果無法在指定時間內載入資源，較短的逾時可能會導致複雜文件的渲染不完整。
### GroupDocs.Viewer 是否適合呈現各種文件格式？
是的，GroupDocs.Viewer 支援呈現多種文件格式，包括 PDF、DOCX、XLSX 等。
### 可以停用資源載入超時嗎？
雖然不建議這樣做，但可以根據具體要求將資源載入逾時設定為較高值或完全停用。