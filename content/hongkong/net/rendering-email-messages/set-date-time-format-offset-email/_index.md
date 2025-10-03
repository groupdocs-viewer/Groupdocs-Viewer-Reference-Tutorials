---
"description": "將 GroupDocs.Viewer for .NET 無縫整合到您的應用程式中，實現強大的文件檢視功能。透過可自訂的選項提升使用者體驗。"
"linktitle": "設定日期時間格式和時區偏移量（電子郵件）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "設定日期時間格式和時區偏移量（電子郵件）"
"url": "/zh-hant/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# 設定日期時間格式和時區偏移量（電子郵件）


## 介紹
GroupDocs.Viewer for .NET 是一款功能強大的工具，可協助開發人員將文件檢視功能無縫整合到其 .NET 應用程式中。使用 GroupDocs.Viewer，您可以直接在應用程式中顯示各種文件格式，包括 PDF、Microsoft Office 文件、映像等，而無需任何外部外掛程式或檢視器。在本教程中，我們將指導您完成 GroupDocs.Viewer for .NET 的設定過程，探索其功能，並示範如何有效地利用它來增強應用程式的文件檢視功能。
## 先決條件
在深入本教學之前，請確保您已滿足以下先決條件：
1. Visual Studio：請確保您的系統上已安裝 Visual Studio。 GroupDocs.Viewer for .NET 與 Visual Studio 完全相容，可無縫整合到您的 .NET 專案中。
2. GroupDocs.Viewer for .NET：從 [下載連結](https://releases.groupdocs.com/viewer/net/)依照提供的安裝說明在您的開發環境中設定庫。
3. .NET Framework：確保您已安裝適當版本的 .NET Framework。 GroupDocs.Viewer for .NET 支援各種版本的 .NET Framework，包括 .NET Core 和 .NET Standard。

## 導入命名空間
為了有效地利用 GroupDocs.Viewer for .NET，您需要將必要的命名空間匯入到您的專案中。請依照下列步驟匯入所需的命名空間：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


讓我們將提供的範例分解為多個步驟，以了解每個組件及其功能。
## 步驟 1：設定輸出目錄和檔案路徑
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
在此步驟中，我們定義將儲存渲染文件的輸出目錄並指定輸出 HTML 檔案的檔案路徑。
## 步驟2：實例化檢視器對象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
在這裡，我們建立一個新的實例 `Viewer` 類，將要查看的文檔的路徑（在本例中為範例 EML 文件）作為參數傳遞。
## 步驟 3：定義 HTML 視圖選項
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
在這一步驟中，我們設定文件渲染的HTML檢視選項，指定渲染後的HTML文件的輸出檔案路徑。
## 步驟 4：設定日期時間格式和時區偏移量
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
在這裡，我們自訂電子郵件訊息的日期和時間格式，並根據所需的時區設定時區偏移。
## 步驟5：渲染文檔
```csharp
viewer.View(options);
```
最後，我們稱 `View` 方法 `Viewer` 對象，傳遞配置的 HTML 視圖選項以將文件呈現為 HTML 格式。
## 步驟6：顯示輸出目錄
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
此步驟僅顯示一則訊息，表示文件渲染成功，並提供渲染的 HTML 文件所在的輸出目錄的路徑。

## 結論
GroupDocs.Viewer for .NET 提供了一個強大的解決方案，可將文件檢視功能整合到您的 .NET 應用程式中。按照本教學中概述的步驟，您可以輕鬆設定 GroupDocs.Viewer，匯入必要的命名空間，並利用其功能以可自訂的選項呈現文件。無論您處理的是 PDF、Microsoft Office 文件或其他格式，GroupDocs.Viewer 都能簡化文件檢視流程，進而提升應用程式的使用者體驗。
## 常見問題解答
### GroupDocs.Viewer 是否與 .NET Core 相容？
是的，GroupDocs.Viewer for .NET 支援 .NET Core，為您的應用程式實作跨平台相容性。
### 我可以自訂渲染文件的外觀嗎？
當然！ GroupDocs.Viewer 提供各種自訂選項，包括縮放等級、頁面旋轉等，以便根據您的教學自訂觀看體驗。
### 是否有可供測試的試用版？
是的，您可以從 [網站連結](https://releases.groupdocs.com/viewer/net/) 在購買之前評估其功能。
### GroupDocs.Viewer 是否支援呈現受密碼保護的文件？
是的，GroupDocs.Viewer 內建了對呈現受密碼保護的文件的支持，確保在您的應用程式中安全地查看文件。
### 在哪裡可以找到有關 GroupDocs.Viewer 的更多支援或協助？
如有任何技術問題或需要協助，您可以造訪 GroupDocs.Viewer [論壇](https://forum.groupdocs.com/c/viewer/9) 或聯繫他們的支援團隊以獲得及時的幫助和指導。