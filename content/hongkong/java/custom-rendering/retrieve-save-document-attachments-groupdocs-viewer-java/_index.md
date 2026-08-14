---
date: '2026-06-30'
description: 了解如何在 Java 應用程式中使用 Java 檔案輸出串流與功能強大的 GroupDocs.Viewer API，有效地取得並儲存文件附件。
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: 如何使用 Java 檔案輸出串流與 GroupDocs.Viewer for Java 取得並儲存文件附件
type: docs
url: /zh-hant/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# 如何使用 java file output stream 與 GroupDocs.Viewer for Java 取得並儲存文件附件

## 介紹

您是否希望在 Java 應用程式中以 **java file output stream** 程式化地提取與管理文件附件？隨著數位文件管理的興起，擁有能有效簡化這些流程的工具變得至關重要。GroupDocs.Viewer for Java 正是您的首選解決方案，可輕鬆取得並儲存文件附件。

![使用 GroupDocs.Viewer for Java 取得並儲存文件附件](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[使用 GroupDocs.Viewer for Java 取得並儲存文件附件](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

在本教學中，我們將探討如何利用 GroupDocs.Viewer 從文件中取得附件並將其儲存至指定目錄。跟隨步驟，您將學會在 Java 環境中有效管理文件資料，並且會看到如何使用標準的 `java file output stream` **儲存附件** 檔案。

## 快速解答
- **java file output stream 的作用是什麼？** 它直接將位元組流寫入檔案，使二進位資料（如附件）能儲存至磁碟。  
- **哪個 API 取得附件？** `Viewer.getAttachments()` 會回傳附件中繼資料的清單。  
- **我可以指定輸出資料夾嗎？** 可以 — 使用 `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`。  
- **是否需要授權？** 免費試用可用於評估；正式環境需要付費授權。  
- **此方法是執行緒安全的嗎？** 每個執行緒建立獨立的 `Viewer` 實例，或對存取進行同步。

## 什麼是 java file output stream？
`java.io.FileOutputStream` 是 Java 核心類別，用於將原始位元組寫入檔案。當您需要持久化二進位內容（如電子郵件附件、影像或任何非文字資料）時，它是理想選擇。它支援高效寫入大小檔案，並可與緩衝串流結合以提升效能，確保二進位負載可靠地寫入磁碟。

## 為什麼在 GroupDocs.Viewer 中使用 java file output stream？
將 `java.io.FileOutputStream` 與 GroupDocs.Viewer 結合，可讓開發者直接將附件位元組寫入磁碟，無需任何中間轉換步驟，保留原始檔案完整性。此方式降低記憶體消耗、加速大型附件處理，並透過標準 Java I/O 與 GroupDocs.Viewer 強大的提取功能簡化程式碼。

- **直接二進位處理** – 無需中間轉換；附件位元組會如原始檔案般寫入。  
- **效能** – 串流寫入可最小化記憶體開銷，特別是大型附件。  
- **簡潔** – API 與標準 Java I/O 無縫整合，使程式碼易於閱讀與維護。

## 前置條件
- **必要的函式庫與相依性**：將 GroupDocs.Viewer 函式庫加入專案（請參考下方 Maven 片段）。  
- **環境設定**：安裝 JDK 8 以上的 Java IDE（IntelliJ IDEA、Eclipse 等）。  
- **知識前提**：熟悉 Java I/O，特別是 `FileOutputStream`，以及基本的 Maven 使用方式。

## 設定 GroupDocs.Viewer for Java
要在專案中使用 GroupDocs.Viewer API，必須透過 Maven 安裝。將以下設定加入 `pom.xml` 檔案：

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
- **免費試用**：先取得免費試用以探索功能。  
- **臨時授權**：取得臨時授權以延長評估期間。  
- **購買**：正式環境需購買授權。

### 基本初始化與設定
將 GroupDocs.Viewer 加入相依性後，即可在 Java 應用程式中初始化。範例如下：

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
讓我們分步說明如何使用 GroupDocs.Viewer 取得附件。此功能可提取文件中每個附件的中繼資料。

#### 概觀
取得附件的流程是呼叫 `getAttachments` 方法，該方法回傳 `Attachment` 物件清單，內含檔名、大小等資訊。**Attachment** 代表嵌入於來源文件中的檔案，例如影像或內嵌檔案。

#### 實作步驟
1. **建立 Viewer 實例**  
   `Viewer` 是 GroupDocs.Viewer 的主要類別，用於載入與處理文件以進行渲染與提取。以文件路徑初始化 `Viewer` 類別：

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
   - `Viewer`：接受文件路徑或串流作為輸入。  
   - `getAttachments()`：回傳附件檔案清單，提供名稱等細節。

### 將文件附件儲存至目錄
現在您已學會如何取得附件，接下來使用 GroupDocs.Viewer API 與 **java file output stream** 將它們儲存至指定目錄。

#### 概觀
此功能會將每個取得的附件檔案寫入預先設定的輸出目錄。

#### 實作步驟
1. **定義輸出目錄**  
   設定 `outputDirectory` 路徑，以便儲存檔案：

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **儲存附件**  
   使用迴圈呼叫 `saveAttachment` 方法將每個附件寫入磁碟。**saveAttachment** 會將 `Attachment` 的二進位內容寫入提供的 `OutputStream`。

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
   - `FileOutputStream`：使用 **java file output stream** 語意管理寫入檔案的資料。

## 如何使用 java file output stream 儲存附件？
載入每個 `Attachment` 物件，為目標檔案開啟 `FileOutputStream`，並直接將附件位元組串流寫入磁碟。此方式會完整寫入原始二進位負載，確保儲存的檔案與原附件逐位相同。對於大型附件，可將串流包裹於 `BufferedOutputStream` 以提升吞吐量並減少 I/O 呼叫。**BufferedOutputStream** 會緩衝寫入，減少 I/O 操作次數，提升大型檔案的效能。

### 常見問題與解決方案
- **缺少相依性**：確保已正確加入所有 Maven 相依性。  
- **檔案路徑錯誤**：再次確認文件與輸出目錄的路徑。  
- **存取權限**：驗證應用程式具備必要的讀寫權限。  

## 實務應用
在 Java 中使用 GroupDocs.Viewer 可在多種情境下發揮關鍵作用：

1. **電子郵件客戶端** – 自動從郵件存檔中提取附件以進行處理或歸檔。  
2. **文件管理系統 (DMS)** – 透過取得與組織附件檔案，提升 DMS 功能。  
3. **法務部門** – 安全地從法律文件中提取證據相關附件。  

與 CRM、ERP 或自訂工作流程引擎的整合，亦可進一步簡化業務流程，使附件處理在各部門間無縫銜接。

## 效能考量
使用 GroupDocs.Viewer 時的效能最佳化建議：

- **優化檔案處理** – 大檔案使用緩衝串流，並及時關閉資源。  
- **記憶體管理** – 盡快釋放 `Viewer` 實例（使用 try‑with‑resources），避免記憶體洩漏。  
- **量化效益** – GroupDocs.Viewer 可處理高達 500 MB 的文件，且每檔案可支援多達 200 個附件，同時在標準 8 GB JVM 上將記憶體使用量控制在 150 MB 以下。

遵循 Java 最佳實踐，將顯著提升附件處理管線的效率。

## 結論
您現在已了解如何使用 **java file output stream** 搭配 GroupDocs.Viewer for Java 取得並儲存文件附件。此強大 API 簡化了文件資料的管理，是開發者處理數位文件的必備工具。欲進一步探索 GroupDocs.Viewer 功能，可嘗試其其他特性——如渲染頁面、格式轉換或文字提取。如有任何問題或需要支援，歡迎透過官方資源聯繫我們。

## 常見問答

**Q: 如何在我的 Java 專案中安裝 GroupDocs.Viewer？**  
A: 只需將前述的 Maven 相依性加入 `pom.xml`，使用提供的倉庫 URL 與版本，即可快速開始。

**Q: GroupDocs.Viewer 能處理所有文件類型嗎？**  
A: 它支援超過 50 種輸入與輸出格式，包括 PDF、DOCX、PPTX、MSG 以及多種影像格式，涵蓋大多數商務常見檔案。

**Q: 若在儲存附件時發生錯誤，該怎麼辦？**  
A: 請確認輸出路徑正確、目錄已存在，且程式具有寫入權限。同時確保依照範例正確使用 `FileOutputStream`。

**Q: 生產環境是否需要授權？**  
A: 是的，正式部署必須使用有效的 GroupDocs.Viewer 授權。可先使用免費試用進行評估。

**Q: 此方法能處理大型附件檔案嗎？**  
A: 使用 **java file output stream** 搭配緩衝 I/O 可有效處理大型二進位檔案；若檔案超過 200 MB，建議分塊串流以監控記憶體使用。

---

**最後更新：** 2026-06-30  
**測試版本：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs  

---

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 取得附件並列印文件附件](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [使用 GroupDocs.Viewer Java 將文件附件渲染為 HTML：一步步指南](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [自訂渲染處理程式 Java – GroupDocs Viewer 教學](/viewer/java/custom-rendering/)