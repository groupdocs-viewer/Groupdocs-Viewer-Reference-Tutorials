---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer for .NET 將 PDF 頁面轉換為 PNG 映像，同時保留原始尺寸。本指南涵蓋設定、配置和最佳實務。"
"title": "使用 GroupDocs.Viewer for .NET 將 PDF 轉換為原始大小的 PNG"
"url": "/zh-hant/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# 使用 GroupDocs.Viewer for .NET 將 PDF 轉換為原始大小的 PNG

## 介紹

將 PDF 文件轉換為 PNG 圖像並保持原始頁面大小對於高品質文件數位化或網頁內容準備至關重要。本教學將指導您使用 GroupDocs.Viewer for .NET 將 PDF 頁面渲染為 PNG 文件，並保留其原始尺寸。

![使用 GroupDocs.Viewer for .NET 將 PDF 轉換為原始大小的 PNG](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**您將學到什麼：**
- 如何在您的專案中設定和設定 GroupDocs.Viewer for .NET
- 將 PDF 渲染為 PNG 圖像並保持頁面大小的逐步過程
- 實現最佳效能的關鍵配置選項和最佳實踐

在本教程結束時，您將能夠將此功能無縫整合到您的應用程式中。讓我們從入門的必要條件開始。

## 先決條件

在您的專案中實作 GroupDocs.Viewer for .NET 之前，請確保您符合以下要求：

### 所需的庫和版本
- **適用於 .NET 的 GroupDocs.Viewer**：版本 25.3.0 或更高版本。

### 環境設定要求
- 相容的開發環境，例如 Visual Studio。
- 對 C# 程式設計有基本的了解。

### 知識前提
- 熟悉NuGet套件管理。
- 具有在 .NET 應用程式中處理 PDF 和影像處理的一些經驗。

一旦滿足這些先決條件，我們就可以繼續設定 GroupDocs.Viewer for .NET。

## 為 .NET 設定 GroupDocs.Viewer

若要開始使用 GroupDocs.Viewer for .NET，請依照下列安裝步驟操作：

### 透過 NuGet 套件管理器控制台安裝
在 Visual Studio 中開啟您的專案並使用以下命令：
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### 透過 .NET CLI 安裝
或者，您可以使用以下命令透過 .NET CLI 安裝它：
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 許可證取得步驟
1. **免費試用**：從下載試用版 [GroupDocs 下載](https://releases。groupdocs.com/viewer/net/).
2. **臨時執照**：取得臨時許可證以探索完整功能 [臨時許可證頁面](https://purchase。groupdocs.com/temporary-license/).
3. **購買**：如需延長使用時間，請透過 [購買頁面](https://purchase。groupdocs.com/buy).

### 基本初始化和設定
若要在 C# 專案中初始化 GroupDocs.Viewer for .NET，請依照下列步驟操作：
1. 導入必要的命名空間：
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. 設定輸入 PDF 和輸出目錄的路徑。
3. 初始化 `Viewer` 使用來源文檔的路徑，如下段所示：
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## 實施指南
本節介紹如何將 PDF 頁面渲染為 PNG 影像並保持其原始大小。

### 將 PDF 頁面渲染為具有原始頁面大小的 PNG
#### 概述
此功能可讓您將 PDF 文件的每一頁渲染為 PNG 影像，並保留其原始尺寸。這對於需要精確呈現文件視覺效果的應用程式尤其有用。

##### 步驟 1：設定路徑並初始化檢視器
為輸入 PDF 路徑和輸出目錄建立變數：
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
初始化 `Viewer` 類別與您的來源文件路徑：
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // 程式碼區塊將在下一步繼續
}
```
##### 步驟2：設定PngViewOptions
建立一個實例 `PngViewOptions`，指定輸出影像的檔案命名模式：
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
配置檢視器選項以按原始大小呈現每個頁面：
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### 步驟3：渲染文件頁面
致電 `View` 方法 `Viewer` 實例，傳入配置的視圖選項：
```csharp
viewer.View(viewOptions);
```
### 故障排除提示
- 確保路徑正確且目錄存在。
- 驗證您是否具有從輸入目錄讀取和寫入輸出目錄所需的權限。

## 實際應用
1. **文件數位化**：將檔案 PDF 文件轉換為數位影像，以便於存取和分發。
2. **入口網站**：無需 PDF 閱讀器即可在網站上顯示文件預覽。
3. **內容管理系統（CMS）**：與 CMS 平台集成，高效管理和顯示大量 PDF 內容。

## 性能考慮
若要使用 GroupDocs.Viewer for .NET 最佳化應用程式的效能：
- 如果處理大文件，則透過分塊處理文件來限制記憶體使用量。
- 盡可能使用非同步方法來避免在渲染期間阻塞執行緒。
- 處置 `Viewer` 實例使用後立即釋放資源。

## 結論
在本教學中，您學習如何使用 GroupDocs.Viewer for .NET 將 PDF 頁面渲染為 PNG 影像，同時保持其原始大小。我們介紹如何設定環境、配置必要的選項以獲得最佳效果，並探討了此功能的實際應用。

下一步包括試驗 GroupDocs.Viewer 中可用的其他渲染選項或將其整合到更大的專案中以增強文件管理功能。

## 常見問題部分
1. **使用 GroupDocs.Viewer 處理大型 PDF 檔案的最佳方法是什麼？**
   - 以較小的區塊處理文件並使用非同步方法來保持效能。
2. **我可以自訂輸出 PNG 檔案名稱嗎？**
   - 是的，透過指定命名模式 `PngViewOptions`。
3. **是否可以僅呈現特定頁面？**
   - 當然，你可以配置 `PageNumbers` 在 `PngViewOptions` 指定要呈現哪些頁面。
4. **如何處理 GroupDocs.Viewer 的授權？**
   - 選項包括免費試用、臨時許可證或購買完整許可證。
5. **這個設定可以在 Web 應用程式中使用嗎？**
   - 是的，它適用於 ASP.NET Core 和其他基於 .NET 的 Web 框架中的伺服器端 PDF 渲染。

## 資源
- [文件](https://docs.groupdocs.com/viewer/net/)
- [API 參考](https://reference.groupdocs.com/viewer/net/)
- [下載 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [購買許可證](https://purchase.groupdocs.com/buy)
- [免費試用](https://releases.groupdocs.com/viewer/net/)
- [臨時執照](https://purchase.groupdocs.com/temporary-license/)
- [支援論壇](https://forum.groupdocs.com/c/viewer/9)