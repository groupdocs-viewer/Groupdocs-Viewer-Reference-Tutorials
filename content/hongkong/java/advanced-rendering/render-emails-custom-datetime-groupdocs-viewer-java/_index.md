---
date: '2026-03-24'
description: 學習如何使用 GroupDocs.Viewer 在 Java 中將 EML 轉換為 HTML，並自訂日期時間格式及設定時區偏移，適用於電郵存檔與支援系統。
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: 使用 GroupDocs.Viewer 在 Java 中將 EML 轉換為 HTML 並自訂日期時間
type: docs
url: /zh-hant/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer 於 Java 轉換 EML 為 HTML 並自訂日期時間

在當今節奏快速的數位世界中，能夠快速 **將 EML 轉換為 HTML** 並正確呈現日期時間對於歸檔、支援入口網站以及法律合規至關重要。本教學將指導您使用 GroupDocs.Viewer for Java 將電子郵件訊息渲染為 HTML，同時套用 **自訂日期時間格式** 與 **時區偏移**。完成後，您將擁有一個可重複使用的解決方案，使時間戳記保持精確且易讀，完美適用於任何 **email to HTML Java** 工作流程。

![使用 GroupDocs.Viewer for Java 渲染帶自訂日期時間的電子郵件](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**您將學習**
- 如何在 Java 專案中設定 GroupDocs.Viewer  
- 如何將電子郵件渲染為內嵌資源的 HTML  
- 如何 **自訂電子郵件訊息的日期時間格式**（custom datetime java）  
- 如何 **設定時區偏移** 以取得正確的時間戳記（timezone offset java）  

## 快速解答
- **GroupDocs.Viewer 能將 EML 轉換為 HTML 嗎？** 是的，它會直接將 EML 檔案渲染為 HTML。  
- **我需要授權嗎？** 免費試用可用於測試；正式環境需購買授權。  
- **需要哪個 Java 版本？** Java 8 或更新版本。  
- **如何變更顯示的日期格式？** 使用 `options.getEmailOptions().setDateTimeFormat(...)`。  
- **我可以調整時區嗎？** 可以，使用 `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`。  

## 什麼是「將 EML 轉換為 HTML」？
將 EML 檔案轉換為 HTML 會把原始電子郵件（包括標頭、內容與附件）轉換成瀏覽器可直接顯示的網頁友好格式，無需額外外掛。這讓在 Web 應用程式、歸檔或支援儀表板中嵌入電子郵件變得簡單。

## 為什麼在此任務中使用 GroupDocs.Viewer？
- **零相依性渲染** – 無需 Outlook 或外部郵件解析器。  
- **內建支援嵌入資源**（圖片、附件）。  
- **細緻的控制** 日期時間格式與時區處理。  

## 前置條件
- **GroupDocs.Viewer for Java** 版本 25.2 或更新。  
- **Java Development Kit (JDK)** 8 以上，並配合 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知識與 Maven 使用經驗。  

## 設定 GroupDocs.Viewer for Java

### Maven 設定
將 GroupDocs 儲存庫與相依性加入您的 `pom.xml`：

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

### 取得授權
先使用免費試用版或申請臨時授權以進行延長測試。正式環境請購買完整授權。  

### 基本初始化
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## 使用 Java 轉換 EML 為 HTML 並自訂日期時間

以下逐步指南說明如何 **將 EML 轉換為 HTML**，同時套用自訂日期時間格式與時區偏移。

### 步驟 1：設定輸出目錄與檔案路徑
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*說明：* `Path.of()` 會建立指向儲存 HTML 的資料夾的參考。`resolve()` 會在其後加入檔名。  

### 步驟 2：使用電子郵件檔案初始化 Viewer
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*說明：* `Viewer` 實例指向您欲轉換的 EML 檔案。  

### 步驟 3：設定 HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*說明：* `forEmbeddedResources()` 會將圖片與其他資源直接嵌入 HTML 輸出中。  

### 步驟 4：設定自訂日期時間格式 *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*說明：* 此模式會顯示月份、日期、年份、時、分、上午/下午標記，以及時區偏移 (`zzz`)。  

### 步驟 5：設定時區偏移 *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*說明：* 調整渲染後的時間戳記至目標時區。將 `"GMT+1"` 替換為任何有效的時區識別字串。  

### 如何在 Java 中調整電子郵件時區
如果您需要 **調整電子郵件時區**，不僅僅是簡單的偏移，例如處理夏令時間變更，您可以透過 `java.util.TimeZone` API 使用區域 ID（如 `"Europe/Paris"` 或 `"America/New_York"`）取得相應的 `TimeZone` 物件，並傳遞給 `setTimeZoneOffset`。這可確保電子郵件時間戳記始終顯示正確的當地時間。  

### 步驟 6：渲染文件
```java
viewer.view(options);
```
*說明：* 執行轉換，產生帶有自訂日期時間設定的 HTML 檔案。  

## 疑難排解技巧
- **FileNotFoundException：** 請再次確認 `Viewer` 與 `Path.of()` 中使用的路徑。  
- **時間戳記不正確：** 確認 `TimeZone` ID 與目標區域相符。  
- **圖片遺失：** 確保使用了 `HtmlViewOptions.forEmbeddedResources()`；否則外部資源可能不會被包含。  

## 實務應用
1. **電子郵件歸檔：** 儲存可搜尋的 HTML 電子郵件快照以符合合規需求。  
2. **客戶支援入口網站：** 顯示帶有正確本地時間的來信工單。  
3. **法律文件：** 產生符合標準時間戳記的法庭可用電子郵件紀錄。  

## 效能考量
- 在專用伺服器上部署以進行大量轉換。  
- 監控 Java 堆積使用情況；若遇到 `OutOfMemoryError`，請增加 `-Xmx`。  
- 當同一封電子郵件被重複請求時，快取已渲染的 HTML。  

## 結論
您現在擁有一套完整、可投入生產環境的 **將 EML 轉換為 HTML** 方法，能使用 GroupDocs.Viewer for Java 套用自訂日期時間格式與時區偏移。此方式提升可讀性、確保時間戳記精確，且能無縫融入歸檔或支援工作流程。  

**下一步：** 探索其他 Viewer 選項，如 CSS 樣式、分頁或 PDF 轉換，以進一步符合您的需求。  

## 常見問題

**Q: 如何處理帶有附件的 EML 檔案？**  
A: 使用 `HtmlViewOptions.forEmbeddedResources()` 時，附件會自動嵌入。若有需要，也可透過 Viewer API 取得附件。  

**Q: 我可以變更 HTML 模板或加入自訂 CSS 嗎？**  
A: 可以，渲染完成後您可以編輯產生的 HTML 檔案，或在儲存前以程式方式注入 CSS。  

**Q: 能否批次渲染多個 EML 檔案？**  
A: 可將渲染邏輯放入迴圈，並為每個檔案重複使用相同的 `HtmlViewOptions` 實例。  

**Q: 若需支援其他電子郵件格式（如 MSG）該怎麼辦？**  
A: GroupDocs.Viewer 亦支援 MSG、PST 及其他郵件容器，只需在 `Viewer` 建構子中更改檔案副檔名即可。  

**Q: 每台伺服器需要單獨授權嗎？**  
A: 授權是依部署計算；請參考 GroupDocs 授權指南以了解多伺服器情境。  

## 資源

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-03-24  
**測試環境：** GroupDocs.Viewer 25.2 (Java)  
**作者：** GroupDocs  

---