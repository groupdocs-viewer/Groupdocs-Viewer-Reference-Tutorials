---
date: '2026-08-08'
description: 了解如何使用 GroupDocs.Viewer for Java 將 IGS 轉換為 PDF、HTML、JPG 及 PNG。提供逐步指南、先決條件與
  Java 開發人員的疑難排解。
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: 使用 GroupDocs.Viewer for Java 將 IGS 轉換為 PDF、HTML、JPG 及 PNG。提供詳細設定、程式碼範例與
  Java 開發人員的疑難排解。
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: 使用 GroupDocs.Viewer Java 將 IGS 轉換為 PDF、HTML、JPG 及 PNG
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: 使用 GroupDocs.Viewer Java 將 IGS 轉換為 PDF、HTML、JPG 及 PNG
type: docs
url: /zh-hant/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# 使用 GroupDocs.Viewer Java 將 IGS 轉換為 PDF、HTML、JPG 與 PNG

![使用 GroupDocs.Viewer for Java 將 IGS 檔案轉換為 HTML、JPG、PNG 與 PDF](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 快速解答
- **我可以使用 Java 將 IGS 轉換為 PDF 嗎？** 是的，請使用 `PdfViewOptions` 搭配 `Viewer` API。  
- **支援哪些輸出格式？** HTML、JPG、PNG 與 PDF 均為原生支援。  
- **生產環境需要授權嗎？** 需要商業授權；免費試用可測試核心功能。  
- **需要哪個 Java 版本？** JDK 8 或以上；此函式庫亦支援 Java 11、17 及更高版本。  
- **加入函式庫只能使用 Maven 嗎？** 不是，亦可使用 Gradle 或手動將 JAR 檔加入 classpath。

## 什麼是將 IGS 轉換為 PDF？
將 IGS 轉換為 PDF 即是把中性 3‑D CAD 檔案轉換為靜態、可在任何平台檢視的文件。這讓您能與沒有 CAD 工具的利害關係人分享設計視覺、將渲染嵌入報告，或將模型存檔以符合合規需求。

## 為何使用 GroupDocs.Viewer 進行 IGS 轉換？
GroupDocs.Viewer 可在不需任何外部 CAD 軟體的情況下處理 IGS 檔案。它支援 **50+ 種輸入與輸出格式**，能渲染包含 **數百個零件** 的組件，同時將記憶體使用量控制在 **200 MB** 以下，且在標準伺服器上對一般模型的處理時間不超過 **2 秒**。這些可量化的優勢使其成為企業流程中高效能且具成本效益的選擇。

## 前置條件
- **GroupDocs.Viewer for Java** ≥ 25.2（最新穩定版）。  
- **JDK 8+** 已安裝並在您的 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）中配置。  
- 基本的 Maven 知識（非必須，但建議用於相依管理）。

## 設定 GroupDocs.Viewer for Java

### Maven 相依設定
在您的 `pom.xml` 中加入 GroupDocs 儲存庫與 Viewer 相依設定：

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
GroupDocs.Viewer 提供三種授權選項：
- **免費試用** – 使用受限，適合快速概念驗證測試。  
- **臨時授權** – 完整功能，適用於短期評估，適合試點專案。  
- **商業授權** – 無限制的生產使用，包含優先支援與更新。

### 基本 Viewer 初始化
`Viewer` 類別是所有渲染操作的入口。它載入來源檔案、解析格式，並提供產生所需輸出的各種方法。

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## 將 IGS 渲染為 HTML

### 如何將 IGS 轉換為 HTML？
使用 `Viewer` 實例載入 IGS 檔案，並傳入包含所有必要資源的 `HtmlViewOptions` 物件。此呼叫會回傳單一 HTML 檔，內含完整的 3‑D 觀景，方便嵌入網頁。您亦可透過設定頁面大小、背景顏色、是否包含互動控制等選項自訂渲染。  
`HtmlViewOptions` 用於設定 HTML 輸出的產生方式，包括資源嵌入與頁面版面配置。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 將 IGS 渲染為 JPG

### 如何將 IGS 轉換為 JPG？
建立 `JpgViewOptions` 物件，設定所需的解析度與壓縮品質，然後讓 `Viewer` 為模型的每一頁產生點陣圖。產生的 JPG 檔可儲存至指定目錄，您亦可調整品質參數以在檔案大小與視覺保真度之間取得平衡，這對縮圖或高解析度列印皆很有用。  
`JpgViewOptions` 指定 JPG 圖像產生的設定，如解析度、品質與輸出目錄。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 將 IGS 渲染為 PNG

### 如何將 IGS 轉換為 PNG？
`PngViewOptions` 類別讓您產生具可選透明度的無損圖像。此格式非常適合在行銷素材中將模型覆蓋於彩色背景上。您亦可設定解析度與背景顏色以符合品牌指南，確保所有產出資產外觀一致。  
`PngViewOptions` 定義 PNG 渲染的參數，包括解析度、透明度與背景顏色。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 將 IGS 渲染為 PDF

### 如何將 IGS 轉換為 PDF？
使用 `PdfViewOptions` 產生分頁的 PDF，保留 3‑D 模型的視覺版面配置。您亦可嵌入字型並控制頁面大小，以符合企業品牌指南。其他設定允許您指定影像品質、壓縮等級，以及是否為多頁組件加入目錄。  
`PdfViewOptions` 控制 PDF 的建立，提供頁面大小、影像品質與字型嵌入等設定。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 實務應用
- **Web 入口網站** – 直接將 HTML 渲染的模型嵌入產品配置器，讓客戶可在不安裝外掛的情況下旋轉與縮放。  
- **行銷素材** – 產生高解析度的 JPG/PNG 圖像，用於手冊、簡報與社群媒體貼文。  
- **技術文件** – 在使用手冊中加入 CAD 模型的 PDF 渲染，確保工程師可離線檢視設計。  
- **品質保證** – 為數千個 IGS 檔自動產生縮圖，加速視覺檢查工作流程。

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| **找不到輸出資料夾** | 確認傳遞給 `Path outputDirectory` 的路徑，並確保 Java 程序對目標資料夾具有寫入權限。 |
| **PDF 出現空白頁** | 確認來源 IGS 檔案未損毀；先在原生 CAD 檢視器中開啟檢查。 |
| **大型組件渲染緩慢** | 增加 JVM 堆積記憶體 (`-Xmx2g` 或更高) 並考慮使用 `viewer.getPageCount()` 逐頁渲染以分批處理。 |
| **PDF 缺少字型** | 使用 `PdfViewOptions` 嵌入所需字型，或在提供轉換服務的伺服器上安裝缺失的字型。 |

## 常見問答

**問：我可以在一次執行中轉換多個 IGS 檔案嗎？**  
答：可以。遍歷檔案路徑集合，並在同一個 `Viewer` 實例中對每個檔案呼叫相應的 `view` 方法。

**問：可以自訂 PDF 頁面大小嗎？**  
答：當然可以。`PdfViewOptions` 提供 `setPageSize(PageSize.A4)`、`PageSize.Letter`，以及透過 `setCustomSize(width, height)` 設定自訂尺寸。

**問：每種輸出格式需要單獨授權嗎？**  
答：不需要。單一的 GroupDocs.Viewer 授權涵蓋所有支援的格式，包括 HTML、JPG、PNG 與 PDF。

**問：IGS 檔案多大會影響效能？**  
答：此函式庫可穩定處理最高 **500 MB** 的檔案；若模型超過 200 MB，請分配更多 JVM 記憶體，並考慮分批渲染。

**問：我能只渲染特定視圖或方向嗎？**  
答：GroupDocs.Viewer 會渲染 IGS 檔案中定義的預設方向。若需自訂視圖，請先使用 CAD 工具前處理檔案或在轉換前調整模型。

---

**最後更新：** 2026-08-08  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

## 相關教學

- [使用 GroupDocs.Viewer Java 將 cdr 轉換為 html、jpg、png、pdf](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [如何在 Java 中使用 GroupDocs.Viewer 將 pdf 轉換為 html 並優化影像品質](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)