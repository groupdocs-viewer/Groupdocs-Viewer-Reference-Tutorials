---
date: '2026-02-02'
description: 学习如何在 Java 应用程序中使用 Java 文件输出流和强大的 GroupDocs.Viewer API 高效检索并保存文档附件。
keywords:
- GroupDocs.Viewer Java
- retrieve document attachments Java
- save document attachments GroupDocs
title: 如何使用 Java 文件输出流和 GroupDocs.Viewer for Java 检索并保存文档附件
type: docs
url: /zh/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# 如何使用 java file output stream 与 GroupDocs.Viewer for Java 检索并保存文档附件 output高效，可轻松检索并保存文档附件。

![Retrieve and Save Document Attachments with GroupDocs.Viewer for Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

在本教程中，我们将探讨如何利用 GroupDocs.Viewer 的强大功能，从文档中检索附件并将其保存到指定目录。通过本教程，您将获得在 Java 环境中高效管理文档数据的实战技能。

## 快速答案
- **java file output stream 是做什么的？** 它直接将字节流写入文件，使二进制数据（如附件）能够保存到磁盘。  
- **哪个 API 用于检索附件？** `Viewer.getAttachments()` 返回附件元数据列表。  
- **可以指定输出文件夹吗？** 可以——使用 `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`。  
- **需要许可证吗？** 免费试用可用于评估；生产环境需要付费许可证。  
- **此方法线程安全吗？** 为每个线程创建单独的 `Viewer` 实例或对访问进行同步。

## 什么是 java file output stream？
`java.io.FileOutputStream` 是 Java 核心类，用于将原始字节写入文件。当您需要持久化二进制内容（如电子邮件附件、图像或从文档中提取的任何非文本数据）时，它是理想选择。

## 为什么在 GroupDocs.Viewer 中使用 java file output stream？
- **直接二进制处理** – 无需中间转换，附件字节会原样写入源文件。  
- **性能** – 流式写入可最小化内存开销，尤其是处理大附件时。  
- **简洁性** – API 与标准 Java I/O 无缝集成，使代码易于阅读和维护。

## 前置条件
- **必需的库和依赖**：将 GroupDocs.Viewer 库添加到项目中（见下方 Maven 代码片段）。  
- **环境设置**：已安装 JDK 8+ 的 Java IDE（IntelliJ IDEA、Eclipse 等）。  
- **知识前置**：熟悉 Java I/O，特别是 `FileOutputStream`，以及基本的 Maven 用法。

## 为 Java 项目设置 GroupDocs.Viewer
要在项目中使用 GroupDocs.Viewer API，需通过 Maven 安装。将以下配置添加到 `pom.xml` 文件中：

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

**获取许可证的步骤：**
- **免费试用**：先使用免费试用探索功能。  
- **临时许可证**：获取临时许可证以延长评估期。  
- **购买**：生产环境需要购买许可证。

### 基本初始化和设置
将 GroupDocs.Viewer 添加为项目依赖后，在 Java 应用中进行初始化。示例代码如下：

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

此基础设置会初始化 GroupDocs.Viewer，并为检索附件做好准备。

## 实现指南

### 使用 java file output索附件。该功能可提取。

#### 概述
检索附件涉及调用 `getAttachments` 方法，该方法返回包含文件名、大小等信息的 `Attachment` 对象列表。

#### 实现步骤
1. **创建 Viewer 实例**  
   使用文档路径初始化 `Viewer` 类：

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **检索附件**  
   调用 `getAttachments` 方法：

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **参数和方法说明**  
   - `Viewer`：接受文档的文件路径或流。  
   - `getAttachments()`：获取附件文件列表，并提供名称等详细信息。

### 将文档附件保存到目录
了解如何检索附件后，接下来使用 GroupDocs.Viewer API 和 **java file output stream** 将其保存到指定目录。

#### 概述
此功能将每个检索到的附件文件保存到预定义的输出目录。

#### 实现步骤
1. **定义输出目录**  
   设置 `outputDirectory` 路径以保存文件：

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **保存附件**  
   使用循环调用 `saveAttachment` 方法保存每个附件：

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **参数和方法说明**  
   - `saveAttachment`：接受 `Attachment` 对象和文件输出流，以保存附件。  
   - `FileOutputStream`：使用 **java file output stream** 语义管理向文件写入数据。

### 故障排除提示
- **缺少依赖**：确保已正确添加所有 Maven 依赖。  
- **文件路径错误**：仔细检查文档和输出目录的路径。  
- **访问权限**：确认应用拥有必要的读写权限。

## 实际应用场景
在 Java 中使用 GroupDocs.Viewer 可在多种情境下发挥重要价值：

1. **邮件客户端** – 自动从邮件存档中提取附件进行处理或归档。  
2. **文档管理系统 (DMS)** – 通过检索并组织附件文件提升 DMS 功能。  
3. **法务部门** – 安全提取法律文档中的证据相关附件。

与 CRM、ERP 或自定义工作流引擎的集成可进一步简化业务流程，实现跨部门的附件处理无缝衔接。

## 性能考虑
使用 GroupDocs.Viewer 时的性能优化建议：

- **优化文件处理** – 对大文件使用缓冲流，并及时关闭资源。  
- **内存管理** – 及时释放 `Viewer` 实例（使用 try‑with‑resources），循 Java 最佳实践将显著提升附件处理流水线的效率。

## 结论
现在，您已经了解如何使用 **java file output stream** 与 GroupDocs.Viewer for Java 检索并保存。

欲进一步探索 GroupDocs提取。如有疑问或在我的 Java 项目中安装 GroupDocs.Viewer？**  
答：添加前文示例的 Maven 依赖；仓库 URL 与版本号即可快速开始。

**问：GroupDocs.Viewer 能处理所有文档类型吗？**  
答：它支持多种格式（PDF、DOCX、MSG 等），出现输出路径正确、目录已存在且进程拥有写入权限。同时确保如示例所示正确使用 `FileOutputStream`。

**问：生产环境是否需要许可证？**  
答：是的，生产部署必须使用有效的 GroupDocs.Viewer 许可证。可先使用免费试用进行评估。

**问：此方法能处理 stream` 可高效在需要时分块流式写入。

  
**作者：** GroupDocs  

---