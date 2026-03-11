---
date: '2026-01-08'
description: 學習如何使用 GroupDocs.Viewer for Java，透過自訂尺寸與背景顏色，將 CAD 圖紙渲染成高品質 PNG 圖像。
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: 如何使用 GroupDocs.Viewer for Java 將 CAD 圖紙渲染為 PNG 並自訂尺寸與背景顏色
type: docs
url: /zh-hant/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# 如何使用 GroupDocs.Viewer for Java 將 CAD 圖紙渲染為 PNG（自訂尺寸與背景顏色）

在將 CAD 圖紙轉換為高品質圖像，同時保持特定尺寸與美觀方面感到困難嗎？本教學將示範 **如何渲染 CAD** 檔案為 PNG，並自訂尺寸與背景顏色，讓您在報告、簡報或網頁預覽中獲得所需的外觀。

## 快速解答
- **「如何渲染 CAD」是什麼意思？** 它指的是使用程式碼將 CAD 檔案（例如 DWG）轉換為 PNG 等影像格式。  
- **我可以設定自訂寬度嗎？** 可以 – 使用 `CadOptions.forRenderingByWidth(int width)`。  
- **如何變更背景？** 呼叫 `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`。  
- **需要哪個函式庫？** GroupDocs.Viewer for Java（版本 25.2 或更新）。  
- **我需要授權嗎？** 臨時或正式授權可移除評估限制。

![使用 GroupDocs.Viewer for Java 將 CAD 圖紙渲染為 PNG（自訂尺寸與背景顏色）](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## 渲染 CAD 圖紙概覽
本節闡述主要目標：**如何渲染 CAD** 圖紙為 PNG 檔案，同時控制尺寸與背景。我們將逐步說明完整設定、程式碼片段與實用技巧。

## 您將學習到
- 在專案中設定 GroupDocs.Viewer for Java  
- **將 DWG 轉換為 PNG**，並自訂尺寸  
- **在渲染時設定 PNG 背景顏色**，以獲得精緻外觀  
- 真實情境中自訂渲染的價值應用  

## 前置條件

### 必要的函式庫與相依性
- Java Development Kit (JDK) 8+  
- Maven 用於相依性管理  

### 環境設定需求
- 如 IntelliJ IDEA 或 Eclipse 等 IDE  
- 基本的 Java 知識  

### 知識前提
- 熟悉 Java 中的檔案處理  

## 設定 GroupDocs.Viewer for Java
將 GroupDocs 儲存庫與相依性加入 Maven `pom.xml`：

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
建立指向 CAD 檔案的 `Viewer` 實例：

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## 實作指南

### 功能 1：使用自訂影像尺寸與背景顏色渲染 CAD 圖紙

#### 概覽
此功能讓您在指定影像寬度與背景色調的同時 **將 DWG 轉換為 PNG**。

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
- `setBackgroundColor(Color color)` – **套用背景顏色渲染** 至 PNG。

#### 疑難排解提示
- 確認輸出資料夾是否存在；如有需要請建立。  
- 再次檢查輸入檔案路徑與權限。  

### 功能 2：在渲染選項中設定背景顏色

#### 概覽
此處我們專注於 **設定 PNG 背景顏色**，以提升視覺一致性。

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

**主要配置選項**  
- 調整 `forRenderingByWidth(int width)` 以取得不同尺寸。  
- 使用任意 `Color` 常數或自訂 `new Color(r,g,b)` 以打造專屬背景。  

## 實務應用

### 1. 工程文件
自訂渲染可確保工程圖紙符合公司樣式指南。

### 2. 建築視覺化
以乾淨的背景呈現藍圖，與簡報投影片相匹配。

### 3. 製造原型製作
產生精確的 PNG 以支援快速原型製作流程。

### 整合可能性
將此渲染流程與文件管理系統結合，以自動化視覺資產產生。

## 效能考量

### 效能最佳化
- **批次處理：** 在迴圈中渲染多個 CAD 檔案。  
- **資源管理：** 為大型圖紙調整 JVM 堆積大小。

### 資源使用指引
監控 CPU 與記憶體使用；及時釋放 `Viewer` 實例。

### Java 記憶體管理最佳實踐
- 使用 try‑with‑resources（如範例所示）自動關閉 `Viewer`。  
- 避免長時間保留大型 `Path` 物件。  

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **找不到輸出資料夾** | 事先建立目錄，或加入 `Files.createDirectories(outputDirectory);` |
| **空白影像** | 確保在 `forRenderingByWidth` 之後設定 `cadOptions.setBackgroundColor`。 |
| **記憶體不足錯誤** | 增加 `-Xmx` JVM 參數或將檔案分成較小批次處理。 |

## 常見問答

**Q: 我可以渲染除 DWG 之外的其他 CAD 格式嗎？**  
A: 可以，GroupDocs.Viewer 支援 DXF、DWF 以及其他多種 CAD 檔案類型。

**Q: 如何使用自訂 RGB 顏色而非預設常數？**  
A: 建立新的 `Color` 例項，例如 `new Color(123, 45, 67)`，並傳入 `setBackgroundColor`。

**Q: 能否只渲染特定的版面或圖層？**  
A: 您可以在呼叫 `viewer.view` 前透過 `CadOptions` 指定版面或圖層選項。

**Q: 此函式庫支援透明背景嗎？**  
A: 若目標格式支援，將背景顏色設為 `new Color(0,0,0,0)` 即可取得完整透明度。

**Q: 需要哪個版本的 GroupDocs.Viewer？**  
A: 本教學使用 25.2 版，但較新版本仍保有相同的 API。

## 結論
現在您已了解 **如何渲染 CAD** 圖紙為 PNG 檔案，並可自訂尺寸與背景顏色，使用 GroupDocs.Viewer for Java。將這些技巧應用於工程、建築或製造工作流程，製作專業外觀的視覺資產。

### 後續步驟
- 嘗試不同的影像寬度與顏色。  
- 將渲染程式碼整合至批次處理服務。  
- 探索其他 Viewer 功能，如 PDF 轉換或多頁渲染。

---

**最後更新：** 2026-01-08  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs