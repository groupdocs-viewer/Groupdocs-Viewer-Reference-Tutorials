---
date: '2026-02-02'
description: 學習如何在 Java 應用程式中使用 Java 檔案輸出串流及功能強大的 GroupDocs.Viewer API，高效檢索與儲存文件附件。
keywords:
- GroupDocs.Viewer Java
- retrieve document attachments Java
- save document attachments GroupDocs
title: 如何使用 Java 檔案輸出串流與 GroupDocs.Viewer for Java 取得並儲存文件附件
type: docs
url: /zh-hant/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# 如何使用 java file output stream 與 GroupDocs.Viewer for Java 取得並儲存文件附件

## 介紹

您是否希望在 Java 應用程式中以 **java file output stream** 程式化地提取與管理文件附件？隨著數位文件管理的興起，擁有能有效簡化這些流程的工具變得至關重要。GroupDocs.Viewer for Java 正是您的首選解決方案，能輕鬆無縫地取得與儲存文件附件。

![使用 GroupDocs.Viewer for Java 取得並儲存文件附件](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

在本教學中，我們將探討如何利用 GroupDocs.Viewer 從文件中取得附件並儲存至 Java stream 的作用是什麼？** 它直接將位元組流寫入檔案，使二進位資料（如附件）能儲。**費授權。  
- **此方法是執行緒安全的嗎？** 請為每個執行緒建立獨立的 `Viewer` 實例，或使用同步機制。

## 什麼是 java file output stream？
`java.io.FileOutputStream` 是 Java 的核心類別，用於將原始位元組寫入檔案。當您需要持久化二進位內容（例如電子郵件附件、影像或任何 為什麼在 GroupDocs.Viewer 中使用 java file output stream？
- **直接換；附件的位元組會完整寫入，與原始檔案完全一致。  
- **效能** – 串流寫入可減少記憶體開銷，特別是處理大型附件時。  
- **簡易性** – API 能與標準 Java I/O 無縫結合，使程式碼易於閱讀與維護。

## 前置條件
- **必要的函式庫與相依性**：將 GroupDocs.Viewer 函式庫加入專案（請參考下方 Maven 片段）。  
- **環境設定**：安裝 JDK 8 以上的 Java IDE（如 IntelliJ IDEA、Eclipse 等）。  
- **知識前提**：熟悉 Java I/O，特別是 `FileOutputStream`，以及基本的 Maven 使用方式。

## 設定 GroupDocs.Viewer for Java
要在專案中開始使用 GroupDocs.Viewer API，需透過 Maven 安裝。請在 `pom.xml` 檔案中加入以下設定：

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

**取得授權步驟：**
- **免費試用**：先使用免費試用版以探索功能。  
- **臨時授權**：取得臨時授權以延長評估期間。  
- **購買**：正式上線時需購買授權。

### 基本初始化與設定
將 GroupDocs.Viewer 加入相依性後，即可在 Java 應用程式中初始化。以下為示範：

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

此基本設定會初始化 GroupDocs.Viewer，並為取得附件做好準備。

## 實作指南

### 使用 java file output stream 取得附件
讓我們一步步說明如何使用 GroupDocs.Viewer 取得附件。此功能可提取文件中每個附件的中繼資料。

#### 概觀
取得附件需要呼叫 `getAttachments` 方法，該方法會回傳 `Attachment` 物件清單，內含檔名、大小等資訊。

#### 實作步驟
1. **建立 Viewer 實例**  
   使用文件路徑初始化 `Viewer` 類別：

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **取得附件**  
   呼叫 `getAttachments` 方法：

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **了解參數與方法**  
   - `Viewer`：接受文件路徑或串流作為文件來源。  
   - `getAttachments()`：取得附件檔案清單，提供檔名等詳細資訊。

### 將文件附件儲存至目錄
現在您已了解如何取得附件，接下來使用 GroupDocs.Viewer API 以及 **java file output stream** 將它們儲存至指定目錄。

#### 概觀
此功能會將每個取得的附件檔案儲存至指定的輸出目錄。

#### 實作步驟
1. **定義輸出目錄**  
   設定 `outputDirectory` 路徑以儲存檔案：

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **儲存附件**  
   使用迴圈搭配 `saveAttachment` 方法儲存每個附件：

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **說明參數與方法**  
   - `saveAttachment`：接受 `Attachment` 物件與檔案輸出串流，以儲存附件。  
   - `FileOutputStream`：使用 **java file output stream** 的語意管理資料寫入檔案。

### 疑難排解技巧
- **缺少相依性**：確認已正確加入所有 Maven 相依性。  
- **檔案路徑錯誤**：再次確認文件與輸出目錄的路徑是否正確。  
- **存取權限**：確保應用程式具備必要的讀寫權限。

## 實務應用
使用 GroupDocs.Viewer 在 Java 中可在多種情境下發揮關鍵作用：
1. **電子郵件客戶端** – 自動從郵件封存中提取附件，以進行處理或歸檔。  
2. **文件管理系統** – 透過取得與整理附件檔案，提升 DMS 功能。  
3. **法務部門** – 安全地從法律文件中提取與證據相關的附件。

與 CRM、ERP 或自訂工作流程引擎的整合，可進一步簡化業務流程，使附件處理在各部門之間無縫銜接。

## 效能考量
使用 GroupDocs.Viewer 時，為提升效能可考慮以下做法：
- **優化檔案處理** – 對大型檔案使用緩衝串流，並及時關閉資源。  
- **記憶體管理** – 立即釋放 `Viewer` 實例（使用 try‑with‑resources），避免記憶體洩漏。

遵java file output提取迎透過官方資源聯繫我們。

## 常見問題

**Q: 如何在我的 Java 專案中安裝 GroupDocs.Viewer？**  
A: 加入前述的 Maven 相依性；只需提供儲存庫 URL**  
A: 它支援多種格式（PDF、DOCX、MSG 等），完整清單請參閱官方文件。

**Q: 若在儲存附件時發生錯具備寫入權限。同時確保如範例所示正確使用 `FileOutputStream`。

**Q: 正式上線是否需要授權？**  
A: 是的，正式部署必須擁有可先使用免費試用版進行評估。

**Q: 此方法能處理大型附件檔案嗎？**  
A: 結合 **java file output stream** 與緩衝 I/O 可有效處理大型二進位檔案。請監控記憶體使用情況，必要時可分測試環境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs