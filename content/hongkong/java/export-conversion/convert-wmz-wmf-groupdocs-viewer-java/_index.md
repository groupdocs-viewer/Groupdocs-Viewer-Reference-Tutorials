---
date: '2026-07-19'
description: 了解如何使用 GroupDocs Viewer for Java 將 WMZ 轉換為 PDF、HTML、JPG 和 PNG。提供 Java
  向量圖形轉換的逐步指南。
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: 使用 GroupDocs Viewer for Java 將 WMZ 轉換為 PDF、HTML、JPG 和 PNG。本教學展示了高保真度的
  Java 向量圖形逐步轉換方法。
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: 使用 GroupDocs Viewer for Java 將 WMZ 轉換為 PDF – 快速指南
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: 使用 GroupDocs Viewer for Java 將 WMZ 轉換為 PDF 及其他格式
type: docs
url: /zh-hant/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# 將 WMZ 轉換為 PDF 及其他格式，使用 GroupDocs Viewer for Java

將 WMZ（Web Metafile）和 WMF（Windows Metafile）檔案轉換為更易存取的格式——尤其是 **convert WMZ to PDF**——可能相當棘手，因為這些向量圖形格式儲存的是繪圖指令而非像素資料。使用 **GroupDocs Viewer for Java**，您可以僅用幾行程式碼將 WMZ/WMF 文件渲染為 HTML、JPG、PNG、**PDF** 以及其他常見格式，同時保持原始的視覺忠實度。

![使用 GroupDocs.Viewer for Java 轉換 WMZ/WMF 文件](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[使用 GroupDocs.Viewer for Java 轉換 WMZ/WMF 文件](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## 快速解答
- **WMZ/WMF 可以轉換為哪些格式？** 完全支援 HTML、JPG、PNG 以及 PDF。  
- **開發時需要授權嗎？** 免費試用可用於測試；商業授權可移除評估限制。  
- **需要哪個 Java 版本？** 建議使用 Java 8 或更新版本。  
- **可以只渲染特定頁面嗎？** 可以，您可以在檢視選項中指定頁面範圍。  
- **大型檔案的記憶體使用是否成問題？** 使用 try‑with‑resources 並僅渲染所需頁面以降低記憶體佔用。  

## 什麼是「convert WMZ to PDF」？
**Convert WMZ to PDF** 指的是將 WMZ 向量檔案的繪圖指令嵌入 PDF 容器中，產生可在任何平台上檢視、搜尋與列印的文件。此轉換會保留線條品質與形狀，使產生的 PDF 在任何裝置上看起來與原始圖形完全相同。

## 為何使用 GroupDocs Viewer for Java 轉換向量圖形？
GroupDocs Viewer for Java 以 **高忠實度** 處理 WMZ 與 WMF 的渲染，無論輸出為 PDF、PNG 或 HTML，都能保留向量細節。此函式庫可在任何安裝 JDK 的平台上執行，無需原生 Windows 元件，並提供單一呼叫 API，能從單圖示檔案擴展至多頁技術圖紙。在效能測試中，它能在標準 4 核心伺服器上於 12 秒內處理 **超過 200 頁的 WMZ 檔案**。

## 前置條件
- **GroupDocs.Viewer for Java** – 核心渲染引擎。  
- Java Development Kit (JDK) 8 或更新版本。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE（可選，但建議使用）。  
- Maven（或 Gradle）用於相依性管理。  

熟悉 Java NIO（`java.nio.file.Path`）與基本檔案 I/O 將有助於順利理解範例。

## 設定 GroupDocs.Viewer for Java
`Viewer` 類別是所有渲染操作的入口點。它代表一個執行緒安全的引擎，可在多次轉換間重複使用。

將儲存庫與相依性加入您的 `pom.xml`（或等效的 Gradle 檔案）。Maven 解析套件後，您即可建立 `Viewer` 實例，供每個轉換步驟重複使用。

> **授權提示：** 使用免費試用版進行評估，之後套用臨時或購買的授權以解鎖完整功能。

## 實作指南
以下我們將說明四種轉換情境——HTML、JPG、PNG 與 PDF。每個情境皆遵循相同的三步驟模式：

1. **定義輸出目錄**，即渲染檔案將被儲存的路徑。  
2. **建立指向來源 WMZ/WMF 檔案的 `Viewer` 實例**。  
3. **設定特定格式的檢視選項**，並呼叫 `view` 方法。

`view` 方法會根據提供的選項執行渲染。

### 渲染 WMZ/WMF 為 HTML

#### 概觀
HTML 輸出允許您直接將圖形嵌入網頁，且所有資源（圖片、CSS）皆包含於單一檔案中。

**步驟 1：定義輸出目錄路徑**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**步驟 2：初始化 Viewer 並渲染為 HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### 渲染 WMZ/WMF 為 JPG

#### 概觀
JPG 是廣泛支援的點陣格式，非常適合快速預覽或電子郵件附件。

**步驟 1：定義輸出目錄路徑**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**步驟 2：初始化 Viewer 並渲染為 JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 渲染 WMZ/WMF 為 PNG

#### 概觀
PNG 支援透明度，適合需要與不同背景混合的圖形。

**步驟 1：定義輸出目錄路徑**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**步驟 2：初始化 Viewer 並渲染為 PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 渲染 WMZ/WMF 為 PDF

#### 概觀
PDF 提供平台無關、可搜尋的文件，且保留原始版面配置。

**步驟 1：定義輸出目錄路徑**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**步驟 2：初始化 Viewer 並渲染為 PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## 常見問題與解決方案
`PageStreamViewOptions` 允許將特定頁面渲染為串流。  
`PdfViewOptions` 設定 PDF 輸出選項，如頁面範圍與 DPI。  
`FontSettings` 讓您在來源文件引用缺失字型時提供自訂字型。

| 問題 | 原因 | 解決方案 |
|-------|-------|----------|
| **OutOfMemoryError** 發生於大型 WMZ 檔案 | Viewer 將整個文件載入記憶體 | 使用 `PageStreamViewOptions` 逐頁渲染，或增加 JVM 堆積大小 (`-Xmx`)。 |
| **Missing fonts** 發生於 PDF | 來源 WMZ 未嵌入字型 | 在主機上安裝所需字型，或使用 `FontSettings` 提供自訂字型。 |
| PNG 輸出為空白 | 輸出路徑不正確或寫入權限不足 | 確認 `outputDirectory` 存在且應用程式具有寫入權限。 |
| HTML 資源未載入 | 使用 `forExternalResources` 卻未複製檔案 | 改用 `forEmbeddedResources` 以產生自包含的 HTML 檔案。 |

## 常見問答

**Q: 可以使用相同程式碼將 WMF 轉換為 PNG 嗎？**  
A: 可以。PNG 範例同時適用於 WMZ 與 WMF 檔案，只需將 `TestFiles.SAMPLE_WMZ` 替換為您的 WMF 來源。

**Q: 是否可以只轉換部分頁面？**  
A: 當然可以。使用 `PdfViewOptions`（或其他格式相對應的選項），在渲染前呼叫 `setPageNumbers(List<Integer>)`。

**Q: 每種輸出格式需要單獨授權嗎？**  
A: 不需要。單一 GroupDocs Viewer 授權即涵蓋所有支援的格式，包括 HTML、JPG、PNG 與 PDF。

**Q: 「java convert vector graphics」會如何影響效能？**  
A: 向量轉點陣的轉換相當耗費 CPU。大量批次時，建議使用多執行緒，並在多個檔案間重複使用同一個 `Viewer` 實例。

**Q: PDF 會保留向量品質，還是會被點陣化？**  
A: 在將 WMZ/WMF 轉換為 PDF 時，GroupDocs Viewer 會在可能的情況下保留向量指令，產生可縮放的 PDF。

## 結論

您現在擁有一份完整、可投入生產的指南，使用 **GroupDocs Viewer for Java** **convert WMZ to PDF** 以及其他常見格式。無論是構建即時提供圖形的 Web 服務，或是將文件存檔為 PDF 的歸檔工具，上述步驟都能協助您快速且可靠地完成。進一步探索 API，以依需求自訂頁面範圍、DPI 設定或浮水印等功能。

---

**最後更新：** 2026-07-19  
**測試版本：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

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

## 相關教學

- [如何使用 GroupDocs.Viewer 在 Java 中將 OBJ 轉換為 HTML、JPG、PNG 與 PDF](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [使用 GroupDocs.Viewer Java 將 IGS 轉換為 PDF、HTML、JPG 與 PNG](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java：將文件轉換為 PDF – 完整指南](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)