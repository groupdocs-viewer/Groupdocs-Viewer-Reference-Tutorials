---
date: '2026-02-05'
description: 了解如何使用 GroupDocs.Viewer 取得 viewinfo 並檢索 Java 壓縮檔類型的結構。本指南涵蓋設定、程式碼範例以及實務案例。
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: 如何在 Java 中取得 ViewInfo 並檢索封存結構
type: docs
url: /zh-hant/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# 如何取得 ViewInfo 並在 Java 中讀取壓縮檔結構

有效管理壓縮檔案需要清楚了解其結構。在本教學中，您將學習 **如何取得 viewinfo** 以檢視任何壓縮檔，並了解它如何協助您處理 **java archive file type**。我們將示範如何設定 GroupDocs.Viewer、擷取檢視資訊，並遞迴讀取資料夾層級，讓您能將此解決方案整合到實際專案中。

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**您將學到的內容**  
- 設定與配置 GroupDocs.Viewer for Java。  
- 從壓縮檔 **取得 viewinfo** 的方法。  
- 讀取與顯示壓縮檔資料夾結構的技巧。  
- 在 Java 專案中使用 GroupDocs.Viewer 的實務應用與效能考量。

## 快速答覆
- **viewinfo 提供什麼資訊？** 它會回傳檔案類型、頁數以及壓縮檔的資料夾清單。  
- **支援哪些壓縮格式？** ZIP、RAR、TAR 以及其他常見格式。  
- **需要授權嗎？** 免費試用可用於評估；正式上線需購買商業授權。  
- **可以處理大型壓縮檔嗎？** 可以——稍後會示範如何使用串流與適當的記憶體管理。  
- **必須使用 Maven 嗎？** Maven 是管理 GroupDocs.Viewer 相依性的推薦方式。

## 什麼是「how to get viewinfo」？
`getViewInfo` 是 GroupDocs.Viewer API 中的一個方法，可在不渲染完整內容的情況下擷取文件或壓縮檔的中繼資料。對於壓縮檔，它會揭示內部資料夾樹狀結構，讓您決定要渲染或進一步處理哪些部分。

## 為何要取得 Java 壓縮檔類型的結構？
了解 **java archive file type**（例如 ZIP、RAR）的內部布局，可讓您：  
- 在不解壓全部內容的前提下快速定位所需檔案。  
- 建立只處理相關子資料夾的自動化流程。  
- 將壓縮檔導覽整合至內容管理或資料匯入系統。

## 前置條件

- **Java Development Kit (JDK)：** 8 版或更新版本。  
- **Maven：** 用於相依性管理與建置。  
- **基本的 Java 知識：** 熟悉 OOP 概念會有幫助，但非必須。

您還需要取得 GroupDocs.Viewer 程式庫，以下示範如何將其加入 Maven 專案。

## 設定 GroupDocs.Viewer for Java

### Maven 設定

將儲存庫與相依性加入 `pom.xml`。

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

**相依性：**  
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

- **免費試用：** 從 GroupDocs 官方網站下載試用版。  
- **臨時授權：** 申請短期評估用的臨時金鑰。  
- **正式授權：** 購買商業授權以獲得無限制的正式環境使用權。

將程式庫加入 classpath 後，即可開始撰寫程式碼。

## 實作指南

### 如何取得壓縮檔的 ViewInfo

本節說明呼叫 `getViewInfo` 並讀取資料夾層級的完整步驟。

#### 初始化 Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### 取得檢視資訊

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 顯示資料夾結構

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 遞迴讀取資料夾

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

### 功能 2：取得壓縮檔資料夾結構

此功能聚焦於列印壓縮檔的資料夾結構，與第一個功能類似，但更強調遞迴探索。

#### 設定 ViewInfo 選項

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 遞迴探索

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 實務應用

1. **資料管理：** 透過了解壓縮檔結構快速整理大型資料集。  
2. **自動化檔案處理：** 在不完整解壓的情況下批次處理壓縮檔。  
3. **CMS 整合：** 為內容管理系統增添即時的壓縮檔導覽功能。

## 效能考量

- **優化記憶體使用：** 一次只處理單層資料夾，並盡快關閉 `Viewer` 實例。  
- **保持更新：** 使用最新的 GroupDocs.Viewer 版本與 JDK 釋出，以獲得效能提升。

## 常見問題與解決方案

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| 讀取資料夾時出現 `NullPointerException` | `viewInfo.getFolders()` 對空目錄回傳 null | 在迭代前先檢查是否為 null 或空集合。 |
| 大型 ZIP 檔處理緩慢 | 整個壓縮檔被載入記憶體 | 使用新版 GroupDocs 提供的串流選項。 |
| 找不到授權 | 授權檔路徑錯誤 | 將授權檔放在應用程式根目錄，或使用 `License.setLicense("path/to/license.json")` 設定路徑。 |

## 常見問答

**Q：什麼是 GroupDocs.Viewer？**  
A：這是一套功能強大的 Java 程式庫，可將文件（包括壓縮檔）渲染成 HTML、影像或 PDF 等格式。

**Q：可以在其他程式語言中使用 GroupDocs.Viewer 嗎？**  
A：可以，GroupDocs 提供多平台 SDK，但本教學僅聚焦於 Java 實作。

**Q：如何處理大型壓縮檔？**  
A：採用有效的記憶體管理方式，必要時將壓縮檔切分處理。

**Q：GroupDocs.Viewer 支援哪些壓縮格式？**  
A：支援多種格式，包括 ZIP、RAR、TAR 等。

**Q：處理壓縮檔的大小有上限嗎？**  
A：上限取決於系統資源，請在目標環境中測試以確定實際可處理的大小。

**Q：「how to get viewinfo」能處理有密碼保護的壓縮檔嗎？**  
A：能，您可在呼叫 `getViewInfo` 前使用 `ArchiveOptions.setPassword("yourPassword")` 提供密碼。

## 結論

透過本指南，您已掌握 **如何取得 viewinfo** 以檢視任何受支援的壓縮檔，並能使用 GroupDocs.Viewer for Java 逐層遍歷其資料夾結構。這些技巧可協助您構建更智慧的資料處理管線、提升 CMS 整合效能，並自信地處理大量壓縮檔。接下來，您可以探索從壓縮檔中渲染單一檔案或使用其他 Viewer 功能將其轉換為 PDF/HTML。

---

**最後更新：** 2026-02-05  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

**資源**  
- **文件說明：** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 參考：** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)  
- **下載 GroupDocs.Viewer：** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **購買授權：** [Buy GroupDocs](https://purchase.groupdocs.com/buy)  
- **免費試用與臨時授權：** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)