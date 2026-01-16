---
date: '2025-12-21'
description: 了解如何使用 GroupDocs.Viewer for Java 通过 PDF 渲染选项中的 java html 禁用 PDF 中的分组，以确保精确的文本表示。
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: 如何使用 GroupDocs.Viewer for Java 禁用 PDF 的分组
type: docs
url: /zh/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# 如何在 Java 的 GroupDocs.Viewer 中禁用 PDF 的分组

当您在渲染 PDF 时需要**禁用分组**，尤其是处理复杂脚本或古代语言时，精确的字符位置至关重要。默认的*字符分组*功能可能会错误地合并字符，导致内容被误解。在本指南中，我们将一步步演示如何使用 GroupDocs.Viewer for Java 禁用分组，以确保每个字形都恰好位于其应有的位置。

![使用 GroupDocs.Viewer for Java 的精确渲染技术](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 快速回答
- **“禁用分组”会有什么作用？** 它强制渲染器将每个字符视为独立元素，保留精确的布局。  
- **哪个 API 选项控制此行为？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **我需要许可证吗？** 试用版可用于测试，但生产环境需要完整许可证。  
- **我可以同时从 PDF 生成 Java HTML 吗？** 可以——使用 `HtmlViewOptions` 在禁用分组的同时生成 HTML 输出。  
- **此功能仅限于 PDF 吗？** 主要针对 PDF，但查看器支持许多其他格式。

## 介绍

在处理 PDF 文档时，渲染的精确性至关重要——尤其是面对象形文字或需要精确字符表现的语言时。“字符分组”功能常常会错误地将字符合并，导致文档内容被误读。这对需要精确复制文档文本布局的用户来说尤为棘手。

### 前置条件

在深入代码实现之前，请确保满足以下要求：
- **库和依赖**：需要 GroupDocs.Viewer for Java 版本 25.2 或更高。  
- **环境配置**：确保已安装 Java Development Kit (JDK)，并在 IDE 中配置好 Maven 项目。  
- **知识前提**：具备基本的 Java 编程了解，尤其是文件路径处理和使用外部库的经验。

## 如何在 PDF 渲染中禁用分组

### 设置 GroupDocs.Viewer for Java

#### 通过 Maven 安装

首先，将必要的库集成到项目中。在 `pom.xml` 中添加以下配置：

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

#### 许可证获取

要充分利用 GroupDocs.Viewer，建议获取许可证：
- **免费试用**：使用免费试用版测试功能。  
- **临时许可证**：如果需要更长时间的评估，可申请临时许可证。  
- **购买**：对于长期项目，建议购买正式许可证。

#### 基本初始化和设置

开始设置项目环境：

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### 实现指南

#### 功能：禁用字符分组

##### 步骤 1：定义输出目录

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**为什么？** 这可确保输出有序且易于访问。

##### 步骤 2：配置文件路径格式

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**为什么？** 有助于系统化地组织 PDF 文档的各页。

##### 步骤 3：初始化 HTML 视图选项

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**为什么？** 嵌入的资源确保每个页面的 HTML 文件中包含所有必需的资产。

##### 步骤 4：禁用字符分组

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**为什么？** 这可确保字符单独渲染，保留其预期的布局和含义。

##### 步骤 5：渲染文档

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**为什么？** 这可确保所有资源得到适当关闭，防止内存泄漏。

### 从 PDF 生成不分组的 Java HTML

`HtmlViewOptions` 类允许您在保持每个字符独立的同时生成**java html from pdf**。当需要将渲染后的页面嵌入到门户网站或电子学习平台，并且字形位置必须精确时，这特别有用。

### 故障排除提示

- 确保文档路径正确，以避免 `FileNotFoundException`。  
- 检查输出目录是否具有写入权限。  
- 再次确认使用的 GroupDocs.Viewer for Java 版本兼容。

## 实际应用

1. **语言保存**：适用于中文、日文或古代文字等对字符精度要求高的文档渲染。  
2. **法律与金融文档**：确保在合规性要求严格的文档中实现精确的文本表现。  
3. **教育资源**：非常适合包含复杂图表或批注的教材和学术论文。

## 性能考虑

- **优化资源使用**：确保服务器具备足够资源以处理大型 PDF 文件。  
- **Java 内存管理**：使用高效的数据结构和垃圾回收实践来有效管理内存。  
- **批量处理**：在渲染多个文档时，采用批量方式以提升吞吐量。

## 结论

您现在已经掌握了在使用 GroupDocs.Viewer for Java 进行 PDF 渲染时**禁用分组**的技巧。这一能力对需要精确文本表现的应用至关重要。接下来，可尝试将此功能与其他文档管理系统集成，或探索更多渲染选项以优化大规模部署的性能。

## 常见问题

**Q:** *为什么需要禁用字符分组？*  
**A:** 禁用分组可防止渲染器合并属于不同字形的字符，这对间距和顺序传递意义的脚本尤为关键。

**Q:** *`setDisableCharsGrouping` 设置仅适用于 HTML 输出吗？*  
**A:** 不是，它影响底层的 PDF 渲染引擎，因此任何输出格式（HTML、PNG 等）都会反映此更改。

**Q:** *我可以将此设置与自定义字体一起使用吗？*  
**A:** 可以——在初始化 `Viewer` 之前加载自定义字体，分组规则仍然适用。

**Q:** *禁用分组会影响性能吗？*  
**A:** 会有轻微影响，因为引擎需要逐字符处理，但对大多数文档的影响微乎其微。

**Q:** *是否可以在每页单独切换分组？*  
**A:** 目前该选项在 `PdfOptions` 实例层面是全局的；若需对不同页使用不同设置，需要为每页创建独立的 `Viewer` 实例。

## 资源

- [GroupDocs 文档](https://docs.groupdocs.com/viewer/java/)  
- [API 参考](https://reference.groupdocs.com/viewer/java/)  
- [下载 GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)  
- [购买许可证](https://purchase.groupdocs.com/buy)  
- [免费试用版](https://releases.groupdocs.com/viewer/java/)  
- [临时许可证申请](https://purchase.groupdocs.com/temporary-license/)  
- [GroupDocs 支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2025-12-21  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs