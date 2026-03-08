---
date: '2026-03-08'
description: 了解如何获取临时许可证，使用本地文件或 URL 设置 GroupDocs.Viewer for Java，并验证许可证路径的可用性。
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: 如何获取临时许可证并在 GroupDocs.Viewer Java 中设置许可证
type: docs
url: /zh/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

 Should translate.

Ok.

Now produce final content.

# 如何获取临时许可证并在 GroupDocs.Viewer Java 中设置许可证

在将第三方库（如 **GroupDocs.Viewer for Java**）集成到您的应用程序时，高效管理许可证至关重要。本指南将向您展示 **如何获取临时许可证**、如何从本地文件或 HTTP URL 设置许可证，以及如何验证许可证路径是否正确。完成本教程后，您将拥有可靠、可用于生产环境的许可证配置，使您的应用保持合规并保持高性能。

![文件和 URL 设置（适用于 GroupDocs.Viewer for Java）](/viewer/getting-started/file-and-url-setup-png.png)

## 快速答案
- **如何获取临时许可证？** 在 GroupDocs 临时许可证页面请求并下载 *.lic* 文件。  
- **可以从 URL 加载许可证吗？** 可以——只需将 `License.setLicense` 指向返回有效许可证文件的 HTTP 地址。  
- **如果许可证路径缺失会怎样？** 实现检查以显示指导信息并阻止查看器启动。  
- **更改许可证后需要重启应用吗？** 不需要，`License.setLicense` 可以在运行时调用。  
- **需要哪个 Java 版本？** 建议使用 JDK 8 或更高版本。

## 什么是临时许可证？
**临时许可证** 是 GroupDocs 发放的限时密钥，允许您在不购买正式许可证的情况下评估产品。它在有效期内的行为与永久许可证完全相同，您可以在真实环境中测试所有功能。

## 为什么要获取临时许可证？
- **快速评估：** 立即获得完整功能，适用于概念验证项目。  
- **无财务承诺：** 先测试后购买。  
- **易于集成：** 与永久许可证使用相同的 API 调用。

## 前置条件
1. **Java Development Kit (JDK)：** 8 版或更高。  
2. **IDE：** IntelliJ IDEA、Eclipse 或任何支持 Java 的 IDE。  
3. **GroupDocs.Viewer for Java 库：** 已添加到项目中（请参阅下方 Maven 配置）。  
4. **基础 Java 知识：** 熟悉类、导入和异常处理。

## 设置 GroupDocs.Viewer for Java
首先，在 Maven 项目中引入库。

### Maven 配置
在 `pom.xml` 文件中添加以下配置：
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
使用 GroupDocs.Viewer 前，需要获取许可证：
- **免费试用：** 从 [GroupDocs site](https://releases.groupdocs.com/viewer/java/) 下载。  
- **临时许可证：** 在 [temporary-license page](https://purchase.groupdocs.com/temporary-license/) 申请。  
- **购买正式许可证：** 请访问 [GroupDocs purchase page](https://purchase.groupdocs.com/buy) 进行购买。

### 基本初始化
库添加完成后，即可初始化查看器：
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## 如何获取临时许可证并从文件设置
### 概述
从本地文件设置许可证是最直接的方式，即使在离线环境下也能正常工作。

### 实现步骤
1. **定义许可证路径** – 指向您在申请临时许可证后收到的 *.lic* 文件：
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **应用许可证** – 使用 `License` 类加载它：
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**提示：**  
- 确认文件路径是绝对路径或相对于工作目录的相对路径。  
- 确保运行 JVM 的用户对该文件拥有读取权限。

## 如何处理许可证 URL
### 概述
基于 URL 的许可证适用于云部署场景，许可证文件存放在安全的存储桶中。

### 实现步骤
1. **定义许可证 URL** – 将占位符替换为实际的端点地址：
```java
final String licensePath = "http://example.com/license.lic";
```
2. **检测并记录 URL 使用情况** – 以下示例仅在提供了 URL 时进行提示：
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**提示：**  
- 在生产环境中，您应下载文件（例如使用 `java.net.HttpURLConnection`），然后调用 `license.setLicense(stream)`。  
- 添加重试逻辑和超时处理，以应对瞬时网络问题。

## 如何检查许可证可用性（验证许可证路径）
### 概述
在尝试加载许可证之前，**检查许可证可用性** 是良好实践，这样可以在需要时引导开发者或用户获取临时许可证。

### 实现步骤
1. **模拟缺失的许可证路径**：
```java
final String licensePath = null;
```
2. **在路径不存在时提供明确指引**：
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**提示：**  
- 在启动时记录此信息，便于运维团队发现许可证缺失。  
- 考虑在未提供有效许可证前退出应用或禁用查看器功能。

## 实际应用场景
掌握 **获取临时许可证**、**从文件或 URL 设置许可证** 以及 **验证许可证路径** 的方法，可帮助您应对多种真实业务需求：
1. **文档管理系统** – 嵌入查看器并在每次启动时自动验证许可证。  
2. **云 SaaS 平台** – 将许可证存放在受保护的 Blob 存储中，通过 URL 加载，实现零停机更新。  
3. **企业部署** – 在试点阶段使用临时许可证，随后再购买全量许可证。

## 性能考虑
- **资源使用：** 在应用启动时加载一次许可证；重复调用会产生不必要的 I/O。  
- **内存管理：** `License` 对象占用的状态极少，但如果手动下载许可证，请务必在使用后关闭流。

## 结论
按照上述步骤，您可以 **获取临时许可证**、使用本地文件或 HTTP URL 配置 GroupDocs.Viewer for Java，并 **检查许可证可用性**，从而保持应用合规。稳固的许可证管理基础可防止运行时错误，并为在开发、测试和生产环境之间切换提供信心。

### 常见问题

1. **如何在 GroupDocs.Viewer Java 中设置本地许可证文件？**  

   使用 `license.setLicense("path/to/license.lic")` 并提供正确的文件路径即可应用本地许可证。

2. **可以直接从 URL 加载许可证吗？**  

   可以，但请确保代码能够处理 URL 访问，必要时在运行时下载许可证或处理网络异常。

3. **如果许可证路径无效或缺失该怎么办？**  

   实现对 null 或无效路径的检查，并提供指引或回退提示，以获取有效许可证。

4. **是否可以在运行时动态切换文件和 URL 两种许可证方式？**  

   完全可以，通过条件逻辑根据环境或运行时参数选择相应的加载方式。

5. **生产环境中许可证管理的最佳实践是什么？**  

   安全存储许可证，定期验证其有效性，并实现错误处理以确保服务不中断。

## Frequently Asked Questions

**Q: 临时许可证的有效期是多长？**  
A: 通常为 30 天，期满后您可以请求续期或升级为永久许可证。

**Q: 使用基于文件的许可证是否需要网络连接？**  
A: 不需要。一次加载本地 *.lic* 文件后即可完全离线使用。

**Q: 可以对许可证文件进行加密以提升安全性吗？**  
A: 许可证文件已经由 GroupDocs 签名；额外加密是可选的，但并非必须。

**Q: 如果许可证在应用运行期间过期会怎样？**  
A: 查看器操作将抛出许可证异常；建议在启动时检查过期时间并提前处理。

**Q: 将许可证 URL 存在源码库中是否安全？**  
A: 不建议将敏感 URL 提交到代码库；请使用环境变量或安全配置存储来管理。

---

**最后更新：** 2026-03-08  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs