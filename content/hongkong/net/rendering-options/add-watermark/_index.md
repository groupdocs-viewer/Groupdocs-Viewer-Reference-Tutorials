---
"description": "了解如何使用 GroupDocs.Viewer for .NET 為文件無縫新增浮水印。本教學簡單易學，幫助您增強文件安全性和品牌形象。"
"linktitle": "在文件中新增浮水印"
"second_title": "GroupDocs.Viewer .NET API"
"title": "在文件中新增浮水印"
"url": "/zh-hant/net/rendering-options/add-watermark/"
"weight": 10
type: docs
---
# 在文件中新增浮水印

## 介紹
在當今的數位時代，無縫管理和查看各種文件格式對許多企業和個人而言都至關重要。幸運的是，借助 GroupDocs.Viewer for .NET 等工具，處理文件變得輕而易舉。這個強大的 .NET 程式庫使開發人員能夠輕鬆地將文件檢視功能整合到他們的應用程式中，使用戶無需使用建立文件的原始軟體即可查看文件。
## 先決條件
在深入使用 GroupDocs.Viewer for .NET 為文件新增浮水印之前，請確保您已具備以下條件：
1. 環境設定：安裝 .NET Framework 或 .NET Core 的開發環境。
2. GroupDocs.Viewer for .NET：從下載並安裝 GroupDocs.Viewer for .NET 程式庫 [下載頁面](https://releases。groupdocs.com/viewer/net/).
3. 文件檔案：準備您想要使用的文件文件，例如 DOCX、PDF 或其他文件。
4. C# 基礎知識：熟悉 C# 程式語言對於實作程式碼範例是必要的。

## 導入命名空間
在開始使用 GroupDocs.Viewer for .NET 為文件新增浮水印之前，請確保在 C# 程式碼中匯入所需的命名空間。此步驟可讓您無縫存取庫提供的類別和方法。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在，讓我們逐步介紹如何使用 GroupDocs.Viewer for .NET 在文件中新增浮水印的過程。請按照以下步驟操作，即可將浮水印功能無縫整合到您的應用程式中。
## 步驟1：設定輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
指定應用浮水印後儲存輸出檔案的目錄。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
設定渲染頁面檔案路徑的格式。本例中，將產生帶有頁碼的 HTML 檔案。
## 步驟3：實例化檢視器對象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // 程式碼在下一步繼續...
}
```
建立 Viewer 類別的實例，並將文件文件的路徑作為參數傳遞。在本例中，我們使用一個範例 DOCX 檔案。
## 步驟 4：配置 HTML 視圖選項
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
配置 HTML 視圖選項，包括您想要新增至文件的浮水印文字。
## 步驟5：查看帶有浮水印的文檔
```csharp
viewer.View(options);
```
呼叫 Viewer 物件的 View 方法，並傳遞已配置的選項。這將使用指定的浮水印渲染文件。
## 步驟6：顯示輸出目錄路徑
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
通知使用者文件已成功呈現並指示儲存輸出檔案的目錄。

## 結論
GroupDocs.Viewer for .NET 提供了一種便捷的方式，可以透過程式設計方式為文件添加浮水印。按照本教學中概述的步驟，您可以將浮水印功能無縫整合到您的 .NET 應用程式中，從而增強文件安全性和品牌形象。
## 常見問題解答
### 我可以自訂浮水印的外觀嗎？
是的，您可以自訂浮水印的各種屬性，例如文字、字體、顏色、大小和位置。
### GroupDocs.Viewer 是否支援檢視遠端來源的文件？
是的，GroupDocs.Viewer 支援查看來自本機儲存和遠端 URL 的文件。
### GroupDocs.Viewer for .NET 有試用版嗎？
是的，您可以從下載免費試用版 [這裡](https://releases。groupdocs.com/).
### 我可以在文件的多個頁面上新增浮水印嗎？
當然，GroupDocs.Viewer 允許在文件的單一頁面或所有頁面上新增浮水印。
### 如果我遇到任何問題，如何獲得支持或協助？
您可以從 GroupDocs 社群論壇尋求協助和支持 [這裡](https://forum。groupdocs.com/c/viewer/9).