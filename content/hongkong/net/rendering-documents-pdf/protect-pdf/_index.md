---
title: 使用密碼保護渲染的 PDF
linktitle: 使用密碼保護渲染的 PDF
second_title: GroupDocs.Viewer .NET API
description: 使用 Groupdocs.Viewer for .NET，使用密碼輕鬆保護渲染的 PDF。確保您的文件安全且保密。
weight: 12
url: /zh-hant/net/rendering-documents-pdf/protect-pdf/
---
## 介紹
在本教學中，您將學習如何使用 Groupdocs.Viewer for .NET 透過密碼保護渲染的 PDF。透過新增安全措施，您可以控制對 PDF 文件的訪問，確保機密性和完整性。
## 先決條件
在開始之前，請確保您具備以下條件：
1.  Groupdocs.Viewer for .NET Library：從以下位置下載並安裝該程式庫：[網站](https://releases.groupdocs.com/viewer/net/).
2. 開發環境：確保您有一個用於 .NET 開發的工作開發環境。

## 導入命名空間
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：定義輸出目錄和檔案路徑
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 第 2 步：初始化檢視器物件並設定安全選項
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
## 第 5 步：檢查渲染文檔
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
透過執行下列步驟，您可以使用 Groupdocs.Viewer for .NET 使用密碼保護渲染的 PDF。這可確保您的文件保持安全，並且只有授權使用者才能存取。

## 結論
保護 PDF 文件的安全性對於維護機密性和完整性至關重要。透過 Groupdocs.Viewer for .NET，您可以輕鬆地使用密碼保護渲染的 PDF，控制對敏感資訊的存取。

## 常見問題解答
### 我可以使用不同等級的權限來保護 PDF 嗎？
是的，您可以指定不同的檢視、列印、複製等權限，同時使用密碼保護 PDF。
### Groupdocs.Viewer 是否與各種文件格式相容？
絕對地！ Groupdocs.Viewer 支援渲染多種檔案格式，包括 DOCX、XLSX、PPTX、PDF 等。
### 我可以將 Groupdocs.Viewer 整合到我現有的 .NET 應用程式中嗎？
當然！ Groupdocs.Viewer 提供用於無縫整合到 .NET 應用程式中的 API，從而提供強大的文件檢視功能。
### Groupdocs.Viewer 是否提供雲端儲存服務支援？
是的，Groupdocs.Viewer 支援與 Dropbox、Google Drive 和 Amazon S3 等流行的雲端儲存服務集成，可讓您呈現儲存在雲端中的文件。
### Groupdocs.Viewer 是否有試用版？
是的，您可以透過造訪免費試用版來開始使用 Groupdocs.Viewer[網站](https://releases.groupdocs.com/).