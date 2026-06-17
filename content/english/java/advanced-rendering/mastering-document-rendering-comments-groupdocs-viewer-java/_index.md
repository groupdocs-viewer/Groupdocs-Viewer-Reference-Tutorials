---
title: "GroupDocs Viewer Java Tutorial - Convert Word to HTML and Render Documents with Comments"
linktitle: "GroupDocs Viewer Java Tutorial"
description: "Learn how to convert Word to HTML and render documents with comments using GroupDocs Viewer for Java. Step‑by‑step guide, troubleshooting, and best practices."
keywords:
  - convert word to html
  - increase jvm heap
  - groupdocs viewer java
  - how to render comments
  - render document comments
weight: 1
url: /java/advanced-rendering/mastering-document-rendering-comments-groupdocs-viewer-java/
date: "2026-05-21"
lastmod: "2026-05-21"
categories: ["Java Development"]
tags: ["groupdocs-viewer", "java-tutorial", "document-rendering", "html-conversion"]
type: docs
schemas:
- type: TechArticle
  headline: GroupDocs Viewer Java Tutorial - Convert Word to HTML and Render Documents
    with Comments
  description: Learn how to convert Word to HTML and render documents with comments
    using GroupDocs Viewer for Java. Step‑by‑step guide, troubleshooting, and best
    practices.
  dateModified: '2026-05-21'
  author: GroupDocs
- type: HowTo
  name: GroupDocs Viewer Java Tutorial - Convert Word to HTML and Render Documents
    with Comments
  description: Learn how to convert Word to HTML and render documents with comments
    using GroupDocs Viewer for Java. Step‑by‑step guide, troubleshooting, and best
    practices.
  steps:
  - name: Verify Java Installation
    text: 'Open a terminal and run: You should see a version string beginning with
      `1.8` or higher. If not, download the latest JDK from the official Oracle or
      OpenJDK website.'
  - name: Check Maven Installation
    text: 'Run: Maven should report its version and the Java version it uses. Install
      Maven from the Apache website if the command is not recognised.'
  - name: Create a New Maven Project
    text: 'Generate a skeleton project with: Navigate into the newly created `viewer-demo`
      folder and you’re ready to add GroupDocs Viewer.'
  - name: Set Up Your File Paths
    text: 'Organise your input and output locations early to avoid path‑related errors:
      **Why This Approach:** - Uses modern Java NIO.2 `Path` API, which is more reliable
      than `java.io.File`. - Descriptive variable names make debugging easier. - The
      `{0}` placeholder in the output pattern is automatically repl'
  - name: Configure HTML Rendering Options
    text: 'This is where the magic happens. We tell GroupDocs exactly how we want
      the document rendered: `HtmlViewOptions` configures how the document is rendered
      to HTML, including resource handling and comment rendering. **Key Configuration
      Details:** - `forEmbeddedResources()` embeds CSS, images, and fonts '
  - name: Execute the Rendering
    text: 'Now we bring everything together: `Viewer` is the primary class used to
      load a document and perform rendering operations. The `view` call reads the
      Word file, extracts comments, generates HTML pages, and writes them to `output/html`.
      Each page is saved as `page_1.html`, `page_2.html`, etc.'
- type: FAQPage
  questions:
  - question: Can I render documents without comments?
    answer: Yes—simply omit the `setRenderComments(true)` call or set it to `false`.
  - question: What file formats support comment rendering?
    answer: Most major formats—including DOC/DOCX, XLS/XLSX, PPT/PPTX, PDF, and many
      more. See the [official documentation](https://docs.groupdocs.com/viewer/java/)
      for the full list.
  - question: Can I customize the HTML output styling?
    answer: Absolutely. Use `HtmlViewOptions.setEmbedResources(false)` to generate
      external CSS files, then add your own stylesheet after rendering.
  - question: How do I handle password‑protected documents?
    answer: 'Provide a `LoadOptions` instance with the password:'
  - question: Is it possible to render only specific pages?
    answer: 'Yes—use the overloaded `view` method that accepts a `PageNumber` collection:'
---

# GroupDocs Viewer Java Tutorial: Convert Word to HTML and Render Documents with Comments

## Introduction

If you need to **convert Word to HTML** while keeping every reviewer’s note, comment, or annotation, you’ve landed in the right place. Many Java developers hit a wall when document conversion strips out the valuable feedback embedded in the original file. This tutorial walks you through using GroupDocs Viewer for Java to **convert Word to HTML** and render a wide range of document types—Word, Excel, PowerPoint, PDF, and more—without losing any comment data.

You’ll discover why GroupDocs Viewer is a production‑ready choice, how to set up the environment, the exact code you need, and proven tricks to keep performance snappy even with large files.

![Render Documents with Comments with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-documents-with-comments.png)

[Render Documents with Comments with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-documents-with-comments.png)

**What you’ll master in this tutorial:**
- Complete GroupDocs Viewer setup and configuration
- Step‑by‑step **convert Word to HTML** with comments preserved
- Common troubleshooting solutions and gotchas to avoid
- Real‑world implementation patterns and best practices
- Performance optimisation techniques for production use

## Quick Answers
- **Can GroupDocs Viewer convert Word to HTML?** Yes—enable HTML rendering and comment support in a single line of code.  
- **Do comments stay in the HTML output?** Absolutely—`setRenderComments(true)` preserves every comment and annotation.  
- **What Java version is required?** JDK 8 or higher.  
- **Is a license needed for production?** A full license removes watermarks and unlocks all features.  
- **How to improve rendering speed?** Render specific pages, use external resources, and increase JVM heap size.

## What is “convert word to html” with comments?
*“Convert Word to HTML”* means transforming a Microsoft Word *.docx* file into a web‑ready HTML document while retaining the original layout, styling, and any embedded comments. This process enables browsers to display the document exactly as authors intended, complete with reviewer feedback.

## Why Choose GroupDocs Viewer for Java?

Before we dive into code, let’s explore why GroupDocs Viewer is the go‑to library for Java‑based document rendering:

- **170+ supported formats** – the library handles everything from DOCX to CAD files, giving you a single dependency for all your conversion needs.  
- **No third‑party Office installation** – it works on any OS without needing Microsoft Office, LibreOffice, or other heavy runtimes.  
- **Preserves formatting and annotations** – comments, footnotes, and track changes survive the conversion intact.  
- **Fast, lightweight engine** – typical 100‑page documents render in under 2 seconds on a standard 4‑core server.  
- **Robust documentation and active community** – you’ll find examples, forums, and quick support whenever you hit a snag.

### When to Use This Approach
- Building web‑based document viewers that need to show reviewer notes  
- Creating collaborative review platforms where feedback must stay visible  
- Converting legacy contracts for online display in legal portals  
- Developing e‑learning solutions that embed instructor comments in study material  

## Prerequisites and Environment Setup

### What You’ll Need
- **Java Development Kit (JDK) 8+** – the runtime that powers your application.  
- **Maven 3.6+** – for dependency management and building the project.  
- **IDE of your choice** – IntelliJ IDEA, Eclipse, or VS Code.  
- **Sample documents with comments** – DOCX, XLSX, PPTX files that contain reviewer notes.  

### Setting Up Your Development Environment

#### Step 1: Verify Java Installation
Open a terminal and run:

```
java -version
```

You should see a version string beginning with `1.8` or higher. If not, download the latest JDK from the official Oracle or OpenJDK website.

#### Step 2: Check Maven Installation
Run:

```
mvn -v
```

Maven should report its version and the Java version it uses. Install Maven from the Apache website if the command is not recognised.

#### Step 3: Create a New Maven Project
Generate a skeleton project with:

```
mvn archetype:generate -DgroupId=com.example.viewer -DartifactId=viewer-demo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

Navigate into the newly created `viewer-demo` folder and you’re ready to add GroupDocs Viewer.

## Setting Up GroupDocs.Viewer for Java

### Adding the Dependency
The first step in any GroupDocs Viewer Java tutorial is getting the library into your project. Add this configuration to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

**Pro Tip:** Always check the [GroupDocs releases page](https://releases.groupdocs.com/viewer/java/) for the latest version. The library is actively maintained with regular updates and bug fixes.

### Understanding Licensing Options
GroupDocs offers flexible licensing that fits different project needs:

- **Free Trial (Perfect for Learning):** 30‑day evaluation with full feature access and evaluation watermarks.  
- **Temporary License (For Development):** Extended evaluation without watermarks; ideal for proof‑of‑concept projects. Request at [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Full License (Production Ready):** No limitations or watermarks, commercial use permitted. Available at [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Basic Initialization Pattern
Here’s the fundamental pattern you’ll use throughout this tutorial:

```java
try (Viewer viewer = new Viewer("input.docx")) {
    // Rendering options will be set later
}
```

**Why This Pattern Works:**  
- **Automatic resource management** prevents memory leaks.  
- **Exception handling** catches common file‑access issues.  
- **Clean, readable code** that’s easy to maintain across large projects.

## Core Implementation: Rendering Documents with Comments

### Understanding the Process
When you render a document with GroupDocs Viewer, the library performs four key steps:

1. **Document Analysis** – parses the input file and builds an internal representation.  
2. **Comment Extraction** – identifies every comment, footnote, and annotation.  
3. **HTML Generation** – creates clean, standards‑compliant HTML that mirrors the original layout.  
4. **Resource Handling** – bundles images, CSS, and fonts either inline or as external files.

### Step‑by‑Step Implementation

#### Step 1: Set Up Your File Paths
Organise your input and output locations early to avoid path‑related errors:

```java
Path inputPath = Paths.get("documents/sample-with-comments.docx");
Path outputDir = Paths.get("output/html");
Files.createDirectories(outputDir);
```

**Why This Approach:**  
- Uses modern Java NIO.2 `Path` API, which is more reliable than `java.io.File`.  
- Descriptive variable names make debugging easier.  
- The `{0}` placeholder in the output pattern is automatically replaced with page numbers.

#### Step 2: Configure HTML Rendering Options
This is where the magic happens. We tell GroupDocs exactly how we want the document rendered:

`HtmlViewOptions` configures how the document is rendered to HTML, including resource handling and comment rendering.

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(outputDir);
viewOptions.setRenderComments(true);   // Preserve every comment
viewOptions.setPageNumberPrefix("page_");
```

**Key Configuration Details:**  
- `forEmbeddedResources()` embeds CSS, images, and fonts directly into the HTML, making the output portable.  
- `setRenderComments(true)` is the single line that ensures **convert word to html** retains all reviewer notes.  
- Alternative `forExternalResources()` lets you store assets separately if you prefer a slimmer HTML file.

#### Step 3: Execute the Rendering
Now we bring everything together:

`Viewer` is the primary class used to load a document and perform rendering operations.

```java
try (Viewer viewer = new Viewer(inputPath.toFile())) {
    viewer.view(viewOptions);
}
```

The `view` call reads the Word file, extracts comments, generates HTML pages, and writes them to `output/html`. Each page is saved as `page_1.html`, `page_2.html`, etc.

### Complete Working Example
Putting all pieces together gives you a single, runnable class that converts a Word document to HTML while keeping comments intact. (The full source code is available in the official GitHub repository.)

## Advanced Configuration and Options

### Setting Up Dynamic Output Directories
For larger applications you may want to generate output directories based on user IDs or timestamps:

```java
String userId = "12345";
Path dynamicOutput = Paths.get("output", userId, LocalDate.now().toString());
Files.createDirectories(dynamicOutput);
HtmlViewOptions dynamicOptions = HtmlViewOptions.forEmbeddedResources(dynamicOutput);
```

### Common Issues and Troubleshooting

#### Issue 1: “File Not Found” Errors
Make sure the input path is absolute or relative to the working directory, and verify file permissions. Using `Path` objects helps avoid common string‑concatenation mistakes.

#### Issue 2: Comments Not Appearing in Output
Double‑check that `setRenderComments(true)` is called **before** `viewer.view()`. Also ensure the source document actually contains comments; you can inspect them via `viewer.getDocumentInfo().getComments()`.

#### Issue 3: Out of Memory Errors with Large Documents
GroupDocs Viewer streams data, but extremely large files (> 500 pages) may still strain the JVM heap. Increase heap size with `-Xmx4g` or render only needed pages.

#### Issue 4: Slow Rendering Performance
Render specific page ranges using `viewer.view(pageRange, viewOptions)`. External resources (`forExternalResources()`) also reduce HTML payload size, speeding up browser rendering.

## Real‑World Implementation Patterns

### Pattern 1: Web Application Integration
Integrate the rendering logic into a Spring Boot controller to serve HTML on demand:

```java
@RestController
@RequestMapping("/api/view")
public class DocumentController {

    @GetMapping("/{id}")
    public ResponseEntity<Resource> renderDocument(@PathVariable String id) throws IOException {
        Path docPath = Paths.get("documents", id + ".docx");
        Path outDir = Files.createTempDirectory("viewer");
        HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(outDir);
        options.setRenderComments(true);
        try (Viewer viewer = new Viewer(docPath.toFile())) {
            viewer.view(options);
        }
        // Return the first HTML page as a Resource
        Path firstPage = outDir.resolve("page_1.html");
        Resource resource = new UrlResource(firstPage.toUri());
        return ResponseEntity.ok()
                .contentType(MediaType.TEXT_HTML)
                .body(resource);
    }
}
```

### Pattern 2: Batch Processing Multiple Documents
When you need to convert a whole folder of Word files, loop through the directory and reuse the same `HtmlViewOptions` instance to minimise object creation overhead.

## Performance Optimization and Best Practices

### Memory Management Tips
- **Always use try‑with‑resources** for `Viewer` instances.  
- **Process large documents in batches** rather than loading everything into memory at once.  
- **Monitor JVM heap usage** with tools like VisualVM and adjust `-Xmx` as needed.  
- **Implement proper caching** for frequently accessed documents to avoid repeated rendering.

### Resource Usage Guidelines

**For Small Applications (< 100 documents/day):**
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(Paths.get("output"));
options.setRenderComments(true);
```

**For High‑Volume Applications (1000+ documents/day):**
```java
HtmlViewOptions options = HtmlViewOptions.forExternalResources(Paths.get("output"));
options.setRenderComments(true);
options.setCacheEnabled(true);
```

### Caching Strategies
Store rendered HTML in a distributed cache (e.g., Redis) keyed by document hash. When a request arrives, check the cache first; if a hit, serve the cached HTML instantly, bypassing the rendering engine.

## When to Use GroupDocs Viewer vs Alternatives

### GroupDocs Viewer is Perfect For
- **Document Management Systems** – need to display many file types with annotations.  
- **Collaborative Review Platforms** – comments must stay visible to all participants.  
- **Educational Tools** – instructors’ notes appear alongside lecture slides.  
- **Legal Applications** – contracts with lawyer comments require faithful rendering.  

### Consider Alternatives When
- **Simple PDF Display** – native browser PDF viewers may be enough.  
- **Basic Image Conversion** – `ImageIO` or similar libraries are lighter.  
- **Pure Text Extraction** – Apache POI or iText might be more appropriate.

## Frequently Asked Questions

**Q: Can I render documents without comments?**  
A: Yes—simply omit the `setRenderComments(true)` call or set it to `false`.

**Q: What file formats support comment rendering?**  
A: Most major formats—including DOC/DOCX, XLS/XLSX, PPT/PPTX, PDF, and many more. See the [official documentation](https://docs.groupdocs.com/viewer/java/) for the full list.

**Q: Can I customize the HTML output styling?**  
A: Absolutely. Use `HtmlViewOptions.setEmbedResources(false)` to generate external CSS files, then add your own stylesheet after rendering.

**Q: How do I handle password‑protected documents?**  
A: Provide a `LoadOptions` instance with the password:

`LoadOptions` allows you to specify document loading parameters such as passwords.

```java
LoadOptions loadOptions = new LoadOptions("myPassword");
try (Viewer viewer = new Viewer(inputPath.toFile(), loadOptions)) {
    viewer.view(viewOptions);
}
```

**Q: Is it possible to render only specific pages?**  
A: Yes—use the overloaded `view` method that accepts a `PageNumber` collection:

`PageNumber` represents a specific page index used when rendering a subset of pages.

```java
viewer.view(new int[]{1, 3, 5}, viewOptions);
```

**Q: Why is rendering slow for large documents?**  
A: Large files require more processing time. Improve speed by rendering only needed pages, using external resources, increasing JVM heap, and enabling asynchronous processing.

**Q: How can I monitor rendering progress?**  
A: While GroupDocs Viewer lacks built‑in callbacks, you can time the operation with `System.nanoTime()` before and after `viewer.view()` to log duration.

**Q: What happens if the source document is corrupted?**  
A: The library throws a `ViewerException`. Wrap the call in a try‑catch block and log the error for graceful degradation.

**Q: Can I use GroupDocs Viewer in a commercial application?**  
A: Yes, but a commercial license is required. The free trial includes watermarks that must be removed for production use.

**Q: Are there any usage limits?**  
A: The library itself imposes no limits, though your license agreement may define usage caps. Review your contract for details.

**Q: Can I redistribute applications that include GroupDocs Viewer?**  
A: You may distribute your own application, but you cannot redistribute the GroupDocs library binaries themselves. Check the license terms for compliance.

## Next Steps and Advanced Topics

You now have a solid foundation for **convert word to html** while preserving comments. Here are a few directions to deepen your expertise:

1. **Watermarking** – add custom watermarks to rendered pages for branding or confidentiality.  
2. **Metadata Extraction** – retrieve author, creation date, and page count via `viewer.getDocumentInfo()`.  
3. **Custom Viewers** – build specialised viewers for PDFs, spreadsheets, or presentations that hide or highlight comments differently.  
4. **Cloud Storage Integration** – render files directly from AWS S3, Azure Blob, or Google Drive without downloading them locally.  

### Recommended Learning Path
1. **Experiment with Different File Types** – try Excel, PowerPoint, and PDF files to see how comments are handled across formats.  
2. **Build a Simple Web Viewer** – create a minimal HTML page that loads the generated HTML via an `<iframe>` or AJAX.  
3. **Explore the GroupDocs Ecosystem** – look at GroupDocs Annotation, Comparison, and Signature for end‑to‑end document workflows.  
4. **Join the Community** – participate in the [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) for tips, sample projects, and support.  

### Getting Help and Support

**Official Resources**
- [GroupDocs.Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://apireference.groupdocs.com/viewer/java)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  
- [GitHub Examples](https://github.com/groupdocs-viewer/GroupDocs.Viewer-for-Java)

**Community Resources**
- Stack Overflow (tag: `groupdocs-viewer`)  
- Reddit programming communities  
- Java developer Discord servers  

---

**Last Updated:** 2026-05-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

```bash
java -version
javac -version
```

```bash
mvn -version
```

```bash
mvn archetype:generate -DgroupId=com.example.documentviewer -DartifactId=groupdocs-viewer-demo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

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

```java
import com.groupdocs.viewer.Viewer;

// The try-with-resources pattern ensures proper cleanup
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // All rendering operations happen here
    // Resources are automatically closed when done
} catch (Exception e) {
    System.err.println("Error rendering document: " + e.getMessage());
    e.printStackTrace();
}
```

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Create a descriptive output directory
Path outputDirectory = Paths.get("rendered-documents");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

// Create HTML options with embedded resources
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);

// The crucial setting – enable comment rendering!
viewOptions.setRenderComments(true);
```

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Create output directory if it doesn't exist
    if (!outputDirectory.toFile().exists()) {
        outputDirectory.toFile().mkdirs();
    }
    
    // Perform the actual rendering
    viewer.view(viewOptions);
    
    System.out.println("Document rendered successfully!");
    System.out.println("Output location: " + outputDirectory.toAbsolutePath());
    
} catch (Exception e) {
    System.err.println("Rendering failed: " + e.getMessage());
    e.printStackTrace();
}
```

```java
package com.example.documentviewer;

import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class DocumentRenderer {
    
    public static void main(String[] args) {
        renderDocumentWithComments("sample-document.docx", "output");
    }
    
    public static void renderDocumentWithComments(String inputFile, String outputDir) {
        // Set up paths
        Path outputDirectory = Paths.get(outputDir);
        Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
        
        // Configure rendering options
        HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
        viewOptions.setRenderComments(true);
        
        // Render the document
        try (Viewer viewer = new Viewer(inputFile)) {
            // Ensure output directory exists
            outputDirectory.toFile().mkdirs();
            
            // Execute rendering
            viewer.view(viewOptions);
            
            System.out.println("✓ Document rendered with comments preserved");
            System.out.println("📂 Output directory: " + outputDirectory.toAbsolutePath());
            
        } catch (Exception e) {
            System.err.println("❌ Rendering failed: " + e.getMessage());
            e.printStackTrace();
        }
    }
}
```

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class PathManager {
    
    /**
     * Creates a structured output path based on document name and timestamp
     */
    public static Path getOutputDirectoryPath(String documentName) {
        String timestamp = String.valueOf(System.currentTimeMillis());
        String cleanDocName = documentName.replaceAll("[^a-zA-Z0-9]", "_");
        
        return Paths.get("rendered-docs")
                   .resolve(cleanDocName)
                   .resolve(timestamp);
    }
    
    /**
     * Simple output directory for basic use cases
     */
    public static Path getSimpleOutputPath(String folderName) {
        return Paths.get("output").resolve(folderName);
    }
}
```

```java
// Always check if file exists before processing
Path inputPath = Paths.get("your-document.docx");
if (!inputPath.toFile().exists()) {
    throw new IllegalArgumentException("Input file not found: " + inputPath.toAbsolutePath());
}

// Check if file is readable
if (!inputPath.toFile().canRead()) {
    throw new IllegalArgumentException("Cannot read input file: " + inputPath.toAbsolutePath());
}
```

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
// This line is crucial – don't forget it!
viewOptions.setRenderComments(true);

// For debugging, you can verify the setting:
System.out.println("Comments enabled: " + viewOptions.isRenderComments());
```

```java
// Increase JVM heap size when running
// java -Xmx2g -Xms1g YourApplication

// Or process documents page by page for very large files
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setRenderComments(true);

// Render only specific pages if needed
viewer.view(viewOptions, 1, 2, 3); // Renders only pages 1, 2, and 3
```

```java
// Use external resources for faster processing of multiple pages
HtmlViewOptions viewOptions = HtmlViewOptions.forExternalResources(
    pageFilePathFormat, 
    "resources/page_{0}/", 
    "resources/page_{0}/{0}"
);

// Enable caching if processing the same document multiple times
// (Note: Implement caching at application level)
```

```java
@RestController
@RequestMapping("/api/documents")
public class DocumentController {
    
    @PostMapping("/render")
    public ResponseEntity<String> renderDocument(
            @RequestParam("file") MultipartFile file) {
        
        try {
            // Save uploaded file temporarily
            Path tempFile = Files.createTempFile("upload", ".tmp");
            file.transferTo(tempFile.toFile());
            
            // Render with comments
            String outputDir = renderDocumentWithComments(
                tempFile.toString(), 
                "web-output"
            );
            
            return ResponseEntity.ok("Document rendered: " + outputDir);
            
        } catch (Exception e) {
            return ResponseEntity.badRequest()
                .body("Rendering failed: " + e.getMessage());
        }
    }
}
```

```java
public class BatchDocumentProcessor {
    
    public void processFolderWithComments(String inputFolder) {
        File folder = new File(inputFolder);
        File[] files = folder.listFiles((dir, name) -> 
            name.toLowerCase().endsWith(".docx") || 
            name.toLowerCase().endsWith(".xlsx") ||
            name.toLowerCase().endsWith(".pptx")
        );
        
        if (files == null) return;
        
        for (File file : files) {
            try {
                String outputDir = file.getName().replace(".", "_") + "_output";
                renderDocumentWithComments(file.getAbsolutePath(), outputDir);
                System.out.println("✓ Processed: " + file.getName());
                
            } catch (Exception e) {
                System.err.println("❌ Failed to process " + file.getName() + ": " + e.getMessage());
            }
        }
    }
}
```

```java
// Simple approach works fine
try (Viewer viewer = new Viewer(documentPath)) {
    viewer.view(viewOptions);
}
```

```java
public class DocumentRenderingService {
    private final ExecutorService executorService = 
        Executors.newFixedThreadPool(4); // Limit concurrent renderings
    
    public CompletableFuture<String> renderAsync(String documentPath) {
        return CompletableFuture.supplyAsync(() -> {
            try (Viewer viewer = new Viewer(documentPath)) {
                // Rendering logic here
                return "success";
            } catch (Exception e) {
                throw new RuntimeException(e);
            }
        }, executorService);
    }
}
```

```java
public class CachedDocumentRenderer {
    private final Map<String, String> renderCache = new ConcurrentHashMap<>();
    
    public String renderWithCaching(String documentPath) {
        String cacheKey = generateCacheKey(documentPath);
        
        return renderCache.computeIfAbsent(cacheKey, key -> {
            // Only render if not already cached
            return performActualRendering(documentPath);
        });
    }
    
    private String generateCacheKey(String documentPath) {
        // Include file modification time in cache key
        File file = new File(documentPath);
        return documentPath + "_" + file.lastModified();
    }
}
```

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setPassword("your-password");
try (Viewer viewer = new Viewer("protected-doc.docx", loadOptions)) {
    // Render as usual
}
```

```java
viewer.view(viewOptions, 1, 3, 5); // Renders only pages 1, 3, and 5
```

```java
System.out.println("Starting render for: " + documentName);
long startTime = System.currentTimeMillis();
viewer.view(viewOptions);
long endTime = System.currentTimeMillis();
System.out.println("Rendering completed in: " + (endTime - startTime) + "ms");
```

```java
try (Viewer viewer = new Viewer(documentPath)) {
    viewer.view(viewOptions);
} catch (CorruptOrDamagedFileException e) {
    System.err.println("Document is corrupted: " + e.getMessage());
} catch (Exception e) {
    System.err.println("General error: " + e.getMessage());
}
```

## Related Tutorials

- [Render word tracked changes in Word Documents with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/render-tracked-changes-word-docs-groupdocs-viewer-java/)
- [Responsive HTML Rendering with GroupDocs.Viewer for Java: A Comprehensive Guide](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [How to Load and Render Documents as HTML using GroupDocs.Viewer for Java](/viewer/java/rendering-basics/groupdocs-viewer-java-html-rendering/)
