---
"description": "使用 GroupDocs.Viewer 增強您的 .NET 應用程序，實現無縫文件檢視。按照我們的逐步指南，輕鬆整合強大的文件檢視功能。"
"linktitle": "從串流設定許可證"
"second_title": "GroupDocs.Viewer .NET API"
"title": "從串流設定許可證"
"url": "/zh-hant/net/getting-started/set-license-from-stream/"
"weight": 11
---

# 從串流設定許可證

## 介紹
您是否希望為您的 .NET 應用程式賦予進階文件檢視功能？ GroupDocs.Viewer for .NET 提供了一個全面的解決方案，可將文件檢視功能無縫整合到您的專案中。在本教學中，我們將深入探討如何利用 GroupDocs.Viewer for .NET 為您的應用程式提供強大的文件檢視功能。 

![使用 GroupDocs.Viewer for .NET 從流程設定許可證](/viewer/getting-started/set-license-from-stream.png)

## 先決條件
在深入研究整合過程之前，請確保您已滿足以下先決條件：
1. .NET 開發基礎知識：熟悉 C# 和 .NET 框架對於學習本教程至關重要。
   
2. GroupDocs.Viewer for .NET 軟體套件：請確保您已下載並安裝了 GroupDocs.Viewer for .NET 軟體套件。您可以從 [下載連結](https://releases。groupdocs.com/viewer/net/).
3. 存取 GroupDocs 文件：保留 [文件](https://tutorials.groupdocs.com/viewer/net/) 方便整合過程中的教學。

## 導入命名空間
首先，將必要的命名空間匯入到您的 .NET 應用程式中。請依照以下步驟操作：
### 步驟 1：開啟您的 .NET 專案。
確保您已在您首選的開發環境中開啟了 .NET 專案。
### 步驟 2： 新增 GroupDocs.Viewer 命名空間。
在您的程式碼檔案中，新增以下命名空間以存取 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
```
## 從串流設定許可證
下一步是從流中設定許可證。請遵循以下詳細步驟：
### 步驟 1：定義輸出目錄。
透過定義輸出目錄來設定儲存文件的目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
### 第 2 步：檢查許可證文件是否存在。
檢查許可證文件是否存在於您的專案目錄中：
```csharp
if (File.Exists(Utils.LicensePath))
```
### 步驟3：設定許可證。
如果許可證文件存在，則使用提供的串流設定許可證：
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 步驟4：處理許可證缺失。
如果找不到許可證文件，請提供取得許可證的說明：
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing。 " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license。 ");
}
```

## 結論
恭喜！您已成功學習如何將 GroupDocs.Viewer for .NET 整合到您的應用程式中。透過這款強大的工具，您現在可以輕鬆地在 .NET 專案中查看各種文件格式，從而提升使用者體驗和工作效率。
## 常見問題解答
### 我需要許可證才能使用 GroupDocs.Viewer for .NET 嗎？
是的，您需要許可證才能使用 GroupDocs.Viewer for .NET。您可以從 GroupDocs 網站取得臨時或永久許可證。
### 我可以將 GroupDocs.Viewer 整合到我的 ASP.NET 應用程式中嗎？
當然！ GroupDocs.Viewer for .NET 無縫整合到桌面和 Web 應用程式（包括 ASP.NET）。
### GroupDocs.Viewer 支援哪些文件格式？
GroupDocs.Viewer 支援多種文件格式，包括 PDF、Microsoft Office（Word、Excel、PowerPoint）、影像等。
### GroupDocs.Viewer 是否與 .NET Core 相容？
是的，GroupDocs.Viewer for .NET 與 .NET Framework 和 .NET Core 相容。
### 我可以根據我的應用程式的主題自訂檢視器介面嗎？
是的，GroupDocs.Viewer 提供了廣泛的自訂選項，可讓您自訂檢視器介面以無縫匹配您的應用程式主題。