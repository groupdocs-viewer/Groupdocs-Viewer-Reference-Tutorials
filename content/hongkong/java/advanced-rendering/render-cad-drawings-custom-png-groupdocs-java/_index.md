---
date: '2026-08-30'
description: 了解如何將 DWG 轉換為 PNG、在 Java 中設定背景顏色，並使用 GroupDocs.Viewer for Java 自訂影像尺寸。
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: 使用 GroupDocs.Viewer for Java 將 DWG 轉換為 PNG，同時設定自訂影像寬度與背景顏色。本指南提供逐步設定說明、程式碼範例與故障排除技巧。
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: 在 Java 中將 DWG 轉換為 PNG，並自訂尺寸與背景顏色
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: 如何使用 GroupDocs.Viewer for Java 將 DWG 轉換為 PNG，並自訂尺寸與背景顏色
type: docs
url: /zh-hant/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# 如何使用 GroupDocs.Viewer for Java 以自訂尺寸與背景顏色將 DWG 轉換為 PNG

在本教學中，您將學習 **如何將 DWG 轉換為 PNG**，同時控制輸出尺寸與背景顏色，使用 GroupDocs.Viewer for Java。無論您是需要在報告中嵌入 CAD 圖紙、為網站入口產生縮圖，或是自動化批次渲染，以下步驟都能讓您完整掌握每個 PNG 檔案的視覺呈現。

## 快速解答
- **「將 DWG 轉換為 PNG」是什麼意思？** 這是透過程式碼將 DWG CAD 檔案轉換為 PNG 圖像的過程，將向量細節保留為點陣像素。  
- **我可以設定自訂寬度嗎？** 可以 – 呼叫 `CadOptions.forRenderingByWidth(int width)` 以定義您需要的精確像素寬度。  
- **如何變更背景顏色？** 在渲染前使用 `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`。  
- **需要哪個函式庫？** GroupDocs.Viewer for Java（版本 25.2 或更新）。  
- **我需要授權嗎？** 臨時或完整授權可移除評估限制，並啟用無限制渲染。

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## 什麼是 GroupDocs.Viewer for Java？
GroupDocs.Viewer for Java 是一個伺服器端 API，能將超過 150 種檔案格式（包括 CAD 檔）渲染為影像、PDF 或 HTML。它不需要任何第三方軟體（如 AutoCAD），因此非常適合自動化流程。

## 如何以自訂尺寸與背景顏色將 DWG 轉換為 PNG？
使用 `Viewer` 實例載入 DWG 檔案，設定 `CadOptions` 以指定寬度與背景，最後以 `PngViewOptions` 呼叫 `viewer.view`。此三步流程在一次記憶體高效的操作中處理檔案 I/O、渲染與輸出命名。

Viewer 是載入文件並執行渲染的主要類別。  
CadOptions 設定 CAD 專屬的參數，如影像寬度與背景顏色。  
PngViewOptions 定義 PNG 輸出格式以及已渲染頁面的命名模式。

現在您可以將任何 DWG 圖紙渲染為符合您指定寬度的 PNG，並可選擇任意純色（或透明）背景，以符合您的品牌或 UI 主題。

## 為何要設定自訂背景顏色？
設定背景顏色可確保渲染出的 PNG 與周圍 UI 元素無縫融合，避免不必要的白色邊緣，並能突顯在預設白色畫布上可能遺失的圖紙細節。GroupDocs.Viewer 支援任何 `java.awt.Color`，包括自訂 RGB 值，讓您擁有像素級的精確控制。

java.awt.Color 代表用於渲染背景的顏色值。

## 前置條件
- **Java Development Kit (JDK) 8+** – 此 API 以 Java 8 及以上版本為目標。  
- **Maven** – 用於相依性管理。  
- **IDE** – 如 IntelliJ IDEA、Eclipse，或您偏好的任何編輯器。  
- **基本的 Java 檔案處理知識** – 用於讀取來源 DWG 檔案並寫入 PNG 輸出。

## 設定 GroupDocs.Viewer for Java
將 GroupDocs 儲存庫與 Viewer 相依性加入您的 Maven `pom.xml`：

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
從 GroupDocs 入口網站取得臨時或完整授權金鑰，並將 `license.lic` 檔案放置於專案的 resources 資料夾中。此舉可移除 20 頁的評估限制，並解鎖完整解析度的渲染。

### 基本初始化與設定
建立指向包含 DWG 檔案之資料夾的 `Viewer` 實例：

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## 功能 1：以自訂影像尺寸與背景顏色渲染 CAD 圖紙

### 如何變更 CAD 背景顏色
要變更 CAD 背景顏色，請在渲染前設定 CadOptions 物件。使用 `forRenderingByWidth` 設定所需寬度，並透過 `setBackgroundColor` 套用新背景。Viewer 隨後會產生符合指定顏色的 PNG 圖像，確保所有輸出檔案的視覺風格一致。

#### 步驟實作

##### 匯入必要的套件
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 設定輸出目錄與檔案路徑格式
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### 使用自訂渲染選項初始化 viewer
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**參數說明**  
- `PngViewOptions` – 定義 PNG 輸出格式與命名模式。  
- `forRenderingByWidth(int width)` – 強制渲染器產生寬度符合提供的像素值的影像；高度按比例縮放。  
- `setBackgroundColor(Color color)` – 用您選擇的顏色覆寫預設的白色畫布，提升生成資產的視覺一致性。

#### 疑難排解技巧
- 確認輸出資料夾已存在；若不存在，使用 `Files.createDirectories(outputDir)` 建立。  
- 核實輸入檔案路徑正確且應用程式具備讀取權限。  

## 功能 2：在渲染選項中設定背景顏色

### 如何設定 PNG 背景顏色
設定 PNG 背景顏色的方式是建立 Color 實例，並在渲染前指派給 CadOptions。這可確保每個生成的 PNG 使用指定的背景，符合您的品牌指南或 UI 主題。您可以使用預定義常數或自訂 RGB 值以取得精確控制。

java.awt.Color 代表用於渲染背景的顏色值。

#### 步驟實作

##### 匯入必要的套件
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 使用背景顏色設定渲染選項
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**關鍵設定選項**  
- 調整 `forRenderingByWidth(int width)` 以符合不同尺寸，例如網頁縮圖的 800 px 或高解析度列印的 1920 px。  
- 使用任何預定義的 `Color` 常數（例如 `Color.LIGHT_GRAY`），或使用 `new Color(r, g, b)` 建立自訂實例，以達到精確的品牌顏色。

## 實務應用

### 1. 工程文件
自訂渲染可確保每張圖紙符合公司樣式指南，免除匯出後的手動影像編輯。

### 2. 建築可視化
以符合投影片或客戶入口網站的背景呈現藍圖，提升視覺一致性。

### 3. 製造原型製作
產生 PNG 供快速原型工作流程使用，因下游工具需要特定的影像尺寸與背景。

### 整合可能性
將此渲染流程與文件管理系統（例如 SharePoint）結合，於每次上傳 DWG 檔案時自動產生預覽圖像。

## 效能考量

### 優化效能
- **批次處理：** 迴圈遍歷 DWG 檔案目錄，依序渲染每個檔案，以分攤 JVM 暖機成本。  
- **資源管理：** 對於大型圖紙（500 頁以上），增加 JVM 堆積大小（`-Xmx2g`）或將檔案分批處理，以避免記憶體不足錯誤。

### 資源使用指引
使用 VisualVM 等工具監控 CPU 與記憶體使用情況；使用 try‑with‑resources 及時釋放 `Viewer` 實例。

### Java 記憶體管理最佳實踐
- 使用 try‑with‑resources（如範例所示）自動關閉 `Viewer`。  
- 避免在即時使用之外保留大型 `Path` 物件。  

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| 找不到輸出資料夾 | 事先建立目錄，或加入 `Files.createDirectories(outputDirectory);` |
| 空白影像 | 確保在 `forRenderingByWidth` 之後呼叫 `cadOptions.setBackgroundColor`。 |
| 記憶體不足錯誤 | 增加 `-Xmx` JVM 參數或將檔案分批處理。 |

## 常見問答

**Q: 我可以渲染除 DWG 之外的其他 CAD 格式嗎？**  
A: 是的，GroupDocs.Viewer 支援 DXF、DWF 以及其他多種 CAD 格式。

**Q: 如何使用自訂 RGB 顏色而非預定義常數？**  
A: 使用 `new Color(123, 45, 67)` 建立新的 `Color`，並傳遞給 `setBackgroundColor`。

**Q: 能否僅渲染特定的版面或圖層？**  
A: 您可以在呼叫 `viewer.view` 前透過 `CadOptions` 指定版面或圖層選項。

**Q: 此函式庫支援透明背景嗎？**  
A: 若輸出格式支援，將背景顏色設為 `new Color(0,0,0,0)` 即可實現完全透明。

**Q: 需要哪個版本的 GroupDocs.Viewer？**  
A: 本教學使用 25.2 版，但較新版本仍保有相同的 API 介面。

---

**最後更新：** 2026-08-30  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

## 相關教學

- [groupdocs viewer dwg – 如何在 Java 中使用 GroupDocs.Viewer 渲染特定 CAD 圖紙](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer 渲染 CAD 圖層 Java – 完整指南](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [如何在 Java 中使用 GroupDocs.Viewer 將 PDF 轉換為 HTML 並優化影像品質](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)