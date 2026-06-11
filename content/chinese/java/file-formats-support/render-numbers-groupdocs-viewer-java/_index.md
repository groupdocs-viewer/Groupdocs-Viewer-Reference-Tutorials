---
date: '2026-03-05'
description: 学习如何使用 GroupDocs.Viewer for Java 将数字转换为 PDF 以及其他格式，如 HTML、JPG、PNG。本指南涵盖设置、渲染技术和实际应用。
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: 使用 GroupDocs.Viewer for Java 将 Numbers 转换为 PDF
type: docs
url: /zh/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer for Java 将 Numbers 转换为 PDF（及其他格式）

在网页或桌面应用中显示 Apple Numbers 文档可能比较棘手，尤其是当您需要 **convert numbers to pdf** 或将其嵌入为图像时。在本教程中，我们将演示如何使用 **GroupDocs.Viewer for Java** 将 Numbers 文件渲染为 HTML、JPG、PNG、**以及 PDF**——为共享、预览或归档电子表格提供灵活的选项。

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### 您将学习
- 如何在基于 Maven 的 Java 项目中设置 GroupDocs.Viewer  
- 逐步代码示例，**convert numbers to pdf**、**convert numbers to html** 和 **convert numbers to jpg**  
- 实际场景，文档转换在 Web 门户、电子邮件工作流和 DMS 集成中提升价值  

## 快速回答
- **我可以使用 Java 将 Numbers 转换为 PDF 吗？** 是的，使用 GroupDocs.Viewer 中的 `PdfViewOptions`。  
- **哪种格式最适合网页预览？** HTML 提供最交互的体验。  
- **生产环境需要许可证吗？** 商业许可证是非试用部署的必需。  
- **支持图像转换吗？** 当然——使用 `JpgViewOptions` 或 `PngViewOptions` 可获得高质量图像。  
- **需要哪个 Java 版本？** Java 8+ 并使用 Maven 管理依赖。  

## 前提条件
- 已安装 Java Development Kit (JDK) 8 或更高版本。  
- 用于处理依赖的 Maven。  
- 熟悉 Java 文件 I/O 和路径的基础知识。  

## 为 Java 设置 GroupDocs.Viewer

### 使用 Maven 安装
将仓库和依赖添加到您的 `pom.xml` 中。此代码块必须保持原样：

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
- **免费试用：** 免费评估所有功能。  
- **临时许可证：** 请求限时密钥以进行扩展测试。  
- **购买：** 为商业项目获取完整许可证。  

## 将 Numbers 文档渲染为 HTML  
*使用场景：将电子表格直接嵌入网页。*

### 步骤 1：初始化 Viewer 并配置 HTML 选项
下面是您将运行的完整代码。注释解释了每一行，但 **请勿修改代码块**。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **原因说明：** `HtmlViewOptions.forEmbeddedResources()` 将 CSS 和图像打包到 HTML 中，非常适合快速网页预览。

## 将 Numbers 文档渲染为 JPG  
*适用于在社交媒体或电子邮件中分享电子表格快照。*

### 步骤 1：设置 Viewer 和 JPG 选项
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **提示：** 如需更小的文件，可通过 `options.setQuality(int)` 调整图像质量。  

## 将 Numbers 文档渲染为 PNG  
*当需要无损、高分辨率的报告图像时的理想选择。*

### 步骤 1：初始化并配置 PNG 选项
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **专业提示：** 使用 `options.setResolution(int)` 控制 DPI，以获得适合打印的图像。  

## 将 Numbers 文档渲染为 PDF  
*许多开发者的主要目标：**convert numbers to pdf** 用于归档或分发。*

### 步骤 1：设置 Viewer 进行 PDF 转换
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **关键配置：** `PdfViewOptions` 允许嵌入字体并控制页面大小，确保输出符合品牌要求。  

## 实际应用
- **Web 集成：** 渲染为 HTML，以在站点上提供交互式电子表格查看器。  
- **内容共享：** 转换为 JPG/PNG，以便在新闻通讯或聊天中快速嵌入图像。  
- **企业 DMS：** 使用 **convert numbers to pdf** 将电子表格存储为不可编辑、可搜索的版本。  

## 性能考虑
- **资源管理：** 始终在 try‑with‑resources 块中关闭 `Viewer`（如示例所示），以及时释放本机资源。  
- **大文件：** 对于巨大的 Numbers 文件，考虑逐页处理并流式输出，以避免高内存消耗。  
- **线程安全：** 为每个线程创建单独的 `Viewer` 实例；该类不是线程安全的。  

## 结论
现在，您已经拥有使用 GroupDocs.Viewer for Java 将 **convert numbers to pdf** 以及转换为 HTML、JPG、PNG 的完整工具箱。这些功能使您能够构建灵活的文档流水线——无论是为 Web 门户提供内容、生成报告，还是归档电子表格。

### 下一步
在 [GroupDocs 文档](https://docs.groupdocs.com/viewer/java/) 中探索更多自定义选项，并尝试将这些功能集成到您自己的应用程序中。

## 常见问题

**Q1: GroupDocs.Viewer 支持哪些文件格式？**  
A1: 它支持包括 DOCX、XLSX、PDF 等在内的多种文档格式。

**Q2: 如何高效处理大型 Numbers 文件？**  
A2: 利用 Java 的内存管理技术并优化代码，以有效处理大文件。

**Q3: GroupDocs.Viewer 能用于商业项目吗？**  
A4: 可以，但您需要购买商业许可证。

**Q4: 能否自定义图像输出质量？**  
A5: 当然。您可以在 `JpgViewOptions` 和 `PngViewOptions` 中调整设置。

**Q5: 在哪里可以找到更高级的使用示例？**  
A5: 请访问 [API 参考](https://reference.groupdocs.com/viewer/java/) 获取详细文档。

## 常见问答

**Q: 如何在不丢失格式的情况下将 Numbers 文件转换为 PDF？**  
A: 如上所示使用 `PdfViewOptions`；Viewer 会自动保留布局、字体和单元格样式。

**Q: 能否一次调用将电子表格转换为图像？**  
A: 可以，`JpgViewOptions` 或 `PngViewOptions` 能在一步完成转换，并允许您指定分辨率和质量。

**Q: 是否可以批量处理多个 Numbers 文件？**  
A: 将 Viewer 逻辑放入循环中，为每个文件重新初始化 `Viewer`，并将每个输出写入不同的文件夹。

**Q: 每种输出格式都需要单独的许可证吗？**  
A: 不需要，单个 GroupDocs.Viewer 许可证涵盖所有支持的格式。

**Q: 这些功能需要哪个版本的 GroupDocs.Viewer？**  
A: 示例针对 25.2 版本，该版本完整支持 Numbers 到 PDF/HTML/图像的转换。

## 资源
- **文档：** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **API 参考：** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **下载：** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **购买许可证：** [Buy a License](https://purchase.groupdocs.com/buy)
- **免费试用：** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **临时许可证：** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **支持论坛：** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-03-05  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs