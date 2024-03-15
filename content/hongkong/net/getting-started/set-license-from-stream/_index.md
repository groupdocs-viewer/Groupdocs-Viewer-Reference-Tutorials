---
title: 從 Stream 設定許可證
linktitle: 從 Stream 設定許可證
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer 增強您的 .NET 應用程序，以實現無縫文件檢視。按照我們的逐步指南，輕鬆整合強大的文件檢視功能。
type: docs
weight: 11
url: /zh-hant/net/getting-started/set-license-from-stream/
---
## 介紹
您是否希望為您的 .NET 應用程式提供進階文件檢視功能？ GroupDocs.Viewer for .NET 提供了一個全面的解決方案，可將文件檢視功能無縫整合到您的專案中。在本教程中，我們將深入研究利用 GroupDocs.Viewer for .NET 透過強大的文件查看功能豐富您的應用程式的過程。 
## 先決條件
在我們深入了解整合過程之前，請確保您符合以下先決條件：
1. .NET 開發的基本知識：熟悉 C# 和 .NET 框架對於學習本教程至關重要。
   
2.  GroupDocs.Viewer for .NET 軟體套件：確保您已下載並安裝 GroupDocs.Viewer for .NET 軟體套件。您可以從[下載連結](https://releases.groupdocs.com/viewer/net/).
3. 存取 GroupDocs 文件：保留[文件](https://reference.groupdocs.com/viewer/net/)方便集成過程中參考。

## 導入命名空間
首先，將必要的命名空間匯入到您的 .NET 應用程式中。按著這些次序：
### 第 1 步：開啟您的 .NET 專案。
確保您已在首選開發環境中開啟 .NET 專案。
### 步驟 2：新增 GroupDocs.Viewer 命名空間。
在您的程式碼檔案中，新增以下命名空間以存取 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
```
## 從 Stream 設定許可證
下一步涉及從流設置許可證。請依照以下詳細步驟操作：
### 第 1 步：定義輸出目錄。
透過定義輸出目錄來設定儲存文件的目錄：
```csharp
string outputDirectory = "Your Document Directory";
```
### 步驟 2：檢查許可證文件是否存在。
檢查您的專案目錄中是否存在許可證文件：
```csharp
if (File.Exists(Utils.LicensePath))
```
### 步驟 3：設定許可證。
如果許可證文件存在，請使用提供的串流設定許可證：
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 步驟 4：處理許可證缺失問題。
如果未找到許可證文件，請提供取得許可證的說明：
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing。 ” +
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license.」）；
}
```

## 結論
恭喜！您已經成功學習如何將 GroupDocs.Viewer for .NET 整合到您的應用程式中。借助這個強大的工具，您現在可以輕鬆查看 .NET 專案中的各種文件格式，從而增強使用者體驗和工作效率。
## 常見問題解答
### 我需要許可證才能使用 GroupDocs.Viewer for .NET 嗎？
是的，您需要許可證才能使用 GroupDocs.Viewer for .NET。您可以從 GroupDocs 網站取得臨時或永久許可證。
### 我可以將 GroupDocs.Viewer 整合到我的 ASP.NET 應用程式中嗎？
絕對地！ GroupDocs.Viewer for .NET 無縫整合到桌面和 Web 應用程式（包括 ASP.NET）。
### GroupDocs.Viewer 支援哪些文件格式？
GroupDocs.Viewer 支援多種文件格式，包括 PDF、Microsoft Office（Word、Excel、PowerPoint）、影像等。
### GroupDocs.Viewer 與 .NET Core 相容嗎？
是的，GroupDocs.Viewer for .NET 與 .NET Framework 和 .NET Core 相容。
### 我可以根據應用程式的主題自訂檢視器介面嗎？
是的，GroupDocs.Viewer 提供了廣泛的自訂選項，可讓您自訂檢視器介面以無縫匹配您的應用程式主題。