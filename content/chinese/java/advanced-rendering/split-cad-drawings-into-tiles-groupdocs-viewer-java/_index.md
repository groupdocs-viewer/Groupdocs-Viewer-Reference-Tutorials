---
date: '2026-04-01'
description: 了解如何使用 GroupDocs Viewer for Java 将 CAD 图纸拆分为瓦片，以提升渲染性能并简化大文件处理。
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: 如何使用 GroupDocs Viewer 将 CAD 绘图拆分为瓦片
type: docs
url: /zh/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs Viewer 将 CAD 图纸拆分为瓦片

如果您想了解 **如何拆分 CAD** 文件为更小、更易管理的部分，您来对地方了。在本教程中，我们将逐步演示使用 **GroupDocs Viewer for Java** 将大型 CAD 图纸拆分为瓦片的具体步骤。完成后，您将拥有一个可直接使用的解决方案，能够提升渲染速度，降低内存消耗，并且更容易在 Web 或移动应用中显示图纸。

![使用 GroupDocs.Viewer for Java 拆分 CAD 图纸](/viewer/advanced-rendering/split-cad-drawings-java.png)

## 快速答案
- **拆分 CAD 有什么作用？** 它将巨大的图纸拆分为更小的图像（瓦片），加载更快且占用更少内存。  
- **瓦片使用什么格式？** 默认生成 PNG 文件，但通过 Viewer 选项可支持其他格式。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要付费许可证。  
- **我可以更改瓦片大小吗？** 可以——调整 `tileWidth` 和 `tileHeight` 的计算以满足需求。  
- **这种方法是线程安全的吗？** 在每个 `Viewer` 实例中使用 try‑with‑resources 渲染每个瓦片，对并发执行是安全的。

## 什么是“拆分 CAD”？
拆分 CAD 是指将单个通常非常大的 CAD 图纸划分为多个矩形区域（瓦片）。每个瓦片独立渲染，使您仅加载用户实际需要的部分——这对于网页地图、文档门户和移动查看器非常适用。

## 为什么使用 GroupDocs Viewer for Java？
GroupDocs Viewer 开箱即支持超过 100 种文件格式，包括 DWG、DXF 和 DWF。其瓦片 API 允许您指定精确坐标，从而只渲染您关注的区域，而无需先处理整个文件。这可以节省 CPU 周期，降低带宽消耗，并提供更流畅的用户体验。

## 前提条件
- **库**：GroupDocs.Viewer for Java ≥ 25.2。  
- **JDK**：任意近期的 Java 开发工具包（Java 8+）。  
- **IDE**：IntelliJ IDEA、Eclipse 或其他兼容 Java 的 IDE。  
- **构建工具**：Maven（只要添加依赖，其他构建工具也可使用）。

## 设置 GroupDocs.Viewer for Java
将 GroupDocs 仓库和依赖添加到您的 `pom.xml` 中：

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

### 获取许可证
GroupDocs.Viewer 提供免费试用许可证用于评估：

- **免费试用**：访问 [GroupDocs 免费试用](https://releases.groupdocs.com/viewer/java/) 下载库。  
- **临时许可证**：在 [临时许可证页面](https://purchase.groupdocs.com/temporary-license/) 申请。  
- **正式许可证**：在 [购买页面](https://purchase.groupdocs.com/buy) 购买生产许可证。

### 基本初始化
创建一个简单的 `Viewer` 实例，以验证库是否正确加载：

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

## 拆分 CAD 图纸为瓦片的分步指南

### 步骤 1：定义输出目录
我们将每个瓦片存储为单独的 PNG 文件。使用实用方法可以保持路径逻辑简洁且可复用。

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### 步骤 2：配置视图选项
将渲染格式设置为 PNG，并告知查看器不要预加载每一页（这可以节省内存）。

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### 步骤 3：计算瓦片尺寸
首先获取图纸的原始宽度和高度，然后将其分为四个相等的象限。

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

### 步骤 4：渲染并保存瓦片
将计算得到的瓦片添加到渲染选项中，让 `Viewer` 生成 PNG 文件。

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### 故障排除提示
- **构建路径** – 确保 GroupDocs JAR 文件在类路径上。  
- **权限** – 输出文件夹必须对 Java 进程可写。  
- **异常** – 如果出现 `ViewerException`，请再次确认 DWG 文件未损坏且已应用正确的许可证。

## 拆分 CAD 瓦片的常见用例
1. **网页映射** – 当用户平移/缩放时，仅加载平面图的可见部分。  
2. **文档管理** – 将每个瓦片单独存储，以加快预览生成速度。  
3. **移动查看** – 仅下载当前屏幕所需的瓦片，以降低带宽消耗。

## 性能考虑因素
- **瓦片大小** – 较大的瓦片文件更少，但渲染更慢；根据 UI 需求找到平衡点。  
- **内存监控** – 使用 Java 的分析工具（如 VisualVM）监控处理超大图纸时的堆使用情况。  
- **资源清理** – 上述 try‑with‑resources 模式会自动释放本机资源。

## 常见问题

**问：我可以使用相同方法将其他文件类型（PDF、图像）拆分为瓦片吗？**  
答：可以。GroupDocs Viewer 支持多种格式，只需使用相应的选项类（例如 `PdfViewOptions`）。

**问：如何更改输出图像质量？**  
答：调整 `viewOptions.setResolution(int dpi)` 或在 `PngOptions` 对象上设置压缩参数。

**问：我的应用在处理非常大的 DWG 文件时内存不足——该怎么办？**  
答：减小瓦片尺寸，增大 JVM 堆（`-Xmx`），或在不同的 `Viewer` 实例中顺序渲染瓦片。

**问：可以异步渲染瓦片吗？**  
答：完全可以。将每个瓦片渲染调用包装在 `CompletableFuture` 中，或使用执行器服务并行化工作负载。

**问：每个瓦片需要单独的许可证吗？**  
答：不需要。一个有效的 GroupDocs Viewer 许可证覆盖您应用中的所有渲染操作。

## 资源
- [文档](https://docs.groupdocs.com/viewer/java/)
- [API 参考](https://reference.groupdocs.com/viewer/java/)
- [下载 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [购买许可证](https://purchase.groupdocs.com/buy)
- [免费试用](https://releases.groupdocs.com/viewer/java/)
- [临时许可证](https://purchase.groupdocs.com/temporary-license/)
- [支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-04-01  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs