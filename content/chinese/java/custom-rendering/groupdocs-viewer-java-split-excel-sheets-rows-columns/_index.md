---
date: '2026-06-15'
description: 了解如何使用 GroupDocs Viewer 将 Excel 转换为 PDF（Java）并按行列拆分 Excel 工作表。包括设置、代码和最佳实践。
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: 将 Excel 转换为 PDF（Java）并按行列拆分工作表
type: docs
url: /zh/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# 将 Excel 转换为 PDF Java 并按行列拆分工作表 (Java)

大型 Excel 工作簿通常包含的数据显示在单个屏幕或打印页上会显得过多。**convert excel to pdf java** 是在需要静态、可共享格式时的常见需求，而 **splitting Excel sheets by rows and columns** 则使数据在网页或打印布局中更易于阅读。在本指南中，我们将使用 **GroupDocs Viewer for Java** 演示这两项任务，展示如何配置分页，并解释性能和故障排除的最佳实践技巧。

![使用 GroupDocs.Viewer for Java 按行列拆分 Excel 工作表](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[使用 GroupDocs.Viewer for Java 按行列拆分 Excel 工作表](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## 快速答案
- **使用的库是什么？** GroupDocs Viewer for Java.  
- **我可以同时按行和列拆分吗？** 是的 – 您可以一起定义每页行数和每页列数。  
- **我需要许可证吗？** 试用或临时许可证可用于开发；生产环境需要完整许可证。  
- **支持哪些输出格式？** 示例显示 HTML（嵌入资源）；使用相同选项也可以生成 PDF。  
- **需要 Maven 吗？** Maven 是管理依赖的推荐方式。  
- **我还能将 Excel 转换为 PDF 吗？** 当然 – 只需将 `HtmlViewOptions` 切换为 `PdfViewOptions` 并复用相同的分页设置。

## 什么是 “如何拆分 Excel”？
拆分 Excel 工作表是指根据固定的行数、列数或两者的组合，将单个工作表划分为多个页面或文件。当您需要创建分页报告、在网页中嵌入数据或生成可打印的章节而无需一次性加载整个工作簿时，此技术非常实用。

## 为什么使用 GroupDocs Viewer for Java？
GroupDocs Viewer 在一次处理过程中处理电子表格并自动分页，省去手动计算。**快速渲染可在典型的双核服务器上在 2 秒内处理 250 页的 XLSX 工作簿**，并且 **该库支持 50 多种输入和输出格式**，包括 XLS、XLSX、CSV、PDF 和 HTML。它可在任何兼容 JVM 的平台上运行——Windows、Linux、macOS、Docker 容器或基于云的无服务器运行时——因此您可以在 Java 应用所在的任何位置集成它。

## 前置条件
- 已安装 Java 17 或更高版本。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 用于依赖管理的 Maven。  
- 基本的 Java 知识以及对 Excel 文件处理的了解。

### 必需的库、版本和依赖
在您的 `pom.xml` 中添加 GroupDocs 仓库和 viewer 依赖：

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
从 [GroupDocs](https://purchase.groupdocs.com/buy) 获取免费试用、临时许可证或购买完整许可证。

## 如何将 Excel 转换为 PDF Java？

`Viewer` 类是 GroupDocs Viewer 的核心组件，用于加载文档并提供各种输出格式的渲染方法。`SpreadsheetOptions` 允许您控制电子表格渲染的分页设置，如每页行数和每页列数。

使用 `new Viewer("source.xlsx")` 加载 Excel 文件，配置 `SpreadsheetOptions` 进行分页，然后调用 `viewer.view(pdfOptions, stream)` —— 这一次调用即可在遵循您设定的行/列限制的同时将工作簿转换为 PDF。转换会保留公式、图像和单元格样式，生成可直接分发的忠实 PDF 副本。

## 如何按行拆分 Excel 工作表

按行拆分会生成一系列 HTML 页面，每个页面包含固定数量的行（例如 15 行）。此方法非常适合在仪表板中每次显示有限记录数的视图。Viewer 将生成诸如 `page_0.html`、`page_1.html` 等单独的 HTML 文件，每个文件包含指定数量的行。这使得在 Web 界面中仅加载所需部分变得简单，从而降低带宽和渲染时间。

### 定义锚点
`Viewer` 是 GroupDocs Viewer 的核心类，负责加载文档并协调渲染到所选输出格式。

### 步骤实现

#### 步骤 1：设置路径并初始化 Viewer
首先，定义拆分页面的保存位置，并为源工作簿创建 `Viewer` 实例。

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### 步骤 2：配置每页行数
告诉 Viewer 每页应包含多少行。

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### 步骤 3：渲染文档
最后，使用您定义的选项渲染工作簿。

```java
viewer.view(viewOptions);
```

## 如何按行列拆分 Excel 工作表

有时单个页面需要显示行 **和** 列的矩阵（例如 15 行 × 7 列）。这让您能够完全控制每个 HTML 页面 的布局。生成的页面显示一个矩形单元格块，例如第一页显示第 1‑15 行和 A‑G 列，下一页显示第 16‑30 行和 H‑N 列。这种网格式分页对于创建适合标准纸张尺寸的可打印报告非常有用。

### 定义锚点
`SpreadsheetOptions` 配置每个生成页面上显示的行数和列数。

### 步骤实现

#### 步骤 1：设置路径并初始化 Viewer
设置方式与仅按行的示例相同，只是文件名不同。

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### 步骤 2：配置每页行列数
同时指定行数和列数以创建网格式拆分。

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### 步骤 3：渲染文档
使用相同的 `view` 调用进行渲染。

```java
viewer.view(options);
```

## 实际应用
- **生成 Excel 报告 Java**：将大型财务模型转换为一系列分页的 HTML 报告。  
- **GroupDocs Viewer Excel**：将拆分页面直接嵌入 Web 门户，实现交互式数据探索。  
- **渲染 Excel HTML Java**：通过 servlet 或 Spring 控制器提供生成的 HTML 页面，实现快速的客户端渲染。  

## 性能考虑因素
- **内存使用** – 大型工作簿可能占用大量堆内存；考虑增大 JVM 的 `-Xmx` 设置。  
- **块大小** – 选择行/列数以平衡页面大小和渲染速度。  
- **版本更新** – 保持 GroupDocs Viewer 为最新，以获得性能提升；最新的 25.2 版本相比 24.x 可提升渲染速度最高达 30 %。  

## 常见问题与故障排除

| 症状 | 可能原因 | 解决方案 |
|---------|--------------|-----|
| `OutOfMemoryError` | 每页行数过多导致渲染非常大的工作表 | 减少 `countRowsPerPage` 或增大 JVM 堆 |
| 输出文件为空 | 文件路径不正确或缺少写入权限 | 确认 `outputDirectory` 存在且可写 |
| HTML 资源未加载 | 使用 `forEmbeddedResources` 但文件从不同的基础 URL 提供 | 提供整个输出文件夹或切换为 `forExternalResources` |

## 常见问题

**问：我可以生成 PDF 而不是 HTML 吗？**  
答：可以。将 `HtmlViewOptions` 替换为 `PdfViewOptions`，并保持相同的 `SpreadsheetOptions` 配置。

**问：是否可以基于单元格内容而不是固定行/列进行拆分？**  
答：GroupDocs Viewer 未内置基于内容的拆分，但您可以使用 Apache POI 预处理工作簿，在渲染前创建单独的工作表。

**问：GroupDocs Viewer 是否支持旧的 Excel 格式（XLS）？**  
答：当然。Viewer 支持 XLS、XLSX、CSV 以及其他电子表格格式。

**问：如何将生成的 HTML 嵌入到 Spring MVC 视图中？**  
答：将输出文件夹作为静态资源提供，并在 Thymeleaf 或 JSP 模板中引用生成的 `page_0.html`、`page_1.html` 等。

**问：商业部署需要什么许可证？**  
答：需要 GroupDocs 的完整生产许可证；试用许可证仅用于评估。

## 资源
- **文档**： [GroupDocs Viewer Java 文档](https://docs.groupdocs.com/viewer/java/)
- **API 参考**： [GroupDocs API 参考](https://reference.groupdocs.com/viewer/java/)
- **下载**： [GroupDocs Viewer Java 发布版](https://releases.groupdocs.com/viewer/java/)
- **购买**： [购买 GroupDocs 许可证](https://purchase.groupdocs.com/buy)
- **免费试用**： [GroupDocs 免费试用](https://releases.groupdocs.com/viewer/java/)
- **临时许可证**： [获取临时许可证](https://purchase.groupdocs.com/temporary-license/)
- **支持**： [GroupDocs 支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-06-15  
**测试环境：** GroupDocs Viewer 25.2 for Java  
**作者：** GroupDocs  

---

## 相关教程

- [在 Java 电子表格中使用 GroupDocs.Viewer 渲染隐藏的行和列](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [在 Java 中使用 GroupDocs.Viewer 跳过渲染空行：性能指南](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [综合指南：使用 GroupDocs.Viewer Java 将 Excel 2003 XML 转换为 HTML/JPG/PNG/PDF](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)