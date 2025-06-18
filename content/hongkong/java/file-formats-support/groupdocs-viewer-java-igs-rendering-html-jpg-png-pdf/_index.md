---
"date": "2025-04-24"
"description": "了解如何使用 GroupDocs.Viewer for Java 將 IGS 檔案轉換為各種格式。請依照本逐步指南，以 HTML、JPG、PNG 或 PDF 格式渲染 3D 模型。"
"title": "掌握 GroupDocs.Viewer Java&#58; 將 IGS 檔案轉換為 HTML、JPG、PNG 和 PDF"
"url": "/zh-hant/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/"
"weight": 1
---

# 掌握 GroupDocs.Viewer Java：將 IGS 檔案轉換為多種格式

## 介紹

您是否想使用 Java 將複雜的 IGS 檔案轉換為 HTML、JPG、PNG 或 PDF 等易於存取的格式？本指南將協助您掌握 GroupDocs.Viewer for Java 程式庫。無論您是經驗豐富的開發人員還是剛入門，本教學都能幫助您輕鬆渲染 IGS 文件。

**您將學到什麼：**
- 如何設定和配置 Java 的 GroupDocs.Viewer。
- 將 IGS 檔案渲染為 HTML、JPG、PNG 和 PDF 格式的逐步說明。
- 關鍵配置選項和故障排除提示。
- 這些轉換在現實場景中的實際應用。

讓我們先來了解先決條件！

## 先決條件

為了有效地遵循本教程，請確保您具備以下條件：

### 所需的庫和依賴項
- **GroupDocs.Viewer for Java**：建議使用 25.2 或更高版本。
- **Java 開發工具包 (JDK)**：確保您的系統上安裝了 JDK 8 或更高版本。

### 環境設定要求
- 合適的整合開發環境 (IDE)，如 IntelliJ IDEA、Eclipse 或 NetBeans。
- 對 Java 程式設計概念和檔案 I/O 操作有基本的了解。

### 知識前提
熟悉 Maven 的依賴管理會很有幫助，但並非強制要求。我們會一步步講解！

## 為 Java 設定 GroupDocs.Viewer

若要開始渲染 IGS 文件，請先在專案中設定 GroupDocs.Viewer 庫。

**Maven 設定**
將以下配置新增至您的 `pom.xml` 文件：

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

### 許可證獲取
GroupDocs.Viewer 提供免費試用、臨時測試許可證以及完全存取權限的購買選項：
- **免費試用**：使用有限的方法來存取核心功能。
- **臨時執照**：在短時間內不受限制地評估圖書館。
- **購買**：購買許可證以供長期使用。

設定完成後，在 Java 應用程式中初始化 GroupDocs.Viewer，如下所示：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // 配置和渲染邏輯在這裡。
        }
    }
}
```

## 實施指南

現在，讓我們分解使用 GroupDocs.Viewer for Java 將 IGS 檔案轉換為各種格式的過程。

### 將 IGS 渲染為 HTML

**概述：**
將 IGS 檔案轉換為包含嵌入資源的互動式 HTML 頁面。此格式非常適合使用者需要直接在瀏覽器中查看 3D 模型的 Web 應用程式。

#### 逐步實施：
1. **設定輸出目錄和檔案路徑：**
   定義儲存渲染檔案的目錄，並指定輸出檔案名稱。

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

2. **了解參數：**
   - `HtmlViewOptions.forEmbeddedResources()` 指定資源（如圖像）應嵌入 HTML 文件中，使其成為獨立文件。

3. **故障排除提示：**
   - 確保您的輸出目錄路徑正確。
   - 驗證在指定目錄中寫入檔案的權限。

### 將IGS渲染為JPG

**概述：**
將您的 IGS 檔案轉換為高品質的 JPG 影像，可用於 3D 模型的縮圖或預覽。

#### 逐步實施：
1. **設定輸出目錄和檔案路徑：**
   與 HTML 轉換類似的設置，但具有 JPG 特定的選項。

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

2. **關鍵配置：**
   - `JpgViewOptions` 允許您定義輸出影像的解析度和品質。

3. **故障排除提示：**
   - 檢查您的 IGS 檔案是否被正確引用。
   - 根據您的需求調整 JPG 選項以獲得最佳品質。

### 將 IGS 渲染為 PNG

**概述：**
從 PNG 格式的 IGS 檔案產生透明或不透明影像，非常適合詳細的視覺化。

#### 逐步實施：
1. **設定輸出目錄和檔案路徑：**

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.PngViewOptions;
    import java.nio.file.Path;
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

2. **配置選項：**
   - `PngViewOptions` 可用於指定影像品質和透明度。

3. **故障排除提示：**
   - 確保您的 IGS 檔案路徑設定正確。
   - 嘗試不同的 PNG 選項以獲得最佳效果。

### 將 IGS 渲染為 PDF

**概述：**
將 IGS 文件轉換為可通用的 PDF 文件，非常適合以標準格式共享詳細的 3D 模型。

#### 逐步實施：
1. **設定輸出目錄和檔案路徑：**

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

2. **主要特點：**
   - `PdfViewOptions` 允許自訂 PDF 設置，如佈局和品質。

3. **故障排除提示：**
   - 驗證輸出目錄是否可寫入。
   - 檢查 IGS 檔案格式是否有任何錯誤。

## 實際應用

將 IGS 檔案渲染為各種格式可以帶來多種可能性：
1. **Web 集成**：將 HTML 渲染的 3D 模型直接嵌入到 Web 應用程式中。
2. **文件共享**：透過 PDF 或影像預覽（JPG/PNG）分享詳細的視覺化效果。
3. **產品視覺化**：在產品目錄和行銷資料中使用高品質的圖像。

本指南為您提供有效利用 GroupDocs.Viewer for Java 的知識，將 IGS 檔案轉換為多種格式。