---
date: '2026-03-16'
description: 學習如何使用 GroupDocs.Viewer for Java 將 DWG 轉換為 PNG，並自訂尺寸與背景顏色。
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: 如何使用 GroupDocs.Viewer for Java 將 DWG 轉換為自訂尺寸與背景顏色的 PNG
type: docs
url: /zh-hant/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

" maybe keep bold. Keep colon.

**Tested With:** -> "**測試環境：**"

**Author:** -> "**作者：**"

But keep the values unchanged.

Now produce final markdown with translations.

Make sure to keep all placeholders and code blocks unchanged.

Let's craft final output.# 如何使用 GroupDocs.Viewer for Java 以自訂尺寸與背景顏色將 DWG 轉換為 PNG

如果您想要 **convert DWG to PNG** 並且完整掌控圖像尺寸與背景樣式，您來對地方了。在本教學中，我們將逐步說明如何將 CAD 檔案渲染為 PNG、自訂寬度，以及變更背景顏色，讓輸出符合您的報告、簡報或網頁預覽需求。

## 快速解答
- **convert DWG to PNG** 是什麼意思？它是將 DWG CAD 檔案透過程式碼轉換為 PNG 圖像的過程。  
- **Can I set a custom width?** 是的 – 使用 `CadOptions.forRenderingByWidth(int width)`。  
- **How do I change the background color?** 呼叫 `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`。  
- **Which library is required?** GroupDocs.Viewer for Java (version 25.2 or later)。  
- **Do I need a license?** 臨時或正式授權可移除評估限制。

![使用 GroupDocs.Viewer for Java 以自訂尺寸與背景顏色渲染 CAD 圖紙為 PNG](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## 如何將 DWG 轉換為 PNG – 概述
在本節中，我們將闡述主要目標：**how to convert DWG to PNG** 同時控制尺寸與背景。您將看到完整的設定、所需的精確程式碼，以及避免常見陷阱的實用技巧。

## 您將學到的內容
- 在 Maven 專案中設定 GroupDocs.Viewer for Java  
- **Convert DWG to PNG** 搭配自訂尺寸  
- 在渲染過程中 **Change CAD background color** 以獲得更佳外觀  
- 自訂渲染提升價值的實務案例  

## 前置條件

### 必要的函式庫與相依性
- Java Development Kit (JDK) 8+  
- Maven 用於相依性管理  

### 環境設定需求
- IDE，例如 IntelliJ IDEA 或 Eclipse  
- 基本的 Java 知識  

### 知識前置條件
- 熟悉 Java 中的檔案操作  

## 設定 GroupDocs.Viewer for Java
將 GroupDocs 儲存庫與相依性加入您的 Maven `pom.xml`：

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
取得臨時或正式授權，以移除評估限制。

### 基本初始化與設定
建立指向您的 CAD 檔案的 `Viewer` 實例：

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
此功能讓您在 **convert DWG to PNG** 時，同時指定自訂寬度並套用新的背景色調。

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

##### 使用自訂渲染選項初始化 Viewer
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
- `PngViewOptions` – 定義輸出格式與命名。  
- `forRenderingByWidth(int width)` – 設定自訂影像寬度。  
- `setBackgroundColor(Color color)` – **set PNG background color** 以提升視覺一致性。

#### 疑難排解技巧
- 確認輸出資料夾是否存在；如未存在請建立。  
- 再次檢查輸入檔案路徑與權限。  

## 功能 2：在渲染選項中設定背景顏色

### 如何設定 PNG 背景顏色
此處我們專注於 **set background color PNG** 選項，以確保每張渲染圖像皆符合您的品牌調色板。

#### 步驟實作

##### 匯入必要的套件
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 使用背景顏色配置渲染選項
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

**關鍵配置選項**  
- 調整 `forRenderingByWidth(int width)` 以取得不同尺寸。  
- 使用任意 `Color` 常數或自訂 `new Color(r,g,b)` 來設定專屬背景。  

## 實務應用

### 1. 工程文件
自訂渲染可確保工程圖符合企業樣式指南。

### 2. 建築視覺化
以乾淨的背景呈現藍圖，與簡報投影片相匹配。

### 3. 製造原型製作
產生精確的 PNG 以支援快速原型製作流程。

### 整合可能性
將此渲染流程與文件管理系統結合，以自動化視覺資產產生。

## 效能考量

### 優化效能
- **Batch Processing:** 在迴圈中渲染多個 CAD 檔案。  
- **Resource Management:** 為大型圖紙調整 JVM 堆積大小。

### 資源使用指引
監控 CPU 與記憶體使用；及時釋放 `Viewer` 實例。

### Java 記憶體管理最佳實踐
- 使用 try‑with‑resources（如範例所示）自動關閉 `Viewer`。  
- 避免長時間保留大型 `Path` 物件。  

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **Output folder not found** | 事先建立目錄，或加入 `Files.createDirectories(outputDirectory);` |
| **Blank image** | 確認在 `forRenderingByWidth` 之後設定 `cadOptions.setBackgroundColor`。 |
| **Out‑of‑memory errors** | 增加 `-Xmx` JVM 參數或將檔案分批處理。 |

## 常見問答

**Q: 除了 DWG，我可以渲染其他 CAD 格式嗎？**  
A: 可以，GroupDocs.Viewer 支援 DXF、DWF 以及其他多種 CAD 檔案類型。

**Q: 如何使用自訂 RGB 顏色而非預定義常數？**  
A: 建立新的 `Color` 實例，例如 `new Color(123, 45, 67)`，並傳遞給 `setBackgroundColor`。

**Q: 能否僅渲染特定的版面或圖層？**  
A: 您可以在呼叫 `viewer.view` 前，透過 `CadOptions` 指定版面或圖層選項。

**Q: 此函式庫支援透明背景嗎？**  
A: 若目標格式支援，將背景顏色設為 `new Color(0,0,0,0)` 即可取得完整透明。

**Q: 需要哪個版本的 GroupDocs.Viewer？**  
A: 本教學使用 25.2 版，較新版本仍保有相同 API。

---

**最後更新：** 2026-03-16  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs