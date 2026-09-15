---
date: '2026-09-15'
description: 了解如何使用 GroupDocs.Viewer for Java 將 eml 轉換為 html，並使用自訂日期時間格式與時區偏移——非常適合電郵存檔與支援入口網站。
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: 使用 GroupDocs.Viewer for Java 將 eml 轉換為 html，並使用自訂日期時間格式與時區偏移。請依照本步驟指南，以確保電郵正確呈現。
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: 使用 GroupDocs.Viewer 在 Java 中將 eml 轉換為 html，並自訂日期時間格式
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: 使用 GroupDocs.Viewer 在 Java 中將 eml 轉換為 html，並自訂日期時間格式
type: docs
url: /zh-hant/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 GroupDocs.Viewer 在 Java 中將 eml 轉換為 html 並自訂日期時間

在現代的支援與歸檔系統中，**convert eml to html** 必須能快速完成且保留精確的時間戳記。本教學示範如何使用 GroupDocs.Viewer for Java 將 EML 電子郵件渲染為 HTML、套用 **自訂日期時間格式**，以及設定 **時區偏移**。完成後，你將擁有可重複使用的程式碼片段，能為任何 **email to html conversion** 工作流程產生準確、可直接在網頁上顯示的郵件視圖。

![使用 GroupDocs.Viewer for Java 渲染帶有自訂日期時間的電子郵件](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## 快速解答
- **GroupDocs.Viewer 能將 EML 轉換為 HTML 嗎？** 可以 – API 直接將 EML 檔案渲染為 HTML，無需外部郵件客戶端。  
- **生產環境需要授權嗎？** 測試可使用免費試用版；正式部署需購買授權。  
- **支援哪個 Java 版本？** 完全支援 Java 8 以上版本。  
- **如何變更顯示的日期格式？** 呼叫 `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`。  
- **可以調整時區嗎？** 可以，使用 `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`。

## 「convert eml to html」是什麼？
`Convert eml to html` 是將 EML 電子郵件檔案轉換為可在瀏覽器中渲染的 HTML 文件的過程。此轉換會把原始郵件（包括標頭、內容與附件）轉為瀏覽器友善的網頁格式，無需額外外掛，即可在 Web 應用、歸檔系統或支援儀表板中嵌入郵件。

## 為什麼要使用 GroupDocs.Viewer 來完成此任務？
GroupDocs.Viewer 支援 **超過 50 種輸入與輸出格式**，包括 EML、MSG、PST 與 PDF，且能在不將整個檔案載入記憶體的情況下渲染上百頁的郵件。其零相依性引擎免除 Outlook 或第三方解析器的需求，讓你能完整掌控 **自訂日期時間格式** 與 **時區偏移**，同時保持低資源使用。

## 前置條件
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ 以及 Java IDE（IntelliJ IDEA、Eclipse、VS Code）  
- 用於相依管理的 Maven  

## 設定 GroupDocs.Viewer for Java

### Maven 設定
將 GroupDocs 套件庫與 Viewer 相依加入你的 `pom.xml` 檔案。

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### 授權取得
先使用免費試用版或申請臨時授權以進行延伸測試。正式上線請購買完整授權。

### 基本初始化
建立指向欲轉換 EML 檔案的 `Viewer` 實例。

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## 使用自訂日期時間將 eml 轉換為 html（Java）

以下步驟說明如何在渲染 EML 為 HTML 時套用自訂日期時間格式與時區偏移。

### 步驟 1：設定輸出目錄與檔案路徑
定義產生的 HTML 要儲存的位置。

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*說明:* `Path.of()` 會建立指向儲存 HTML 的資料夾的參考。`resolve()` 則會在該資料夾下加入檔名。

### 步驟 2：以郵件檔案初始化 Viewer
為目標 EML 檔案建立 `Viewer` 物件。

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*說明:* `Viewer` 實例指向你想要轉換的 EML 檔案。

### 步驟 3：設定 HtmlViewOptions
建立 `HtmlViewOptions` 物件，將圖片與其他資源直接嵌入 HTML 輸出。

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*說明:* `forEmbeddedResources()` 會將圖片與其他資源直接嵌入 HTML 輸出。

### 步驟 4：設定自訂日期時間格式 *(custom datetime java)*
`setDateTimeFormat` 用於設定渲染郵件時間戳記時的日期時間樣式。  
定義此樣式後，所有渲染出的時間戳記皆會使用相同格式。

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*說明:* 此樣式會顯示月份縮寫、日期、年份、時、分、上午/下午標記，以及時區偏移 (`zzz`)。

### 步驟 5：設定時區偏移 *(timezone offset java)*
`setTimeZoneOffset` 指定要套用於所有郵件時間戳記的時區。  
將時間戳記調整至目標時區。

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*說明:* 調整渲染出的時間戳記至指定時區。將 `"GMT+1"` 替換為任何有效的時區識別碼即可。

### 如何在 Java 中調整郵件時區
若需 **調整 email timezone** 超過簡單的時差（例如處理夏令時間），可從 `java.util.TimeZone` API 取得相應的 `TimeZone` 物件，使用類似 `"Europe/Paris"` 或 `"America/New_York"` 的區域 ID，然後傳入 `setTimeZoneOffset`。如此即可確保郵件時間戳記始終顯示正確的本地時間。

### 步驟 6：渲染文件
執行轉換並產生最終的 HTML 檔案。

```java
viewer.view(options);
```
*說明:* 執行轉換，產生帶有自訂日期時間設定的 HTML 檔案。

## 自訂日期時間格式如何影響渲染出的 HTML？
自訂日期時間格式決定每筆郵件時間戳記在產生的 HTML 中的呈現方式，會影響可讀性與在地化符合度。使用 `"MMM dd, yyyy hh:mm a zzz"` 這類樣式，可確保所有日期一致顯示月份縮寫、日期、年份、時、分、上午/下午標記與明確的時區偏移，對全球支援團隊尤為重要。

## GroupDocs.Viewer 支援哪些郵件渲染檔案格式？
GroupDocs.Viewer 可將 **EML、MSG、PST、MBOX、EMLX** 檔案渲染為 HTML、PDF、PNG 與 JPEG。支援超過 50 種文件與影像格式，讓你無需額外轉檔工具即可將郵件轉為最常見的 Web 友善輸出。

## 如何批次轉換多個 eml 檔案？
將所有 EML 檔案放入同一資料夾，使用 `for` 或 `foreach` 迴圈逐一處理，每次重複使用相同的 `HtmlViewOptions` 實例，並呼叫 `viewer.view`。此方式可減少物件建立開銷，提升批次轉換效能。

## 疑難排解小技巧
- **FileNotFoundException:** 請確認 `Viewer` 與 `Path.of()` 使用的路徑正確。  
- **時間戳記不正確:** 確認 `TimeZone` ID 與目標區域相符。  
- **圖片遺失:** 請確認已使用 `HtmlViewOptions.forEmbeddedResources()`，否則外部資源可能不會被包含。

## 實務應用
1. **Email archiving:** 將郵件存為可搜尋的 HTML 快照，以符合合規稽核需求。  
2. **Customer support portals:** 為全球客服人員顯示帶有正確本地時間的來信票證。  
3. **Legal documentation:** 產生具標準化時間戳記的法庭級郵件紀錄。

## 效能考量
- 在專用伺服器上執行大量轉換。  
- 監控 Java 堆積使用量，若出現 `OutOfMemoryError`，請調高 `-Xmx` 參數。  
- 當相同郵件被重複請求時，快取已渲染的 HTML 以降低 CPU 負載。

## 結論
現在你已掌握使用 GroupDocs.Viewer for Java 以自訂日期時間格式與時區偏移將 **convert eml to html** 的完整生產就緒方法。此解決方案提升可讀性、確保時間戳記精確，且能無縫整合至歸檔、支援或法律工作流程中。

**後續步驟:** 探索其他 Viewer 選項，如自訂 CSS 注入、分頁或 PDF 轉換，以進一步符合你的應用需求。

## 常見問題

**Q: 如何處理含有附件的 eml 檔案？**  
A: 使用 `HtmlViewOptions.forEmbeddedResources()` 時，附件會自動嵌入。若需要分離檔案，也可透過 Viewer API 取得。

**Q: 能否變更 HTML 範本或加入自訂 CSS？**  
A: 可以，渲染完成後，你可以編輯產生的 HTML 檔案，或在儲存前以程式方式注入 CSS。

**Q: 是否可以批次渲染多個 eml 檔案？**  
A: 可以，將渲染邏輯放入迴圈，並為每個檔案重複使用同一個 `HtmlViewOptions` 實例。

**Q: 若需支援其他郵件格式（如 msg）該怎麼做？**  
A: GroupDocs.Viewer 亦支援 MSG、PST 等郵件容器，只需在 `Viewer` 建構子中更改檔案副檔名即可。

**Q: 每台伺服器需要單獨授權嗎？**  
A: 授權依部署計算；如需多伺服器部署，請參考 GroupDocs 授權指南。

## 資源

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-09-15  
**測試環境：** GroupDocs.Viewer 25.2 (Java)  
**作者：** GroupDocs

## 相關教學

- [Convert Email to HTML & Rename Fields – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – Optimize Email-to-PDF Rendering with GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java Responsive Html Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}