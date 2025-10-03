---
"date": "2025-04-24"
"description": "学习如何使用 GroupDocs.Viewer Java 将 Excel 文件转换为 HTML、JPG、PNG 和 PDF。本指南涵盖设置、渲染选项和实际应用。"
"title": "如何使用 GroupDocs.Viewer Java 将 Excel 转换为 HTML/JPG/PNG/PDF — 分步指南"
"url": "/zh/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
type: docs
---
# 如何使用 GroupDocs.Viewer Java 将 Excel 转换为 HTML/JPG/PNG/PDF：分步指南

## 介绍

在许多情况下，将电子表格数据转换为 HTML、JPG、PNG 或 PDF 等各种格式，同时保留行标题和列标题等关键细节至关重要。无论您是生成报告、与利益相关者共享信息，还是将电子表格集成到 Web 应用程序中，转换 Excel 表格都是一项关键需求。本指南将引导您了解 GroupDocs.Viewer Java 如何轻松、精准地完成这些任务。

**您将学到什么：**
- 设置并使用 GroupDocs.Viewer for Java
- 将 Excel 文件渲染为 HTML、JPG、PNG 和 PDF 格式
- 配置选项以在输出中包含行和列标题
- 渲染文档的实际应用

在我们深入实施之前，让我们先了解一下所需的先决条件。

## 先决条件

在使用 GroupDocs.Viewer Java 呈现电子表格之前，请确保您已：

### 所需的库和依赖项

使用 Maven 设置 Java 版 GroupDocs.Viewer。以下是如何将其添加到项目中：

**Maven设置：**
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

### 环境设置
- 确保您已安装 Java 开发工具包 (JDK)。
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE 以方便开发。

### 知识前提
- 熟悉 Java 编程
- 对 Maven 依赖管理有基本的了解

有了这些先决条件，让我们继续设置 GroupDocs.Viewer for Java 并开始实现其功能。

## 为 Java 设置 GroupDocs.Viewer

GroupDocs.Viewer for Java 是一个功能强大的库，可让您以各种格式呈现文档。以下是使用方法：

### 安装信息
如上所述，使用 Maven 将 GroupDocs.Viewer 添加为项目依赖项 `pom.xml` 文件。

### 许可证获取步骤
1. **免费试用：** 下载试用版 [GroupDocs 免费试用](https://releases。groupdocs.com/viewer/java/).
2. **临时执照：** 获取临时许可证以获得更多功能 [GroupDocs 临时许可证](https://purchase。groupdocs.com/temporary-license/).
3. **购买：** 如需完全访问权限和支持，请购买许可证 [GroupDocs 购买](https://purchase。groupdocs.com/buy).

### 基本初始化
安装后，您可以使用以下命令初始化 GroupDocs.Viewer：
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // 此处的代码用于使用查看器
        }
    }
}
```
这将初始化您的环境，为您渲染文档做好准备。

## 实施指南

让我们分解每个功能并详细探讨如何实现它们。

### 将电子表格渲染为 HTML
**概述：** 将 Excel 工作表转换为 HTML 格式，同时保留用于网络演示或报告的行和列标题。

#### 逐步实施：
##### 1.导入所需的库
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2.设置输出目录
定义渲染文件的存储位置。
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3.初始化查看器并配置选项
使用 GroupDocs.Viewer 呈现文档：
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // 启用电子表格中的行和列标题的呈现。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 页。
}
```
**解释：** 这 `HtmlViewOptions` 类用于配置 HTML 输出。设置 `setRenderHeadings(true)` 确保行和列标题在呈现的 HTML 中可见。

### 将电子表格渲染为 JPG
**概述：** 将 Excel 工作表转换为高质量图像文件 (JPG)，同时包含行和列标题，非常适合视觉演示或打印输出。

#### 逐步实施：
##### 1.导入所需的库
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2.设置输出目录
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3.初始化查看器并配置选项
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // 启用电子表格中的行和列标题的呈现。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 页。
}
```
**解释：** `JpgViewOptions` 处理图像设置。 `setRenderHeadings(true)` 选项确保标题包含在 JPG 输出中。

### 将电子表格渲染为 PNG
**概述：** 将 Excel 工作表转换为 PNG 格式，同时保留行和列标题，适合高质量的图像输出。

#### 逐步实施：
##### 1.导入所需的库
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2.设置输出目录
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3.初始化查看器并配置选项
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // 启用电子表格中的行和列标题的呈现。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 页。
}
```
**解释：** `PngViewOptions` 用于 PNG 设置。使用 `setRenderHeadings(true)`，标题包含在输出图像中。

### 将电子表格渲染为 PDF
**概述：** 将 Excel 工作表转换为 PDF 格式，同时确保行和列标题可见，非常适合存档或共享文档。

#### 逐步实施：
##### 1.导入所需的库
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2.设置输出目录
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3.初始化查看器并配置选项
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // 启用电子表格中的行和列标题的呈现。
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // 渲染第 1 至 3 页。
}
```
**解释：** `PdfViewOptions` 配置 PDF 输出设置。 `setRenderHeadings(true)` 选项确保标题在最终 PDF 中可见。

## 实际应用
以下是一些可以应用这些功能的实际场景：

1. **业务报告：** 将 Excel 数据转换为 HTML 或 PDF 格式以便于传播和查看，与利益相关者共享详细报告。
2. **数据可视化：** 将电子表格转换为 JPG 或 PNG 等图像格式以用于演示，确保标题为可视化数据提供上下文。
3. **文件归档：** 使用 PDF 转换以通用可访问的格式存档文档，保留所有必要的细节，例如标题。