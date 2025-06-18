---
"date": "2025-04-24"
"description": "學習如何使用 Java 中的 GroupDocs.Viewer 有效地擷取歸檔結構。請遵循本指南，輕鬆設定、取得程式碼範例和實際應用。"
"title": "如何使用 GroupDocs.Viewer for Java 擷取檔案結構－綜合指南"
"url": "/zh-hant/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/"
"weight": 1
---

# 如何使用 GroupDocs.Viewer for Java 擷取檔案結構

## 介紹

有效管理歸檔文件需要清楚了解其結構。本指南內容詳盡，示範如何使用 Java 中的 GroupDocs.Viewer 程式庫擷取歸檔檔案資訊（包括資料夾結構）。掌握這些技巧，您將簡化資料管理流程並提高工作效率。

**您將學到什麼：**
- 為 Java 設定和配置 GroupDocs.Viewer。
- 從檔案中檢索視圖資訊的方法。
- 讀取和顯示存檔檔案的資料夾結構的技術。
- 在 Java 專案中使用 GroupDocs.Viewer 時的實際應用和效能考量。

讓我們先介紹使用 GroupDocs.Viewer for Java 實作這些功能之前所需的先決條件。

## 先決條件

要遵循本教程，請確保您已具備：

- **Java 開發工具包 (JDK)：** 您的機器上安裝了版本 8 或更高版本。
- **Maven：** 用於管理依賴項和專案建置。
- **Java 程式設計的基本理解：** 熟悉物件導向的程式設計概念將會很有幫助。

此外，透過為你的專案添加特定的儲存庫和依賴項，使用 Maven 將 GroupDocs.Viewer 庫包含在你的專案中 `pom.xml` 文件。

## 為 Java 設定 GroupDocs.Viewer

若要開始使用 GroupDocs.Viewer 和 Java，請依照下列步驟操作：

### Maven配置

將以下內容新增至您的 Maven 設定檔：

**儲存庫：**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**依賴項：**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### 許可證獲取

- **免費試用：** 從 GroupDocs 網站下載免費試用版即可開始使用。
- **臨時執照：** 如果您需要不受限制地延長存取權限，請申請臨時許可證。
- **購買許可證：** 考慮購買長期項目的完整許可證。

配置完成後，透過匯入必要的類別並設定基本的檢視器實例，使用 GroupDocs.Viewer 初始化您的專案。

## 實施指南

### 功能 1：取得存檔檔案的檢視訊息

此功能示範如何使用 GroupDocs.Viewer 擷取存檔檔案的詳細資訊。它涉及初始化 Viewer 類別、指定視圖選項以及提取檔案類型和頁數。

#### 初始化檢視器

首先創建一個 `Viewer` 實例與您的目標存檔檔路徑：

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // 接下來將執行其他步驟。
}
```

#### 檢索視圖資訊

使用 `getViewInfo()` 使用 HTML 視圖選項來取得存檔文件的詳細資訊：

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 顯示資料夾結構

若要探索檔案中的資料夾結構，請呼叫遞歸方法：

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 遞歸資料夾讀取

此輔助方法使用 `ViewInfoOptions` 指定資料夾視圖並遞歸讀取子資料夾：

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### 功能 2：檢索存檔資料夾結構

此功能專注於列印存檔檔案的資料夾結構。它與第一個功能類似，但更側重於遞歸探索。

#### 設定視圖資訊選項

配置 `ViewInfoOptions` 使用特定資料夾：

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 遞迴探索

此方法遍歷子資料夾，列印每個子資料夾並以遞歸方式進行更深入的探索：

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 實際應用

1. **數據管理：** 透過了解檔案結構來快速組織大型資料集。
2. **自動文件處理：** 使用此技術自動處理批次作業中的存檔檔案。
3. **與 CMS 系統整合：** 透過整合 GroupDocs.Viewer 來增強內容管理系統，實現高效率的文件處理。

## 性能考慮

- **優化記憶體使用：** 透過明智地管理資源來有效地處理大型檔案，尤其是在處理大量或相當大的文件時。
- **最佳實踐：** 定期更新到最新版本的庫和 JDK 以利用效能改進。

## 結論

透過本教學課程，您學習如何有效地使用 GroupDocs.Viewer for Java 來擷取和管理檔案結構。這項技能在涉及資料組織和處理的各種應用中都非常有用。接下來，您可以考慮探索 GroupDocs.Viewer 庫的其他功能，或將這些技術整合到更大的專案中。

## 常見問題部分

**Q：什麼是 GroupDocs.Viewer？**
答：它是一個強大的 Java 庫，用於將文件（包括檔案）呈現為 HTML、圖像和 PDF 等不同格式。

**Q：我可以將 GroupDocs.Viewer 與其他程式語言一起使用嗎？**
答：是的，GroupDocs 為多個平台提供 SDK，但本教學重點在於 Java 實作。

**Q：如何處理大型存檔檔案？**
答：使用高效率的記憶體管理方法，並在必要時考慮分解檔案。

**Q：GroupDocs.Viewer 支援哪些類型的檔案？**
答：它支援多種格式，包括 ZIP、RAR、TAR 等。

**Q：我可以處理的檔案大小有限制嗎？**
答：具體限制取決於您的系統資源。請務必根據具體環境進行測試。

## 資源

- **文件:** [GroupDocs 檢視器 Java 文檔](https://docs.groupdocs.com/viewer/java/)
- **API 參考：** [Java 版 GroupDocs API 參考](https://reference.groupdocs.com/viewer/java/)
- **下載 GroupDocs.Viewer：** [GroupDocs 下載頁面](https://releases.groupdocs.com/viewer/java/)
- **購買許可證：** [購買 GroupDocs](https://purchase.groupdocs.com/buy)
- **免費試用和臨時許可證：** [GroupDocs 免費試用](https://releases.groupdocs.com/viewer/java/) | [臨時執照](https://purchase.groupdocs.com/temporary-license/)

在您的專案中嘗試以下步驟，以增強您的 Java 應用程式使用 GroupDocs.Viewer 處理存檔檔案的能力。祝您編碼愉快！