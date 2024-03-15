---
title: 設定日期時間格式和時區偏移量（電子郵件）
linktitle: 設定日期時間格式和時區偏移量（電子郵件）
second_title: GroupDocs.Viewer .NET API
description: 將 GroupDocs.Viewer for .NET 無縫整合到您的應用程式中，以獲得強大的文件檢視功能。透過可自訂的選項增強使用者體驗。
type: docs
weight: 11
url: /zh-hant/net/rendering-email-messages/set-date-time-format-offset-email/
---

## 介紹
GroupDocs.Viewer for .NET 是一個功能強大的工具，使開發人員能夠將文件檢視功能無縫整合到他們的 .NET 應用程式中。透過 GroupDocs.Viewer，您可以直接在應用程式中顯示各種文件格式，包括 PDF、Microsoft Office 文件、圖像等，而無需任何外部外掛程式或檢視器。在這個綜合教學中，我們將引導您完成為 .NET 設定 GroupDocs.Viewer 的過程，探索其功能，並示範如何有效地利用它來增強應用程式的文件檢視功能。
## 先決條件
在深入學習本教學之前，請確保您已設定以下先決條件：
1. Visual Studio：確保您的系統上安裝了 Visual Studio。 GroupDocs.Viewer for .NET 與 Visual Studio 完全相容，可無縫整合到您的 .NET 專案中。
2.  GroupDocs.Viewer for .NET：從下列位置下載並安裝 GroupDocs.Viewer for .NET[下載連結](https://releases.groupdocs.com/viewer/net/)。按照提供的安裝說明在您的開發環境中設定庫。
3. .NET Framework：確保已安裝了適當版本的 .NET Framework。 GroupDocs.Viewer for .NET 支援各種版本的 .NET Framework，包括 .NET Core 和 .NET Standard。

## 導入命名空間
為了有效地利用 GroupDocs.Viewer for .NET，您需要將必要的命名空間匯入到您的專案中。請依照下列步驟匯入所需的命名空間：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


讓我們將提供的範例分解為多個步驟，以了解每個組件及其功能。
## 步驟1：設定輸出目錄和檔案路徑
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
在此步驟中，我們定義儲存渲染文件的輸出目錄，並指定輸出 HTML 檔案的檔案路徑。
## 第 2 步：實例化檢視器對象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
在這裡，我們建立一個新的實例`Viewer`類，將要查看的文檔的路徑（在本例中為範例 EML 文件）作為參數傳遞。
## 第 3 步：定義 HTML 視圖選項
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
在此步驟中，我們配置文件渲染的 HTML 視圖選項，指定渲染的 HTML 文件的輸出檔案路徑。
## 步驟 4：設定日期時間格式和時區偏移
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
在這裡，我們自訂電子郵件的日期和時間格式，並根據所需的時區設定時區偏移量。
## 第5步：渲染文檔
```csharp
viewer.View(options);
```
最後，我們調用`View`的方法`Viewer`對象，傳遞配置的 HTML 視圖選項以將文件呈現為 HTML 格式。
## 步驟6：顯示輸出目錄
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
此步驟僅顯示一則訊息，指示文件已成功呈現，並提供呈現的 HTML 文件所在的輸出目錄的路徑。

## 結論
GroupDocs.Viewer for .NET 提供了一個強大的解決方案，將文件檢視功能整合到您的 .NET 應用程式中。透過遵循本教學中概述的步驟，您可以輕鬆設定 GroupDocs.Viewer、匯入必要的命名空間，並利用其功能透過可自訂選項呈現文件。無論您使用的是 PDF、Microsoft Office 文件或其他格式，GroupDocs.Viewer 都可以簡化文件檢視流程，從而增強應用程式的使用者體驗。
## 常見問題解答
### GroupDocs.Viewer 與 .NET Core 相容嗎？
是的，GroupDocs.Viewer for .NET 支援 .NET Core，為您的應用程式提供跨平台相容性。
### 我可以自訂渲染文件的外觀嗎？
絕對地！ GroupDocs.Viewer 提供各種自訂選項，包括縮放等級、頁面旋轉等，以便根據您的喜好自訂檢視體驗。
### 是否有可用於測試目的的試用版？
是的，您可以從以下位置下載 GroupDocs.Viewer for .NET 的免費試用版：[網站連結](https://releases.groupdocs.com/viewer/net/)在購買之前評估其功能。
### GroupDocs.Viewer 是否支援呈現受密碼保護的文件？
是的，GroupDocs.Viewer 內建支援呈現受密碼保護的文檔，確保在應用程式中安全地查看文檔。
### 在哪裡可以找到有關 GroupDocs.Viewer 的其他支援或協助？
如需任何技術問題或協助，您可以造訪 GroupDocs.Viewer[論壇](https://forum.groupdocs.com/c/viewer/9)或聯繫他們的支援團隊以獲得及時的幫助和指導。