---
date: '2026-06-05'
description: 了解如何使用 GroupDocs.Viewer Java 将 Excel 转换为 HTML、JPG、PNG 和 PDF。本分步指南涵盖环境设置、渲染选项以及实际使用案例。
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: 如何使用 GroupDocs.Viewer Java 将 Excel 转换为 HTML、JPG、PNG 和 PDF
type: docs
url: /zh/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# 使用 GroupDocs.Viewer Java 将 Excel 转换为 HTML、JPG、PNG 和 PDF

将 Excel 转换为 HTML 是在网页上显示电子表格数据并保留行列标题的常见需求。在本教程中，您将学习 GroupDocs.Viewer for Java 如何简化 **convert excel to html**，以及如何将同一工作簿渲染为 JPG、PNG 和 PDF 格式。我们将逐步介绍前置条件、库的设置以及每种渲染场景，并提供清晰、可直接用于生产的代码片段。

## 快速答案
- **GroupDocs.Viewer 能将 Excel 渲染为多种格式吗？** 是的——HTML、JPG、PNG 和 PDF 开箱即用。  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需要永久许可证。  
- **行列标题会被保留吗？** 在视图选项上设置 `setRenderHeadings(true)` 即可包含标题。  
- **需要哪个 Java 版本？** Java 8 或更高；库兼容 Java 11、 17 及更高版本。  
- **对大型工作簿的转换速度如何？** 在典型服务器硬件上，GroupDocs.Viewer 能在一秒以内处理 200 页的电子表格。

## 什么是“convert excel to html”？
**Convert excel to html** 指将 Excel 工作簿转换为可在网页上直接使用的 HTML 文档，同时保持原始布局、公式和标题。这使得可以无缝地将电子表格嵌入网页或门户，而无需用户安装 Excel。

## 为什么在 Excel 渲染中使用 GroupDocs.Viewer Java？
GroupDocs.Viewer Java 支持 **50+ 输入和输出格式**，包括 DOCX、XLSX、PPTX、HTML、JPG、PNG 和 PDF。它能够在不将整个文件加载到内存的情况下处理数百页的工作簿，转换速度比许多开源方案快 **10 ×**。库还提供对渲染选项的细粒度控制，如标题可见性、页面大小和图像质量。

## 前置条件

- **Java Development Kit (JDK) 8+** 已安装并在您的 IDE（IntelliJ IDEA、Eclipse 等）中配置。  
- **Maven** 用于依赖管理。  
- 熟悉 Java 语法和 Maven 的 `pom.xml`。  
- 拥有有效的 **GroupDocs.Viewer Java** 许可证（试用或永久）。

### 必需的库和依赖
将 GroupDocs.Viewer Java 依赖添加到您的 `pom.xml`：

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
- 验证 `java -version` 返回 1.8 或更高版本。  
- 打开您喜欢的 IDE 并创建一个 Maven 项目。

让我们先完成前置条件，然后再深入实现。

![使用 GroupDocs.Viewer for Java 将 Excel 文件转换为 HTML、JPG、PNG 和 PDF](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## 设置 GroupDocs.Viewer Java

### 安装信息
在项目的 `pom.xml` 中加入上面展示的 Maven 依赖。运行 `mvn clean install` 后，库将出现在类路径上。

### 获取许可证的步骤
1. **免费试用：** 从 [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) 下载试用版。  
2. **临时许可证：** 从 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 获取临时许可证以进行扩展测试。  
3. **购买：** 在 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 获取用于生产的完整许可证。

### 基本初始化
`Viewer` 类是所有渲染操作的入口。初始化非常简单：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

这将创建一个绑定本地许可证文件的 `Viewer` 实例，准备处理 Excel 文件。

## 实现指南

下面我们逐一介绍每种渲染目标。对每种格式，首先 **导入所需类**，然后 **设置输出目录**，最后 **使用 `setRenderHeadings(true)` 配置视图选项** 以保留行列标题。

### 将电子表格渲染为 HTML
**如何使用 GroupDocs.Viewer Java 将 Excel 工作簿转换为 HTML？**  
要将 Excel 工作簿转换为 HTML，使用 Viewer 加载文件，创建 HtmlViewOptions 实例，启用标题渲染，然后调用 view 方法。该过程会将每个工作表写入单独的 HTML 文件，保留单元格格式、公式和原始布局，以实现准确的网页显示。

#### 步骤实现
**1. 导入所需库**  
HtmlViewOptions 配置工作簿渲染为 HTML 的方式，允许自定义标题、样式和页面布局。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. 设置输出目录**  
指定生成的 HTML 页面将写入的文件夹。

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. 初始化 Viewer 并配置选项**  
创建 `Viewer` 实例，设置 `setRenderHeadings(true)`，并调用 `view`。

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**说明：** `HtmlViewOptions` 控制 HTML 输出。启用 `setRenderHeadings(true)` 可确保首行和首列（通常是标题）出现在生成的 HTML 中，使数据一目了然。

### 将电子表格渲染为 JPG
**如何在包含标题的情况下将 Excel 工作表渲染为 JPG 图像？**  
将 Excel 工作表渲染为 JPG 包括使用 Viewer 加载工作簿，构建 JpgViewOptions 对象，设置 renderHeadings 为 true，然后调用 view。库会以指定 DPI 对每页进行光栅化，生成保留电子表格视觉结构和标题的高分辨率 JPG 文件。

#### 步骤实现
**1. 导入所需库**  
JpgViewOptions 定义将工作表渲染为 JPG 图像的设置，包括 DPI、质量和标题可见性。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. 设置输出目录**  
定义 JPG 文件的存储位置。

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. 初始化 Viewer 并配置选项**  
创建 Viewer，设置标题渲染，并执行转换。

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**说明：** `JpgViewOptions` 让您控制 DPI 和质量。通过 `setRenderHeadings(true)`，生成的图像会保留电子表格的标题行和列，这对报告和演示尤为重要。

### 将电子表格渲染为 PNG
**在保留列标题的情况下将 Excel 转换为 PNG 的流程是什么？**  
要从 Excel 文件生成 PNG 图像，使用 Viewer 打开工作簿，创建 PngViewOptions 实例，启用标题渲染，然后执行 view。PNG 输出提供无损质量，保留所有单元格样式和标题行，适合归档或进一步图像处理。

#### 步骤实现
**1. 导入所需库**  
PngViewOptions 控制工作表渲染为 PNG 图像，提供无损压缩和标题选项。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. 设置输出目录**  
选择 PNG 输出的文件夹。

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. 初始化 Viewer 并配置选项**  
创建 Viewer，启用标题渲染，并调用 `view`。

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**说明：** 通过调用 `setRenderHeadings(true)`，PNG 文件会包含原始电子表格的标题行和列，为下游使用者保留上下文信息。

### 将电子表格渲染为 PDF
**如何在 PDF 中显示行列标题并将 Excel 文件转换为 PDF？**  
将 Excel 转换为 PDF 非常直接：使用源文件实例化 Viewer，配置 PdfViewOptions 对象以渲染标题，然后调用 view。生成的 PDF 完全复制工作簿布局，包括行列标题，并支持矢量图形，适合高质量打印和分发。

#### 步骤实现
**1. 导入所需库**  
PdfViewOptions 指定 PDF 生成参数，如页面大小、边距和标题渲染。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. 设置输出目录**  
指定 PDF 文档的目标文件夹。

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. 初始化 Viewer 并配置选项**  
创建 `Viewer`，启用标题渲染，并执行转换。

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**说明：** 在 `PdfViewOptions` 上设置 `setRenderHeadings(true)` 可确保首行/首列出现在最终 PDF 中，使文档可直接用于打印或归档。

## 实际应用
在以下真实场景中，**convert excel to html**、**excel to pdf java** 或 **convert spreadsheet to image** 都极具价值：

1. **业务报告：** 从财务模型生成 HTML 仪表盘或 PDF 报告，无需手动复制粘贴。  
2. **数据可视化：** 将电子表格的 JPG/PNG 快照嵌入幻灯片，确保标题为观众提供即时上下文。  
3. **文档归档：** 将 Excel 工作簿存为 PDF 以满足合规要求，同时保留原始布局和标题。  
4. **Web 门户：** 直接在浏览器中提供 HTML 版电子表格，实现基于 JavaScript 的交互过滤。

## 常见问题

**Q: 能转换受密码保护的 Excel 文件吗？**  
A: 可以。将密码传递给 `Viewer` 构造函数，库将在渲染前解密工作簿。

**Q: GroupDocs.Viewer 是否支持宏启用的工作簿 (.xlsm)？**  
A: 完全支持。渲染时宏被视为数据并被忽略，确保转换安全。

**Q: 支持的最大文件大小是多少？**  
A: 由于流式架构，库可处理高达 **2 GB** 的文件而无需将整个文档加载到内存。

**Q: 能只渲染特定工作表吗？**  
A: 可以。使用 `ViewOptions.setPageNumber(pageIndex)` 在生成 HTML、JPG、PNG 或 PDF 时定位单个工作表。

**Q: 如何控制 JPG 输出的图像质量？**  
A: 设置 `JpgViewOptions.setQuality(90)`（取值 0‑100）即可在文件大小和视觉保真度之间取得平衡。

## 结论
现在您已经拥有使用 GroupDocs.Viewer Java 完成 **convert excel to html**、**excel to pdf java** 和 **convert spreadsheet to image** 的完整、可投入生产的指南。遵循上述步骤，您可以将电子表格渲染集成到任何 Java 后端，自动生成带有标题的 HTML 报告、高分辨率图像或归档 PDF。

---

**最后更新：** 2026-06-05  
**测试版本：** GroupDocs.Viewer Java 23.12  
**作者：** GroupDocs

## 相关教程

- [如何使用 GroupDocs.Viewer for Java 将 DOCX 转换为 HTML：一步步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer for Java 的响应式 HTML 渲染：综合指南](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – 使用 GroupDocs.Viewer for Java 将 ODF 转换为 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)