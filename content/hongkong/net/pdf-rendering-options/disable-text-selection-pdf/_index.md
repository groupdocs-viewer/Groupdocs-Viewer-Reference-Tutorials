---
"description": "了解如何使用 GroupDocs.Viewer for .NET 停用 PDF 中的文字選擇功能。請按照我們的逐步指南，實現無縫整合。"
"linktitle": "停用 PDF 中的文字選擇"
"second_title": "GroupDocs.Viewer .NET API"
"title": "停用 PDF 中的文字選擇"
"url": "/zh-hant/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
---

# 停用 PDF 中的文字選擇

## 介紹
GroupDocs.Viewer for .NET 是一個強大的文件渲染 API，可讓開發人員輕鬆地將文件檢視功能整合到他們的 .NET 應用程式中。 GroupDocs.Viewer 提供的關鍵功能是能夠停用 PDF 文件中的文字選擇。此功能在需要防止使用者從敏感文件中複製文字以確保文件安全性和完整性的情況下特別有用。

![使用 GroupDocs.Viewer .NET 停用 PDF 中的文字選擇](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## 先決條件
在深入介紹如何使用 GroupDocs.Viewer for .NET 停用 PDF 中的文字選擇的逐步指南之前，請確保您已滿足以下先決條件：
1. 安裝 GroupDocs.Viewer for .NET：確保您已從 [下載連結](https://releases。groupdocs.com/viewer/net/).
2. 文件目錄：準備一個用於儲存文件的目錄。您需要在程式碼片段中指定此目錄來渲染 PDF 文件。

## 導入命名空間
首先，您需要匯入必要的命名空間才能存取 GroupDocs.Viewer for .NET 提供的功能。操作方法如下：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在，讓我們將使用 GroupDocs.Viewer for .NET 停用 PDF 文件中的文字選擇的過程分解為多個步驟：
## 步驟 1：指定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
在此步驟中，替換 `"Your Document Directory"` 與您的 PDF 文件所在的目錄路徑。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
此步驟定義渲染後的 HTML 頁面檔案路徑的格式。 PDF 文件的每一頁都會轉換為具有連續頁碼的 HTML 檔案。
## 步驟3：停用文字選擇渲染PDF文檔
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
代替 `"Path to Your PDF Document"` 替換為 PDF 檔案的實際路徑。此程式碼片段初始化一個 `Viewer` 對象，配置 HTML 視圖選項以嵌入資源，並透過設定停用文字選擇 `RenderTextAsImage` 財產 `true`。
## 步驟4：顯示成功訊息
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
渲染 PDF 文件後，此步驟將顯示成功訊息以及儲存渲染的 HTML 頁面的目錄。

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 停用 PDF 文件中的文字選擇功能。請按照逐步指南操作，您可以將此功能無縫整合到您的 .NET 應用程式中，確保文件安全並增強使用者體驗。
## 常見問題解答
### 我可以自訂渲染 HTML 頁面的輸出目錄嗎？
是的，您可以指定任何您想要儲存呈現的 HTML 頁面的目錄路徑。
### GroupDocs.Viewer for .NET 是否與不同版本的 .NET 框架相容？
是的，GroupDocs.Viewer for .NET 與各種版本的 .NET 框架相容，包括 .NET Core 和 .NET Framework。
### 停用文字選擇會影響 PDF 文件的其他功能嗎？
不會。停用文字選擇功能只會阻止使用者從文件中選擇和複製文字。其他功能不變。
### 渲染文檔後我可以再次啟用文字選擇嗎？
是的，您可以透過簡單設定來啟用文字選擇 `RenderTextAsImage` 財產 `false` 在 HTML 視圖選項中。
### GroupDocs.Viewer for .NET 有試用版嗎？
是的，您可以從 [網站](https://releases。groupdocs.com/).