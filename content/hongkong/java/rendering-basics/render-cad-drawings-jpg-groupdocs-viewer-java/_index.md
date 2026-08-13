---
date: '2026-06-10'
description: 了解如何使用 GroupDocs.Viewer for Java 將 DWG 渲染為 JPG，並將 CAD 檔案轉換為 JPG，提供逐步教學。
keywords:
- render dwg as jpg
- convert cad files to jpg
- java convert dwg to jpg
schemas:
- author: GroupDocs
  dateModified: '2026-06-10'
  description: Learn how to render DWG as JPG and convert CAD files to JPG using GroupDocs.Viewer
    for Java in a step-by-step tutorial.
  headline: Render DWG as JPG with GroupDocs.Viewer Java – Full Guide
  type: TechArticle
- description: Learn how to render DWG as JPG and convert CAD files to JPG using GroupDocs.Viewer
    for Java in a step-by-step tutorial.
  name: Render DWG as JPG with GroupDocs.Viewer Java – Full Guide
  steps:
  - name: '**Architectural Design** – Share building plans with clients who don’t
      have CAD software.'
    text: '**Architectural Design** – Share building plans with clients who don’t
      have CAD software.'
  - name: '**Engineering Projects** – Include detailed schematics in PowerPoint decks.'
    text: '**Engineering Projects** – Include detailed schematics in PowerPoint decks.'
  - name: '**Interior Design** – Quickly generate mood‑board images from floor‑plan
      DWG files.'
    text: '**Interior Design** – Quickly generate mood‑board images from floor‑plan
      DWG files.'
  type: HowTo
- questions:
  - answer: Yes, loop through page numbers and call `viewer.view(page, options, stream)`
      for each page; the library streams each JPG independently.
    question: Can I render multiple pages of a DWG in one call?
  - answer: Absolutely – you can render to PNG, BMP, or TIFF by using `PngViewOptions`,
      `BmpViewOptions`, or `TiffViewOptions` respectively.
    question: Does GroupDocs.Viewer support other raster formats?
  - answer: The engine handles files up to 2 GB; for larger archives split the drawing
      into separate files before rendering.
    question: How large a DWG can be processed?
  - answer: No, GroupDocs.Viewer performs rendering entirely on the server side without
      needing AutoCAD installed.
    question: Is a separate CAD installation required?
  - answer: Java 8, 11, 17, and newer are fully supported.
    question: What Java versions are compatible?
  type: FAQPage
title: 使用 GroupDocs.Viewer Java 渲染 DWG 為 JPG – 完整指南
type: docs
url: /zh-hant/java/rendering-basics/render-cad-drawings-jpg-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer Java 渲染 DWG 為 JPG：逐步教學

## 簡介

使用 GroupDocs.Viewer Java 將 DWG 渲染為 JPG，可輕鬆將複雜的 CAD 圖紙轉換為輕量、適合網頁的圖像。於本指南中，您將了解如何設定程式庫、配置輸出路徑，以及使用 PC3 檔案來控制圖像尺寸與品質。完成後，您只需幾行 Java 程式碼即可自動將 DWG 檔案轉換為 JPG。

![使用 GroupDocs.Viewer for Java 渲染 CAD 圖紙為 JPG](/viewer/rendering-basics/render-cad-drawings-as-jpg-java.png)

## 快速答覆
- **哪個程式庫負責轉換？** GroupDocs.Viewer for Java.
- **產生的檔案格式是什麼？** JPG images.
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買完整授權。
- **我可以控制圖像尺寸嗎？** 可以，透過 PC3 設定檔。
- **Java 8 足夠嗎？** 支援 Java 8 及更新版本。

## 什麼是「render dwg as jpg」？

*Render dwg as jpg* 是將 DWG（AutoCAD）圖紙轉換為 JPEG 點陣圖的過程。此轉換在保留視覺忠實度的同時，使檔案易於在瀏覽器、電子郵件或行動應用程式中檢視。它亦能大幅減少檔案大小，提升載入速度，並簡化跨平台與裝置的分發。

## 為何使用 GroupDocs.Viewer for Java？

GroupDocs.Viewer 支援 **50+** 種輸入格式——包括 DWG、DXF 與 DWF，且能在不將整個檔案載入記憶體的情況下渲染多百頁的圖紙。此程式庫在標準 8 核心伺服器上可於 5 秒內處理一般 200 頁的 CAD 檔案，產出保留線寬與顏色的高品質 JPG。

## 先決條件

### 必需的程式庫與相依性
- **GroupDocs.Viewer for Java** – 版本 25.2（或更新）。

### 環境設定需求
- Java Development Kit 8 或更新版本。
- Maven 或 Gradle 用於相依性管理。

### 知識先備條件
- 基本的 Java 語法。
- 熟悉檔案系統路徑。

## 設定 GroupDocs.Viewer for Java

首先，加入必要的相依性。若使用 Maven，請加入以下設定：

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

### 授權取得
- **免費試用**：從 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 下載試用版。
- **臨時授權**：於 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 取得臨時授權以獲得完整功能。
- **購買**：長期使用請透過 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 購買授權。

### 其他資源
- [GroupDocs Viewer 文件說明](https://docs.groupdocs.com/viewer/java/)
- [API 參考文件](https://reference.groupdocs.com/viewer/java/)
- [下載 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [購買授權](https://purchase.groupdocs.com/buy)
- [免費試用](https://releases.groupdocs.com/viewer/java/)
- [臨時授權](https://purchase.groupdocs.com/temporary-license/)
- [支援論壇](https://forum.groupdocs.com/c/viewer/9)

## 基本初始化

`Viewer` 類別會載入文件，並提供將頁面渲染為各種格式的方法。設定好環境並加入相依性後，於 Java 應用程式中初始化 GroupDocs.Viewer：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/dwg/file.dwg")) {
            // Your rendering code will go here.
        }
    }
}
```

## 實作指南

### 使用特定設定渲染 CAD 圖紙

此功能可使用 PC3 檔案中定義的設定，將 DWG 檔案渲染為 JPG 圖像。

#### 概觀

我們將載入 DWG 圖紙，建立 `JpgViewOptions`，並將選項指向自訂的 PC3 檔案，以定義頁面大小、DPI 與線條渲染樣式。

#### 步驟實作

##### 匯入必要的套件

`JpgViewOptions` 指定 JPEG 圖像的渲染設定，如解析度、頁面大小與輸出格式；`Viewer` 則執行實際的轉換。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;
```

##### 定義輸出目錄與檔案路徑

輸出資料夾可將產生的圖像整理有序，亦方便在批次處理後清理。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("pc3_result.jpg");
```

##### 載入 CAD 圖紙並設定組態

`Viewer` 讀取 DWG 檔案，`setRenderOptions` 方法在渲染每頁前套用 PC3 設定。

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Set the PC3 configuration for rendering
    options.getCadOptions().setPc3File(TestFiles.SAMPLE_PC3_CONFIG);
    
    // Render the CAD drawing to a JPG image
    viewer.view(options);
}
```

#### 故障排除技巧
- **缺少相依性**：確認 Maven 坐標與您安裝的版本相符。
- **路徑不正確**：使用絕對路徑或 `Path.of(...)` 以避免平台特定問題。

## 渲染輸出路徑設定

正確的路徑處理可避免找不到檔案的錯誤，並簡化批次作業。

### 定義輸出目錄路徑

您可將渲染出的圖像存放於以來源檔案命名的子資料夾中，便於查找。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
```

### 建立渲染圖像的檔案路徑

使用如 `drawing_page_{page}.jpg` 的命名模式，可在之後需要引用單獨頁面時提供便利。

```java
Path pageFilePathFormat = outputDirectory.resolve("pc3_result.jpg");
```

## 實務應用

1. **建築設計** – 與沒有 CAD 軟體的客戶分享建築平面圖。
2. **工程專案** – 在 PowerPoint 簡報中加入詳細的原理圖。
3. **室內設計** – 快速從平面圖 DWG 檔產生情緒板圖像。

## 效能考量

- **資源管理**：渲染完成後立即呼叫 `viewer.close()` 以釋放檔案句柄。
- **記憶體調校**：對於非常大的 DWG 檔，增加 JVM 堆積大小（`-Xmx2g`）以避免 `OutOfMemoryError`。

## 如何使用 GroupDocs.Viewer Java 渲染 DWG 為 JPG？

使用 `new Viewer("drawing.dwg")` 載入 DWG，建立指向您的 PC3 檔的 `JpgViewOptions` 物件，並呼叫 `viewer.view(pageNumber, options, outputStream)`。此單行呼叫會將指定頁面渲染為高品質 JPG，並自動套用 PC3 版面規則。該方法亦會回傳渲染後的中繼資料，讓您在轉換後驗證頁數與圖像尺寸。

## 什麼是 PC3 設定檔？

PC3 檔案是 AutoCAD 的純文字設定檔，用於定義頁面大小、列印樣式、DPI 以及點陣輸出的線寬比例。提供自訂 PC3 可讓您在所有渲染圖紙中統一圖像尺寸。透過編輯 PC3，您可控制邊距、紙張方向與顏色對映，確保每次轉換皆產生一致的視覺結果。

## 常見問題與解決方案

- **空白圖像**：確保 PC3 檔案引用有效的印表機，且 DWG 包含可列印的圖層。
- **解析度過低**：在 PC3 檔內提升 DPI 設定，或以程式方式設定 `options.setResolution(300)`。
- **授權錯誤**：確認授權檔已放置於應用程式的 classpath 中，且試用期未過期。

## 常見問答

**Q: 我可以一次呼叫渲染 DWG 的多個頁面嗎？**  
A: 可以，遍歷頁碼並對每頁呼叫 `viewer.view(page, options, stream)`；程式庫會獨立串流每個 JPG。

**Q: GroupDocs.Viewer 支援其他點陣格式嗎？**  
A: 當然可以——您可分別使用 `PngViewOptions`、`BmpViewOptions` 或 `TiffViewOptions` 渲染為 PNG、BMP 或 TIFF。

**Q: 可處理多大的 DWG 檔案？**  
A: 引擎可處理最高 2 GB 的檔案；若檔案更大，請在渲染前將圖紙分割為多個檔案。

**Q: 需要額外安裝 CAD 軟體嗎？**  
A: 不需要，GroupDocs.Viewer 完全在伺服器端執行渲染，無需安裝 AutoCAD。

**Q: 支援哪些 Java 版本？**  
A: 完全支援 Java 8、11、17 及更新版本。

## 結論

您現在已掌握使用 GroupDocs.Viewer for Java **render dwg as jpg** 的完整、可投入生產的方案。本教學涵蓋環境設定、基於 PC3 的組態、路徑處理與效能技巧。將此模式整合至批次流程、Web 服務或桌面工具，即可為任何 CAD 圖紙提供快速、高品質的 JPEG 預覽。

---

**最後更新：** 2026-06-10  
**測試版本：** GroupDocs.Viewer for Java 25.2  
**作者：** GroupDocs

## 相關教學

- [如何使用 GroupDocs.Viewer for Java 以自訂尺寸與背景色渲染 CAD 圖紙為 PNG](/viewer/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/)
- [使用 GroupDocs.Viewer 渲染 CAD 圖層 Java – 完整指南](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [使用 GroupDocs.Viewer Java 將 CAD 圖紙切割為圖塊以提升渲染效能](/viewer/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/)