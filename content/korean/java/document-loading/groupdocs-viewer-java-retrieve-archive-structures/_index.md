---
date: '2026-02-05'
description: GroupDocs.Viewer를 사용하여 viewinfo를 가져오고 Java 아카이브 파일 유형 구조를 검색하는 방법을 배웁니다.
  이 가이드는 설정, 코드 예제 및 실제 사용 사례를 다룹니다.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Java에서 ViewInfo를 가져오고 아카이브 구조를 검색하는 방법
type: docs
url: /ko/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# How to Get ViewInfo and Retrieve Archive Structures in Java

Managing archive files effectively requires a clear understanding of their structure. In this tutorial you’ll learn **how to get viewinfo** for any archive and see how it helps you work with the **java archive file type**. We’ll walk through setting up GroupDocs.Viewer, extracting view information, and recursively reading folder hierarchies so you can integrate the solution into real projects.

![GroupDocs.Viewer for Java를 사용한 아카이브 구조](/viewer/document-loading/archive-structures-java.png)

**What You'll Learn**
- Setting up and configuring GroupDocs.Viewer for Java.  
- Methods to **get viewinfo** from archives.  
- Techniques to read and display the folder structure of an archive file.  
- Practical applications and performance considerations when using GroupDocs.Viewer in Java projects.

## Quick Answers
- **What does “viewinfo” provide?** It returns file type, page count, and archive folder listings.  
- **Which archives are supported?** ZIP, RAR, TAR, and other common formats.  
- **Do I need a license?** A free trial works for evaluation; a commercial license is required for production.  
- **Can I process large archives?** Yes – use streaming and proper memory handling as shown later.  
- **Is Maven required?** Maven is the recommended way to manage the GroupDocs.Viewer dependency.

## What is “how to get viewinfo”?
`getViewInfo` is a method in the GroupDocs.Viewer API that extracts metadata about a document or archive without rendering the full content. For archives, it reveals the internal folder tree, allowing you to decide which parts to render or process further.

## Why Retrieve Java Archive File Type Structures?
Understanding the internal layout of a **java archive file type** (e.g., ZIP, RAR) lets you:
- Quickly locate needed files without extracting everything.  
- Build automated pipelines that process only relevant sub‑folders.  
- Integrate archive navigation into content‑management or data‑ingestion systems.

## Prerequisites

- **Java Development Kit (JDK):** Version 8 or newer.  
- **Maven:** For dependency management and builds.  
- **Basic Java knowledge:** Familiarity with OOP concepts helps but isn’t mandatory.

You also need access to the GroupDocs.Viewer library, which you can add to your Maven project as shown below.

## Setting Up GroupDocs.Viewer for Java

### Maven Configuration

Add the repository and dependency to your `pom.xml`.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### License Acquisition

- **Free Trial:** Download a trial version from the GroupDocs website.  
- **Temporary License:** Request a temporary key for short‑term evaluation.  
- **Full License:** Purchase a commercial license for unlimited production use.

Once the library is on your classpath, you can start coding.

## Implementation Guide

### How to Get ViewInfo for Archive Files

This section shows the exact steps to call `getViewInfo` and read the folder hierarchy.

#### Initialize the Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Retrieve View Information

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Display Folder Structure

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Recursive Folder Reading

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Feature 2: Retrieve Archive Folder Structure

This feature focuses on printing the folder structure of an archive file. It’s similar to the first feature but emphasizes the recursive exploration.

#### Setup View Info Options

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Recursive Exploration

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Practical Applications

1. **Data Management:** Quickly organize large datasets by understanding archive structures.  
2. **Automated File Processing:** Batch‑process archived files without fully extracting them.  
3. **CMS Integration:** Enhance content‑management systems with on‑the‑fly archive navigation.

## Performance Considerations

- **Optimize Memory Usage:** Process folders one level at a time and close the `Viewer` instance promptly.  
- **Stay Updated:** Use the latest GroupDocs.Viewer version and JDK releases for performance gains.

## Common Issues and Solutions

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| `NullPointerException` when reading folders | `viewInfo.getFolders()` returns null for empty directories | Check for null or empty list before iterating. |
| Slow processing of huge ZIP files | Entire archive is loaded into memory | Use streaming options available in newer GroupDocs versions. |
| License not found | License file path is incorrect | Place the license file in the application root or set `License.setLicense("path/to/license.json")`. |

## Frequently Asked Questions

**Q: What is GroupDocs.Viewer?**  
A: It's a powerful Java library for rendering documents, including archives, into formats such as HTML, image, and PDF.

**Q: Can I use GroupDocs.Viewer with other programming languages?**  
A: Yes, GroupDocs offers SDKs for multiple platforms, but this tutorial focuses on the Java implementation.

**Q: How do I handle large archive files?**  
A: Use efficient memory management practices, and consider breaking down archives if necessary.

**Q: What types of archives does GroupDocs.Viewer support?**  
A: It supports a variety of formats including ZIP, RAR, TAR, among others.

**Q: Is there a limit on the size of archives I can process?**  
A: Limits depend on your system’s resources. Test with your target environment to determine practical limits.

**Q: Does “how to get viewinfo” work with password‑protected archives?**  
A: Yes, you can supply the password via `ArchiveOptions.setPassword("yourPassword")` before calling `getViewInfo`.

## Conclusion

By following this guide you now know **how to get viewinfo** for any supported archive and how to traverse its folder hierarchy using GroupDocs.Viewer for Java. These techniques empower you to build smarter data‑processing pipelines, improve CMS integrations, and handle large collections of archived files with confidence. Next, explore rendering individual files from the archive or converting them to PDF/HTML using other Viewer features.

---

**Last Updated:** 2026-02-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**
- **Documentation:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)