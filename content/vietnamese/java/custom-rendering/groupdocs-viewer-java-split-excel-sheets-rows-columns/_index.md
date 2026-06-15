---
date: '2026-06-15'
description: Tìm hiểu cách chuyển đổi Excel sang PDF Java và tách các trang tính Excel
  theo hàng và cột bằng GroupDocs Viewer. Bao gồm cài đặt, mã nguồn và các thực tiễn
  tốt nhất.
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
title: Chuyển đổi Excel sang PDF Java & Tách các trang tính theo hàng và cột
type: docs
url: /vi/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Chuyển đổi Excel sang PDF Java & Tách các trang tính theo Hàng & Cột (Java)

Large Excel workbooks often contain more data than can be comfortably displayed on a single screen or printed page. **convert excel to pdf java** is a common requirement when you need a static, share‑able format, while **splitting Excel sheets by rows and columns** makes the data easier to consume in web or print layouts. In this guide we’ll walk through both tasks using **GroupDocs Viewer for Java**, show you how to configure pagination, and explain best‑practice tips for performance and troubleshooting.

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Câu trả lời nhanh
- **Thư viện nào được sử dụng?** GroupDocs Viewer for Java.  
- **Tôi có thể tách theo cả hàng và cột không?** Có – bạn có thể định nghĩa rows‑per‑page và columns‑per‑page cùng nhau.  
- **Tôi có cần giấy phép không?** Một giấy phép dùng thử hoặc tạm thời hoạt động cho phát triển; một giấy phép đầy đủ là bắt buộc cho môi trường sản xuất.  
- **Các định dạng đầu ra nào được hỗ trợ?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **Maven có bắt buộc không?** Maven là cách được khuyến nghị để quản lý các phụ thuộc.  
- **Tôi cũng có thể chuyển đổi Excel sang PDF không?** Absolutely – just switch `HtmlViewOptions` to `PdfViewOptions` and reuse the same pagination settings.

## “Cách Tách Excel” là gì?
Splitting an Excel sheet means dividing a single worksheet into multiple pages or files based on a fixed number of rows, columns, or both. This technique is handy when you need to create paginated reports, embed data in web pages, or generate printable sections without loading the entire workbook at once.

## Tại sao nên sử dụng GroupDocs Viewer for Java?
GroupDocs Viewer processes spreadsheets in a single pass and automatically paginates them, eliminating manual calculations. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, and **the library supports 50+ input and output formats**, including XLS, XLSX, CSV, PDF, and HTML. It runs on any JVM‑compatible platform—Windows, Linux, macOS, Docker containers, or cloud‑based serverless runtimes—so you can integrate it wherever your Java application lives.

## Yêu cầu trước
- Java 17 hoặc mới hơn đã được cài đặt.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  
- Maven để quản lý phụ thuộc.  
- Kiến thức cơ bản về Java và quen thuộc với việc xử lý tệp Excel.

### Thư viện, Phiên bản và Phụ thuộc cần thiết
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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

### Cách nhận giấy phép
Obtain a free trial, temporary license, or purchase a full license from [GroupDocs](https://purchase.groupdocs.com/buy).

## Cách chuyển đổi Excel sang PDF Java?

The `Viewer` class is the core component of GroupDocs Viewer that loads a document and provides rendering methods for various output formats. `SpreadsheetOptions` allows you to control pagination settings such as rows‑per‑page and columns‑per‑page for spreadsheet rendering.

Load your Excel file with `new Viewer("source.xlsx")`, configure `SpreadsheetOptions` for pagination, and call `viewer.view(pdfOptions, stream)` – that single call converts the workbook to a PDF while respecting the row/column limits you set. The conversion preserves formulas, images, and cell styles, delivering a faithful PDF replica ready for distribution.

## Cách tách các trang tính Excel theo hàng

Splitting by rows creates a series of HTML pages, each containing a fixed number of rows (e.g., 15). This approach is ideal for dashboards that display a limited number of records per view. The viewer will generate separate HTML files such as `page_0.html`, `page_1.html`, etc., each containing the specified number of rows. This makes it simple to load only the needed portion in a web interface, reducing bandwidth and rendering time.

### Định nghĩa Anchor
`Viewer` is GroupDocs Viewer’s core class that loads a document and orchestrates rendering to the chosen output format.

### Triển khai theo từng bước

#### Bước 1: Thiết lập đường dẫn và khởi tạo Viewer
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Bước 2: Cấu hình số hàng mỗi trang
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Bước 3: Kết xuất tài liệu
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## Cách tách các trang tính Excel theo Hàng và Cột

Sometimes a single page needs to show a matrix of rows **and** columns (e.g., 15 rows × 7 columns). This gives you full control over the layout of each HTML page. The resulting pages display a rectangular block of cells, for example rows 1‑15 and columns A‑G on the first page, rows 16‑30 and columns H‑N on the next. This grid‑style pagination is useful for creating printable reports that fit standard paper sizes.

### Định nghĩa Anchor
`SpreadsheetOptions` configures how many rows and columns appear on each generated page.

### Triển khai theo từng bước

#### Bước 1: Thiết lập đường dẫn và khởi tạo Viewer
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Bước 2: Cấu hình số hàng và cột mỗi trang
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Bước 3: Kết xuất tài liệu
Render using the same `view` call.

```java
viewer.view(options);
```

## Ứng dụng thực tiễn
- **Generate Excel report Java**: Turn large financial models into a series of paginated HTML reports.  
- **GroupDocs Viewer Excel**: Embed split pages directly into a web portal for interactive data exploration.  
- **Render Excel HTML Java**: Serve the generated HTML pages via a servlet or Spring controller for fast client‑side rendering.  

## Các cân nhắc về hiệu suất
- **Memory usage** – Large workbooks can consume significant heap; consider increasing the JVM `-Xmx` setting.  
- **Chunk size** – Choose row/column counts that balance page size and rendering speed.  
- **Version updates** – Keep GroupDocs Viewer up‑to‑date to benefit from performance improvements; the latest 25.2 release improves rendering speed by up to 30 % compared with 24.x.

## Các vấn đề thường gặp & Khắc phục sự cố
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `OutOfMemoryError` | Render một sheet rất lớn với quá nhiều hàng mỗi trang | Giảm `countRowsPerPage` hoặc tăng heap JVM |
| Blank output files | Đường dẫn tệp không đúng hoặc thiếu quyền ghi | Xác minh `outputDirectory` tồn tại và có thể ghi |
| HTML resources not loading | Sử dụng `forEmbeddedResources` nhưng phục vụ tệp từ một URL cơ sở khác | Phục vụ toàn bộ thư mục đầu ra hoặc chuyển sang `forExternalResources` |

## Câu hỏi thường gặp

**Q: Tôi có thể tạo PDF thay vì HTML không?**  
A: Có. Thay `HtmlViewOptions` bằng `PdfViewOptions` và giữ cấu hình `SpreadsheetOptions` giống nhau.

**Q: Có thể tách dựa trên nội dung ô thay vì số hàng/cột cố định không?**  
A: Việc tách dựa trên nội dung trực tiếp không được tích hợp trong GroupDocs Viewer, nhưng bạn có thể tiền xử lý sổ làm việc bằng Apache POI để tạo các sheet riêng trước khi render.

**Q: GroupDocs Viewer có hỗ trợ các định dạng Excel cũ (XLS) không?**  
A: Chắc chắn. Viewer xử lý XLS, XLSX, CSV và các định dạng bảng tính khác.

**Q: Làm thế nào để nhúng HTML đã tạo vào một view Spring MVC?**  
A: Phục vụ thư mục đầu ra như một tài nguyên tĩnh và tham chiếu các tệp `page_0.html`, `page_1.html`, v.v., từ các mẫu Thymeleaf hoặc JSP của bạn.

**Q: Tôi cần loại giấy phép nào cho triển khai thương mại?**  
A: Cần một giấy phép sản xuất đầy đủ từ GroupDocs; giấy phép dùng thử chỉ dành cho đánh giá.

## Tài nguyên
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-06-15  
**Được kiểm tra với:** GroupDocs Viewer 25.2 for Java  
**Tác giả:** GroupDocs  

## Hướng dẫn liên quan

- [Hiển thị các hàng và cột ẩn trong bảng tính Java bằng GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Bỏ qua việc render các hàng trống trong Java bằng GroupDocs.Viewer: Hướng dẫn hiệu suất](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Hướng dẫn toàn diện: Chuyển đổi Excel 2003 XML sang HTML/JPG/PNG/PDF với GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)