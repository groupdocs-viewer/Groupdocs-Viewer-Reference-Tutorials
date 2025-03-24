---
title: 設定資源載入超時（進階）
linktitle: 設定資源載入超時（進階）
second_title: GroupDocs.Viewer .NET API
description: 了解如何在 GroupDocs.Viewer for .NET 中有效地配置資源載入逾時。精準穩定地掌握文件渲染。
weight: 13
url: /zh-hant/net/advanced-loading/set-resource-loading-timeout/
---
## 介紹
在 .NET 開發領域，GroupDocs.Viewer 提供了強大的工具集，可以精確、有效率地呈現文件和影像。利用其功能需要了解其複雜性，包括設定資源載入逾時。在本教程中，我們將深入研究在 GroupDocs.Viewer for .NET 中配置資源載入逾時的過程。
## 先決條件
在開始本教學之前，請確保您具備以下先決條件：
1. .NET 開發的基本知識：熟悉 C# 程式設計和 .NET 框架基礎至關重要。
2. 安裝 GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET 程式庫[下載頁面](https://releases.groupdocs.com/viewer/net/).
3. 整合開發環境 (IDE)：在系統上安裝 IDE，例如 Visual Studio。

## 導入命名空間
在深入編碼過程之前，先導入必要的命名空間：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 第 1 步：定義輸出目錄
首先，定義渲染文檔的保存目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`以及要儲存渲染文檔的路徑。
## 步驟2：定義頁面檔案路徑格式
定義各頁面的文件路徑的格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
這種格式將產生以下檔案名`page_1.html`, `page_2.html`等，在指定的輸出目錄中。
## 步驟 3：配置載入選項
配置載入選項，包括資源載入逾時：
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
本例中，資源載入超時時間設定為5秒。
## 第 4 步：初始化檢視器對象
初始化`Viewer`包含要渲染的文件和定義的載入選項的物件：
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
代替`TestFiles.WITH_EXTERNAL_IMAGE_DOC`以及要渲染的文件的路徑。
## 步驟 5：配置 HTML 視圖選項
配置嵌入資源的 HTML 視圖選項：
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
此配置可確保將圖像等嵌入資源包含在呈現的 HTML 中。
## 第 6 步：渲染文檔
使用配置的選項渲染文件：
```csharp
viewer.View(options);
```
此步驟啟動渲染程序。
## 步驟7：顯示輸出目錄
顯示一則訊息，指示渲染成功以及輸出目錄的位置：
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
掌握 GroupDocs.Viewer for .NET 中的資源載入逾時對於確保文件呈現過程順利進行至關重要。透過學習本教程，您將深入了解有效配置逾時，從而提高 .NET 開發的熟練程度。
## 常見問題解答
### 設定資源載入超時的意義是什麼？
設定資源載入逾時可確保渲染程序不會無限期掛起，進而增強應用程式穩定性。
### 是否可以根據文件類型自訂資源載入逾時？
是的，可以根據渲染文件的複雜性和大小來調整資源載入逾時。
### 設定較短的超時是否會對效能產生影響？
如果無法在指定的持續時間內載入資源，較短的逾時可能會導致複雜文件的渲染不完整。
### GroupDocs.Viewer是否適合渲染各種文件格式？
是的，GroupDocs.Viewer 支援渲染多種文件格式，包括 PDF、DOCX、XLSX 等。
### 可以停用資源載入超時嗎？
雖然不建議這樣做，但可以根據具體要求將資源載入逾時設定為較高值或完全停用。