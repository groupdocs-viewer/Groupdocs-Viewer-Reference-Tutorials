---
date: '2026-03-29'
description: 學習如何使用 GroupDocs Viewer 於 Java 中建立 HTML 檢視 MPP，按時間間隔渲染專案文件，並提供逐步程式碼。
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: 使用 GroupDocs Viewer (Java) 建立 MPP 的 HTML 檢視
type: docs
url: /zh-hant/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# 如何在 Java 中使用 GroupDocs Viewer 按時間間隔渲染專案文件

在本教學中，您將學習如何使用 GroupDocs Viewer for Java **create html view mpp**，只渲染符合特定時間區間的 Microsoft Project 檔案部分。我們將逐步說明 Maven 設定、程式碼配置以及實務情境，讓您能將精確的時間軸視圖直接嵌入應用程式中。

![使用 GroupDocs.Viewer for Java 按時間間隔渲染專案文件](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## 快速解答
- **此功能的作用是什麼？** 它僅渲染介於開始日期與結束日期之間的 Microsoft Project 檔案部分。  
- **使用哪種輸出格式？** HTML（內嵌資源），非常適合網頁整合。  
- **是否需要授權？** 免費試用可用於評估；正式環境需購買完整授權。  
- **可以在執行時變更日期範圍嗎？** 可以——在渲染選項中調整 `setStartDate` 與 `setEndDate` 的值。  
- **支援所有 Java 版本嗎？** 只要使用 GroupDocs.Viewer 25.2 或更新版本，即可在 Java 8 以上執行。  

## 如何為專案文件建立 html view mpp
GroupDocs Viewer 能將 Microsoft Project 檔案（`.mpp`、`.mpt`）轉換為 HTML 頁面。透過在渲染選項中設定開始與結束日期，即可將輸出限制在您關注的時間區段，從而減少檔案大小並加快頁面載入速度。

## 在此情境下「How to Use GroupDocs」是什麼意思？
GroupDocs Viewer 是一個 Java 函式庫，可將超過 100 種檔案格式轉換為適合網頁的呈現方式。當您 **how to use GroupDocs** 於專案檔案時，便能在不需要客戶端安裝 Microsoft Project 的情況下，提取、視覺化與分享排程資料。

## 為什麼要以時間間隔渲染專案文件？
- **聚焦分析：** 僅顯示您關心的階段（例如 2024 年第 3 季）。  
- **效能：** 較小的 HTML 輸出可加快頁面載入速度。  
- **整合性：** 可將時間軸視圖嵌入儀表板、報告入口網站或自訂專案管理工具中。  

## 前置條件
- **GroupDocs.Viewer for Java** 版本 25.2 或以上。  
- Java Development Kit (JDK) 8 或更新版本。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 基本的 Maven 知識。  

## 設定 GroupDocs.Viewer for Java

### Maven 依賴

將以下儲存庫與依賴項加入您的 `pom.xml`：

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

1. **免費試用** – 從 [GroupDocs 下載頁面](https://releases.groupdocs.com/viewer/java/) 下載試用版。  
2. **臨時授權** – 透過 [此連結](https://purchase.groupdocs.com/temporary-license/) 取得延長測試的臨時授權。  
3. **購買** – 若需無限制的正式使用，請於 [GroupDocs 購買頁面](https://purchase.groupdocs.com/buy) 購買授權。  

### 基本 Viewer 初始化

以下程式碼片段示範如何建立指向 Microsoft Project 檔案（`.mpp`）的 `Viewer` 實例：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## 步驟式實作指南

### 1. 定義輸出目錄

建立一個資料夾，用於儲存產生的 HTML 頁面：

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*為什麼？* 將渲染檔案妥善組織，可更輕鬆地從 Web 伺服器提供或嵌入 UI 中。

### 2. 使用您的專案檔案初始化 Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*為什麼？* 載入文件會初始化內部解析器，並使專案相關的中繼資料可供存取。

### 3. 取得專案檔案的檢視資訊

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*為什麼？* `ProjectManagementViewInfo` 可取得排程的開始與結束日期，稍後可用於限制渲染範圍。

### 4. 設定 HTML 渲染選項（從專案產生 HTML）

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*為什麼？* 設定 `StartDate` 與 `EndDate` 可指示 GroupDocs 僅在該時間窗口內 **generate html view mpp** 資料。

### 5. 執行渲染程序

```java
viewer.view(viewOptions);
```

*為什麼？* 此呼叫會產生一系列自包含的 HTML 頁面，呈現您專案排程中選取的時間切片。

## 常見問題與除錯
- **檔案路徑錯誤** – 請再次確認來源 `.mpp` 檔案與輸出目錄皆存在。  
- **不支援的檔案類型** – 確認文件為支援的 Project 格式（例如 `.mpp`、`.mpt`）。  
- **授權錯誤** – 試用授權可能有限制渲染次數；請改用正式授權以獲得無限制使用。  

## 實務應用
1. **專案時間軸分析** – 僅向利害關係人顯示當前階段。  
2. **自動化報告** – 產生具時間限制的 HTML 報告，用於每週狀態更新。  
3. **與儀表板整合** – 將渲染頁面嵌入 BI 工具或自訂入口網站。  
4. **歸檔** – 保存專案排程的網頁友好快照，以備未來參考。  

## 效能建議
- 使用 *embedded resources* 選項，使每個 HTML 頁面自包含，減少 HTTP 請求。  
- 對於極大型專案，建議分段渲染較小的日期區間，以降低記憶體使用量。  
- 服務完畢後清除暫存檔，以防磁碟空間膨脹。  

## 結論
您現在已了解如何 **how to use GroupDocs** Viewer 在特定時間區間內渲染專案文件，並在 Java 中 **generate HTML from project** 資料。此功能簡化時間軸視覺化、提升報告效率，且能順利整合至現代 Web 應用程式。

### 後續步驟
- 探索其他 Viewer 功能，如浮水印、密碼保護或自訂 CSS 樣式。  
- 將此渲染流程與 REST API 結合，以提供即時的時間軸視圖。  

## 常見問答

**Q: GroupDocs.Viewer 支援哪些檔案格式？**  
A: GroupDocs.Viewer 支援多種格式，包括 Microsoft Project (MPP)、PDF、Word、Excel、PowerPoint 等等。

**Q: 如何開始使用 GroupDocs.Viewer 的免費試用？**  
A: 您可從 [此處](https://releases.groupdocs.com/viewer/java/) 下載試用版。

**Q: 可以在不嵌入資源的情況下渲染文件嗎？**  
A: 可以，您可以選擇其他 HTML 檢視選項，使用外部資源連結而非嵌入。

**Q: 如果文件過大無法渲染該怎麼辦？**  
A: 可將文件拆分為較小的區段，或僅渲染所需的日期範圍，如前述示例所示。

**Q: 如何處理渲染錯誤？**  
A: 請檢查所有設定、確認授權有效，並參考 GroupDocs 文件以取得錯誤代碼說明。

## 資源
- **文件**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 參考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下載**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **購買**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **免費試用**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **臨時授權**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **支援**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新:** 2026-03-29  
**測試環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs  

---