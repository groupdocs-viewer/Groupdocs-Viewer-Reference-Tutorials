---
title: 渲染選定的頁面
linktitle: 渲染選定的頁面
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 Groupdocs.Viewer for .NET 從文件中呈現選定的頁面。包含程式碼範例的逐步教學。
weight: 17
url: /zh-hant/net/rendering-options/render-selected-pages/
---

# 渲染選定的頁面

## 介紹

在本教學中，我們將深入研究如何利用 Groupdocs.Viewer for .NET 呈現文件中的選定頁面。無論您是經驗豐富的開發人員還是剛起步，本逐步指南都將引導您輕鬆完成整個過程。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

### 1. 安裝

確保您的開發環境中安裝了 Groupdocs.Viewer for .NET。如果沒有，您可以從以下位置下載[下載連結](https://releases.groupdocs.com/viewer/net/).

## 導入命名空間

在 C# 程式碼檔案中，匯入必要的命名空間以存取所需的類別和方法。您可以使用`using`指示：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在讓我們將提供的範例程式碼分解為多個步驟：

## 第1步：設定輸出目錄

定義要儲存渲染頁面的目錄。代替`"Your Document Directory"`與所需的目錄路徑。

```csharp
string outputDirectory = "Your Document Directory";
```

## 步驟2：定義頁面檔案路徑格式

指定渲染頁面的檔案路徑的格式。這將用於將每個頁面儲存為輸出目錄中的 HTML 檔案。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 第 3 步：實例化檢視器對象

建立 Viewer 類別的實例，並將要呈現的文件的路徑作為參數傳遞。

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 步驟 4：配置 HTML 視圖選項

設定用於渲染的 HTML 視圖選項。在此範例中，我們配置選項以將資源嵌入 HTML 輸出中。

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 第 5 步：渲染選定頁面

指定要呈現的頁碼。在本例中，我們將渲染頁面 1 到 3。然後，呼叫 Viewer 物件上的 View 方法，將選項和頁碼作為參數傳遞。

```csharp
viewer.View(options, 1, 3);
```

## 第六步：輸出結果

最後，顯示一則訊息，指示文件渲染成功以及輸出檔案的儲存位置。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

恭喜！您已成功學習如何使用 Groupdocs.Viewer for .NET 從文件中呈現選定的頁面。有了這些知識，您現在可以輕鬆地將文件渲染功能整合到您的 .NET 應用程式中。

## 常見問題解答

### Q：我可以渲染不同類型文件（例如 PDF 或圖像）的頁面嗎？

答：是的，Groupdocs.Viewer for .NET 支援渲染各種文件格式的頁面，包括 PDF、Microsoft Office 文件和圖片檔案。

### Q：購買前是否有試用版可供測試？

答：是的，您可以從以下位置存取 Groupdocs.Viewer for .NET 的免費試用版：[網站](https://releases.groupdocs.com/).

### Q：我可以自訂 HTML 以外的輸出格式嗎？

答：當然，除了 HTML 之外，Groupdocs.Viewer for .NET 還提供將頁面呈現為圖像、PDF 等的選項。

### Q：如何取得用於測試目的的臨時許可證？

答：臨時許可證可以從[臨時許可證頁面](https://purchase.groupdocs.com/temporary-license/)在 Groupdocs 網站上。

### Q：我可以在哪裡尋求幫助或遇到任何問題時獲得幫助？

答：您可以訪問[Groupdocs.Viewer 論壇](https://forum.groupdocs.com/c/viewer/9)尋求社區和開發者的支持和指導。