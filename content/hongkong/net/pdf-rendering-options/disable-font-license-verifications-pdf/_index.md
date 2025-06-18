---
"description": "使用 GroupDocs.Viewer for .NET，在 .NET 中解鎖無縫文件檢視功能。輕鬆整合和自訂文件渲染，最大程度減少依賴。"
"linktitle": "停用 PDF 中的字型許可證驗證"
"second_title": "GroupDocs.Viewer .NET API"
"title": "停用 PDF 中的字型許可證驗證"
"url": "/zh-hant/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
---

# 停用 PDF 中的字型許可證驗證

## 介紹
在 .NET 開發領域，文件的管理和操作通常是許多應用程式的關鍵環節。無論是查看 PDF、Word 文件或其他類型的文件，擁有強大的工具來有效率地處理這些任務都至關重要。這正是 GroupDocs.Viewer for .NET 應運而生的地方。這個強大的程式庫使開發人員能夠將文件檢視功能無縫整合到他們的 .NET 應用程式中。

![使用 GroupDocs.Viewer .NET 停用 PDF 中的字型授權驗證](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## 先決條件
在深入使用 GroupDocs.Viewer for .NET 之前，您需要滿足一些先決條件：
### 1.安裝 Visual Studio
首先，請確保您的系統上已安裝 Visual Studio。如果您還沒有安裝，可以從微軟網站下載。
### 2. 下載 GroupDocs.Viewer for .NET
前往 [下載連結](https://releases.groupdocs.com/viewer/net/) 取得 GroupDocs.Viewer for .NET 的最新版本。請按照提供的安裝說明在您的開發環境中進行設定。
### 3. 取得臨時許可證
為了在開發和測試期間充分發揮 GroupDocs.Viewer for .NET 的潛力，建議您取得臨時許可證。您可以透過以下方式申請： [這裡](https://purchase。groupdocs.com/temporary-license/).

## 導入命名空間
完成先決條件後，您就可以開始在專案中使用 GroupDocs.Viewer for .NET 了。首先，將必要的命名空間匯入到您的程式碼庫中。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

為了更清楚地理解，我們將提供的範例分解為多個步驟：
## 步驟 1：定義輸出目錄
首先定義要儲存渲染的文檔頁面的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
設定文件各頁面的文件路徑的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## 步驟3：初始化檢視器對象
建立 Viewer 類別的實例，並將路徑傳遞到您想要檢視的文件。
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## 步驟 4：配置 HTML 視圖選項
定義以 HTML 形式檢視文件的選項，指定嵌入資源（例如圖片）的格式。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 步驟 5：停用字型授權驗證
啟用該選項以停用字體授權驗證，以確保流暢渲染。
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## 步驟6：查看文檔
呼叫 Viewer 物件的 View 方法，傳遞配置的選項。
```csharp
viewer.View(options);
```
## 步驟 7：顯示輸出目錄
告知使用者呈現的文檔頁面的儲存位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
GroupDocs.Viewer for .NET 為開發人員提供了一個全面的解決方案，可輕鬆將文件檢視功能整合到他們的 .NET 應用程式中。按照本教學中概述的步驟，您可以有效地利用這個強大的庫來增強您的文件管理工作流程。
## 常見問題解答
### GroupDocs.Viewer for .NET 可以處理多種文件格式嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、Microsoft Word、Excel、PowerPoint 等。
### GroupDocs.Viewer for .NET 是否適合 Web 應用程式？
當然，GroupDocs.Viewer 可以無縫整合到使用 .NET 技術開發的桌面和 Web 應用程式中。
### GroupDocs.Viewer 是否需要任何額外的依賴項？
不，GroupDocs.Viewer for .NET 具有最小的依賴性，可輕鬆整合到您現有的專案中。
### 我可以自訂渲染文件的外觀嗎？
是的，GroupDocs.Viewer 提供了各種選項來客製化呈現文件的外觀和行為，以滿足您的特定要求。
### GroupDocs.Viewer for .NET 是否提供技術支援？
是的，您可以透過以下方式向專門的支援團隊尋求協助和指導 [論壇](https://forum。groupdocs.com/c/viewer/9).