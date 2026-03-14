---
date: '2026-02-23'
description: 了解如何使用 GroupDocs.Viewer for Java 將 IGS 轉換為 PDF、HTML、JPG 和 PNG。請跟隨本逐步指南，內含可直接執行的程式碼範例。
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: 使用 GroupDocs.Viewer Java 將 IGS 轉換為 PDF、HTML、JPG 與 PNG
type: docs
url: /zh-hant/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

 we kept all headings.

Now produce final answer.# 轉換 IGS 為 PDF、HTML、JPG 與 PNG（使用 GroupDocs.Viewer Java）

如果您需要直接從 Java 應用程式 **convert IGS to PDF**（或轉換為 HTML、JPG、PNG），您來對地方了。在本教學中，我們將一步步說明您所需的全部內容——從設定函式庫到以符合您專案的格式呈現 3‑D 模型。您將了解為何 GroupDocs.Viewer 是快速、可靠轉換的理想選擇，並取得可直接套用於您解決方案的實作程式碼。

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 快速答覆
- **Can I convert IGS to PDF with Java?** 是的，使用 GroupDocs.Viewer 的 `PdfViewOptions`。
- **Which output formats are supported?** 支援 HTML、JPG、PNG 與 PDF。
- **Do I need a license for production?** 需要商業授權；亦提供免費試用供測試使用。
- **What Java version is required?** 需要 JDK 8 或更高版本。
- **Is Maven the only way to add the library?** 不是，您也可以使用 Gradle 或手動加入 JAR。

## 什麼是 “convert IGS to PDF”？

將 IGS（用於 3‑D CAD 資料的中性檔案格式）轉換為 PDF，即把複雜的 3‑D 模型轉換成靜態且廣泛可檢視的文件。此方式適合與沒有 CAD 工具的利害關係人分享設計稿。

## 為何使用 GroupDocs.Viewer 進行 IGS 轉換？

- **Zero‑code CAD rendering** – 此函式庫負責解析 IGS 格式的繁重工作。  
- **Multiple output options** – 單一次 API 呼叫即可產生 HTML、JPG、PNG 或 PDF。  
- **Cross‑platform** – 可在任何支援 Java 的作業系統上執行。  
- **Performance‑focused** – 即使是大型組件亦能快速渲染。

## 前置條件
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** 已安裝並在您的 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）中設定。  
- 基本的 Maven 知識（非必須，但建議具備）

## 設定 GroupDocs.Viewer for Java

### Maven 相依性

將 GroupDocs 儲存庫與 Viewer 相依性加入您的 `pom.xml`：

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

GroupDocs.Viewer 提供：
- **Free trial** – 使用量受限，適合快速測試。  
- **Temporary license** – 在短期評估期間提供完整功能。  
- **Commercial license** – 生產環境無限制使用。

### 基本 Viewer 初始化

以下程式碼片段示範如何建立指向您的 IGS 檔案的 `Viewer` 實例：

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

## 將 IGS 轉換為 HTML

### 如何將 IGS 轉換為 HTML？

HTML 輸出可為您提供可互動、適合瀏覽器檢視的 3‑D 模型。

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

**Key point:** `HtmlViewOptions.forEmbeddedResources()` 會將所有必要的資源（CSS、圖片）直接嵌入 HTML 檔案，使其具備可攜性。

## 將 IGS 轉換為 JPG

### 如何將 IGS 轉換為 JPG？

JPG 圖像非常適合作為縮圖或快速預覽。

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

您可以調整 `JpgViewOptions` 以控制解析度與壓縮品質。

## 將 IGS 轉換為 PNG

### 如何將 IGS 轉換為 PNG？

PNG 支援透明度，方便將模型覆蓋於不同背景上。

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

可嘗試使用 `PngViewOptions` 以取得檔案大小與視覺品質之最佳平衡。

## 將 IGS 轉換為 PDF

### 如何將 IGS 轉換為 PDF？

PDF 是分享詳細設計文件的首選格式。本節直接針對主要關鍵字 **convert IGS to PDF** 進行說明。

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

`PdfViewOptions` 讓您可控制頁面佈局、影像品質，以及是否嵌入字型。

## 實務應用

- **Web portals** – 將 HTML 渲染的模型直接嵌入產品配置器中。  
- **Marketing assets** – 為手冊產生高解析度的 JPG/PNG 圖像。  
- **Technical documentation** – 在使用手冊中加入 CAD 模型的 PDF 渲染圖。  
- **Quality assurance** – 為大量 IGS 檔案自動產生縮圖。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **找不到輸出資料夾** | 確認傳遞給 `Path outputDirectory` 的路徑，並確保 Java 程序具有寫入權限。 |
| **PDF 中出現空白頁** | 確保 IGS 檔案未損壞；可先在 CAD 檢視器中開啟測試。 |
| **大型組件渲染緩慢** | 增加 JVM 堆積記憶體（`-Xmx2g` 或更高），必要時考慮使用 `viewer.getPageCount()` 逐頁渲染。 |
| **PDF 缺少字型** | 使用 `PdfViewOptions` 嵌入所需字型，或在伺服器上安裝缺少的字型。 |

## 常見問答

**Q: 我可以在一次執行中轉換多個 IGS 檔案嗎？**  
A: 是的。遍歷檔案路徑清單，對每個檔案呼叫相應的 `view` 方法。

**Q: 是否可以自訂 PDF 頁面大小？**  
A: 當然可以。`PdfViewOptions` 提供 `setPageSize(PageSize.A4)` 等方法。

**Q: 每種輸出格式都需要單獨的授權嗎？**  
A: 不需要。單一 GroupDocs.Viewer 授權即可涵蓋所有支援的格式。

**Q: IGS 檔案多大會影響效能？**  
A: 函式庫可處理數百 MB 的檔案，但對於非常大的模型，可能需要分配更多 JVM 記憶體。

**Q: 我能只渲染特定視圖或方向嗎？**  
A: GroupDocs.Viewer 會渲染預設視圖。若需自訂方向，請在轉換前使用 CAD 工具先行處理 IGS 檔案。

---

**最後更新：** 2026-02-23  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs