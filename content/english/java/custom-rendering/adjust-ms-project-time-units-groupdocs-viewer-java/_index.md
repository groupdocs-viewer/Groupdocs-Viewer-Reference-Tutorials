---
title: "How to Adjust MS Project Time Units Using GroupDocs.Viewer Java&#58; A Step-by-Step Guide"
description: "Learn how to adjust MS Project time units with GroupDocs.Viewer for Java. Streamline your project document rendering process efficiently and accurately."
date: "2025-04-24"
weight: 1
url: "/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/"
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
type: docs
---
# How to Adjust MS Project Time Units Using GroupDocs.Viewer Java: A Step-by-Step Guide
## Introduction
Are you tired of manually adjusting time units in your MS Project documents before rendering them into HTML format? The process can be tedious and prone to errors, especially when dealing with large projects. With **GroupDocs.Viewer for Java**, you can easily adjust the time unit settings programmatically, ensuring accuracy and efficiency.

![Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

In this guide, we'll demonstrate how to change the time units of MS Project documents into days using GroupDocs.Viewer Java. By the end of this tutorial, you will be able to:
- Set up your environment for rendering MS Project files with GroupDocs.Viewer.
- Adjust project management time units directly in your code.
- Integrate these adjustments seamlessly into your application.
Before we dive in, let's ensure you have everything ready to get started!
## Prerequisites
### Required Libraries and Dependencies
To follow this tutorial, you'll need the following:
- **GroupDocs.Viewer for Java** library (version 25.2 or later).
- Maven installed on your machine for dependency management.
- Basic understanding of Java programming.
### Environment Setup Requirements
Ensure your development environment is set up with JDK (Java Development Kit) and an IDE like IntelliJ IDEA or Eclipse that supports Maven projects.
### Knowledge Prerequisites
A basic familiarity with Java syntax, file handling in Java, and working with Maven dependencies will be beneficial. However, this guide aims to make the process straightforward for all skill levels.
## Setting Up GroupDocs.Viewer for Java
To begin using GroupDocs.Viewer for Java, you need to add it as a dependency in your project's `pom.xml` file:
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
### License Acquisition Steps
GroupDocs offers a free trial of their libraries, allowing you to explore the features before purchasing or applying for a temporary license:
- **Free Trial**: Visit [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) to download and start using the library.
- **Temporary License**: For extended testing, request a [temporary license](https://purchase.groupdocs.com/temporary-license/).
- **Purchase**: If you decide GroupDocs.Viewer is right for your project, purchase it directly from their [buy page](https://purchase.groupdocs.com/buy).
### Basic Initialization and Setup
Once the dependency is set up in your Maven `pom.xml`, you're ready to start coding. Initialize a Viewer instance with the path of your MS Project file and prepare for rendering.
## Implementation Guide
Let's dive into how you can adjust time units for MS Project documents using GroupDocs.Viewer Java. We'll break it down step-by-step.
### Feature Overview: Adjust Time Units in MS Project Documents
This feature lets you change the project management time unit setting from the default (usually minutes) to days, making your rendered HTML more user-friendly and aligned with typical reporting standards.
#### Step 1: Define Output Directory and Page File Path Format
First, specify where the rendered HTML files will be stored:
```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
Use this directory to resolve file paths dynamically for each page of your MS Project document:
```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
#### Step 2: Initialize View Options
Create view options with embedded resources, which allow you to specify how the project should be viewed and rendered:
```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
#### Step 3: Adjust Time Unit Setting
Specify that the time unit for project management is set to days, which is often more suitable for presentations and reports:
```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```
#### Step 4: Render MS Project Document
Finally, use the Viewer class to render your document with the specified view options:
```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```
### Troubleshooting Tips
- Ensure your output directory path is correctly specified and writable.
- Verify that the MS Project file path is correct and accessible.
- If rendering issues occur, check for any exceptions thrown by the Viewer class.
## Practical Applications
Here are some real-world use cases where adjusting time units in MS Project documents can be particularly useful:
1. **Project Reporting**: For stakeholders who prefer daily summaries over minute details.
2. **Integration with Dashboards**: When embedding project timelines into business dashboards that require day-level granularity.
3. **Automated Updates**: For systems that need to update project statuses on a daily basis automatically.
## Performance Considerations
When working with large MS Project files, consider the following for optimal performance:
- Use embedded resources sparingly if only certain parts of the document are needed frequently.
- Monitor memory usage when dealing with multiple or very large projects simultaneously.
- Utilize Java's garbage collection effectively to manage resource allocation and deallocation.
## Conclusion
You've now learned how to adjust MS Project time units using GroupDocs.Viewer for Java. This feature streamlines the process of rendering project documents, making them more accessible and easier to integrate into broader systems. 
Consider exploring other features of GroupDocs.Viewer to enhance your document management solutions further.
Ready to take it a step further? Try implementing this solution in your next project!
## FAQ Section
**1. What is GroupDocs.Viewer for Java used for?**
GroupDocs.Viewer for Java allows developers to render documents in various formats, including MS Project files, into HTML or image formats for viewing purposes.
**2. Can I use GroupDocs.Viewer for other document types?**
Yes, GroupDocs.Viewer supports a wide range of document formats beyond MS Project, such as PDFs, Word documents, and spreadsheets.
**3. How do I handle licensing for GroupDocs.Viewer?**
GroupDocs offers different license options, including free trials, temporary licenses for extended testing, and permanent licenses upon purchase.
**4. What if I encounter errors when rendering my project files?**
Check the file paths, ensure you have write access to your output directory, and review any exceptions thrown by GroupDocs.Viewer for troubleshooting hints.
**5. Can I customize how documents are rendered with GroupDocs.Viewer?**
Absolutely! GroupDocs.Viewer provides a range of options to customize rendering, including setting time units for projects, selecting which resources to embed, and more.
## Resources
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase a License](https://purchase.groupdocs.com/buy)
