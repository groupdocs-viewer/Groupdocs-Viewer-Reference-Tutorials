---
date: '2026-06-10'
description: 了解如何使用 GroupDocs.Viewer for Java 将 DWG 渲染为 JPG，并将 CAD 文件转换为 JPG，分步教程。
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
title: 使用 GroupDocs.Viewer Java 将 DWG 渲染为 JPG – 完整指南
type: docs
url: /zh/java/rendering-basics/render-cad-drawings-jpg-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer Java 将 DWG 渲染为 JPG：一步一步教程

## 介绍

使用 GroupDocs.Viewer Java 将 DWG 渲染为 JPG 可以轻松将复杂的 CAD 图纸转换为轻量级、适合网页的图像。在本指南中，您将了解如何设置库、配置输出路径以及使用 PC3 文件来控制图像尺寸和质量。完成后，您只需几行 Java 代码即可实现 DWG 文件到 JPG 的自动转换。

![Render CAD Drawings as JPG with GroupDocs.Viewer for Java](/viewer/rendering-basics/render-cad-drawings-as-jpg-java.png)

## 快速回答
- **哪个库负责转换？** GroupDocs.Viewer for Java.
- **生成的文件格式是什么？** JPG images.
- **开发是否需要许可证？** A free trial works for testing; a full license is required for production.
- **我可以控制图像尺寸吗？** Yes, via a PC3 configuration file.
- **Java 8 足够吗？** Java 8 or newer is fully supported.

## 什么是“render dwg as jpg”？

*Render dwg as jpg* 是将 DWG（AutoCAD）图纸转换为 JPEG 栅格图像的过程。此转换在保持视觉保真度的同时，使文件易于在浏览器、电子邮件或移动应用中查看。它还能显著减小文件大小，从而加快加载速度并简化跨平台、跨设备的分发。

## 为什么使用 GroupDocs.Viewer for Java？

GroupDocs.Viewer 支持 **50+** 种输入格式——包括 DWG、DXF 和 DWF，并且可以在不将整个文件加载到内存中的情况下渲染数百页的图纸。该库在标准 8 核服务器上可在 5 秒内处理典型的 200 页 CAD 文件，生成保留线宽和颜色的高质量 JPG。

## 先决条件

### 必需的库和依赖项
- **GroupDocs.Viewer for Java** – version 25.2 (or later).

### 环境设置要求
- Java Development Kit 8 or newer.
- Maven or Gradle for dependency management.

### 知识先决条件
- Basic Java syntax.
- Familiarity with file‑system paths.

## 设置 GroupDocs.Viewer for Java

要开始，请包含必要的依赖项。如果使用 Maven，请添加以下配置：

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

### 许可证获取
- **Free Trial**：从 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 下载试用版本。
- **Temporary License**：在 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 获取临时许可证以获得全部功能。
- **Purchase**：通过 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 购买长期使用许可证。

### 其他资源
- [GroupDocs Viewer 文档](https://docs.groupdocs.com/viewer/java/)
- [API 参考](https://reference.groupdocs.com/viewer/java/)
- [下载 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [购买许可证](https://purchase.groupdocs.com/buy)
- [免费试用](https://releases.groupdocs.com/viewer/java/)
- [临时许可证](https://purchase.groupdocs.com/temporary-license/)
- [支持论坛](https://forum.groupdocs.com/c/viewer/9)

## 基本初始化

`Viewer` 类加载文档并提供将页面渲染为各种格式的方法。设置好环境并添加依赖后，在 Java 应用中初始化 GroupDocs.Viewer：

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

## 实现指南

### 使用特定配置渲染 CAD 图纸

此功能允许使用 PC3 文件中定义的设置将 DWG 文件渲染为 JPG 图像。

#### 概述

我们将加载 DWG 图纸，创建 `JpgViewOptions`，并将选项指向自定义 PC3 文件，以定义页面尺寸、DPI 和线条渲染样式。

#### 逐步实现

##### 导入所需的包

`JpgViewOptions` 指定渲染设置（如分辨率、页面尺寸和 JPEG 输出格式），`Viewer` 执行实际转换。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;
```

##### 定义输出目录和文件路径

输出文件夹用于组织生成的图像，并便于批处理后清理。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("pc3_result.jpg");
```

##### 加载 CAD 图纸并设置配置

`Viewer` 读取 DWG 文件，`setRenderOptions` 方法在渲染每页之前应用 PC3 配置。

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Set the PC3 configuration for rendering
    options.getCadOptions().setPc3File(TestFiles.SAMPLE_PC3_CONFIG);
    
    // Render the CAD drawing to a JPG image
    viewer.view(options);
}
```

#### 故障排除提示
- **缺少依赖项**：验证 Maven 坐标与您安装的版本匹配。
- **路径不正确**：使用绝对路径或 `Path.of(...)` 以避免平台特定的问题。

## 渲染输出的路径配置

正确的路径处理可防止文件未找到错误并简化批处理作业。

### 定义输出目录路径

您可以将渲染的图像存放在以源文件名命名的子文件夹中，便于查找。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
```

### 构建渲染图像的文件路径

使用类似 `drawing_page_{page}.jpg` 的命名模式，可在后续需要引用单独页面时提供便利。

```java
Path pageFilePathFormat = outputDirectory.resolve("pc3_result.jpg");
```

## 实际应用

1. **建筑设计** – 与没有 CAD 软件的客户共享建筑平面图。
2. **工程项目** – 在 PowerPoint 演示文稿中包含详细原理图。
3. **室内设计** – 快速从平面图 DWG 文件生成情绪板图像。

## 性能考虑

- **资源管理**：渲染完成后立即调用 `viewer.close()` 以释放文件句柄。
- **内存调优**：对于非常大的 DWG 文件，增加 JVM 堆（`-Xmx2g`）以避免 `OutOfMemoryError`。

## 如何使用 GroupDocs.Viewer Java 将 DWG 渲染为 JPG？

使用 `new Viewer("drawing.dwg")` 加载 DWG，创建指向 PC3 文件的 `JpgViewOptions` 对象，然后调用 `viewer.view(pageNumber, options, outputStream)`。此单行调用即可在自动应用 PC3 布局规则的同时，将指定页面渲染为高质量 JPG。该方法还返回渲染元数据，便于在转换后验证页数和图像尺寸。

## 什么是 PC3 配置文件？

PC3 文件是一个纯文本的 AutoCAD 配置文件，定义了页面尺寸、打印样式、DPI 和线宽缩放等栅格输出参数。提供自定义 PC3 可在所有渲染图纸中统一图像尺寸。通过编辑 PC3，您可以控制边距、纸张方向和颜色映射，确保每次转换的视觉结果一致。

## 常见问题及解决方案

- **空白图像**：确保 PC3 文件引用有效的绘图仪，并且 DWG 包含可打印的图层。
- **低分辨率**：在 PC3 文件中增加 DPI 设置，或在代码中设置 `options.setResolution(300)`。
- **许可证错误**：确认许可证文件放置在应用程序的类路径中，并且试用期未过期。

## 常见问题

**Q: 我可以在一次调用中渲染 DWG 的多个页面吗？**  
A: 可以，遍历页码并对每页调用 `viewer.view(page, options, stream)`；库会独立流式输出每个 JPG。

**Q: GroupDocs.Viewer 支持其他栅格格式吗？**  
A: 当然可以——通过使用 `PngViewOptions`、`BmpViewOptions` 或 `TiffViewOptions` 分别渲染为 PNG、BMP 或 TIFF。

**Q: 能处理多大的 DWG 文件？**  
A: 引擎可处理高达 2 GB 的文件；对于更大的档案，请在渲染前将图纸拆分为多个文件。

**Q: 是否需要单独安装 CAD 软件？**  
A: 不需要，GroupDocs.Viewer 完全在服务器端完成渲染，无需安装 AutoCAD。

**Q: 支持哪些 Java 版本？**  
A: 完全支持 Java 8、11、17 及更高版本。

## 结论

现在，您已经掌握了使用 GroupDocs.Viewer for Java **render dwg as jpg** 的完整、可投入生产的方案。本教程涵盖了环境搭建、基于 PC3 的配置、路径处理以及性能技巧。将此模式集成到批处理流水线、Web 服务或桌面工具中，即可为任何 CAD 图纸提供快速、高质量的 JPEG 预览。

---

**Last Updated:** 2026-06-10  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs

## 相关教程

- [如何使用 GroupDocs.Viewer for Java 将 CAD 图纸渲染为 PNG（自定义尺寸和背景颜色）](/viewer/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/)
- [使用 GroupDocs.Viewer 渲染 CAD 图层 Java – 完整指南](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [使用 GroupDocs.Viewer Java 将 CAD 图纸拆分为瓦片以实现高效渲染](/viewer/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/)