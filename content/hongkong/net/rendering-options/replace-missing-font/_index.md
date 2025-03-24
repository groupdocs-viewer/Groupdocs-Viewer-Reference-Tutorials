---
title: 替換遺失的字體
linktitle: 替換遺失的字體
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer 輕鬆取代 .NET 文件中缺少的字型。透過簡單的步驟確保準確的渲染。
weight: 20
url: /zh-hant/net/rendering-options/replace-missing-font/
---

# 替換遺失的字體

## 介紹
在 .NET 開發領域，高效率的文件處理至關重要。 GroupDocs.Viewer for .NET 提供了一個強大的解決方案，用於在 .NET 應用程式中查看各種文件格式。在本教學中，我們將探討如何使用 GroupDocs.Viewer for .NET 取代文件中遺失的字型。無論您是處理 PDF、PowerPoint 簡報或 Word 文檔，GroupDocs.Viewer 都能簡化流程，確保即使在字體缺失的情況下也能準確呈現文檔。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
1. GroupDocs.Viewer for .NET：從網站下載並安裝 GroupDocs.Viewer 函式庫](https://releases.groupdocs.com/viewer/net/）。
2. 開發環境：建置.NET開發環境，例如Visual Studio。
3. 基本 C# 知識：熟悉 C# 程式語言和 .NET 架構。

## 導入命名空間
在 C# 程式碼中，匯入必要的命名空間以存取 GroupDocs.Viewer 功能。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在，讓我們逐步完成使用 GroupDocs.Viewer for .NET 取代文件中缺少字體的過程。
## 第 1 步：定義輸出目錄
```csharp
string outputDirectory = "Your Document Directory";
```
設定保存渲染文檔頁面的目錄。
## 步驟2：定義頁面檔案路徑格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
指定輸出 HTML 檔案的命名格式。在此範例中，每個頁面都將儲存為 HTML 文件，命名約定為「page_{page_number}.html」。
## 第 3 步：初始化檢視器對象
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
初始化 Viewer 類別的新實例，將文件檔案（在本例中為缺少字體的 PowerPoint 簡報）的路徑作為參數傳遞。
## 第 4 步：設定 HTML 視圖選項
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
建立 HtmlViewOptions 的實例並將其配置為在 HTML 輸出中嵌入資源。指定預設字體名稱以替換遺失的字體。
## 第5步：渲染文檔
```csharp
viewer.View(options);
```
呼叫 Viewer 物件的 View 方法，傳遞 HTML 視圖選項。這將使用指定的選項呈現文件頁面。
## 步驟6：顯示輸出路徑
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
列印一條訊息，指示文件已成功呈現，並提供保存輸出 HTML 文件的路徑。

## 結論
在本教學中，我們學習如何使用 GroupDocs.Viewer for .NET 來取代文件中遺失的字型。透過執行這些步驟，即使某些字體不可用，您也可以確保準確呈現文件。 GroupDocs.Viewer 簡化了該過程，使您可以專注於建立強大的 .NET 應用程序，而不必擔心字體相容性問題。
## 常見問題解答
### GroupDocs.Viewer 可以處理其他類型的字體相關問題嗎？
是的，GroupDocs.Viewer 提供了各種與字體相關的功能，包括字體替換和字體檢測。
### GroupDocs.Viewer 是否與所有 .NET 框架相容？
GroupDocs.Viewer 支援廣泛的 .NET 框架，包括 .NET Core 和 .NET Standard。
### 我可以自訂 GroupDocs.Viewer 中的預設字體替換嗎？
當然，您可以指定您選擇的任何字體作為缺失字體的預設替換。
### GroupDocs.Viewer是否支援文件的批次處理？
是的，GroupDocs.Viewer 允許您同時處理多個文檔，非常適合批次場景。
### 在哪裡可以找到有關 GroupDocs.Viewer 的進一步協助或支援？
您可以造訪 GroupDocs.Viewer 論壇[這裡](https://forum.groupdocs.com/c/viewer/9)如有任何幫助或支援查詢。