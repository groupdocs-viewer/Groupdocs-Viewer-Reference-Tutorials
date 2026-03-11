---
date: '2026-01-10'
description: 學習如何使用 GroupDocs.Viewer 在 Java 中將 EML 轉換為 HTML，並使用自訂日期時間格式及設定時區偏移。非常適合電郵歸檔與支援系統。
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: 在 Java 中使用 GroupDocs.Viewer 將 EML 轉換為 HTML 並自訂日期時間
type: docs
url: /zh-hant/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer 在 Java 中將 EML 轉換為 HTML 並自訂日期時間

## 介紹

在當今節奏快速的數位世界中，能夠快速 **將 EML 轉換為 HTML** 並正確呈現日期時間，對於歸檔、支援入口網站及法律合規至關重要。本教學將指導您使用 GroupDocs.Viewer for Java 將電子郵件訊息渲染為 HTML，同時套用 **自訂日期時間格式** 以及 **時區偏移**。完成後，您將擁有一個可重複使用的解決方案，使時間戳記保持準確且易於閱讀。

![使用 GroupDocs.Viewer for Java 渲染帶有自訂日期時間的電子郵件](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**您將學習**
- 如何在 Java 專案中設定 GroupDocs.Viewer  
- 如何將電子郵件渲染為帶嵌入資源的 HTML  
- 如何 **自訂電子郵件的日期時間格式** (custom datetime format java)  
- 如何 **設定時區偏移** 以獲得正確的時間戳記 (set timezone offset java)  

## 快速解答
- **GroupDocs.Viewer 能將 EML 轉換為 HTML 嗎？** 是的，它會直接將 EML 檔案渲染為 HTML。  
- **我需要授權嗎？** 免費試用可用於測試；正式環境需要付費授權。  
- **需要哪個版本的 Java？** Java 8 或更新版本。  
- **如何變更顯示的日期格式？** 使用 `options.getEmailOptions().setDateTimeFormat(...)`。  
- **我可以調整時區嗎？** 可以，使用 `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`。  

## 什麼是「將 EML 轉換為 HTML」？
將 EML 檔案轉換為 HTML 會把原始電子郵件（包括標頭、內容與附件）轉換為瀏覽器可直接顯示的網頁友好格式，無需額外插件。這使得在 Web 應用程式、歸檔或支援儀表板中嵌入電子郵件變得簡單。

## 為何在此任務中使用 GroupDocs.Viewer？
- **零相依性渲染** – 無需 Outlook 或外部郵件解析器。  
- **內建支援嵌入資源**（圖片、附件）。  
- **細緻的控制** 日期時間格式化與時區處理。  

## 前置條件
- **GroupDocs.Viewer for Java** 版本 25.2 或更新。  
- **Java Development Kit (JDK)** 8 以上，並搭配 IDE（IntelliJ IDEA、Eclipse 等）。  
- 具備基本的 Java 知識與 Maven 使用經驗。  

## 設定 GroupDocs.Viewer for Java

### Maven 設定
Add the GroupDocs repository and dependency to your `pom.xml`:

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

## 使用自訂日期時間於 Java 轉換 EML 為 HTML

以下逐步指南說明如何 **將 EML 轉換為 HTML**，同時套用自訂日期時間格式與時區偏移。

### 步驟 1：設定輸出目錄與檔案路徑
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*說明：* `Path.of()` 會建立指向將儲存 HTML 的資料夾的參考。`resolve()` 會在其後加上檔名。

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
*說明：* `forEmbeddedResources()` 會將圖片及其他資源直接嵌入 HTML 輸出中。

### 步驟 4：設定自訂日期時間格式 *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*說明：* 此模式會顯示月份、日期、年份、時、分、上午/下午標記，以及時區偏移 (`zzz`)。

### 步驟 5：設定時區偏移 *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*說明：* 調整渲染出的時間戳記至目標時區。將 `"GMT+1"` 替換為任何有效的時區識別碼。

### 步驟 6：渲染文件
```java
viewer.view(options);
```
*說明：* 執行轉換，產生帶有自訂日期時間設定的 HTML 檔案。

## 疑難排解技巧
- **FileNotFoundException：** 請再次確認 `Viewer` 與 `Path.of()` 中使用的路徑。  
- **時間戳記不正確：** 確認 `TimeZone` ID 與目標區域相符。  
- **圖片遺失：** 確認已使用 `HtmlViewOptions.forEmbeddedResources()`；否則外部資源可能不會被包含。  

## 實務應用
1. **電子郵件歸檔：** 儲存可搜尋的 HTML 快照以符合合規需求。  
2. **客戶支援入口網站：** 顯示帶有正確本地時間的來信工單。  
3. **法律文件：** 產生具標準化時間戳記的法庭可用電子郵件紀錄。  

## 效能考量
- 在專用伺服器上部署以進行大量轉換。  
- 監控 Java 堆積使用情況；若遇到 `OutOfMemoryError`，請增大 `-Xmx`。  
- 當同一封電子郵件被重複請求時，快取已渲染的 HTML。  

## 結論
現在您已擁有一套完整、可投入生產環境的方式，使用 GroupDocs.Viewer for Java **將 EML 轉換為 HTML**，並套用自訂日期時間格式與時區偏移。此方法提升可讀性、確保時間戳記的準確性，且能無縫整合至歸檔或支援工作流程中。

**下一步：** 探索其他 Viewer 選項，如 CSS 樣式、分頁或 PDF 轉換，以進一步客製化輸出。

## 常見問題

**Q: 如何處理帶有附件的 EML 檔案？**  
A: 使用 `HtmlViewOptions.forEmbeddedResources()` 時，附件會自動嵌入。若有需要，也可透過 Viewer API 進行提取。

**Q: 我可以更改 HTML 模板或加入自訂 CSS 嗎？**  
A: 可以，渲染完成後，您可以編輯產生的 HTML 檔案，或在儲存前以程式方式注入 CSS。

**Q: 能否批次渲染多個 EML 檔案？**  
A: 可將渲染邏輯放入迴圈，並為每個檔案重複使用相同的 `HtmlViewOptions` 實例。

**Q: 若需支援其他電子郵件格式（如 MSG）該怎麼辦？**  
A: GroupDocs.Viewer 亦支援 MSG、PST 及其他郵件容器，只需在 `Viewer` 建構子中更改檔案副檔名即可。

**Q: 每台伺服器需要單獨的授權嗎？**  
A: 授權以部署為單位；如有多伺服器情境，請參考 GroupDocs 授權指南。  

## 資源
- [文件說明](https://docs.groupdocs.com/viewer/java/)
- [API 參考](https://reference.groupdocs.com/viewer/java/)
- [下載](https://releases.groupdocs.com/viewer/java/)
- [購買](https://purchase.groupdocs.com/buy)
- [免費試用](https://releases.groupdocs.com/viewer/java/)
- [臨時授權](https://purchase.groupdocs.com/temporary-license/)
- [支援論壇](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-01-10  
**測試環境：** GroupDocs.Viewer 25.2 (Java)  
**作者：** GroupDocs