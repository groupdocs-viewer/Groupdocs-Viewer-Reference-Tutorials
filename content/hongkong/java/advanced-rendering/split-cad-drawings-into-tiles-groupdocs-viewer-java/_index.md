---
date: '2026-04-01'
description: 了解如何使用 GroupDocs Viewer for Java 將 CAD 圖紙切割成瓦片，提升渲染效能並簡化大型檔案的處理。
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: 如何使用 GroupDocs Viewer 將 CAD 圖紙拆分為瓦片
type: docs
url: /zh-hant/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs Viewer 將 CAD 圖紙切割成圖塊

如果你想了解**如何切割 CAD**檔案成較小、更易管理的片段，你來對地方了。在本教學中，我們將逐步說明如何使用 **GroupDocs Viewer for Java** 將大型 CAD 圖紙切割成圖塊。完成後，你將擁有一個即用的解決方案，可提升渲染速度、降低記憶體使用，並讓在網頁或行動應用程式中顯示圖紙變得更簡單。

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## 快速解答
- **“splitting CAD” 能帶來什麼效果？** 它將巨大的圖紙分割成較小的影像（圖塊），使載入更快且佔用較少記憶體。  
- **圖塊使用哪種格式？** 預設產生 PNG 檔案，但透過 Viewer 選項也支援其他格式。  
- **我需要授權嗎？** 開發階段可使用免費試用版；正式上線則需付費授權。  
- **我可以調整圖塊大小嗎？** 可以——調整 `tileWidth` 和 `tileHeight` 的計算方式即可符合需求。  
- **此方法是執行緒安全的嗎？** 在每個 `Viewer` 實例中使用 try‑with‑resources 逐一渲染圖塊，對於併發執行是安全的。

## 什麼是「如何切割 CAD」？
切割 CAD 是指將單一且通常非常龐大的 CAD 圖紙分割成多個矩形區塊（圖塊）。每個圖塊會獨立渲染，讓你僅載入使用者實際需要的部分——非常適合網頁地圖、文件入口網站以及行動檢視器。

## 為什麼使用 GroupDocs Viewer for Java？
GroupDocs Viewer 內建支援超過 100 種檔案格式，包括 DWG、DXF 與 DWF。其圖塊 API 允許你指定精確座標，僅渲染你關注的區域，而不必先處理整個檔案。這可節省 CPU 時間、降低頻寬需求，並提供更流暢的使用者體驗。

## 前置條件
- **函式庫**: GroupDocs.Viewer for Java ≥ 25.2。  
- **JDK**: 任意近期的 Java Development Kit (Java 8+)。  
- **IDE**: IntelliJ IDEA、Eclipse，或其他相容 Java 的 IDE。  
- **建置工具**: Maven（其他建置工具亦可，只要加入相依性即可）。

## 設定 GroupDocs.Viewer for Java
將 GroupDocs 套件庫與相依性加入你的 `pom.xml`：

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
GroupDocs.Viewer 提供免費試用授權供評估使用：

- **Free Trial**: 前往 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 下載程式庫。  
- **Temporary License**: 前往 [Temporary License Page](https://purchase.groupdocs.com/temporary-license/) 申請臨時授權。  
- **Full License**: 在 [Purchase Page](https://purchase.groupdocs.com/buy) 購買正式授權。

### 基本初始化
建立簡易的 `Viewer` 實例，以驗證程式庫正確載入：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## 分步指南：將 CAD 圖紙切割成圖塊

### 步驟 1：定義輸出目錄
我們會將每個圖塊儲存為單獨的 PNG 檔案。使用工具方法可讓路徑邏輯保持簡潔且可重複使用。

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### 步驟 2：設定檢視選項
將渲染格式設定為 PNG，並告訴檢視器不要預先載入所有頁面（可節省記憶體）。

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### 步驟 3：計算圖塊尺寸
首先取得圖紙的原始寬度與高度，然後將其分割成四個等大的象限。

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### 步驟 4：渲染並儲存圖塊
將計算出的圖塊加入渲染選項，讓 `Viewer` 產生 PNG 檔案。

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### 疑難排解提示
- **Build path** – 確認 GroupDocs JAR 檔案已在 classpath 中。  
- **Permissions** – 輸出資料夾必須允許 Java 程序寫入。  
- **Exceptions** – 若出現 `ViewerException`，請再次確認 DWG 檔案未損毀且已套用正確的授權。

## 常見 CAD 圖塊切割的使用情境
1. **Web Mapping** – 只載入使用者平移/縮放時可見的樓層平面圖部分。  
2. **Document Management** – 將每個圖塊分別儲存，以加快預覽產生速度。  
3. **Mobile Viewing** – 只下載當前螢幕所需的圖塊，以降低頻寬使用。

## 效能考量
- **Tile Size** – 較大的圖塊檔案較少，但渲染較慢；請根據 UI 需求取得平衡。  
- **Memory Monitoring** – 使用 Java 的效能分析工具（例如 VisualVM）監控處理超大型圖紙時的堆積使用情況。  
- **Resource Cleanup** – 如上所示的 try‑with‑resources 模式會自動釋放原生資源。

## 常見問題

**Q: 我可以使用相同方法將其他檔案類型（PDF、圖像）切割成圖塊嗎？**  
A: 可以。GroupDocs Viewer 支援多種格式，只需使用相對應的選項類別（例如 `PdfViewOptions`）。

**Q: 我該如何調整輸出影像品質？**  
A: 調整 `viewOptions.setResolution(int dpi)`，或在 `PngOptions` 物件上設定壓縮參數。

**Q: 我的應用程式在處理非常大的 DWG 檔案時記憶體不足，我該怎麼辦？**  
A: 縮小圖塊尺寸、增加 JVM 堆積大小（`-Xmx`），或在不同的 `Viewer` 實例中依序渲染圖塊。

**Q: 可以非同步渲染圖塊嗎？**  
A: 完全可以。將每個圖塊的渲染呼叫包在 `CompletableFuture` 中，或使用執行緒池服務將工作負載平行化。

**Q: 每個圖塊都需要單獨的授權嗎？**  
A: 不需要。一個有效的 GroupDocs Viewer 授權即可涵蓋應用程式內所有渲染操作。

## 資源
- [文件說明](https://docs.groupdocs.com/viewer/java/)
- [API 參考](https://reference.groupdocs.com/viewer/java/)
- [下載 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [購買授權](https://purchase.groupdocs.com/buy)
- [免費試用](https://releases.groupdocs.com/viewer/java/)
- [臨時授權](https://purchase.groupdocs.com/temporary-license/)
- [支援論壇](https://forum.groupdocs.com/c/viewer/9)

---

**最後更新：** 2026-04-01  
**測試環境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

---