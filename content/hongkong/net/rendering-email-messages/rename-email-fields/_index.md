---
title: 在渲染期間重命名電子郵件字段
linktitle: 在渲染期間重命名電子郵件字段
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 增強文件檢視體驗。無縫渲染和自訂電子郵件。
weight: 12
url: /zh-hant/net/rendering-email-messages/rename-email-fields/
---

# 在渲染期間重命名電子郵件字段

## 介紹

在當今的數位時代，有效管理和查看文件對於企業和個人來說至關重要。無論是合約、報告或電子郵件，能夠無縫瀏覽這些文件都可以大大提高工作效率。這就是 GroupDocs.Viewer for .NET 發揮作用的地方。這個強大的程式庫允許開發人員將文件檢視功能直接整合到他們的 .NET 應用程式中，提供用於呈現各種文件格式的廣泛功能。

## 先決條件

在深入了解使用 GroupDocs.Viewer for .NET 進行渲染期間重命名電子郵件欄位的教學之前，請確保您符合以下先決條件：

1.  GroupDocs.Viewer for .NET 函式庫：從下列位置下載並安裝 GroupDocs.Viewer for .NET 函式庫[這裡](https://releases.groupdocs.com/viewer/net/).

2. 開發環境：確保您擁有適合 .NET 開發的開發環境，例如 Visual Studio。

3. C# 的基本了解：熟悉 C# 程式語言的基礎知識，因為本教學將涉及 C# 程式碼片段。

4. 文件目錄：準備一個目錄，用來存放要渲染的文件。

## 導入命名空間

為了在 .NET 應用程式中使用 GroupDocs.Viewer 功能，您需要匯入必要的命名空間。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

現在，讓我們將使用 GroupDocs.Viewer for .NET 在渲染期間重新命名電子郵件欄位的過程分解為多個步驟：

## 第 1 步：定義輸出目錄

首先，指定已儲存渲染的 HTML 頁面的目錄。

```csharp
string outputDirectory = "Your Document Directory";
```

## 步驟2：定義頁面檔案路徑格式

定義所呈現的 HTML 頁面的檔案路徑的格式。每個頁面將儲存為單獨的 HTML 檔案。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 第 3 步：初始化檢視器對象

建立 Viewer 類別的實例，並將要查看的文件的路徑作為參數傳遞。

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## 步驟 4：配置 HTML 視圖選項

配置 HTML 視圖的選項，包括指定輸出檔案格式和設定電子郵件欄位對應。

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## 第5步：渲染文檔

呼叫 Viewer 物件的 View 方法，傳遞配置的 HTML 視圖選項。

```csharp
viewer.View(options);
```

## 步驟6：顯示成功訊息

通知使用者文件已成功呈現。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

總之，GroupDocs.Viewer for .NET 提供了在 .NET 應用程式中呈現文件的無縫解決方案。透過遵循本教學中概述的步驟，您可以在渲染期間輕鬆重命名電子郵件字段，從而增強電子郵件文件的可讀性和可用性。憑藉其直覺的 API 和全面的功能，GroupDocs.Viewer 使開發人員能夠有效地簡化文件檢視流程。

## 常見問題解答

### Q：我可以使用 GroupDocs.Viewer for .NET 呈現電子郵件以外的文件嗎？

答：是的，GroupDocs.Viewer 支援渲染各種文件格式，包括 PDF、Microsoft Office 文件、圖片等。

### Q：GroupDocs.Viewer 與 .NET Core 相容嗎？

答：是的，GroupDocs.Viewer 支援 .NET Core 以及傳統的 .NET Framework。

### Q：我可以自訂渲染文檔的外觀嗎？

答：當然，GroupDocs.Viewer 提供了廣泛的自訂選項來控制渲染文件的外觀和行為。

### Q：GroupDocs.Viewer 是否支援文件流？

答：是的，GroupDocs.Viewer 允許將文件直接串流到客戶端的瀏覽器，而無需將它們儲存在伺服器上。

### Q：GroupDocs.Viewer 適合企業級應用程式嗎？

答：當然，GroupDocs.Viewer 旨在以其可擴展性、可靠性和強大的功能集滿足企業級應用程式的需求。
