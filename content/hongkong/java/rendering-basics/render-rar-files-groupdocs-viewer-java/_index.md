---
"date": "2025-04-24"
"description": "了解如何使用 GroupDocs.Viewer for Java 將 RAR 檔案轉換為 HTML、JPG、PNG 和 PDF 等易於存取的格式。本逐步指南涵蓋了從設定到渲染特定資料夾的所有內容。"
"title": "使用 GroupDocs.Viewer for Java 將 RAR 檔案渲染為 HTML、JPG、PNG 和 PDF"
"url": "/zh-hant/java/rendering-basics/render-rar-files-groupdocs-viewer-java/"
"weight": 1
---

# 使用 GroupDocs.Viewer for Java 將 RAR 檔案渲染為各種格式

使用 GroupDocs.Viewer for Java 將 RAR 檔案轉換為 HTML、JPG、PNG 和 PDF 等易於存取的格式，釋放其潛力。本教學將引導您完成每個步驟，實現無縫的文件管理和簡報。

## 您將學到什麼
- 使用 GroupDocs.Viewer for Java 將 RAR 檔案呈現為多種格式。
- 將 RAR 轉換為 HTML、JPG、PNG 和 PDF 的逐步程式碼範例。
- 從 RAR 檔案中擷取視圖資訊。
- 呈現 RAR 檔案中的特定資料夾。

讓我們開始吧！

### 先決條件
在開始之前，請確保您具備以下條件：

1. **Java 開發工具包 (JDK)**：需要版本 8 或更高版本。
2. **Maven**：本教學使用 Maven 進行依賴管理。
3. **GroupDocs.Viewer Java 函式庫**：我們將使用 25.2 版本。

#### 環境設定
- 確保您的開發環境已安裝 JDK 和 Maven。
- 熟悉基本的 Java 程式設計概念將幫助您更輕鬆地跟進。

### 為 Java 設定 GroupDocs.Viewer
若要將 GroupDocs.Viewer 整合到您的專案中，請在您的 `pom.xml` 文件：

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

#### 許可證獲取
- **免費試用**：從下載免費試用版 [GroupDocs 網站](https://releases。groupdocs.com/viewer/java/).
- **臨時執照**：取得擴充功能的臨時許可證 [GroupDocs 許可證頁面](https://purchase。groupdocs.com/temporary-license/).
- **購買**：如需長期使用，請透過 [GroupDocs 購買頁面](https://purchase。groupdocs.com/buy).

#### 基本初始化
設定好環境和依賴項後，初始化 GroupDocs.Viewer，如下所示：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/file.rar")) {
            // 您的渲染程式碼在這裡
        }
    }
}
```

### 實施指南
我們將探討如何將 RAR 檔案轉換為不同的格式，每種格式都有自己的一組配置。

#### 將 RAR 渲染為 HTML
**概述**：將 RAR 檔案轉換為 HTML 文件以供網路上檢視。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class RenderRarToHtml {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options); // 將 RAR 檔案渲染為 HTML 格式
        }
    }
}
```
- **解釋**： 這 `HtmlViewOptions` 類別與嵌入式資源一起使用，允許完整的網頁渲染，包括 CSS 和圖像。

#### 將 RAR 渲染為 JPG
**概述**：將 RAR 檔案轉換為 JPEG 影像，非常適合縮圖預覽。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;

public class RenderRarToJpg {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.jpg");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options); // 將 RAR 檔案轉換為 JPG 格式
        }
    }
}
```
- **解釋**： `JpgViewOptions` 指定輸出路徑並處理影像渲染。

#### 將 RAR 渲染為 PNG
**概述**：將 RAR 檔案轉換為 PNG 影像以獲得高品質預覽。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

public class RenderRarToPng {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.png");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options); // 將 RAR 檔案渲染為 PNG 格式
        }
    }
}
```
- **解釋**：類似 JPG， `PngViewOptions` 用於將 RAR 的每一頁渲染為 PNG 影像。

#### 將 RAR 渲染為 PDF
**概述**：從 RAR 文件產生 PDF 文檔，以便於共用和列印。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class RenderRarToPdf {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result.pdf");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options); // 將 RAR 檔案轉換為 PDF 格式
        }
    }
}
```
- **解釋**： `PdfViewOptions` 配置PDF文檔的輸出路徑。

#### 取得 RAR 的視圖信息
**概述**：從 RAR 檔案中檢索元資料和結構資訊。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ArchiveViewInfo;

public class GetViewInfoForRar {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            ViewInfo info = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
            System.out.println("File type: " + info.getFileType());
            System.out.println("Pages count: " + info.getPages().size());

            readFolders(viewer, "");
        }
    }

    private static void readFolders(Viewer viewer, String folder) {
        ViewInfoOptions options = ViewInfoOptions.forHtmlView();
        options.getArchiveOptions().setFolder(folder);

        ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(options);
        for (String subFolder : viewInfo.getFolders()) {
            System.out.println(" - " + subFolder);
            readFolders(viewer, subFolder);
        }
    }
}
```
- **解釋**：此程式碼擷取並列印 RAR 檔案中的文件類型和頁數。

#### 渲染 RAR 壓縮包的特定資料夾
**概述**：專注於將 RAR 檔案中的特定資料夾呈現為 HTML 格式。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class RenderSpecificArchiveFolder {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderSpecificArchiveFolder");
        Path pageFilePathFormat = outputDirectory.resolve("archive_folder_page_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            options.getArchiveOptions().setFolder("TargetFolderName"); // 指定要渲染的資料夾
            viewer.view(options); // 將指定資料夾內容呈現為 HTML
        }
    }
}
```
- **解釋**： 使用 `HtmlViewOptions` 使用特定的資料夾設定來定位和呈現 RAR 檔案中的各個資料夾。

透過遵循這些步驟，您可以有效地使用 GroupDocs.Viewer for Java 來管理您的 RAR 檔案並將其轉換為各種格式。

## 結論

本教學將幫助您輕鬆使用 GroupDocs.Viewer for Java 將 RAR 檔案轉換為 HTML、JPG、PNG 和 PDF 等易於存取的格式。您將逐步學習實作細節，包括渲染特定資料夾和檢索檔案訊息，從而增強您的文件管理能力。無論是用於 Web 檢視、預覽或共享，這些技巧都能簡化您在 Java 應用程式中處理 RAR 檔案的方式。

### 常見問題解答

1. **我可以使用 GroupDocs.Viewer for Java 轉換受密碼保護的 RAR 檔案嗎？**  

是的，但是您需要在選項中提供密碼才能解鎖和查看受保護的檔案。

2. **是否可以僅呈現 RAR 中的特定頁面或資料夾？**  

當然，您可以使用專用選項來指定要呈現的資料夾或頁面，例如 `setFolder()` 在渲染設定中。

3. **GroupDocs.Viewer 支援哪些 RAR 檔案輸出格式？**  

它支援 HTML、JPG、PNG 和 PDF 格式，提供靈活的檢視和共享選項。

4. **我需要許可證才能使用 GroupDocs.Viewer for Java 嗎？**  

可以免費試用；為了獲得完整功能和長期使用，建議購買許可證或取得臨時許可證。

5. **我可以在 Java 應用程式中自動執行 RAR 轉換嗎？**  

是的，您可以將提供的程式碼範例嵌入到您的 Java 專案中，以無縫地實現批量轉換的自動化。