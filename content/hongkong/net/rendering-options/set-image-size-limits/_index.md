---
"description": "了解如何使用 GroupDocs.Viewer for .NET 輕鬆在 .NET 應用程式中設定圖片大小限制，從而增強文件檢視體驗。"
"linktitle": "設定圖像大小限制"
"second_title": "GroupDocs.Viewer .NET API"
"title": "設定圖像大小限制"
"url": "/zh-hant/net/rendering-options/set-image-size-limits/"
"weight": 21
---

# 設定圖像大小限制

## 介紹
GroupDocs.Viewer for .NET 是一款功能強大的工具，旨在促進 .NET 應用程式中文件的無縫檢視。憑藉其強大的功能和直覺的介面，開發人員可以輕鬆地將文件檢視功能整合到他們的專案中，從而提升使用者體驗和生產力。在本教學中，我們將探討如何使用 GroupDocs.Viewer for .NET 設定影像大小限制，以確保文件的最佳顯示效果，同時保持效能和效率。
## 先決條件
在深入學習本教程之前，請確保您已滿足以下先決條件：
1. GroupDocs.Viewer for .NET：確保您的開發環境中已安裝必要的 GroupDocs.Viewer for .NET 程式庫。您可以從 [網站](https://releases。groupdocs.com/viewer/net/).
2. 開發環境：設定您首選的 .NET 開發環境，例如 Visual Studio，並進行所需的配置。
3. 文檔目錄：有一個指定的目錄來儲存您的文檔，並確保該目錄路徑在您的應用程式中可存取。

## 導入命名空間
在繼續實施之前，必須匯入所需的命名空間才能有效地存取 GroupDocs.Viewer for .NET 的功能。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟 1：定義輸出目錄和檔案路徑
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
確保更換 `"Your Document Directory"` 使用您的文件目錄的實際路徑。
## 步驟2：初始化檢視器物件並指定文件路徑
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX 表示範例文件的路徑。
    // 將其替換為您所需文件的路徑。
```
代替 `TestFiles.SAMPLE_DOCX` 替換為文檔的路徑。該路徑可以是 DOCX、PDF 或任何其他受支援的文件格式。
## 步驟 3：配置 JPEG 視圖選項
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
調整 `MaxWidth` 屬性可根據您的需求設定渲染影像的最大寬度。這可確保影像不超過指定的寬度，從而保持最佳顯示效果。
## 步驟 4：使用指定選項渲染文檔
```csharp
viewer.View(options);
```
這行程式碼觸發渲染過程，產生具有定義的大小限制的輸出影像。
## 步驟5：顯示成功訊息
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
渲染成功後，將顯示一條指示成功完成的訊息以及輸出目錄路徑。

## 結論
總而言之，掌握使用 GroupDocs.Viewer for .NET 設定影像大小限制的技巧可以顯著增強 .NET 應用程式中的文件檢視體驗。按照本教學中概述的逐步指南，您可以輕鬆優化影像顯示，同時確保效能和效率。
## 常見問題解答
### 我可以設定渲染圖像的最大寬度和高度嗎？
是的，您可以使用視圖選項中的對應屬性來設定最大寬度和高度。
### GroupDocs.Viewer for .NET 支援哪些文件格式？
GroupDocs.Viewer for .NET 支援多種文件格式，包括 DOCX、PDF、PPT、XLS 等。
### GroupDocs.Viewer for .NET 是否與 .NET Core 相容？
是的，GroupDocs.Viewer for .NET 與 .NET Core 相容，可無縫整合到現代 .NET 應用程式中。
### 我可以自訂 JPEG 以外的輸出影像格式嗎？
是的，GroupDocs.Viewer for .NET 支援各種輸出格式，包括 PNG、TIFF 和 PDF。
### 購買前是否有可供測試的試用版？
是的，你可以從 [網站](https://releases.groupdocs.com/viewer/net/)在購買之前探索 GroupDocs.Viewer for .NET 的功能和功能。