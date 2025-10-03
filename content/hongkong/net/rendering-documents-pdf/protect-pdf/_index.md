---
"description": "使用 Groupdocs.Viewer for .NET 輕鬆設定密碼保護渲染的 PDF。確保您的文件安全保密。"
"linktitle": "使用密碼保護渲染的 PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "使用密碼保護渲染的 PDF"
"url": "/zh-hant/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
type: docs
---
# 使用密碼保護渲染的 PDF

## 介紹
在本教程中，您將學習如何使用 Groupdocs.Viewer for .NET 為渲染的 PDF 新增密碼保護。透過新增安全措施，您可以控制對 PDF 文件的訪問，確保其機密性和完整性。
## 先決條件
在開始之前，請確保您已準備好以下內容：
1. Groupdocs.Viewer for .NET 函式庫：從 [網站](https://releases。groupdocs.com/viewer/net/).
2. 開發環境：確保您已為 .NET 開發設定了有效的開發環境。

## 導入命名空間
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步驟 1：定義輸出目錄和檔案路徑
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 步驟 2：初始化檢視器物件並設定安全選項
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## 步驟 3：設定 PDF 檢視選項
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## 步驟 4：使用安全選項渲染文檔
```csharp
    viewer.View(options);
}
```
## 步驟5：檢查渲染文檔
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
請依照下列步驟，您可以使用 Groupdocs.Viewer for .NET 為渲染的 PDF 設定密碼保護。這可確保您的文件安全無虞，並且只有授權使用者才能存取。

## 結論
保護 PDF 文件的安全性對於維護其機密性和完整性至關重要。使用 Groupdocs.Viewer for .NET，您可以輕鬆使用密碼保護渲染的 PDF，從而控制對敏感資訊的存取。

## 常見問題解答
### 我可以使用不同等級的權限來保護 PDF 嗎？
是的，您可以指定檢視、列印、複製等的不同權限，同時使用密碼保護 PDF。
### Groupdocs.Viewer 是否相容於各種文件格式？
當然！ Groupdocs.Viewer 支援渲染多種檔案格式，包括 DOCX、XLSX、PPTX、PDF 等。
### 我可以將 Groupdocs.Viewer 整合到我現有的 .NET 應用程式中嗎？
當然！ Groupdocs.Viewer 提供可無縫整合至 .NET 應用程式的 API，提供強大的文件檢視功能。
### Groupdocs.Viewer 是否支援雲端儲存服務？
是的，Groupdocs.Viewer 支援與 Dropbox、Google Drive 和 Amazon S3 等流行的雲端儲存服務集成，可讓您呈現儲存在雲端中的文件。
### Groupdocs.Viewer 有試用版嗎？
是的，您可以透過造訪免費試用版開始使用 Groupdocs.Viewer [網站](https://releases。groupdocs.com/).