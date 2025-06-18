---
"date": "2025-04-24"
"description": "學習如何使用 GroupDocs.Viewer Java 將 Excel 檔案轉換為 HTML、JPG、PNG 和 PDF。本指南涵蓋設定、渲染選項和實際應用。"
"title": "如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML/JPG/PNG/PDF — 逐步指南"
"url": "/zh-hant/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
---

# 如何使用 GroupDocs.Viewer Java 將 Excel 轉換為 HTML/JPG/PNG/PDF：逐步指南

## 介紹

在許多情況下，將電子表格資料轉換為 HTML、JPG、PNG 或 PDF 等各種格式，同時保留行標題和列標題等關鍵細節至關重要。無論您是產生報告、與利益相關者共享信息，還是將電子表格整合到 Web 應用程式中，轉換 Excel 表格都是關鍵需求。本指南將引導您了解 GroupDocs.Viewer Java 如何輕鬆、精準地完成這些任務。

**您將學到什麼：**
- 設定並使用 GroupDocs.Viewer for Java
- 將 Excel 檔案渲染為 HTML、JPG、PNG 和 PDF 格式
- 配置選項以在輸出中包含行和列標題
- 渲染文檔的實際應用

在我們深入實施之前，讓我們先了解所需的先決條件。

## 先決條件

在使用 GroupDocs.Viewer Java 呈現電子表格之前，請確保您已：

### 所需的庫和依賴項

使用 Maven 設定 Java 版 GroupDocs.Viewer。以下是如何將其添加到項目中：

**Maven設定：**
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

### 環境設定
- 確保您已安裝 Java 開發工具包 (JDK)。
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE 以方便開發。

### 知識前提
- 熟悉 Java 程式設計
- 對 Maven 依賴管理有基本的了解

有了這些先決條件，讓我們繼續設定 GroupDocs.Viewer for Java 並開始實作其功能。

## 為 Java 設定 GroupDocs.Viewer

GroupDocs.Viewer for Java 是一個功能強大的程式庫，可讓您以各種格式呈現文件。以下是使用方法：

### 安裝訊息
如上所述，使用 Maven 將 GroupDocs.Viewer 新增為專案依賴項 `pom.xml` 文件。

### 許可證取得步驟
1. **免費試用：** 下載試用版 [GroupDocs 免費試用](https://releases。groupdocs.com/viewer/java/).
2. **臨時執照：** 取得臨時許可證以獲得更多功能 [GroupDocs 臨時許可證](https://purchase。groupdocs.com/temporary-license/).
3. **購買：** 如需完全存取權限和支持，請購買許可證 [GroupDocs 購買](https://purchase。groupdocs.com/buy).

### 基本初始化
安裝後，您可以使用以下命令初始化 GroupDocs.Viewer：
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // 此處的程式碼用於使用檢視器
        }
    }
}
```
這將初始化您的環境，為您渲染文件做好準備。

## 實施指南

讓我們分解每個功能並詳細探討如何實現它們。

### 將電子表格渲染為 HTML
**概述：** 將 Excel 工作表轉換為 HTML 格式，同時保留用於網頁演示或報表的行和列標題。

#### 逐步實施：
##### 1.導入所需的庫
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2.設定輸出目錄
定義渲染檔案的儲存位置。
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3.初始化檢視器並配置選項
使用 GroupDocs.Viewer 呈現文件：
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // 啟用電子表格中的行和列標題的呈現。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 頁。
}
```
**解釋：** 這 `HtmlViewOptions` 類別用於配置 HTML 輸出。設定 `setRenderHeadings(true)` 確保行和列標題在呈現的 HTML 中可見。

### 將電子表格渲染為 JPG
**概述：** 將 Excel 工作表轉換為高品質影像檔案 (JPG)，同時包含行和列標題，非常適合視覺演示或列印輸出。

#### 逐步實施：
##### 1.導入所需的庫
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2.設定輸出目錄
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3.初始化檢視器並配置選項
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // 啟用電子表格中的行和列標題的呈現。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 頁。
}
```
**解釋：** `JpgViewOptions` 處理影像設定。 `setRenderHeadings(true)` 選項確保標題包含在 JPG 輸出中。

### 將電子表格渲染為 PNG
**概述：** 將 Excel 工作表轉換為 PNG 格式，同時保留行和列標題，適合高品質的圖片輸出。

#### 逐步實施：
##### 1.導入所需的庫
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2.設定輸出目錄
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3.初始化檢視器並配置選項
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // 啟用電子表格中的行和列標題的呈現。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 頁。
}
```
**解釋：** `PngViewOptions` 用於 PNG 設定。使用 `setRenderHeadings(true)`，標題包含在輸出影像中。

### 將電子表格渲染為 PDF
**概述：** 將 Excel 工作表轉換為 PDF 格式，同時確保行和列標題可見，非常適合存檔或共用文件。

#### 逐步實施：
##### 1.導入所需的庫
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2.設定輸出目錄
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3.初始化檢視器並配置選項
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // 啟用電子表格中的行和列標題的呈現。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 頁。
}
```
**解釋：** `PdfViewOptions` 配置 PDF 輸出設定。 `setRenderHeadings(true)` 選項確保標題在最終 PDF 中可見。

## 實際應用
以下是一些可以應用這些功能的實際場景：

1. **業務報告：** 將 Excel 資料轉換為 HTML 或 PDF 格式以便於傳播和查看，與利害關係人分享詳細報告。
2. **數據視覺化：** 將電子表格轉換為 JPG 或 PNG 等圖像格式以用於演示，確保標題為可視化資料提供上下文。
3. **文件歸檔：** 使用 PDF 轉換以通用可存取的格式存檔文檔，保留所有必要的細節，例如標題。