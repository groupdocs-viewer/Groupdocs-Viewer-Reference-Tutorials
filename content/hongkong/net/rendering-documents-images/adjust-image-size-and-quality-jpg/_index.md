---
title: 調整影像尺寸和品質 (JPG)
linktitle: 調整影像尺寸和品質 (JPG)
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 Groupdocs.Viewer for .NET 最佳化 JPEG 格式的影像大小和品質。增強您的文件檢視體驗。
weight: 11
url: /zh-hant/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

# 調整影像尺寸和品質 (JPG)

## 介紹
Groupdocs.Viewer for .NET 是一個功能強大的程式庫，使開發人員能夠將文件檢視功能無縫整合到他們的 .NET 應用程式中。文件檢視應用程式中的一項常見要求是能夠調整影像的大小和質量，特別是在處理 JPEG (JPG) 影像時。在本教學中，我們將引導您完成使用 Groupdocs.Viewer for .NET 調整影像大小和品質的過程。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. 對 C# 程式語言有基本了解。
2. Visual Studio 安裝在您的系統上。
3. 安裝了 .NET 函式庫的 Groupdocs.Viewer。您可以從以下位置下載：[這裡](https://releases.groupdocs.com/viewer/net/).

## 導入命名空間
首先，您需要將必要的命名空間匯入到 C# 程式碼中。這些命名空間提供對使用 Groupdocs.Viewer 所需的類別和方法的存取。
## 第 1 步：導入命名空間
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在，讓我們將提供的範例程式碼分解為多個步驟，以便更好地理解。
## 步驟2：設定輸出目錄和頁面檔案路徑格式
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
在此步驟中，我們指定儲存渲染影像的輸出目錄，並定義每個頁面影像的檔案路徑的格式。
## 步驟 3：初始化檢視器並配置 JPG 視圖選項
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
在這裡，我們使用要查看的文檔的路徑初始化 Viewer 物件。然後，我們建立 JpgViewOptions 的實例並設定 JPEG 影像所需的寬度和高度。
## 第 4 步：渲染來源文檔
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後，我們列印一條訊息，指示來源文件已成功渲染以及輸出影像的保存位置。

## 結論
在本教學中，我們學習如何使用 Groupdocs.Viewer for .NET 調整 JPEG 影像的大小和品質。透過執行上述步驟，您可以輕鬆地將此功能合併到您的 .NET 應用程式中，為使用者提供最佳化的影像檢視體驗。
## 常見問題解答
### 我也可以調整影像品質嗎？
是的，您可以透過設定 JpgViewOptions 中的 Quality 屬性來調整影像品質。
### Groupdocs.Viewer for .NET 支援哪些文件格式？
Groupdocs.Viewer for .NET 支援多種文件格式，包括 DOCX、PDF、PPTX、XLSX 等。
### Groupdocs.Viewer for .NET 是否與 .NET Core 相容？
是的，Groupdocs.Viewer for .NET 與 .NET Core 以及傳統的 .NET Framework 相容。
### 我可以自訂輸出檔案命名格式嗎？
是的，您可以透過修改程式碼中的 pageFilePathFormat 變數來自訂輸出檔案命名格式。
### Groupdocs.Viewer for .NET 支援文件註解嗎？
是的，Groupdocs.Viewer for .NET 提供對文件註釋的全面支持，包括文字突出顯示、下劃線和註釋。