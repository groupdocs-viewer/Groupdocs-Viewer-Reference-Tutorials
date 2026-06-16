---
date: '2026-03-08'
description: 了解如何取得臨時授權、使用本機檔案或 URL 設定 GroupDocs.Viewer for Java，並驗證授權路徑是否可用。
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: 如何取得暫時授權並在 GroupDocs.Viewer Java 中設定授權
type: docs
url: /zh-hant/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

# 如何取得臨時授權並在 GroupDocs.Viewer Java 中設定授權

在將像 **GroupDocs.Viewer for Java** 這類第三方函式庫整合至應用程式時，有效管理授權至關重要。本指南將示範 **如何取得臨時授權**、如何從本機檔案或 HTTP URL 設定授權，並驗證授權路徑是否正確。完成本教學後，您將擁有可靠、可投入生產環境的授權設定，確保應用程式符合規範且效能良好。

![使用 GroupDocs.Viewer for Java 的檔案與 URL 設定](/viewer/getting-started/file-and-url-setup-png.png)

## 快速解答
- **如何取得臨時授權？** 從 GroupDocs 臨時授權頁面申請，並下載 *.lic* 檔案。  
- **可以從 URL 載入授權嗎？** 可以，只需將 `License.setLicense` 指向回傳有效授權檔案的 HTTP 位址。  
- **如果授權路徑遺失會發生什麼？** 實作檢查以顯示指引，並阻止檢視器啟動。  
- **變更授權後需要重新啟動應用程式嗎？** 不需要，`License.setLicense` 可於執行時呼叫。  
- **需要哪個版本的 Java？** 建議使用 JDK 8 或更高版本。

## 什麼是臨時授權？
**臨時授權** 是由 GroupDocs 發放的時效性金鑰，讓您在未購買正式授權的情況下評估產品。只要在有效期內，其行為與永久授權完全相同，讓您能在真實環境中測試所有功能。

## 為什麼要取得臨時授權？
- **快速評估：** 立即取得完整功能，以支援概念驗證（Proof‑of‑Concept）專案。  
- **無金錢承諾：** 先測試再決定是否購買。  
- **輕鬆整合：** 與永久授權使用相同的 API 呼叫。

## 前置條件
1. **Java Development Kit (JDK)：** 版本 8 或以上。  
2. **IDE：** IntelliJ IDEA、Eclipse，或任何相容 Java 的開發環境。  
3. **GroupDocs.Viewer for Java 函式庫：** 已加入專案（請參考下方 Maven 設定）。  
4. **基本的 Java 知識：** 熟悉類別、匯入以及例外處理。

## 設定 GroupDocs.Viewer for Java
要開始使用，請在 Maven 專案中加入此函式庫。

### Maven 設定
Add the following configuration to your `pom.xml` file:
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
- **免費試用：** 從 [GroupDocs 網站](https://releases.groupdocs.com/viewer/java/) 下載。  
- **臨時授權：** 前往 [臨時授權頁面](https://purchase.groupdocs.com/temporary-license/) 申請。  
- **購買：** 若需永久解決方案，請考慮於 [GroupDocs 購買頁面](https://purchase.groupdocs.com/buy) 購買授權。

### 基本初始化
Once the library is added, you can initialize the viewer:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## 如何取得臨時授權並從檔案設定
### 概觀
從本機檔案設定授權是最直接的方式，即使應用程式離線執行亦可正常運作。

### 實作步驟
1. **定義授權路徑** – 指向在申請臨時授權後取得的 *.lic* 檔案：
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **套用授權** – 使用 `License` 類別載入授權檔案：
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**提示：**  
- 確認檔案路徑為絕對路徑或相對於工作目錄。  
- 確保執行 JVM 的使用者對該檔案具有讀取權限。

## 如何處理授權 URL
### 概觀
基於 URL 的授權對於雲端部署相當便利，授權檔案可存放於安全的儲存空間中。

### 實作步驟
1. **定義授權 URL** – 將佔位符替換為實際的端點網址：
```java
final String licensePath = "http://example.com/license.lic";
```
2. **偵測並記錄 URL 使用** – 以下範例僅會通知您已提供 URL：
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**提示：**  
- 在正式環境中，您會先下載檔案（例如使用 `java.net.HttpURLConnection`），再呼叫 `license.setLicense(stream)`。  
- 加入重試機制與逾時處理，以因應暫時性的網路問題。

## 如何檢查授權可用性（驗證授權路徑）
### 概觀
在嘗試載入授權之前，最佳做法是 **檢查授權是否可用**，以便在需要時指導開發者或使用者取得臨時授權。

### 實作步驟
1. **模擬缺少授權路徑**：
```java
final String licensePath = null;
```
2. **若路徑不存在，提供明確指引**：
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**提示：**  
- 在啟動時記錄此訊息，讓運維團隊知道授權缺失。  
- 考慮在未提供有效授權前退出應用程式或停用檢視器功能。

## 實務應用
了解如何 **取得臨時授權**、從檔案或 URL 設定授權，以及 **驗證授權路徑** 的可用性，可應用於多種實務情境：
1. **文件管理系統** – 嵌入檢視器，於每次啟動時自動驗證授權。  
2. **雲端 SaaS 平台** – 將授權存放於受保護的 Blob 儲存，透過 URL 載入，以實現零停機更新。  
3. **企業部署** – 在試點階段使用臨時授權，之後再購買完整授權。

## 效能考量
- **資源使用：** 在應用程式啟動時載入授權一次；重複呼叫會產生不必要的 I/O。  
- **記憶體管理：** `License` 物件僅保留最小狀態，但若手動下載授權檔案，務必關閉串流。

## 結論
依照上述步驟，您即可 **取得臨時授權**、使用本機檔案或 HTTP URL 設定 GroupDocs.Viewer for Java，並 **檢查授權可用性**，確保應用程式符合規範。這套穩固的授權基礎可避免執行時錯誤，並讓您在開發、測試與正式環境之間自信切換。

### 常見問答

1. **如何在 GroupDocs.Viewer Java 中設定本機授權檔案？**  

   使用 `license.setLicense("path/to/license.lic")` 並提供正確的檔案路徑，即可套用本機授權。

2. **可以直接從 URL 載入授權嗎？**  

   可以，但請確保程式碼能處理 URL 存取，可能需要在執行時下載授權或處理網路問題。

3. **如果授權路徑無效或遺失該怎麼辦？**  

   實作對 null 或無效路徑的檢查，並提供指引或備援提示，以取得有效授權。

4. **能否動態在授權檔案與 URL 之間切換？**  

   完全可以，透過加入條件判斷，根據環境或執行時參數處理兩種情況。

5. **在正式環境中，授權管理的最佳實踐是什麼？**  

   安全保存授權、定期驗證其有效性，並實作授權錯誤的例外處理，以確保服務不中斷。

## 常見問題

**Q：臨時授權的有效期限多久？**  
A：通常為 30 天，之後您可申請續期或升級為永久授權。

**Q：使用檔案式授權是否需要網際網路連線？**  
A：不需要。只要本機 *.lic* 檔案已載入，即可完全離線使用。

**Q：我可以加密授權檔案以提升安全性嗎？**  
A：授權檔案已由 GroupDocs 簽署；額外加密是可選的，非必要。

**Q：如果授權在應用程式執行期間過期會怎樣？**  
A：檢視器操作會拋出授權例外；建議在啟動時檢查授權是否過期。

**Q：將授權 URL 存放於原始碼管理是否安全？**  
A：請避免提交敏感 URL；建議使用環境變數或安全的設定儲存方式。

---

**最後更新：** 2026-03-08  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs