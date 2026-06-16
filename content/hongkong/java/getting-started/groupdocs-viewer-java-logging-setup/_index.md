---
date: '2026-04-10'
description: 學習如何在 GroupDocs.Viewer for Java 中設定日誌記錄，包括如何新增主控台記錄器與檔案記錄器，以提升文件渲染效果。
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: 如何在 GroupDocs.Viewer for Java 中設定日誌
type: docs
url: /zh-hant/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# 如何在 GroupDocs.Viewer for Java 中設定日誌記錄

在本教學中，您將學習 **如何設定日誌記錄** 於 GroupDocs.Viewer for Java，這可讓您即時了解文件渲染流程，並協助快速排除問題。

## 快速解答
- **日誌提供什麼功能？** 即時回饋渲染操作與錯誤細節。  
- **哪個記錄器會輸出到主控台？** `ConsoleLogger`（新增主控台記錄器）。  
- **哪個記錄器會寫入檔案？** `FileLogger`（新增檔案記錄器）。  
- **啟用日誌記錄是否需要授權？** 不需要，日誌記錄在試用版與授權版皆可使用。  
- **我可以自訂日誌格式嗎？** 可以，透過擴充記錄器類別即可。

## 介紹
使用 **GroupDocs.Viewer for Java** 強化 Java 應用程式的文件渲染流程。本指南將帶您設定日誌記錄，無論是輸出至主控台或檔案，提供關於文件渲染運作的關鍵見解。

![使用 GroupDocs.Viewer for Java 的主控台與檔案日誌記錄](/viewer/getting-started/console-and-file-logging-java.png)

**學習要點：**
- 在 GroupDocs.Viewer for Java 中設定日誌記錄。  
- 實作主控台與檔案為基礎的日誌系統。  
- 使用 GroupDocs.Viewer 將文件渲染為內嵌資源的 HTML。

## 前置條件
確保您已具備：
1. **必要的函式庫：**  
   - GroupDocs.Viewer for Java 函式庫（版本 25.2 或更新）。  

2. **環境設定需求：**  
   - 已在系統上安裝 Java Development Kit（JDK）。  
   - 如 IntelliJ IDEA 或 Eclipse 等整合開發環境（IDE）。  

3. **知識前提：**  
   - 基本的 Java 程式設計概念。  
   - 熟悉 Maven 以管理相依性。  

具備上述前置條件後，即可開始設定 GroupDocs.Viewer for Java！

## 設定 GroupDocs.Viewer for Java
若要使用 GroupDocs.Viewer，請於 Maven 中將其加入專案相依性。操作步驟如下：

### Maven 設定
在 `pom.xml` 檔案中加入以下設定：
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
- **免費試用：** 從 [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) 下載免費試用版。  
- **臨時授權：** 於 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 取得臨時授權，以解除評估限制。  
- **購買授權：** 若需完整功能，請於 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 購買授權。  

### 基本初始化
使用以下範例初始化 GroupDocs.Viewer：
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

此設定為更複雜的日誌配置奠定基礎。

## 如何設定日誌記錄
探討如何使用 GroupDocs.Viewer **新增主控台記錄器** 以及 **新增檔案記錄器**。

### 功能 1：主控台日誌記錄
#### 概述
將日誌輸出至主控台可在終端機即時回饋，對開發或除錯階段相當有用。

#### 步驟
##### 步驟 1：匯入必要類別
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### 步驟 2：設定日誌配置
使用 `ConsoleLogger` 將日誌導向主控台。
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**說明**  
- **ConsoleLogger：** 此類別將日誌導向主控台，提供即時的操作檢視。  
- **HtmlViewOptions.forEmbeddedResources：** 為每頁產生內嵌資源的 HTML，是有效使用 **html view options** 的範例。

#### 疑難排解提示
確保文件路徑正確且可存取。檢查主控台設定中已正確配置日誌語句。

### 功能 2：檔案日誌記錄
#### 概述
將日誌寫入檔案可保留持續的操作紀錄，對稽核或事後分析很有幫助。

#### 步驟
##### 步驟 1：匯入必要類別
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### 步驟 2：設定檔案式日誌配置
使用 `FileLogger` 將日誌寫入指定檔案。
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**說明**  
- **FileLogger：** 此類別將日誌寫入名為 `output.log` 的檔案。  
- **ViewerSettings 搭配 FileLogger：** 設定 GroupDocs.Viewer 將 **viewer 日誌** 捕獲至指定的日誌檔案。

#### 疑難排解提示
確保輸出檔案的目錄具有寫入權限。若日誌寫入失敗，請檢查檔案權限。

## 實務應用
GroupDocs.Viewer 可提升文件管理與渲染功能：
1. **Web 入口網站：** 為網頁使用者即時渲染文件，無需直接下載。  
2. **企業系統：** 與 CRM 工具整合，顯示合約或協議。  
3. **內部儀表板：** 在內部網路中提供報告與簡報的可存取檢視。

## 效能考量與 Java 日誌最佳實踐
在 Java 中使用 GroupDocs.Viewer 時，請留意以下要點：
- **優化資源使用：** 渲染大型文件時監控記憶體消耗。  
- **Java 記憶體管理：** 使用 try‑with‑resources 以自動清理資源。  
- **日誌詳細度：** 調整記錄器等級（如 INFO、DEBUG）以在細節與效能影響之間取得平衡——這是 **java logging best practices** 的關鍵部分。  

## 結論
您已學會在 GroupDocs.Viewer for Java 中 **設定日誌記錄**，無論是快速的主控台檢視或持久的檔案紀錄。此功能對除錯、監控與稽核應用程式極為重要。請探索更多設定、嘗試自訂記錄器，並將 GroupDocs.Viewer 與其他系統整合，以提升韌性。

準備好將實作技能提升到更高層次了嗎？嘗試在不同環境中設定日誌，觀察它如何增強應用程式的可靠性！

## 資源
- [文件說明](https://docs.groupdocs.com/viewer/java/)
- [API 參考](https://reference.groupdocs.com/viewer/java/)
- [下載](https://downloads.groupdocs.com/viewer/java/)

---

**最後更新：** 2026-04-10  
**測試版本：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

---