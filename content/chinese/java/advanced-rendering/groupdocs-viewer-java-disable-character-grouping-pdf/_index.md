---
date: '2026-03-22'
description: 了解如何使用 GroupDocs Viewer for Java 将 PDF 生成 HTML，并禁用字符分组，以实现精确的文本呈现。
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: 从 PDF 生成 HTML 并禁用分组 – GroupDocs Java
type: docs
url: /zh/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# 从 PDF 生成 HTML 并禁用分组 - 使用 GroupDocs Viewer for Java

在许多项目中，你需要 **从 PDF 生成 HTML**，同时保持每个字形恰好位于其应有的位置。这在复杂脚本、古代语言或法律文档中尤为重要，因为一个字符位置的错误可能会改变含义。在本教程中，我们将完整演示如何使用 GroupDocs Viewer for Java 将 PDF 渲染为 HTML，并展示 **如何禁用分组**，使每个字符都被视为独立的元素。

![精确渲染技术与 GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 快速回答
- **“禁用分组”会做什么？** 它强制渲染器将每个字符视为独立元素，保留精确布局。  
- **哪个 API 选项控制此行为？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **我需要许可证吗？** 试用版可用于测试，但生产环境需要完整许可证。  
- **我可以同时从 PDF 生成 HTML 吗？** 可以——使用 `HtmlViewOptions` 在禁用分组的同时生成 HTML 输出。  
- **此功能仅限于 PDF 吗？** 主要针对 PDF，但 Viewer 支持许多其他格式。

## 介绍

在处理 PDF 文档时，渲染的精确度至关重要——尤其是面对象形文字或需要精确字符呈现的语言时。“字符分组”功能常常会错误地将字符合并，导致文档内容被误读。这对需要精确复制文档文本布局的用户来说尤为棘手。

### 前置条件

在编写代码实现之前，请确保满足以下要求：
- **库与依赖**：需要 GroupDocs.Viewer for Java 版本 25.2 或更高。  
- **环境配置**：确保已安装 Java Development Kit (JDK)，并在 IDE 中配置好 Maven 项目。  
- **知识前提**：具备基本的 Java 编程理解，尤其是文件路径处理和使用外部库的经验。

## 如何使用 GroupDocs Viewer 从 PDF 生成 HTML

从 PDF 生成 HTML 是一个两步过程：配置 Viewer，然后渲染文档。关键是在渲染前关闭字符分组，以便 HTML 输出逐字符地镜像原始 PDF 布局。

### 设置 GroupDocs.Viewer for Java

#### 通过 Maven 安装

首先，将所需库集成到项目中。 在你的 `pom.xml` 中添加以下配置：

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

要充分利用 GroupDocs.Viewer，请考虑获取许可证：
- **免费试用**：使用免费试用版测试功能。  
- **临时许可证**：如果需要更长时间的评估，可申请临时许可证。  
- **购买**：对于长期项目，建议购买正式许可证。

#### 基本初始化与设置

下面是一个可直接运行的代码片段，展示了完整工作流——从设置输出文件夹到在禁用字符分组的情况下将 PDF 渲染为 HTML：

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

下面我们逐行拆解示例代码，帮助你理解 **为什么** 要这么做以及 **如何** 通过它实现从 PDF 生成 HTML 而不出现不期望的字符合并。

##### 步骤 1：定义输出目录  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**为什么？** 这确保渲染后的 HTML 文件存放在专用文件夹中，便于后续查找和管理。

##### 步骤 2：配置文件路径格式  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**为什么？** 使用占位符 (`{0}`) 让 Viewer 为每个 PDF 页面创建单独的 HTML 文件，保持输出结构化。

##### 步骤 3：初始化 HTML 视图选项  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**为什么？** 将资源（图片、字体、CSS）直接嵌入每个 HTML 页面，适合基于网页的查看器或在线学习平台。

##### 步骤 4：禁用字符分组  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**为什么？** 这行代码是关键，它告诉渲染引擎 **不要** 合并相邻字符，确保生成的 HTML 与源 PDF 中的字形位置完全一致。

##### 步骤 5：渲染文档  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**为什么？** 将 `Viewer` 放在 try‑with‑resources 块中，可自动释放所有本机资源，防止长时间运行的应用出现内存泄漏。

### 在不进行分组的情况下生成 Java HTML（从 PDF）

`HtmlViewOptions` 类允许你 **从 PDF 生成 HTML**，同时保持每个字符独立。这在需要将渲染页面嵌入网页门户或在线学习平台、且对字形位置要求极高的场景中尤为实用。

### 常见问题与解决方案

- **FileNotFoundException** – 再次检查传递给 `new Viewer(...)` 的路径。建议使用绝对路径或 `Path.of(...)` 来提升可读性。  
- **写入权限** – 确保输出目录对 Java 进程可写；在 Linux 上可能需要调整文件夹权限（`chmod 775`）。  
- **版本不匹配** – `setDisableCharsGrouping` 选项自 25.2 版本起可用。请确认 `pom.xml` 中使用了正确的版本号。  

### 实际应用场景

1. **语言保护** – 适用于中文、日文、阿拉伯文或古代文字等字符间距承载意义的文档。  
2. **法律与金融文档** – 为合规性要求高的文件提供精确的文本复制。  
3. **教育资源** – 完美支持包含复杂图表、批注或多语言内容的教材。

### 性能考量

- **优化资源使用** – 大型 PDF 可能占用大量内存。建议分批处理页面并及时释放 `Viewer` 实例。  
- **Java 内存管理** – 如需处理数百页的 PDF，可调大 JVM 堆内存（如 `-Xmx2g` 或更高）。  
- **并行渲染** – 对于批量转换，可为每个线程创建独立的 `Viewer` 实例，以利用多核 CPU。

## 常见问答

**问：** *为什么需要禁用字符分组？*  
**答：** 禁用分组可防止渲染器将本应独立的字形合并，对于字符间距和顺序承载意义的脚本尤为关键。

**问：** *`setDisableCharsGrouping` 设置仅适用于 HTML 输出吗？*  
**答：** 不是，它影响底层 PDF 渲染引擎，任何输出格式（HTML、PNG、JPEG 等）都会体现此更改。

**问：** *我可以将此设置与自定义字体一起使用吗？*  
**答：** 可以——在初始化 `Viewer` 前加载自定义字体，分组规则仍然有效。

**问：** *禁用分组会影响性能吗？*  
**答：** 会略有增加，因为引擎需要逐字符处理，但对大多数文档的影响微乎其微。

**问：** *是否可以在每页单独切换分组？*  
**答：** 目前该选项在 `PdfOptions` 实例层面全局生效；若需混合行为，需要为不同页面创建独立的 `Viewer` 实例。

## 资源

- [GroupDocs 文档](https://docs.groupdocs.com/viewer/java/)
- [API 参考](https://reference.groupdocs.com/viewer/java/)
- [下载 GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [购买许可证](https://purchase.groupdocs.com/buy)
- [免费试用版](https://releases.groupdocs.com/viewer/java/)
- [临时许可证申请](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-03-22  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs