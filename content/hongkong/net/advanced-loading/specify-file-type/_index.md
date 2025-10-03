---
"description": "了解如何使用 GroupDocs.Viewer for .NET 載入文件時指定文件類型。在您的 .NET 應用程式中準確呈現各種格式。"
"linktitle": "載入文檔時指定文件類型"
"second_title": "GroupDocs.Viewer .NET API"
"title": "載入文檔時指定文件類型"
"url": "/zh-hant/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# 載入文檔時指定文件類型

## 介紹
GroupDocs.Viewer for .NET 是一款功能豐富的文件渲染 API，支援多種文件格式，包括 DOCX、PDF、PPTX 等。透過在載入文件時指定文件類型，您可以確保渲染準確，並為使用者帶來流暢的瀏覽體驗。

![在 GroupDocs.Viewer for .NET 中載入文件時指定文件類型](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## 先決條件
在開始之前，請確保您符合以下先決條件：
- C# 和 .NET 架構的基本知識。
- 您的系統上安裝了 Visual Studio。
- 已在您的專案中安裝 GroupDocs.Viewer for .NET。您可以從 [這裡](https://releases。groupdocs.com/viewer/net/).
##
## 導入命名空間
首先，你需要將必要的命名空間匯入到你的 C# 程式碼中。這些命名空間提供了對文件渲染所需的類別和方法的存取。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟 1：設定輸出目錄
定義要儲存渲染的文件頁面的目錄。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步驟2：定義頁面檔案路徑格式
指定文件每頁輸出 HTML 文件的命名格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步驟 3：指定載入選項
建立一個實例 `LoadOptions` 類別並設定所需的文件類型。
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## 步驟 4：載入文件並渲染
使用 `Viewer` 類別來載入文件並將其呈現為 HTML 格式。
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 步驟5：顯示成功訊息
通知使用者文件已成功呈現並指定輸出文件的位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 在載入文件時指定文件類型。透過遵循這些簡單的步驟，您可以確保在 .NET 應用程式中準確呈現各種文件格式。
## 常見問題解答
### 我可以使用 GroupDocs.Viewer for .NET 呈現 DOCX 以外的文件嗎？
是的，GroupDocs.Viewer 支援多種文件格式，包括 PDF、PPTX、XLSX 等。
### GroupDocs.Viewer for .NET 是否與 .NET Core 相容？
是的，GroupDocs.Viewer for .NET 與 .NET Framework 和 .NET Core 相容。
### 我可以自訂 GroupDocs.Viewer 產生的輸出 HTML 檔案嗎？
是的，您可以使用 API 提供的各種選項自訂 HTML 輸出。
### GroupDocs.Viewer for .NET 是否需要任何外部依賴？
不，GroupDocs.Viewer for .NET 是一個獨立函式庫，不需要任何外部依賴。
### GroupDocs.Viewer for .NET 有試用版嗎？
是的，您可以從下載免費試用版 [這裡](https://releases。groupdocs.com/viewer/net/).