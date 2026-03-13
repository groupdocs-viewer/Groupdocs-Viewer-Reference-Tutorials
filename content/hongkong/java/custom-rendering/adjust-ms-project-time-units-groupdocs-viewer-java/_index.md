---
date: '2026-01-28'
description: 了解如何使用 GroupDocs Viewer Java 調整 MS Project 時間單位。高效且精準地簡化您的專案文件渲染流程。
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 如何使用 GroupDocs Viewer Java 調整 MS Project 時間單位 - 逐步指南
type: docs
url: /zh-hant/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# 如何使用 groupdocs viewer java 調整 MS Project 時間單位：一步一步指南

## 介紹
您是否厭倦了在將 MS Project 文件渲染為 HTML 格式之前手動調整時間單位？這個過程既繁瑣又容易出錯，尤其是面對大型專案時。使用 **groupdocs viewer java**，您可以透過程式碼輕鬆調整時間單位設定，確保精確與高效。

![使用 GroupDocs.Viewer for Java 調整 MS Project 時間單位](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

在本指南中，我們將示範如何使用 groupdocs viewer java 將 MS Project 文件的時間單位變更為天。完成本教學後，您將能夠：
- 為使用 GroupDocs.Viewer 渲染 MS Project 檔案設定環境。
- 直接在程式碼中調整專案管理時間單位。
- 將這些調整無縫整合到您的應用程式中。

在開始之前，請先確保您已準備好所有必要的項目！

## 快速回答
- **哪個函式庫負責 MS Project 渲染？** groupdocs viewer java  
- **可以設定哪種時間單位？** 天（透過 `TimeUnit.DAYS`）  
- **需要授權嗎？** 提供試用或臨時授權；正式環境需購買永久授權。  
- **哪個 IDE 最適合？** 任何支援 Maven 的 Java IDE（IntelliJ IDEA、Eclipse 等）。  
- **是否必須使用 Maven？** 必須，Maven 可簡化 groupdocs viewer java 的相依管理。

## 什麼是 groupdocs viewer java？
groupdocs viewer java 是一套 Java SDK，讓開發者能將各種文件格式（包括 MS Project 檔案）渲染成網頁友善的格式，如 HTML 或圖片。它抽象化了檔案解析的複雜度，讓您專注於業務邏輯。

## 為什麼要使用 groupdocs viewer java 調整時間單位？
將預設的時間單位（通常為分鐘）改為天，可讓渲染出的結果對利害關係人更易閱讀，符合一般報告的頻率，也能減少 HTML 報告中的視覺雜訊。這在將專案時間線嵌入儀表板或產生日報狀態摘要時特別有價值。

## 前置條件
### 必要的函式庫與相依性
完成本教學您需要：
- **groupdocs viewer java** 函式庫（版本 25.2 或更新）。  
- 已在機器上安裝 Maven 以管理相依性。  
- 基本的 Java 程式設計概念。

### 環境設定需求
確保開發環境已安裝 JDK（Java Development Kit）並使用支援 Maven 專案的 IDE，如 IntelliJ IDEA 或 Eclipse。

### 知識前提
熟悉 Java 語法、檔案操作以及 Maven 相依管理會有幫助，但本指南旨在讓所有技能層級的使用者都能輕鬆上手。

## 設定 groupdocs viewer java
要開始使用 groupdocs viewer java，請在專案的 `pom.xml` 中加入相依性：

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

### 取得授權的步驟
groupdocs 提供函式庫的免費試用，讓您在購買或申請臨時授權前先行體驗功能：
- **免費試用**：前往 [GroupDocs 免費試用](https://releases.groupdocs.com/viewer/java/) 下載並開始使用函式庫。  
- **臨時授權**：如需延長測試，可申請 [臨時授權](https://purchase.groupdocs.com/temporary-license/)。  
- **購買**：若您決定將 groupdocs.viewer java 用於專案，請直接於其 [購買頁面](https://purchase.groupdocs.com/buy) 取得授權。

### 基本初始化與設定
在 Maven `pom.xml` 加入相依性後，即可開始撰寫程式碼。使用檔案路徑建立 Viewer 實例，並為渲染作好準備。

## 實作指南
以下將一步步說明如何使用 groupdocs viewer java 調整 MS Project 文件的時間單位。

### 功能概述：調整 MS Project 文件的時間單位
此功能可將專案管理的時間單位從預設（通常為分鐘）改為天，使渲染出的 HTML 更友善，且符合一般報告標準。

#### 步驟 1：定義輸出目錄與頁面檔案路徑格式
首先，指定渲染後 HTML 檔案的存放位置：

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

使用此目錄可為 MS Project 文件的每一頁動態解析檔案路徑：

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### 步驟 2：初始化檢視選項
建立包含嵌入資源的檢視選項，以指定專案的檢視與渲染方式：

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### 步驟 3：調整時間單位設定
將專案管理的時間單位設定為天，這通常較適合簡報與報告使用：

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### 步驟 4：渲染 MS Project 文件
最後，使用 Viewer 類別搭配先前設定的檢視選項來渲染文件：

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### 疑難排解小技巧
- 確認輸出目錄路徑正確且具有寫入權限。  
- 檢查 MS Project 檔案路徑是否正確且可存取。  
- 若發生渲染問題，請留意 Viewer 類別拋出的例外資訊。

## 實務應用
以下是調整 MS Project 文件時間單位的幾個真實情境：
1. **專案報告** – 利害關係人通常較偏好每日摘要，而非分鐘級細節。  
2. **與儀表板整合** – 將時間線嵌入需要天級粒度的商業儀表板。  
3. **自動化更新** – 系統每日自動刷新專案狀態的需求。

## 效能考量
處理大型 MS Project 檔案時，請留意以下最佳化方式：
- 如非必要，請適度使用嵌入資源，以免載入不需要的部分。  
- 同時處理多個或極大檔案時，需監控記憶體使用情況。  
- 善用 Java 的垃圾回收機制，妥善管理資源的配置與釋放。

## 結論
您已學會如何使用 groupdocs viewer java 調整 MS Project 時間單位。此功能簡化了專案文件的渲染流程，提升可存取性，並更容易整合至其他系統。

建議您進一步探索 groupdocs viewer java 的其他功能，以強化文件管理解決方案。準備好更進一步了嗎？試著在下一個專案中實作此解決方案吧！

## 常見問題
**1. GroupDocs.Viewer for Java 的用途是什麼？**  
GroupDocs.Viewer for Java 讓開發者能將各種文件（包括 MS Project）渲染成 HTML 或圖片，以供檢視。

**2. 我可以用 GroupDocs.Viewer 處理其他文件類型嗎？**  
可以，GroupDocs.Viewer 支援除 MS Project 外的多種格式，如 PDF、Word 文件與試算表。

**3. 如何處理 GroupDocs.Viewer 的授權？**  
GroupDocs 提供多種授權選項，包括免費試用、延長測試的臨時授權，以及購買後的永久授權。

**4. 若渲染專案文件時發生錯誤該怎麼辦？**  
請檢查檔案路徑、確保輸出目錄具寫入權限，並參考 GroupDocs.Viewer 拋出的例外訊息進行排除。

**5. 我可以自訂文件的渲染方式嗎？**  
當然可以！GroupDocs.Viewer 提供多種自訂選項，包括設定專案時間單位、選擇要嵌入的資源等。

## 資源
- [文件說明](https://docs.groupdocs.com/viewer/java/)  
- [API 參考文件](https://reference.groupdocs.com/viewer/java/)  
- [下載 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [購買授權](https://purchase.groupdocs.com/buy)

---

**最後更新：** 2026-01-28  
**測試環境：** groupdocs viewer java 25.2  
**作者：** GroupDocs