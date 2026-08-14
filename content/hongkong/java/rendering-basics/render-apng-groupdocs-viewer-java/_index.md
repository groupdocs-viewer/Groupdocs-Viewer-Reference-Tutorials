---
date: '2026-06-20'
description: GroupDocs Viewer Java 教學，示範如何將 APNG 檔案渲染為 HTML、JPG、PNG 和 PDF。包括設定步驟、程式碼片段以及實務案例。
keywords:
- groupdocs viewer java tutorial
- render animated png
- how to convert apng to jpg
schemas:
- author: GroupDocs
  dateModified: '2026-06-20'
  description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  headline: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  type: TechArticle
- description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  name: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  steps:
  - name: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
    text: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
  - name: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
    text: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
  - name: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
    text: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
  - name: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
    text: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
  - name: '**Configure Paths** – specify the output folder for the generated JPG files.'
    text: '**Configure Paths** – specify the output folder for the generated JPG files.'
  - name: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
    text: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
  - name: '**Set Output Paths** – choose a folder for the PNG sequence.'
    text: '**Set Output Paths** – choose a folder for the PNG sequence.'
  - name: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
    text: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
  type: HowTo
- questions:
  - answer: Yes, it supports GIF, WebP, and even animated SVG, providing the same
      HTML, image, and PDF output options.
    question: Can GroupDocs Viewer render other animated formats like GIF or WebP?
  - answer: There’s no hard limit, but performance may degrade after ~500 frames;
      consider down‑sampling for very large animations.
    question: Is there a limit to the number of frames an APNG can have?
  - answer: APNG does not support encryption, but if the file is inside a ZIP archive,
      supply the password via `Viewer`’s `load` method.
    question: How do I handle password‑protected APNG files?
  - answer: Absolutely—use `JpgViewOptions.setResolution(300)` and `setQuality(90)`
      before calling `view`.
    question: Can I customize the DPI or quality of the generated JPGs?
  - answer: Yes, GroupDocs Viewer is pure Java and runs on any OS with a compatible
      JRE, making it ideal for Docker deployments.
    question: Does the library work on Linux containers?
  type: FAQPage
title: GroupDocs Viewer Java 教學：渲染動畫 PNG
type: docs
url: /zh-hant/java/rendering-basics/render-apng-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer Java 教學：渲染動畫 PNG

在本 **GroupDocs Viewer Java 教學** 中，您將了解如何使用強大的 GroupDocs.Viewer 函式庫將動畫 PNG（APNG）檔案轉換為 HTML、JPG、PNG 與 PDF 格式。無論您是構建網站入口、報告工具，或是數位出版流程，正確渲染 APNG 對於在各平台上保留動畫品質皆相當重要。

![使用 GroupDocs.Viewer for Java 渲染動畫 PNG](/viewer/rendering-basics/render-animated-pngs-java.png)  
[使用 GroupDocs.Viewer for Java 渲染動畫 PNG](/viewer/rendering-basics/render-animated-pngs-java.png)

## 快速解答
- **GroupDocs.Viewer 的功能是什麼？** 它可將超過 70 種檔案類型（包括 APNG）渲染為 HTML、圖像與 PDF，且不需要外部軟體。  
- **將 APNG 轉換為 JPG 需要多少行程式碼？** 只需兩行：建立 `Viewer` 實例，並呼叫 `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`。  
- **開發時需要授權嗎？** 試用授權可用於測試；正式環境需購買商業授權。  
- **能有效率地渲染大型 APNG（100+ 幀）嗎？** 可以——使用 try‑with‑resources 並串流輸出以降低記憶體使用。  
- **唯一的加入函式庫方式是 Maven 嗎？** 建議使用 Maven，但也可使用 Gradle 或手動加入 JAR。

## 什麼是 GroupDocs Viewer？
**GroupDocs Viewer** 是一個 Java 元件，可將超過 70 種文件與圖像格式轉換為適合網頁的表示形式，如 HTML、JPG、PNG 與 PDF。它能處理複雜版面、保留向量圖形，且支援 APNG 等動畫格式，無需外部相依性。

## 為何使用 GroupDocs Viewer 渲染動畫 PNG？
GroupDocs Viewer 提供可靠且高效能的方式來轉換 APNG，同時保留動畫時間與透明度。它免除第三方工具的需求，可在任何平台上運作，且能輕鬆整合至 Java 應用程式。

- **廣泛的格式支援：** 超過 70 種輸入格式，包含 APNG、PDF、DOCX 與 SVG。  
- **效能最佳化：** 可在一般伺服器上使用低於 150 MB 記憶體處理數百頁文件或 200 幀動畫。  
- **零安裝：** 無需本機函式庫或作業系統特定編解碼器，讓容器部署變得簡單。  
- **一致的輸出：** 確保像素完美渲染，保留透明度與動畫時間。

## 前置條件
- **Java Development Kit (JDK) 8+** – 確保相容現代語言特性。  
- **Maven** – 簡化相依性管理；Gradle 亦可使用。  
- **APNG 檔案** – 放置於專案的 `resources` 資料夾（例如 `src/main/resources/sample.apng`）。

## 設定 GroupDocs Viewer for Java

### Maven 設定
在您的 `pom.xml` 中加入以下相依性，以取得最新的穩定版：

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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
要評估 GroupDocs Viewer，您可以：
- **下載試用版** 從 [GroupDocs 網站](https://releases.groupdocs.com/viewer/java/)。  
- **申請臨時授權** 以進行完整功能測試。  
- **購買正式授權** 以獲得無限制的商業使用。  
- 如需詳細說明，請參閱 [官方文件](https://docs.groupdocs.com/viewer/java/)。

### 基本初始化
`Viewer` 類別是所有渲染操作的入口點。它會載入來源檔案，並提供輸出不同格式的方法。

`Viewer` 代表文件或圖像，並協調渲染至選定的輸出格式。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.*;
```

## 如何將動畫 PNG 渲染為 HTML？
載入 APNG 檔案，設定 HTML 選項，然後呼叫 `view`。此流程簡單，通常只需少量程式碼，適合在 Web 服務或批次作業中快速整合。

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.html");
   ```

### 定義錨點 – Viewer 實例
`Viewer` 是 GroupDocs.Viewer 的核心類別，代表文件或圖像，並協調渲染至選定的輸出格式。

### 步驟說明 – HTML 渲染
1. **設定路徑** – 定義 HTML 檔案及其資源的儲存位置。  
2. **初始化 Viewer** – 使用 APNG 路徑建立 `Viewer` 物件。  
3. **設定選項** – 使用 `HtmlViewOptions.forEmbeddedResources` 將 CSS、JS 與圖像直接嵌入 HTML 檔案，消除外部相依性。  
4. **渲染** – 呼叫 `viewer.view(documentPath, htmlOptions)`。

## 如何將 APNG 轉換為 JPG？
GroupDocs Viewer 能將每個動畫幀提取為單獨的 JPG 圖像，非常適合縮圖或靜態預覽。轉換會保留原始幀順序，且可控制圖像品質與解析度。

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.jpg");
   ```

### 定義錨點 – JpgViewOptions
`JpgViewOptions` 定義來源 APNG 每個幀如何渲染為單獨的 JPEG 檔案，讓您可設定品質、DPI 與命名規則。

### 步驟說明 – JPG 轉換
1. **設定路徑** – 指定產生的 JPG 檔案輸出資料夾。  
2. **渲染為 JPG** – 呼叫 `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`。  
3. **結果** – 每個幀會產生 `output_1.jpg`、`output_2.jpg`…，保留原始動畫順序。

## 如何將 APNG 轉換為 PNG？
當需要無損品質時，PNG 是理想的目標格式。GroupDocs Viewer 會提取每個幀而不產生壓縮痕跡，保持透明度完整，確保像素完美的忠實度。

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.png");
   ```

### 定義錨點 – PngViewOptions
`PngViewOptions` 告訴檢視器將每個動畫幀寫入為單獨的 PNG 檔案，保留透明度與精確的像素資料。

### 步驟說明 – PNG 抽取
1. **設定輸出路徑** – 選擇 PNG 序列的資料夾。  
2. **執行渲染** – 呼叫 `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`。  
3. **結果** – 您會得到一系列 PNG 檔案，可重新組合或單獨使用。

## 如何將 APNG 轉換為 PDF？
將動畫序列彙編成單一 PDF 對於可列印文件或存檔用途相當有用。每個幀會成為單獨的頁面，以靜態、可分享的格式保留動畫順序。

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.pdf");
   ```

### 定義錨點 – PdfViewOptions
`PdfViewOptions` 將 APNG 的所有幀彙總為一個多頁 PDF，每個幀佔用單獨的頁面。

### 步驟說明 – PDF 產生
1. **定義路徑** – 設定目標 PDF 檔案路徑。  
2. **渲染為 PDF** – 執行 `viewer.view(documentPath, PdfViewOptions.forEmbeddedResources(outputPath))`。  
3. **結果** – 產生的 PDF 每頁對應原始動畫的幀。

## 實務應用
- **Web 開發：** 在部落格或產品頁面嵌入 APNG，無需依賴 GIF，確保更流暢的動畫與較小的檔案大小。  
- **數位出版：** 將動畫圖表轉換為會議用 PDF 手冊，保留視覺敘事。  
- **行銷素材：** 產生高解析度的 JPG 或 PNG 快照，用於橫幅、廣告與社群媒體貼文。  
- **資料視覺化：** 將時間序列圖表轉為逐幀圖像，用於分析儀表板。

## 效能考量
- **圖像尺寸最佳化：** 在渲染前調整或壓縮來源 APNG，以降低 CPU 使用。  
- **資源管理：** 使用 try‑with‑resources 包裹 `Viewer`，自動關閉串流並釋放本機緩衝區。  
- **批次處理：** 處理多個 APNG 時，將其分批（10–20 個）執行，以避免記憶體峰值。

## 常見問題與解決方案
- **缺少幀：** 確認 APNG 符合 APNG 規範；某些舊工具會產生非標準檔案。  
- **時間不正確：** 使用 `AnimatedPngOptions`（若支援）在渲染後調整幀延遲。  
- **記憶體不足錯誤：** 啟用 `viewer.setCacheSize(50)` 以限制大型動畫的記憶體快取。

## 常見問答

**Q: GroupDocs Viewer 能渲染其他動畫格式如 GIF 或 WebP 嗎？**  
A: 可以，它支援 GIF、WebP，甚至動畫 SVG，提供相同的 HTML、圖像與 PDF 輸出選項。

**Q: APNG 的幀數有上限嗎？**  
A: 沒有硬性上限，但在約 500 幀之後效能可能下降；對於非常大的動畫請考慮降採樣。

**Q: 如何處理受密碼保護的 APNG 檔案？**  
A: APNG 本身不支援加密，但若檔案位於 ZIP 壓縮檔中，可透過 `Viewer` 的 `load` 方法提供密碼。

**Q: 我可以自訂產生的 JPG 的 DPI 或品質嗎？**  
A: 當然可以——在呼叫 `view` 前使用 `JpgViewOptions.setResolution(300)` 與 `setQuality(90)`。

**Q: 此函式庫能在 Linux 容器上運作嗎？**  
A: 能，GroupDocs Viewer 完全以 Java 實作，可在任何具相容 JRE 的作業系統上執行，適合 Docker 部署。

**最後更新：** 2026-06-20  
**測試版本：** GroupDocs.Viewer 23.9 for Java  
**作者：** GroupDocs

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
       // Render the APNG into HTML with embedded resources.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
       // Each frame becomes a separate JPG image.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PngViewOptions options = new PngViewOptions(pageFilePathFormat);
       // Converts each frame to a separate PNG.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
       // Convert the APNG into a single PDF.
       viewer.view(options);
   }
   ```

## 相關教學

- [Java 文件渲染教學 - 將檔案轉換為 HTML、PDF 與圖像](/viewer/java/rendering-basics/)
- [如何在 Java 使用 GroupDocs.Viewer 將 PDF 渲染為 HTML 並優化圖像品質](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [如何使用 GroupDocs.Viewer for Java 將 DOCX 檔案轉換為 PNG](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)