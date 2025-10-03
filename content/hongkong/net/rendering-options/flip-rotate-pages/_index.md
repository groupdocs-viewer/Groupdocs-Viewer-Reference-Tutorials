---
"description": "了解如何將 Groupdocs.Viewer for .NET 整合到您的應用程式中，以實現無縫文件渲染、翻轉和旋轉。"
"linktitle": "翻轉和旋轉頁面"
"second_title": "GroupDocs.Viewer .NET API"
"title": "翻轉和旋轉頁面"
"url": "/zh-hant/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# 翻轉和旋轉頁面

## 介紹
在本教學中，我們將深入探討 Groupdocs.Viewer for .NET 的功能，特別是翻頁和旋轉頁面。 Groupdocs.Viewer for .NET 是一款功能強大的工具，旨在在 .NET 應用程式中以各種格式呈現文件。無論您是開發文件管理系統，還是需要將文件檢視功能整合到您的軟體中，Groupdocs.Viewer for .NET 都能提供高效率的解決方案。
## 先決條件
在開始之前，請確保您已設定以下先決條件：
### 安裝 Groupdocs.Viewer for .NET
若要使用 Groupdocs.Viewer for .NET，您需要透過 NuGet 套件管理器安裝該套件。您可以在 [文件](https://tutorials。groupdocs.com/viewer/net/).

## 導入命名空間
確保您已在專案中匯入必要的命名空間，以便有效利用 Groupdocs.Viewer for .NET。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

讓我們將使用 Groupdocs.Viewer for .NET 翻轉和旋轉頁面的過程分解為簡單的步驟：
## 步驟 1：設定輸出目錄和檔案路徑
定義要儲存輸出檔案的目錄並指定輸出檔案路徑。
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## 步驟2：初始化檢視器對象
透過傳遞要檢視的文件的路徑來建立 Viewer 類別的實例。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## 步驟 3：配置視圖選項
設定檢視選項，例如指定輸出檔案格式和任何其他設定（如頁面旋轉）。
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## 步驟 4：渲染文檔
呼叫Viewer物件的View方法並傳遞視圖選項。
```csharp
viewer.View(viewOptions);
```
## 步驟5：顯示成功訊息
通知使用者文件已成功渲染，並指定用於驗證的輸出目錄。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
總而言之，Groupdocs.Viewer for .NET 提供了強大的文件渲染功能，包括翻轉和旋轉頁面。按照本教學中概述的步驟，您可以將這些功能無縫整合到您的 .NET 應用程式中，從而增強使用者的文件檢視體驗。
## 常見問題解答
### Groupdocs.Viewer for .NET 是否相容於所有文件格式？
是的，Groupdocs.Viewer for .NET 支援多種文件格式，包括 DOCX、PDF、PPTX 等。
### 除了翻頁和旋轉頁面之外，我還可以自訂檢視選項嗎？
當然，Groupdocs.Viewer for .NET 提供了各種用於查看文件的自訂選項，可讓您根據您的要求自訂體驗。
### Groupdocs.Viewer for .NET 有免費試用版嗎？
是的，您可以造訪以下網址免費試用 Groupdocs.Viewer for .NET [網站](https://releases。groupdocs.com/).
### 如何獲得 Groupdocs.Viewer for .NET 的支援？
您可以透過以下方式尋求協助並與社群互動 [Groupdocs.Viewer 論壇](https://forum。groupdocs.com/c/viewer/9).
### 我可以在哪裡獲得 Groupdocs.Viewer for .NET 的臨時授權？
Groupdocs.Viewer for .NET 的臨時許可證可以從 [購買頁面](https://purchase。groupdocs.com/temporary-license/).