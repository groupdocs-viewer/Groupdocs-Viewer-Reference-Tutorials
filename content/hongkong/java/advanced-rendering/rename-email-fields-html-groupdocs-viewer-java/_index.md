---
date: '2026-01-05'
description: 了解如何使用 GroupDocs.Viewer for Java 重新命名電郵欄位、將電郵轉換為 HTML，以及自訂電郵標頭。
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: 如何在使用 GroupDocs.Viewer Java 將電子郵件渲染為 HTML 時重新命名電子郵件欄位
type: docs
url: /zh-hant/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# 如何在使用 GroupDocs.Viewer Java 渲染電子郵件為 HTML 時重新命名電子郵件欄位

您是否在想 **如何重新命名電子郵件** 欄位，同時將電子郵件轉換為 HTML？在本指南中，我們將逐步說明如何重新命名電子郵件欄位、**將電子郵件轉換為 HTML**，以及使用 GroupDocs.Viewer for Java **自訂電子郵件標頭**。完成後，您將得到一個乾淨的 HTML 表示，使用您偏好的標頭名稱，使輸出更易於閱讀並整合到您的應用程式中。

![在使用 GroupDocs.Viewer for Java 將電子郵件轉換為 HTML 時重新命名電子郵件欄位](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### 您將學習到
- 如何使用 GroupDocs.Viewer for Java 來 **將電子郵件轉換為 HTML**。  
- 重新命名電子郵件欄位的技巧，例如 “From”、 “To”、 “Sent” 與 “Subject”。  
- 設定 Maven 與授權的最佳實踐。  
- 真實案例中 **自訂電子郵件標頭** 能帶來價值。

## 快速解答
- **「how to rename email」是什麼意思？** 它指的是在渲染過程中將預設的電子郵件標頭名稱映射為自訂標籤。  
- **哪個函式庫負責轉換？** GroupDocs.Viewer for Java (v25.2+)。  
- **我需要授權嗎？** 試用版可用於評估；正式環境需要完整授權。  
- **我可以變更任何標頭名稱嗎？** 可以，任何標準的電子郵件標頭皆可透過 `fieldTextMap` 重新映射。  
- **輸出是 HTML 還是嵌入式資源？** 您可以選擇嵌入式資源，以產生單一自包含檔案。

## 「how to rename email」在 GroupDocs.Viewer 中的意義是什麼？
重新命名電子郵件欄位是指在將電子郵件渲染為 HTML 時，將預設標籤（例如 “From”）替換為自訂文字（例如 “Sender”）。此作法有助於使輸出符合企業用語或提升最終使用者的可讀性。

## 為什麼要將電子郵件轉換為 HTML 並自訂電子郵件標頭？
- **一致的品牌形象：** 讓組織的語言在所有溝通中保持一致。  
- **提升可搜尋性：** 自訂標頭可在歸檔系統中更有效率地建立索引。  
- **更佳的 UI 整合：** 調整 HTML 片段，使其無縫嵌入網站入口或支援儀表板。

## 前置作業

### 必要的函式庫、版本與相依性
- **GroupDocs.Viewer for Java** – 版本 25.2 或更新版本。  
- **Java Development Kit (JDK)** – 版本 8 以上。

### 環境設定需求
- **Maven** 用於相依性管理。  
- IDE，例如 IntelliJ IDEA、Eclipse 或 VS Code。

### 知識前置條件
具備基本的 Java 與 Maven 知識將有助於您快速跟隨本教學。

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
- **臨時授權：** 前往 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 取得臨時授權，以無限制探索完整功能。  
- **購買：** 若需持續使用，請考慮透過 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 購買授權。

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
調整檔案路徑以指向您的 `.msg` 檔案。

## 實作指南

### 重新命名電子郵件欄位 – 步驟說明

#### 1. 設定輸出目錄路徑
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*將 `"YOUR_OUTPUT_DIRECTORY"` 替換為您希望儲存 HTML 檔案的資料夾。*

#### 2. 定義頁面檔案路徑格式
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` 會在渲染時被頁碼取代。*

 3. 建立電子郵件欄位與新名稱的對映
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
*此處將預設標籤變更為自訂名稱。*

#### 4. 設定 HTML 檢視選項
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` 會將 CSS/JS 內嵌於 HTML 中，而 `setFieldTextMap` 則套用自訂的標頭名稱。*

#### 5. 將電子郵件渲染為 HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*將 `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` 替換為您實際的 MSG 檔案路徑。*

#### 疑難排解提示
- 確認輸出目錄具備寫入權限。  
- 確保入的 MSG 檔案存在且路徑正確。  
- 使用與 Maven 中聲明相同的 GroupDocs.Viewer 版本（25.2）。

## 實務應用
1. **自訂電子郵件報告：** 使電子郵件標頭符合企業用語，以產生更清晰的報告。  
2. **電子郵件歸檔系統：** 使用標準化的標頭名稱提升可搜尋性。  
3. **客服平台：** 以個人化的標頭標籤呈現工單，提升客服人員的使用體驗。

## 效能考
 使用 try‑with‑resources 釋放 `Viewer` 物件，以即時釋放記憶體。  
- 對大量批次進行效能分析，必要時考慮使用平行串流處理電子郵件。

## 結論
您現在已了解 **如何重新命名電子郵件** 欄位，同時 **將電子郵件轉換為 HTML** 並 **自訂電子郵件標頭**，使用 GroupDocs.Viewer for Java。此技巧讓您能完整掌控 HTML 輸出中電子郵件中繼資料的呈現方式。

### 後續步驟
- 嘗試其他欄位對映（例如 CC、BCC）。  
- 探索其他渲染格式，如 PDF 或 PNG。  
- 前往 [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) 取得更深入的 API 資訊。

## FAQ Section
1. **我可以使用此方法重新命名所有電子郵件標頭嗎？**  
   - 可以，您可以依需求將任何標準電子郵件標頭映射為新名稱。  
2. **是否可以在沒有授權的情況下使用 GroupDocs.Viewer？**  
   - 提供試用版供測試使用，但完整功能版需有效授權。  
3. **如何使用 GroupDocs.Viewer 高效處理大量電子郵件？**  
   - 考慮批次處理，並優化系統資源以有效管理大型資料集。  
4. **我可以將此解決方案整合到現有的 Java 應用程式中嗎？**  
   - 當然可以，使用 Maven 相依性即可輕鬆整合。  
5. **如果遇到問題，我該去哪裡尋求支援？**  
   - 前往 [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) 取得社群與官方協助。

## Frequently Asked Questions

**Q: 此方法是否支援其他電子郵件格式，例如 EML？**  
A: 是的，GroupDocs.Viewer 同時支援 MSG 與 EML 檔案；相同的欄位對映邏輯皆適用。

**Q: 我可以輸出不含嵌入式資源的 HTML 嗎？**  
A: 若偏好分離的 CSS/JS 檔案，可使用 `HtmlViewOptions.forExternalResources(...)`。

**Q: 測試使用的 GroupDocs.Viewer 版本為何？**  
A: 程式碼已於 GroupDocs.Viewer **25.2** 版本測試。

**Q: 能否變更自訂標頭的字型或樣式？**  
A: 可於渲染後透過 CSS 進行樣式設定，或使用 `HtmlViewOptions.getResourcesPath()` 注入自訂 CSS。

**Q: 如何以程式方式取得產生的 HTML 檔案路徑？**  
A: 檔案路徑遵循 `pageFilePathFormat` 定義的模式，可使用 `String.format` 並傳入頁碼來組合。

## Resources
- **文件說明：** 完整指南可於 [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) 取得。  
- **API 參考：** 詳細的 API 資訊可於 [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/) 查閱。  
- **下載 GroupDocs.Viewer：** 可透過 [Downloads Page](https://releases.groupdocs.com/viewer/java/) 取得最新版本。

---

**最後更新：** 2026-01-05  
**測試版本：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs