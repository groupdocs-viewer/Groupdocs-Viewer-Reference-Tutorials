---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer for .NET 高效提取存檔資訊。本指南涵蓋設定、程式碼範例和實際應用。"
"title": "如何使用 GroupDocs.Viewer for .NET 擷取存檔資訊－綜合指南"
"url": "/zh-hant/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
type: docs
---
# 如何使用 GroupDocs.Viewer for .NET 擷取存檔資訊：綜合指南

## 介紹

您是否希望有效率地從 ZIP 等存檔檔案中提取詳細資訊？了解其結構對於文件管理至關重要。本指南將向您展示如何使用 **適用於 .NET 的 GroupDocs.Viewer** 檢索並顯示有關存檔文件的詳細資訊。

![使用 GroupDocs.Viewer for .NET 擷取存檔訊息](/viewer/metadata-properties/retrieve-archive-information.png)

在本教程中，我們將介紹：
- 在 .NET 應用程式中設定 GroupDocs.Viewer
- 從存檔文件中檢索視圖資訊
- 顯示檔案中的資料夾結構

讀完本指南後，您將對如何實現這些功能有深入的了解。在深入研究程式碼之前，我們先了解一下您需要什麼。

### 先決條件

確保您已準備好以下物品：

- **庫和版本**：安裝適用於 .NET 的 GroupDocs.Viewer（版本 25.3.0）。
- **環境設定**：使用適當的.NET 開發環境，如 Visual Studio。
- **知識前提**：對 C# 和 .NET 應用程式中的文件處理有基本的了解。

## 為 .NET 設定 GroupDocs.Viewer

若要使用 GroupDocs.Viewer for .NET，請透過 NuGet 套件管理器安裝它：

### 安裝說明

**NuGet 套件管理器控制台**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 取得許可證

GroupDocs.Viewer 提供多種授權選項：
- **免費試用**：探索基本功能。
- **臨時執照**：評估期間可存取全部功能。
- **購買**：為了長期使用，請考慮購買許可證。

安裝並設定許可證後，請在應用程式中初始化 GroupDocs.Viewer。以下是範例設定：

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // 在此處使用檢視器功能。
}
```

## 實施指南

我們將把實施過程分解為結構化方法的關鍵特徵。

### 檢索存檔文件的視圖資訊

了解檔案庫的結構至關重要。以下是如何實現這一點：

#### 初始化檢視器對象

建立一個實例 `Viewer` 類別與您的存檔檔案路徑：

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // 您的處理代碼將會放在這裡。
}
```

#### 取得視圖資訊

檢索視圖訊息，格式為 JPG 影像：

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### 顯示根資料夾訊息

為了全面概述，請列印根資料夾詳細資訊：

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### 遞歸讀取並列印子資料夾名稱

若要探索檔案中的子資料夾，請使用此遞歸方法：

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### 實際應用

GroupDocs.Viewer for .NET 可用於各種場景：
- **文件管理系統**：自動擷取並顯示檔案結構。
- **內容交付平台**：向使用者提供存檔內容的預覽。
- **數據分析工具**：分析檔案中的資料夾層次結構以取得業務洞察。

與 ASP.NET 或 WPF 等其他框架的整合非常簡單，可以無縫地融入現有系統。

## 性能考慮

為了獲得最佳性能：
- **優化資源使用**：高效率管理記憶體和處理大檔案。
- **記憶體管理最佳實踐**：處理 `Viewer` 對像以便及時釋放資源。

## 結論

在本教學中，您學習如何利用 GroupDocs.Viewer for .NET 從存檔檔案中擷取詳細資訊。實現這些功能可以顯著增強您的文件管理能力。

### 後續步驟

不妨探索 GroupDocs.Viewer 提供的更多進階功能，或將其與應用程式的其他元件整合。嘗試不同的文件類型和複雜的資料夾結構，以加深您的理解。

## 常見問題部分

1. **目的是什麼 `ViewInfoOptions`？**
   - 它配置您想要如何查看文檔，例如呈現 JPG 等特定格式。

2. **如何有效率地處理大型檔案？**
   - 使用記憶體管理技術並適當處理資源。

3. **GroupDocs.Viewer 可以處理受密碼保護的檔案嗎？**
   - 是的，有了正確的許可證和配置，它可以處理加密文件。

4. **可處理的存檔檔案大小有限制嗎？**
   - 此限制取決於系統的記憶體容量；檔案越大，所需的資源就越多。

5. **如何將 GroupDocs.Viewer 與 ASP.NET 應用程式整合？**
   - 在控制器操作或服務中使用 Viewer 類，類似於在控制台應用程式中的操作。

## 資源

- [文件](https://docs.groupdocs.com/viewer/net/)
- [API 參考](https://reference.groupdocs.com/viewer/net/)
- [下載 GroupDocs.Viewer for .NET](https://releases.groupdocs.com/viewer/net/)
- [購買許可證](https://purchase.groupdocs.com/buy)
- [免費試用版](https://releases.groupdocs.com/viewer/net/)
- [臨時執照申請](https://purchase.groupdocs.com/temporary-license/)
- [支援論壇](https://forum.groupdocs.com/c/viewer/9)