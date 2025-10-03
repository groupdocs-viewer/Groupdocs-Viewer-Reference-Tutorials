---
"description": "使用 GroupDocs.Viewer 增強您的 .NET 應用程序，實現無縫文件檢視。輕鬆將文件渲染功能整合到您的專案中。"
"linktitle": "設定計量許可證"
"second_title": "GroupDocs.Viewer .NET API"
"title": "設定計量許可證"
"url": "/zh-hant/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# 設定計量許可證

## 介紹
在 .NET 開發領域，將強大的文件檢視功能整合到應用程式中對於提升使用者體驗和功能至關重要。 GroupDocs.Viewer for .NET 提供了一個強大的解決方案，可將文件檢視功能無縫整合到您的 .NET 專案中。無論您處理的是 PDF、Microsoft Office 文件或各種影像格式，GroupDocs.Viewer 都能簡化在應用程式中渲染和顯示這些文件的流程。

![使用 GroupDocs.Viewer for .NET 設定計量許可證](/viewer/getting-started/set-metered-license.png)

## 先決條件
在深入研究 GroupDocs.Viewer for .NET 的實作之前，請確保您已滿足以下先決條件：
### 1. 安裝 GroupDocs.Viewer for .NET
首先，您需要下載並安裝 GroupDocs.Viewer for .NET。您可以找到下載鏈接 [這裡](https://releases.groupdocs.com/viewer/net/)依照提供的安裝說明在您的開發環境中設定庫。
### 2. 取得計量許可證
若要使用 GroupDocs.Viewer for .NET，您需要取得計量許可證。此許可證可讓您根據預先定義的配額控制和監控 API 的使用情況。請依照以下步驟設定您的計量許可證：

## 導入命名空間
首先，請確保匯入必要的命名空間以存取 GroupDocs.Viewer for .NET 提供的功能：
```csharp
using System;
```

現在，讓我們將提供的範例程式碼分解為多個步驟：
## 步驟 1：聲明公鑰和私鑰
聲明變數來儲存您的公鑰和私鑰：
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
確保更換 `"YOUR_PUBLIC_KEY"` 和 `"YOUR_PRIVATE_KEY"` 使用你的真實鑰匙。
## 步驟 2：設定計量許可證
檢查是否提供了公鑰。如果沒有，則提示使用者設定金鑰：
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered。 ");
    return;
}
```
## 步驟3：初始化計量物件並設定許可證
初始化 Metered 物件並使用您的公鑰和私鑰設定計量許可證：
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## 步驟4：確認訊息
顯示許可證設定成功的確認訊息：
```csharp
Console.WriteLine("License set successfully.");
```

## 結論
總而言之，GroupDocs.Viewer for .NET 提供了一個全面的解決方案，將文件檢視功能整合到您的 .NET 應用程式中。按照概述的步驟，您可以輕鬆設定計量許可證，並開始在您的專案中利用 GroupDocs.Viewer 的功能。
## 常見問題解答
### Q：在哪裡可以找到 GroupDocs.Viewer for .NET 的文檔？
您可以找到文檔 [這裡](https://tutorials。groupdocs.com/viewer/net/).
### Q：GroupDocs.Viewer for .NET 有免費試用版嗎？
是的，您可以免費試用 [這裡](https://releases。groupdocs.com/).
### Q：如何取得用於測試目的的臨時許可證？
可以獲得臨時許可證 [這裡](https://purchase。groupdocs.com/temporary-license/).
### Q：我可以在哪裡尋求支援或詢問與 GroupDocs.Viewer for .NET 相關的問題？
您可以在 GroupDocs.Viewer 論壇上尋求支援並提出問題 [這裡](https://forum。groupdocs.com/c/viewer/9).
### Q：我可以在哪裡購買 GroupDocs.Viewer for .NET 的許可證？
您可以購買許可證 [這裡](https://purchase。groupdocs.com/buy).