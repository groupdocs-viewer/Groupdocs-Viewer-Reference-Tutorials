---
date: '2026-06-05'
description: 了解如何使用 GroupDocs Viewer for Java 將 docx 轉換為 jpeg，涵蓋設定、配置以及實務影像渲染。
keywords:
- convert docx to jpeg
- convert word to image
- GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  headline: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  name: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  steps:
  - name: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
    text: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
  - name: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
    text: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
  - name: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
    text: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
  type: HowTo
- questions:
  - answer: '`DocumentSplitter` allows you to divide a large document into separate
      parts for easier processing. Split the source file into smaller sections using
      `DocumentSplitter` before rendering, or process pages in sequential batches
      to keep memory usage low.'
    question: How do I handle documents larger than 500 pages?
  - answer: Yes, replace `JpgViewOptions` with `PngViewOptions` and adjust the file‑path
      pattern accordingly.
    question: Can I output PNG instead of JPEG?
  - answer: A free trial license works for evaluation and development, but a commercial
      license is required for production deployments.
    question: Is a license mandatory for development builds?
  - answer: Absolutely. Pass the password to the `Viewer` constructor to unlock the
      document before rendering.
    question: Does the library support password‑protected DOCX files?
  - answer: GroupDocs.Viewer for Java is compatible with Java 8, 11, and 17.
    question: What Java versions are supported?
  type: FAQPage
title: 如何使用 GroupDocs Viewer for Java 將 DOCX 轉換為 JPEG
type: docs
url: /zh-hant/java/rendering-basics/groupdocs-viewer-java-render-docx-to-image/
weight: 1
---

# 將 DOCX 轉換為 JPEG（使用 GroupDocs Viewer for Java）

將 **DOCX 轉換為 JPEG** 可讓您以輕量圖像的形式分享文件頁面，且在瀏覽器和電子郵件客戶端中顯示一致。本文將說明如何使用 **GroupDocs.Viewer for Java** 將 Word 檔案轉換為高品質 JPEG 圖片、自訂尺寸，並有效管理資源。

![使用 GroupDocs.Viewer for Java 渲染 DOCX 為圖像](/viewer/rendering-basics/render-docx-to-image.png)

[使用 GroupDocs.Viewer for Java 渲染 DOCX 為圖像](/viewer/rendering-basics/render-docx-to-image.png)

## 快速解答
- **哪個程式庫負責 DOCX → JPEG 轉換？** GroupDocs.Viewer for Java。  
- **需要多少行程式碼？** 只需兩行即可載入並渲染檔案。  
- **我可以設定自訂圖像尺寸嗎？** 可以，透過 `JpgViewOptions` 您可以定義寬度和高度。  
- **生產環境是否需要授權？** 需要商業授權；亦提供免費試用。  
- **它能處理大型文件嗎？** 能，處理最多 500 頁的檔案，同時將記憶體使用量控制在 200 MB 以下。

## 什麼是「將 docx 轉換為 jpeg」？

將 DOCX 檔案轉換為 JPEG 會為每一頁產生一張圖像，保留原始版面配置、字型與圖形。每張 JPEG 可在瀏覽器中顯示、嵌入電子郵件，或作為縮圖使用。此格式輕量、支援廣泛，適合在不需要 Microsoft Word 或額外外掛的情況下預覽文件。

## 為什麼使用 GroupDocs Viewer for Java 進行此轉換？

GroupDocs.Viewer 支援 **超過 50 種輸入與輸出格式**，且可在標準伺服器硬體上於 **每頁 2 秒內** 渲染最多 **500 頁** 的文件。API 無需安裝 Microsoft Office，即可保證版面一致性與低記憶體佔用。

## 先決條件
- **Java Development Kit** 8 或更新版本。  
- **Maven** 用於相依性管理（或手動加入 JAR）。  
- **GroupDocs.Viewer for Java** 程式庫（可從官方網站下載）。  
- 熟悉 Java 專案結構的基本知識。

## 設定 GroupDocs Viewer for Java

要將程式庫加入 Maven 專案，請在 `pom.xml` 中插入以下相依性：

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

### 取得授權
GroupDocs 提供免費試用以探索功能。若需長期使用，請透過官方網站取得臨時或正式授權。

## 如何將 DOCX 轉換為 JPEG？

`Viewer` 類別負責讀取文件並提供渲染功能。  
`JpgViewOptions` 用於設定 JPEG 輸出參數，如尺寸、品質與檔名模式。

要執行轉換，只需以 DOCX 路徑建立 `Viewer` 實例，建立指向輸出資料夾的 `JpgViewOptions`，可選擇設定尺寸與品質，最後呼叫 `viewer.view(options)`。程式庫會逐頁處理並依指定命名規則儲存 JPEG 檔案。

## 實作指南

### 將 DOCX 渲染為 JPEG

將 Word 文件轉換為 JPEG 圖片，以供預覽或分享使用。

#### 逐步實作

**1. 設定輸出目錄**  
定義儲存已渲染 JPEG 的資料夾：

```java
import com.groupdocs.viewer.Viewer;

public class DocumentRenderer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Configuration and rendering logic goes here
        }
    }
}
```

**2. 指定檔案路徑格式**  
建立包含頁碼的命名模式，例如 `page_{0}.jpg`：

```java
import java.nio.file.Path;

// Define output directory using Path API
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("rendered_document");
```

**3. 設定圖像選項**  
`JpgViewOptions` 讓您設定寬度、高度與品質。例如 1024 × 768 像素、90 % 品質：

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**4. 渲染文件**  
使用 try‑with‑resources 區塊確保 `Viewer` 實例自動關閉，釋放原生資源並防止記憶體洩漏：

```java
import com.groupdocs.viewer.options.JpgViewOptions;

// Create JpgViewOptions with specified path format
JpgViewOptions viewOptions = new JpgViewOptions(pageFilePathFormat);

// Set custom width and height for each image
viewOptions.setWidth(600);  // Image width in pixels
viewOptions.setHeight(800); // Image height in pixels
```

### 常見問題與解決方案
- **檔案路徑問題** – 確認輸出目錄已存在且應用程式具有寫入權限。  
- **記憶體管理** – 對於超過 300 頁的文件，建議分批處理頁面，並在每批後呼叫 `System.gc()`。  
- **不支援的元素** – 某些進階 Word 功能（例如嵌入巨集）在渲染時會被忽略，且不會影響視覺輸出。

## 實務應用

1. **預覽產生** – 在內容管理系統中顯示文件縮圖，無需完整檢視器。  
2. **電子郵件附件** – 將每頁 JPEG 嵌入郵件，以避免附件大小限制。  
3. **網頁顯示** – 將頁面渲染為圖像，適合低頻寬環境快速載入。

## 效能考量

- **資源管理** – 始終使用 try‑with‑resources 關閉 `Viewer`。  
- **圖像尺寸** – 較小的尺寸可降低 RAM 使用量；選擇符合視覺品質需求的最小尺寸。  
- **非同步處理** – 大量轉換時，將渲染任務放在獨立執行緒池中，以保持 UI 響應。

## 常見問題

**Q: 如何處理超過 500 頁的文件？**  
A: 可使用 `DocumentSplitter` 將大型文件分割為多個較小的部分以便處理。先使用 `DocumentSplitter` 將來源檔案切分，或以順序批次方式處理頁面，以降低記憶體使用。

**Q: 可以輸出 PNG 而非 JPEG 嗎？**  
A: 可以，將 `JpgViewOptions` 換成 `PngViewOptions`，並相應調整檔案路徑模式。

**Q: 開發版是否必須購買授權？**  
A: 評估與開發階段可使用免費試用授權，但正式上線需購買商業授權。

**Q: 程式庫是否支援受密碼保護的 DOCX 檔案？**  
A: 完全支援。只要在 `Viewer` 建構子中傳入密碼，即可在渲染前解鎖文件。

**Q: 支援哪些 Java 版本？**  
A: GroupDocs.Viewer for Java 相容於 Java 8、11 與 17。

## 資源

- **文件說明**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 參考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **下載頁面**: [Download Page](https://releases.groupdocs.com/viewer/java/)
- **購買授權**: [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **免費試用**: [Try GroupDocs for Free](https://releases.groupdocs.com/viewer/java/)
- **臨時授權**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **支援論壇**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-06-05  
**測試環境：** GroupDocs.Viewer 23.12 for Java  
**作者：** GroupDocs

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 將 DOCX 檔案轉換為 PNG](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)
- [如何使用 GroupDocs.Viewer for Java 將 DOCX 轉換為 HTML：逐步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer 在 Java 中從 InputStream 渲染 DOCX 檔案](/viewer/java/rendering-basics/render-docx-from-inputstream-groupdocs-viewer-java/)