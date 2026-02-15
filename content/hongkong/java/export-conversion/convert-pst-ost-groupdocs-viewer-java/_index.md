---
date: '2026-02-15'
description: 學習如何使用 GroupDocs.Viewer for Java 將 pst 轉換為 html 以及 JPG、PNG、PDF 等其他格式。本指南涵蓋所有必要的步驟和設定。
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: 使用 GroupDocs.Viewer for Java 將 PST 轉換為 HTML、JPG、PNG、PDF
type: docs
url: /zh-hant/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

 GroupDocs.Viewer for Java 25.2  
**作者：** GroupDocs  

But keep bold formatting.

Now ensure all markdown formatting preserved.

Check for any other elements: there are no other shortcodes.

Now produce final content.

# 使用 GroupDocs.Viewer for Java 轉換 PST 為 HTML、JPG、PNG、PDF

您是否想要 **convert pst to html** 或其他格式如 JPG、PNG 或 PDF？使用功能強大的 GroupDocs.Viewer for Java 函式庫，這項工作既簡單又高效。在本教學中，您將學習如何將 Outlook PST/OST 檔案轉換為適合網頁的 HTML、影像檔或單一 PDF，讓您的電子郵件檔案易於分享與保存。

![使用 GroupDocs.Viewer for Java 轉換 PST/OST 為 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**您將學到的內容**
- 如何在 Maven 專案中設定 GroupDocs.Viewer for Java。  
- 逐步說明如何使用 **java convert pst** 檔案轉換為 HTML、JPG、PNG 與 PDF。  
- 最佳效能與常見陷阱的設定技巧。

## 快速解答
- **什麼函式庫負責 PST 轉換？** GroupDocs.Viewer for Java.  
- **我可以直接將 PST 轉換為 PDF 嗎？** 可以，使用 `PdfViewOptions`.  
- **在正式環境需要授權嗎？** 需要有效的 GroupDocs 授權。  
- **支援哪個 Java 版本？** JDK 8 或更高版本。  
- **我需要手動提取附件嗎？** 不需要，檢視器會自動渲染附件。

## 如何使用 GroupDocs.Viewer for Java 轉換 pst 為 html
以下您將看到轉換流程的簡要概述，之後再深入詳細程式碼範例。

### 為什麼選擇 GroupDocs.Viewer？
- **高保真** 渲染電子郵件內容、附件與格式。  
- **多種輸出格式**（HTML、JPG、PNG、PDF）可透過單一 API 取得。  
- **無外部相依性** – 所有功能皆在您的 Java 應用程式內執行。

## 前置條件

- **GroupDocs.Viewer for Java** – 版本 25.2 或更新。  
- **Java Development Kit (JDK)** – 8 或更新版本。  
- 用於相依性管理的 Maven。  
- 基本的 Java 知識與 Maven 使用經驗。

## 設定 GroupDocs.Viewer for Java

將 GroupDocs 儲存庫與相依性加入您的 `pom.xml`：

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
- **免費試用** – 無需付費即可探索全部功能。  
- **臨時授權** – 如有需要可延長評估時間。  
- **正式授權** – 正式部署時必須取得。

### 基本初始化

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## 實作指南

以下各節將逐步說明如何將 PST/OST 檔案渲染為每種支援的格式。

### 渲染 PST/OST 文件為 HTML

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 步驟 2：設定載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 3：初始化 Viewer 並渲染 HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### 渲染 PST/OST 文件為 JPG

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### 步驟 2：設定載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 3：初始化 Viewer 並渲染 JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 渲染 PST/OST 文件為 PNG

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 步驟 2：設定載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 3：初始化 Viewer 並渲染 PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 渲染 PST/OST 文件為 PDF

#### 步驟 1：設定輸出目錄

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 步驟 2：設定載入選項

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步驟 3：初始化 Viewer 並渲染 PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## 實務應用

- **Email Archiving:** 將大型 PST 檔案轉換為可搜尋的 HTML 或 PDF，以符合合規需求。  
- **Document Management Systems:** 將轉換後的檔案儲存於僅接受 PDF、PNG 或 JPG 的系統中。  
- **Collaboration Platforms:** 在 Slack 或 Teams 等協作平台上以影像形式分享轉換後的電子郵件。  
- **Legal Review:** 向法院提供電子郵件證據的 PDF 版本。  
- **Backup Strategies:** 為關鍵訊息保留輕量的 PNG 或 JPG 快照。

## 效能考量

- **資源管理**：在處理多個檔案時重複使用 `Viewer` 實例，以減少開銷。  
- **記憶體調校**：根據伺服器容量調整 `loadOptions.setResourceLoadingTimeout`。  
- **非同步處理**：將轉換工作交由背景執行緒，以提升 UI 響應速度。

## 常見問題

**Q: 我如何使用相同的程式碼基礎 **convert pst to pdf**？**  
A: 使用 `PdfViewOptions` 如 PDF 渲染章節所示；其餘程式碼保持相同。

**Q: GroupDocs.Viewer 能處理加密的 PST 檔案嗎？**  
A: 可以，在渲染前透過 `LoadOptions.setPassword("yourPassword")` 提供密碼。

**Q: **java convert pst** 轉換為 PNG 與 JPG 有何差異？**  
A: PNG 保持無損品質，適合截圖；JPG 檔案較小，適合電子郵件預覽。

**Q: 有沒有方法可以 **how to convert pst** 批次處理檔案？**  
A: 將渲染邏輯包在迴圈中，遍歷 PST 檔案目錄；對每個檔案重複使用相同的 `Viewer` 設定。

## 結論

您現在擁有一套完整、可直接投入生產環境的指南，使用 GroupDocs.Viewer for Java **convert pst to html**、JPG、PNG 與 PDF。依照上述步驟，您即可將電子郵件轉換整合至任何基於 Java 的工作流程，提升可存取性，並符合合規需求。

---

**最後更新：** 2026-02-15  
**測試版本：** GroupDocs.Viewer for Java 25.2  
**作者：** GroupDocs