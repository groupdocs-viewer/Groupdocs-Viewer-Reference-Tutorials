---
date: '2026-02-18'
description: 學習如何使用 GroupDocs Viewer for Java 將 WMZ 與 WMF 檔案轉換為 PDF、HTML、JPG 及 PNG。本指南涵蓋
  GroupDocs Viewer Java 以及 Java 向量圖形轉換。
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: 如何使用 GroupDocs Viewer for Java 將 WMZ 轉換為 PDF 及其他格式
type: docs
url: /zh-hant/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs Viewer for Java 將 WMZ 轉換為 PDF 及其他格式

將 WMZ（Web Metafile）和 WMF（Windows Metafile）檔案轉換為更易於存取的格式——尤其是 **convert WMZ to PDF**——可能相當棘手，因為這些向量圖形格式儲存的是繪圖指令而非像素資料。使用 **GroupDocs Viewer for Java**，您只需幾行程式碼即可將 WMZ/WMF 文件渲染為 HTML、JPG、PNG、**PDF** 以及其他常見格式。

![使用 GroupDocs.Viewer for Java 轉換 WMZ/WMF 文件](/viewer/export-conversion/convert-wmz-wmf-documents.png)

在本教學中，您將學習如何設定函式庫、將 WMZ/WMF 檔案渲染為所需的輸出，並處理常見的陷阱。完成後，您即可將 **groupdocs viewer java** 整合到您的 Java 應用程式中，快速且可靠地 **java convert vector graphics**。

## 快速解答
- **WMZ/WMF 可以轉換成哪些格式？** 完全支援 HTML、JPG、PNG 與 PDF。  
- **開發時需要授權嗎？** 免費試用可用於測試；商業授權可移除評估限制。  
- **需要哪個版本的 Java？** 建議使用 Java 8 或更新版本。  
- **可以只渲染特定頁面嗎？** 可以，您可以在檢視選項中指定頁面範圍。  
- **大型檔案的記憶體使用是否成問題？** 使用 try‑with‑resources 並僅渲染所需頁面，以降低記憶體佔用。

## 什麼是「convert WMZ to PDF」？

將 WMZ 轉換為 PDF 意指將向量基礎的 WMZ 檔案轉換為光柵圖（或保留其向量資料）並嵌入 PDF 容器中。PDF 可在任何平台上檢視、搜尋與列印，因而非常適合用於保存與分享 WMZ 圖形。

## 為何使用 GroupDocs Viewer for Java 轉換向量圖形？

- **高保真度**：函式庫保留原始繪圖品質，無論輸出為 PDF 或 PNG。  
- **零外部相依性**：不需原生 Windows 函式庫；只要有 JDK，便可在任何平台上執行。  
- **簡易 API**：只需一個 `Viewer` 實例與一次 `view` 呼叫，即可完成整個轉換。  
- **可擴充**：無論是單頁圖示或多頁技術圖紙，都能同樣順暢運作。

## 前置條件

### 必要函式庫
- **GroupDocs.Viewer for Java** – 核心渲染引擎。  
- Java Development Kit (JDK) 8+。

### 環境設定
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 用於相依性管理的 Maven（若偏好亦可使用 Gradle）。

### 知識前提
- 熟悉 Java 檔案 I/O（`java.nio.file.Path`）。  
- 基本了解文件檢視器如何渲染內容。

## 設定 GroupDocs.Viewer for Java

將儲存庫與相依性加入您的 `pom.xml`：

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

> **授權提示：** 使用免費試用版進行評估，之後套用臨時或購買的授權即可解鎖完整功能。

相依性解析完成後，您即可建立一個 `Viewer` 實例，於每個轉換步驟中重複使用。

## 實作指南

我們將逐一說明四種轉換情境：HTML、JPG、PNG 與 PDF。每個範例遵循相同流程——定義輸出路徑、以來源 WMZ 檔案建立 `Viewer`、設定相應的檢視選項，最後呼叫 `view`。

### 將 WMZ/WMF 渲染為 HTML

#### 概觀
HTML 輸出可讓您直接將圖形嵌入網頁，所有資源（圖片、CSS）皆包含於單一檔案中。

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

### 將 WMZ/WMF 渲染為 JPG

#### 概觀
JPG 是廣受支援的光柵格式，適合快速預覽或作為電子郵件附件。

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

### 將 WMZ/WMF 渲染為 PNG

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

### 將 WMZ/WMF 渲染為 PDF

#### 概觀
PDF 提供跨平台、可搜尋的文件，且保留原始版面配置。

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

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **OutOfMemoryError** 發生於大型 WMZ 檔案 | Viewer 將整個文件載入記憶體 | 使用 `PageStreamViewOptions` 逐頁渲染，或增加 JVM 堆積大小（`-Xmx`）。 |
| **Missing fonts** 出現在 PDF 中 | 來源 WMZ 未嵌入字型 | 在主機上安裝所需字型，或使用 `FontSettings` 提供自訂字型。 |
| **Blank PNG output**（空白 PNG 輸出） | 輸出路徑不正確或寫入權限不足 | 確認 `outputDirectory` 已存在且應用程式具寫入權限。 |
| **HTML resources not loading**（HTML 資源未載入） | 使用 `forExternalResources` 卻未複製檔案 | 改用 `forEmbeddedResources` 以產生自包含的 HTML 檔案。 |

## 常見問答

**Q: 我可以使用相同程式碼將 WMF 轉換為 PNG 嗎？**  
A: 可以。PNG 範例同樣適用於 WMZ 與 WMF 檔案，只需將 `TestFiles.SAMPLE_WMZ` 替換為您的 WMF 來源。

**Q: 能否只轉換部分頁面？**  
A: 完全可以。使用 `PdfViewOptions`（或其他格式相對應的選項），在渲染前呼叫 `setPageNumbers(List<Integer>)`。

**Q: 每種輸出格式需要單獨的授權嗎？**  
A: 不需要。單一的 GroupDocs Viewer 授權即可涵蓋所有支援的格式，包括 HTML、JPG、PNG 與 PDF。

**Q: 「java convert vector graphics」會如何影響效能？**  
A: 向量轉光柵的轉換相當耗費 CPU。大量批次時，建議使用多執行緒並在多個檔案間重複使用同一個 `Viewer` 實例。

**Q: PDF 會保留向量品質，還是會被光柵化？**  
A: 將 WMZ/WMF 轉換為 PDF 時，GroupDocs Viewer 會在可能的情況下保留向量指令，產生可縮放的 PDF。

## 結論

您現在已擁有一套完整、可投入生產的指南，使用 **GroupDocs Viewer for Java** 將 **convert WMZ to PDF** 以及其他常見格式進行轉換。無論是建置即時提供圖形的 Web 服務，或是將文件存為 PDF 的歸檔工具，上述步驟都能協助您快速達成目標。

---

**最後更新：** 2026-02-18  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs