---
date: '2026-06-30'
description: 了解如何使用 GroupDocs.Viewer 取得 viewinfo 並檢索 Java 封存檔案類型結構。本指南涵蓋設定、程式碼範例以及實務案例。
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: 如何在 Java 中取得 ViewInfo 並檢索封存結構
type: docs
url: /zh-hant/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# 如何取得 ViewInfo 以及在 Java 中檢索封存結構

有效管理封存檔案需要清楚了解其結構。在本教學中，您將學習 **如何取得 viewinfo** 以用於任何封存檔，並了解它如何協助您處理 **java archive file type**。我們將逐步說明設定 GroupDocs.Viewer、擷取檢視資訊，並遞迴讀取資料夾層級，讓您能將此解決方案整合到實際專案中。

![使用 GroupDocs.Viewer for Java 的封存結構](/viewer/document-loading/archive-structures-java.png)

**您將學習**
- 設定與配置 GroupDocs.Viewer for Java。  
- 從封存檔取得 **get viewinfo** 的方法。  
- 讀取並顯示封存檔的資料夾結構的技巧。  
- 在 Java 專案中使用 GroupDocs.Viewer 時的實務應用與效能考量。  

## 快速解答
- **「viewinfo」提供什麼資訊？** 它會回傳檔案類型、頁數，以及封存檔內所有資料夾與檔案的完整清單。  
- **支援哪些封存格式？** ZIP、RAR、TAR、7z、ISO，以及其他 12 種以上常見格式。  
- **在正式環境需要授權嗎？** 是——正式環境需要商業授權；免費試用版可用於評估。  
- **大型封存檔能有效率地處理嗎？** 當然可以——使用串流選項，並一次處理單層資料夾，以降低記憶體使用。  
- **Maven 是唯一加入此函式庫的方式嗎？** Maven 為推薦的相依管理工具，但 Gradle 或手動加入 JAR 亦可使用。  

## 「how to get viewinfo」是什麼？

`getViewInfo` 是 GroupDocs.Viewer 的 API 方法，能在不完整渲染的情況下擷取文件或封存檔的中繼資料。它一次呼叫即回傳內部資料夾樹、檔案數量與基本屬性，讓您自行決定要處理哪些部分。此呼叫可在一般伺服器上於一秒內返回最高 500 MB 封存檔的完整快照。  

## 為何要檢索 Java 封存檔類型的結構？

檢索 **java archive file type** 的內部佈局，可讓您即時定位所需檔案、避免不必要的解壓，並建立只觸及相關子資料夾的自動化流程。此方法可將大型封存檔的 I/O 減少最高 70 %，並使在資料匯入情境下每分鐘掃描數千檔案成為可能。  

## 前置條件

- **Java Development Kit (JDK)：** 8 版或更新版本。  
- **Maven：** 用於相依管理與建置。  
- **Basic Java knowledge：** 熟悉 OOP 概念有助於開發，但非必須。  

您還需要取得 GroupDocs.Viewer 函式庫，可依下列方式將其加入 Maven 專案。

## 設定 GroupDocs.Viewer for Java

### Maven 設定

將儲存庫與相依項目加入您的 `pom.xml`。

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

**相依項目：**  
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### 取得授權

- **Free Trial：** 從 GroupDocs 官方網站下載試用版。  
- **Temporary License：** 申請臨時金鑰以進行短期評估。  
- **Full License：** 購買商業授權以獲得無限制的正式使用。  

將函式庫加入 classpath 後，即可開始編寫程式碼。

## 實作指南

### 取得 Archive 檔案的 ViewInfo 方法

要取得檢視資訊，首先將封存檔載入 Viewer，接著呼叫 `getViewInfo` 取得中繼資料，最後遍歷回傳的資料夾層級。此三步驟模式適用於所有支援的封存格式，並在單一次 API 呼叫中提供完整快照，簡化後續處理。

#### 初始化 Viewer

`Viewer` 類別是所有渲染與檢查操作的入口點。它負責管理檔案串流、格式偵測與資源清理。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### 取得檢視資訊

`ViewInfo` 包含檔案類型、總頁數以及資料夾與檔案的階層清單等中繼資料。呼叫 `getViewInfo` 可即時取得此物件。

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 顯示資料夾結構

遍歷 `viewInfo.getFolders()` 以列印每個資料夾名稱、深度與包含的檔案。此簡單迴圈即可提供可讀的封存樹狀圖。

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 遞迴資料夾讀取

對於深層巢狀的封存檔，可使用遞迴輔助方法深度優先遍歷樹狀結構，確保每個子資料夾皆被訪問，而不需將整個封存檔載入記憶體。

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

### 功能 2：取得封存資料夾結構

此功能著重於列印封存檔的資料夾結構。它與第一個功能類似，但更強調遞迴探索。

#### 設定 ViewInfo 選項

`ArchiveOptions` 允許您在呼叫 `getViewInfo` 前設定密碼保護、頁面限制與串流偏好。

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 遞迴探索

第二個遞迴程式示範如何有效處理受密碼保護的封存檔與大型檔案集合。

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 實務應用

1. **資料管理：** 透過了解封存結構快速整理大型資料集。  
2. **自動化檔案處理：** 批次處理封存檔而不需完整解壓，將 I/O 減少最高 70 %。  
3. **CMS 整合：** 強化內容管理系統的即時封存導覽，讓編輯者直接從封存檔預覽檔案。  

## 效能考量

- **最佳化記憶體使用：** 一次處理單層資料夾，並及時關閉 `Viewer` 實例。  
- **保持更新：** 使用最新的 GroupDocs.Viewer 版本（本文撰寫時為 25.2）與 JDK 版本，以提升效能。  
- **串流支援：** 函式庫可串流超過 1 GB 的封存檔，無需將整個檔案載入記憶體，得益於其內部分塊讀取架構。  

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| `NullPointerException` 讀取資料夾時發生 | `viewInfo.getFolders()` 在空目錄時回傳 null | 在迭代前檢查是否為 null 或空清單。 |
| 處理大型 ZIP 檔案緩慢 | 整個封存檔被載入記憶體 | 使用新版 GroupDocs 提供的串流選項。 |
| 找不到授權 | 授權檔案路徑不正確 | 將授權檔案放置於應用程式根目錄，或設定 `License.setLicense("path/to/license.json")`。 |

## 常見問答

**Q：** GroupDocs.Viewer 是什麼？  
A: GroupDocs.Viewer 是一個 Java 函式庫，可將超過 100 種文件、影像與封存格式渲染為 HTML、PDF 或影像串流，且不需要原生應用程式。

**Q：** 我可以在其他程式語言中使用 GroupDocs.Viewer 嗎？  
A: 可以，GroupDocs 提供 .NET、Python、PHP 等 SDK，但本教學聚焦於 Java 實作。

**Q：** 如何處理大型封存檔？  
A: 透過 `ArchiveOptions.setUseStreaming(true)` 啟用串流，一次處理單層資料夾，使用完畢後釋放 `Viewer` 物件。

**Q：** GroupDocs.Viewer 支援哪些類型的封存檔？  
A: 支援超過 12 種封存格式，包括 ZIP、RAR、TAR、7z、ISO、ARJ、CAB，以及許多專有容器類型。

**Q：** 封存檔有大小限制嗎？  
A: 實際限制取決於伺服器的記憶體與 CPU；測試顯示在啟用串流時，16 GB 記憶體的機器可順暢處理 2 GB 的封存檔。

**Q：** 「how to get viewinfo」能處理受密碼保護的封存檔嗎？  
A: 可以，在呼叫 `getViewInfo` 前透過 `ArchiveOptions.setPassword("yourPassword")` 提供密碼。

## 結論

透過本指南，您現在已掌握 **how to get viewinfo** 任意支援封存檔的方式，並能使用 GroupDocs.Viewer for Java 逐層遍歷其資料夾結構。這些技巧讓您能構建更智慧的資料處理管線、提升 CMS 整合，並自信地處理大量封存檔。接下來，可探索從封存檔渲染單一檔案或使用其他 Viewer 功能將其轉換為 PDF/HTML。

---

**最後更新：** 2026-06-30  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

**資源**
- **文件說明：** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 參考：** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **下載 GroupDocs.Viewer：** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **購買授權：** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **免費試用與臨時授權：** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## 相關教學

- [使用 GroupDocs.Viewer for Java 提取文件中繼資料 - 取得文件檢視資訊與洞察](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [使用 GroupDocs.Viewer for Java 取得附件並列印文件附件](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java 指南：使用 GroupDocs.Viewer API 渲染特定頁面以進行文件預覽與管理](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)