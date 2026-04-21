---
date: '2026-03-24'
description: 學習如何使用 GroupDocs Viewer for Java 將電子郵件轉換為 HTML 並重新命名電子郵件欄位。本指南展示了如何以自訂標頭將電子郵件渲染為
  HTML。
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: 將電子郵件轉換為 HTML 並重新命名欄位 – GroupDocs Viewer Java
type: docs
url: /zh-hant/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# 轉換電子郵件為 HTML 並重新命名欄位 – GroupDocs Viewer Java

如果您需要 **將電子郵件轉換為 HTML** 並為電子郵件標頭提供自訂外觀，您來對地方了。在本教學中，我們將逐步說明如何重新命名電子郵件欄位、**將電子郵件轉換為 HTML**，以及使用 GroupDocs.Viewer for Java 來自訂電子郵件標頭。完成後，您將得到一個乾淨的 HTML 表示，並使用您偏好的標頭名稱，使輸出更易於閱讀與整合至您的應用程式中。

![在使用 GroupDocs.Viewer for Java 轉換電子郵件為 HTML 時重新命名欄位](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### 您將學到
- 如何使用 GroupDocs.Viewer for Java 來 **將電子郵件轉換為 HTML**。  
- 重新命名電子郵件欄位的技巧，例如 “From”、 “To”、 “Sent” 與 “Subject”。  
- 設定 Maven 與授權的最佳實踐。  
- 在實務情境中 **自訂電子郵件標頭** 能帶來的價值。

## 快速解答
- **「將電子郵件轉換為 HTML」是什麼意思？** 它指的是將電子郵件檔案（MSG/EML）呈現為可在網頁上使用的 HTML 文件。  
- **哪個函式庫負責轉換？** GroupDocs.Viewer for Java（v25.2 以上）。  
- **我需要授權嗎？** 試用版可用於評估；正式環境需購買完整授權。  
- **我可以變更任何標頭名稱嗎？** 可以，任何標準的電子郵件標頭皆可透過 `fieldTextMap` 重新映射。  
- **輸出是 HTML 還是嵌入式資源？** 您可以選擇嵌入式資源，以產生單一自包含檔案。

## 在 GroupDocs.Viewer 中，「將電子郵件轉換為 HTML」是什麼意思？
將電子郵件轉換為 HTML 表示將原始的電子郵件檔案轉換成一個 HTML 頁面，顯示訊息內容及其中繼資料。當您同時 **重新命名電子郵件欄位** 時，預設的標籤（例如 “From”）會被自訂文字（例如 “Sender”）取代，這有助於符合企業用語或提升 UI 一致性。

## 為何要將電子郵件轉換為 HTML 並重新命名欄位？
- **一致的品牌形象：** 使輸出符合貴組織的語言慣例。  
- **提升可搜尋性：** 自訂標頭可在歸檔系統中更有效率地建立索引。  
- **更佳的 UI 整合：** 調整 HTML 片段，使其能無縫嵌入網站入口或支援儀表板。

## 前置條件

### 必要的函式庫、版本與相依性
- **GroupDocs.Viewer for Java** – 版本 25.2 或更新。  
- **Java Development Kit (JDK)** – 版本 8 以上。

### 環境設定需求
- **Maven** 用於相依性管理。  
- IDE 如 IntelliJ IDEA、Eclipse 或 VS Code。

### 知識前提
具備基本的 Java 與 Maven 知識將有助於您快速跟上教學步驟。

## 設定 GroupDocs.Viewer for Java

### Maven 設定
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

### 取得授權步驟
- **免費試用：** 從 [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) 下載免費試用版。  
- **臨時授權：** 於 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 取得臨時授權，以無限制探索完整功能。  
- **購買：** 若需長期使用，請考慮透過 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 購買授權。

### 基本初始化與設定
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
將檔案路徑調整為指向您的 `.msg` 檔案。

## 如何將電子郵件轉換為 HTML 並重新命名欄位 – 步驟說明

### 1. 設定輸出目錄路徑
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*將 `"YOUR_OUTPUT_DIRECTORY"` 替換為您希望儲存 HTML 檔案的資料夾。*

### 2. 定義頁面檔案路徑格式
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` 會在渲染時被頁碼取代。*

### 3. 建立電子郵件欄位與新名稱的對映
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*此處將預設標籤改為自訂名稱。*

### 4. 設定 HTML 檢視選項
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` 會將 CSS/JS 內嵌於 HTML 中，而 `setFieldTextMap` 則套用自訂的標頭名稱。*

### 5. 將電子郵件渲染為 HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*將 `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` 替換為實際的 MSG 檔案路徑。*

#### 疑難排解提示
- 確認輸出目錄具有寫入權限。  
- 確保輸入的 MSG 檔案存在且路徑正確。  
- 使用與 Maven 中聲明相同的 GroupDocs.Viewer 版本（25.2）。

## 實務應用
1. **自訂電子郵件報告：** 使電子郵件標頭符合企業用語，提升報告可讀性。  
2. **電子郵件歸檔系統：** 使用標準化的標頭名稱提升可搜尋性。  
3. **客服平台：** 以個人化的標頭標籤呈現工單，改善客服人員的使用體驗。

## 效能考量
- 使用 try‑with‑resources 釋放 `Viewer` 物件，以即時回收記憶體。  
- 對大量批次進行效能分析，必要時考慮使用平行串流處理電子郵件。

## 結論
您現在已了解如何使用 GroupDocs.Viewer for Java **將電子郵件轉換為 HTML**、**重新命名電子郵件欄位**，以及 **自訂電子郵件標頭**。此技巧讓您能完整掌控 HTML 輸出中電子郵件中繼資料的呈現方式。

### 後續步驟
- 嘗試其他欄位對映（例如 CC、BCC）。  
- 探索其他渲染格式，如 PDF 或 PNG。  
- 前往 [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) 取得更深入的 API 資訊。

## 常見問題

**Q: 此方法是否支援其他電子郵件格式，例如 EML？**  
A: 是的，GroupDocs.Viewer 同時支援 MSG 與 EML 檔案；相同的欄位對映邏輯皆適用。

**Q: 我可以輸出不含嵌入式資源的 HTML 嗎？**  
A: 若您偏好分離的 CSS/JS 檔案，可使用 `HtmlViewOptions.forExternalResources(...)`。

**Q: 測試使用的 GroupDocs.Viewer 版本為何？**  
A: 程式碼已在 GroupDocs.Viewer **25.2** 版本上測試。

**Q: 能否變更自訂標頭的字型或樣式？**  
A: 可在渲染後透過 CSS 進行樣式設定，或使用 `HtmlViewOptions.getResourcesPath()` 注入自訂 CSS。

**Q: 如何以程式方式取得產生的 HTML 檔案路徑？**  
A: 檔案路徑遵循 `pageFilePathFormat` 定義的模式；您可使用 `String.format` 並傳入頁碼來組合路徑。

## 資源
- **文件說明：** 完整指南可於 [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) 取得。  
- **API 參考：** 詳細的 API 資訊請參考 [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)。  
- **下載 GroupDocs.Viewer：** 可透過 [Downloads Page](https://releases.groupdocs.com/viewer/java/) 取得最新版本。

---

**最後更新：** 2026-03-24  
**測試環境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs