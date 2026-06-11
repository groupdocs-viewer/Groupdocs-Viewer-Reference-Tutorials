---
date: '2026-03-05'
description: 學習如何使用 GroupDocs.Viewer for Java 將數字轉換為 PDF 以及其他格式，如 HTML、JPG、PNG。本指南涵蓋設定、渲染技術及實務應用。
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: 使用 GroupDocs.Viewer for Java 將 Numbers 轉換為 PDF
type: docs
url: /zh-hant/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer for Java 轉換 Numbers 為 PDF（及其他格式）

在網頁或桌面應用程式上顯示 Apple Numbers 文件可能相當棘手，尤其是當您需要 **convert numbers to pdf** 或將其嵌入為圖像時。在本教學中，我們將說明如何使用 **GroupDocs.Viewer for Java** 將 Numbers 檔案轉換為 HTML、JPG、PNG、**以及 PDF**——為您提供彈性的分享、預覽或歸檔試算表的選項。

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### 您將學習的內容
- 如何在基於 Maven 的 Java 專案中設定 GroupDocs.Viewer  
- 步驟式程式碼示範 **convert numbers to pdf**、**convert numbers to html** 以及 **convert numbers to jpg**  
- 真實案例說明文件轉換如何為 Web 入口、電子郵件工作流程與 DMS 整合增值  

## 快速解答
- **我可以使用 Java 轉換 Numbers 為 PDF 嗎？** 是的，使用 `PdfViewOptions` 在 GroupDocs.Viewer 中。  
- **哪種格式最適合網頁預覽？** HTML 提供最具互動性的體驗。  
- **生產環境需要授權嗎？** 需要商業授權才能在非試用部署中使用。  
- **支援圖像轉換嗎？** 當然可以——使用 `JpgViewOptions` 或 `PngViewOptions` 取得高品質圖像。  
- **需要哪個 Java 版本？** 需要 Java 8 以上，並使用 Maven 進行相依管理。  

## 前置條件
- 已安裝 Java Development Kit (JDK) 8 或更高版本。  
- 使用 Maven 處理相依性。  
- 具備基本的 Java 檔案 I/O 與路徑概念。  

## 設定 GroupDocs.Viewer for Java

### 使用 Maven 安裝
將儲存庫與相依性加入您的 `pom.xml`。此區塊必須保持原樣顯示：

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
- **Free Trial:** 免費試用，無需付費即可評估所有功能。  
- **Temporary License:** 申請時間限制的授權金鑰以進行延長測試。  
- **Purchase:** 購買完整授權以用於商業專案。  

## 將 Numbers 文件渲染為 HTML  
*使用情境：將試算表直接嵌入網頁。*

### 步驟 1：初始化 Viewer 並設定 HTML 選項
以下是您將執行的完整程式碼。註解說明每一行，但 **不要修改程式碼區塊**。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **為何重要：** `HtmlViewOptions.forEmbeddedResources()` 會將 CSS 與圖像內嵌於 HTML 中，使其非常適合快速的網頁預覽。

## 將 Numbers 文件渲染為 JPG  
*適用於在社交媒體或電子郵件中分享試算表快照。*

### 步驟 1：設定 Viewer 與 JPG 選項
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **提示：** 若需要較小的檔案，可透過 `options.setQuality(int)` 調整影像品質。  

## 將 Numbers 文件渲染為 PNG  
*當您需要無損且高解析度的圖像用於報告時的理想選擇。*

### 步驟 1：初始化並設定 PNG 選項
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **專業提示：** 使用 `options.setResolution(int)` 來控制列印就緒圖像的 DPI。  

## 將 Numbers 文件渲染為 PDF  
*許多開發者的主要目標：**convert numbers to pdf** 用於歸檔或分發。*

### 步驟 1：設定 Viewer 以進行 PDF 轉換
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **關鍵設定：** `PdfViewOptions` 允許嵌入字型並控制頁面大小，確保輸出符合您的品牌需求。  

## 實務應用
- **Web Integration:** 將文件渲染為 HTML，以在網站上提供互動式試算表檢視器。  
- **Content Sharing:** 轉換為 JPG/PNG，以在電子報或聊天中快速嵌入圖像。  
- **Enterprise DMS:** 使用 **convert numbers to pdf** 以儲存不可編輯且可搜尋的試算表版本。  

## 效能考量
- **Resource Management:** 總是於 try‑with‑resources 區塊中關閉 `Viewer`（如範例所示），以即時釋放本機資源。  
- **Large Files:** 對於大型 Numbers 檔案，建議逐頁處理並串流結果，以避免高記憶體使用。  
- **Thread Safety:** 為每個執行緒建立獨立的 `Viewer` 實例；此類別並非執行緒安全。  

## 結論
現在您已擁有使用 GroupDocs.Viewer for Java 進行 **convert numbers to pdf**，以及轉換為 HTML、JPG、PNG 的完整工具箱。這些功能讓您能構建彈性的文件流程——無論是供應給 Web 入口、產生報告，或是歸檔試算表。

### 後續步驟
探索更多自訂選項，請參閱 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)，並嘗試將這些功能整合至您的應用程式中。

## 常見問答

**Q1: GroupDocs.Viewer 支援哪些檔案格式？**  
A1: 它支援包括 DOCX、XLSX、PDF 等在內的多種文件格式。

**Q2: 如何有效處理大型 Numbers 檔案？**  
A2: 利用 Java 的記憶體管理技巧，並優化程式碼以有效處理大型檔案。

**Q3: GroupDocs.Viewer 可以用於商業專案嗎？**  
A4: 可以，但您需要購買商業授權才能使用。

**Q4: 是否可以自訂圖像的輸出品質？**  
A5: 當然可以。您可以在 `JpgViewOptions` 與 `PngViewOptions` 中調整相關設定。

**Q5: 在哪裡可以找到更進階的使用範例？**  
A5: 請參閱 [API reference](https://reference.groupdocs.com/viewer/java/) 以取得詳細文件。

## 常見問題

**Q: 如何將 Numbers 檔案轉換為 PDF 而不失去格式？**  
A: 如上所示使用 `PdfViewOptions`；Viewer 會自動保留版面配置、字型與儲存格樣式。

**Q: 能否一次呼叫就將試算表轉換為圖像？**  
A: 可以，`JpgViewOptions` 或 `PngViewOptions` 可在單一步驟完成轉換，讓您指定解析度與品質。

**Q: 是否有辦法批次處理多個 Numbers 檔案？**  
A: 可將 Viewer 邏輯包在迴圈中，為每個檔案重新初始化 `Viewer`，並將每個輸出寫入不同的資料夾。

**Q: 每種輸出格式是否需要單獨的授權？**  
A: 不需要，單一的 GroupDocs.Viewer 授權即可涵蓋所有支援的格式。

**Q: 需要哪個版本的 GroupDocs.Viewer 才能使用這些功能？**  
A: 範例針對 25.2 版，該版完整支援 Numbers 轉換為 PDF/HTML/Image。

## 資源
- **文件說明：** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **API 參考：** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **下載：** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **購買授權：** [Buy a License](https://purchase.groupdocs.com/buy)
- **免費試用：** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **臨時授權：** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **支援論壇：** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-03-05  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs