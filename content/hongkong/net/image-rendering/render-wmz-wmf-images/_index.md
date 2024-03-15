---
title: 渲染 WMZ 和 WMF 影像
linktitle: 渲染 WMZ 和 WMF 影像
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 在 .NET 應用程式中輕鬆渲染 WMZ 和 WMF 映像。輕鬆增強文件處理能力。
type: docs
weight: 18
url: /zh-hant/net/image-rendering/render-wmz-wmf-images/
---
## 介紹

在軟體開發領域，有效處理和呈現各種文件格式至關重要。 GroupDocs.Viewer for .NET 是一款功能強大的工具，可促進各種文件格式的呈現，確保 .NET 應用程式內的無縫整合和增強的使用者體驗。其功能之一是渲染 WMZ 和 WMF 影像，這是文件處理場景中經常遇到的任務。

## 先決條件

在使用 GroupDocs.Viewer for .NET 深入研究 WMZ 和 WMF 影像的渲染過程之前，需要先滿足幾個先決條件：

1. 安裝 GroupDocs.Viewer for .NET：先從提供的網站下載並安裝 GroupDocs.Viewer for .NET[下載連結](https://releases.groupdocs.com/viewer/net/)。請遵循安裝說明以確保正確設定。

2. 取得許可證：要使用 GroupDocs.Viewer for .NET，您需要取得許可證。您可以選擇從以下機構取得臨時許可證[臨時許可證頁面](https://purchase.groupdocs.com/temporary-license/)或從以下位置購買完整許可證[購買頁面](https://purchase.groupdocs.com/buy).

3. 熟悉 .NET 環境：對 .NET 框架和 C# 程式語言的基本了解對於有效實現渲染過程至關重要。

4. 整合到您的專案中：確保 GroupDocs.Viewer for .NET 正確整合到您的 .NET 專案中。有關整合的詳細說明，請參閱文件：[文件](https://reference.groupdocs.com/viewer/net/).

## 導入命名空間

在繼續渲染過程之前，將必要的命名空間匯入到 C# 程式碼中至關重要。這些命名空間提供對渲染 WMZ 和 WMF 影像所需的類別和方法的存取。

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

現在我們已經介紹了先決條件並導入了所需的命名空間，讓我們將渲染過程分解為多個步驟。

## 步驟 1：將 WMZ 圖像渲染為 HTML

若要將 WMZ 影像渲染為 HTML 格式，請依照下列步驟操作：

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.html");

//至 HTML
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

    viewer.View(options);
}
```

## 步驟 2：將 WMZ 影像渲染為 JPG

若要將 WMZ 影像渲染為 JPG 格式，請依照下列步驟操作：

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.jpg");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 步驟 3：將 WMZ 影像渲染為 PNG

若要將 WMZ 影像渲染為 PNG 格式，請依照下列說明操作：

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.png");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 步驟 4：將 WMZ 影像渲染為 PDF

若要將 WMZ 影像渲染為 PDF 格式，請依照下列步驟操作：

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.pdf");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 結論

總之，GroupDocs.Viewer for .NET 提供了一個全面的解決方案，可以在 .NET 應用程式中輕鬆渲染 WMZ 和 WMF 影像。透過遵循本教學中概述的步驟，您可以將渲染功能無縫整合到您的專案中，從而增強文件處理能力。

## 常見問題解答

### 問題 1：GroupDocs.Viewer for .NET 是否與所有 .NET 框架相容？

A1：GroupDocs.Viewer for .NET 與多種 .NET 框架相容，包括 .NET Core 和 .NET Framework。

### Q2：我可以自訂 WMZ 和 WMF 影像的渲染選項嗎？

A2：是的，GroupDocs.Viewer for .NET 提供了廣泛的用於渲染圖像的自訂選項，可讓您根據您的要求自訂輸出。

### 問題 3：GroupDocs.Viewer for .NET 是否提供技術支援？

 A3：是的，您可以透過專用的 GroupDocs.Viewer for .NET 獲得技術支持[支援論壇](https://forum.groupdocs.com/c/viewer/9).

### 問題 4：GroupDocs.Viewer for .NET 支援在行動裝置上檢視文件嗎？

A4：是的，GroupDocs.Viewer for .NET 提供響應式文件檢視功能，確保在各種裝置（包括手機和平板電腦）上達到最佳效能。

### Q5：我可以在購買前試用 GroupDocs.Viewer for .NET 嗎？

 A5：是的，您可以透過造訪可用的免費試用版來探索 GroupDocs.Viewer for .NET 的功能[這裡](https://releases.groupdocs.com/).