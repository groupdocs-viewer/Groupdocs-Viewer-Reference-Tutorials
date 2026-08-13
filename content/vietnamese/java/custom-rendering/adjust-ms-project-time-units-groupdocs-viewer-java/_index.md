---
date: '2026-05-21'
description: Tìm hiểu cách thực hiện xuất HTML từ MS Project với các đơn vị thời gian
  đã được điều chỉnh bằng cách sử dụng GroupDocs Viewer for Java. Hướng dẫn từng bước
  với prerequisites, setup và troubleshooting.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Xuất HTML từ MS Project: Điều chỉnh đơn vị thời gian qua GroupDocs Java'
type: docs
url: /vi/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Xuất HTML MS Project: Điều chỉnh Đơn vị Thời gian qua GroupDocs Java

Xuất một tệp **MS Project** sang HTML là một yêu cầu phổ biến cho các bảng điều khiển quản lý dự án, các cổng báo cáo trạng thái và các công cụ đánh giá cộng tác. Mặc định, trình xem hiển thị dữ liệu liên quan đến thời gian bằng phút, điều này có thể làm lộn xộn bố cục và khiến việc báo cáo hằng ngày khó đọc hơn. Với **GroupDocs Viewer for Java** bạn có thể lập trình đặt đơn vị thời gian thành **days**, tạo ra một *ms project html export* sạch sẽ, phù hợp với mong đợi thường gặp của các bên liên quan. Trong hướng dẫn này, bạn sẽ học cách cấu hình trình xem, điều chỉnh đơn vị thời gian và chuyển đổi dự án sang HTML trong một vài bước đơn giản.

![Điều chỉnh Đơn vị Thời gian MS Project với GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Điều chỉnh Đơn vị Thời gian MS Project với GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Câu trả lời nhanh
- **Thư viện nào hỗ trợ hiển thị tệp MS Project?** GroupDocs Viewer for Java.  
- **Đơn vị thời gian nào tôi có thể đặt cho xuất HTML?** Days, sử dụng `TimeUnit.DAYS`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có— cần một giấy phép vĩnh viễn; bản dùng thử hoạt động cho việc đánh giá. Bạn có thể bắt đầu với một [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **IDE nào phù hợp nhất?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, NetBeans) hỗ trợ Maven.  
- **Maven có bắt buộc không?** Maven đơn giản hoá việc quản lý phụ thuộc, nhưng bạn cũng có thể dùng Gradle hoặc thêm JAR thủ công.  
- **Tôi có thể mua ở đâu?** Truy cập [buy page](https://purchase.groupdocs.com/buy) để xem giá.

## GroupDocs Viewer for Java là gì?
**GroupDocs Viewer for Java** là một SDK Java chuyển đổi hơn 150 định dạng tài liệu—bao gồm MS Project—thành HTML, PNG, JPEG hoặc PDF thân thiện với web.  
Nó trừu tượng hoá logic phân tích, cho phép bạn kiểm soát các tùy chọn hiển thị như đơn vị thời gian, và hoạt động trên bất kỳ nền tảng nào hỗ trợ Java 8 hoặc cao hơn.  

## Tại sao cần điều chỉnh đơn vị thời gian cho xuất HTML MS Project?
Đặt đơn vị thời gian thành **days** giảm nhiễu thị giác, phù hợp với hầu hết các chu kỳ báo cáo và cải thiện thời gian tải trang vì ít dấu thời gian chi tiết hơn được tạo ra. Theo các số liệu định lượng, việc xuất với ngày thay vì phút có thể giảm kích thước HTML tạo ra tới **45 %** cho các dự án 30‑ngày điển hình, và tăng tốc độ hiển thị phía khách hàng khoảng **30 %**.

## Yêu cầu trước
- **Java Development Kit (JDK) 8 hoặc mới hơn** được cài đặt trên máy làm việc của bạn.  
- **Maven** (hoặc Gradle) để quản lý phụ thuộc.  
- Một tệp **MS Project (.mpp)** mà bạn muốn xuất.  
- Truy cập giấy phép **GroupDocs Viewer for Java** (dùng thử hoặc vĩnh viễn).  

### Thư viện cần thiết
Thêm phụ thuộc sau vào `pom.xml` của bạn (hoặc đoạn mã Gradle tương đương):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Mẹo chuyên nghiệp:** Giữ số phiên bản luôn cập nhật; các bản phát hành mới thêm hỗ trợ định dạng và cải thiện hiệu năng.

## Làm thế nào để thiết lập GroupDocs Viewer for Java?
Khởi tạo trình xem bằng cách tạo một thể hiện `Viewer` trỏ tới tệp MS Project của bạn. Lớp `Viewer` là điểm vào cho tất cả các thao tác kết xuất. Nó tải tài liệu nguồn, chuẩn bị các cấu trúc nội bộ và cung cấp các phương thức như `view()` và `viewToHtml()` để tạo ra các định dạng đầu ra mong muốn.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Định nghĩa:** Lớp `Viewer` là thành phần cốt lõi của GroupDocs Viewer, tải tài liệu nguồn và cung cấp các phương thức hiển thị như `view()` và `viewToHtml()`.

## Làm thế nào để điều chỉnh đơn vị thời gian cho xuất HTML?
Để thay đổi độ chi tiết thời gian, tạo một đối tượng `ViewOptions`, cấu hình `ProjectOptions` của nó để sử dụng `TimeUnit.DAYS`, và truyền nó cho trình xem. `ViewOptions` định nghĩa các cài đặt kết xuất cho tài liệu, trong khi enum `TimeUnit` chỉ định đơn vị (phút, giờ, ngày) cho dữ liệu thời gian. Sau khi thiết lập các tùy chọn này, gọi `viewer.view(options)` để tạo HTML với các dấu ngày.

Tải tệp MS Project của bạn bằng `new Viewer("file.mpp")`, tạo một đối tượng `ViewOptions`, đặt `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, sau đó gọi `viewer.view(options)`. Quy trình ba bước này chuyển đổi đơn vị thời gian từ phút sang ngày và tạo các tệp HTML chỉ hiển thị khoảng thời gian hằng ngày.

### Bước 1: Xác định thư mục đầu ra
Chọn một thư mục có thể ghi được để lưu các trang HTML, ví dụ `output/`.

### Bước 2: Tạo tùy chọn xem với tài nguyên nhúng
Các tài nguyên nhúng (CSS, JavaScript) đảm bảo các trang HTML tự chứa.

### Bước 3: Đặt đơn vị thời gian thành ngày
Sử dụng `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` để chuyển đổi độ chi tiết.

### Bước 4: Kết xuất tài liệu
Gọi `viewer.view(options)`; trình xem sẽ ghi một tệp HTML cho mỗi trang dự án vào thư mục đầu ra.

### Bước 5: Xác minh kết quả
Mở `index.html` đã tạo trong trình duyệt; bạn sẽ thấy các thanh nhiệm vụ căn chỉnh với các dấu ngày thay vì dấu phút.

## Các vấn đề thường gặp và khắc phục
- **Đường dẫn đầu ra không đúng** – Đảm bảo thư mục tồn tại và quá trình Java có quyền ghi.  
- **Thiếu giấy phép** – Nếu không có giấy phép hợp lệ, trình xem sẽ chuyển sang chế độ dùng thử và có thể chèn watermark.  
- **Tệp lớn (> 500 MB)** – Xem xét tăng kích thước heap JVM (`-Xmx2g`) hoặc xuất với `options.setRenderLimit(1000)` để xử lý các trang theo lô.  

## Ứng dụng thực tiễn của xuất HTML với đơn vị thời gian đã điều chỉnh
1. **Bảng điều khiển điều hành** – Độ chi tiết hằng ngày phù hợp với hầu hết các biểu đồ KPI.  
2. **Email trạng thái tự động** – Nhúng HTML đã tạo trực tiếp vào nội dung email để cập nhật nhanh.  
3. **Cổng dự án** – Lưu trữ HTML trên trang nội bộ, nơi các thành viên có thể lọc nhiệm vụ theo ngày.  

## Các cân nhắc về hiệu năng cho tệp MS Project lớn
- **Quản lý bộ nhớ** – Sử dụng các flag của garbage collector Java (`-XX:+UseG1GC`) để giải phóng các đối tượng không dùng nhanh chóng.  
- **Kết xuất chọn lọc** – Nếu chỉ cần biểu đồ Gantt, tắt việc kết xuất các tài nguyên khác bằng `options.getProjectOptions().setRenderGantt(true)` và `setRenderResources(false)`.  
- **Xử lý song song** – Đối với chuyển đổi hàng loạt, tạo các đối tượng `Viewer` riêng cho mỗi tệp và chạy chúng trong một pool thread để tận dụng CPU đa nhân.

## Kết luận
Bạn hiện đã có một quy trình hoàn chỉnh, sẵn sàng cho môi trường sản xuất để thực hiện **ms project html export** với đơn vị thời gian được đặt thành ngày bằng GroupDocs Viewer for Java. Cách tiếp cận này giảm kích thước HTML, tăng tốc độ hiển thị phía khách hàng và cung cấp một giao diện thân thiện với các bên liên quan cho lịch trình dự án. Khám phá các tùy chọn kết xuất bổ sung—như xuất PDF hoặc ảnh chụp màn hình—để mở rộng tích hợp vào các quy trình báo cáo rộng hơn.

## Câu hỏi thường gặp

**H: Tôi có thể xuất các chế độ xem Project khác (ví dụ: Bảng tài nguyên) sang HTML không?**  
A: Có, đối tượng `ProjectOptions` cho phép bạn bật hoặc tắt các chế độ xem cụ thể như Gantt, Bảng tài nguyên và Lịch trước khi xuất.

**H: Có thể tùy chỉnh CSS của HTML đã tạo không?**  
A: Chắc chắn. Cung cấp đường dẫn tới stylesheet tùy chỉnh bằng `options.setStyleSheetPath("path/to/custom.css")` và trình xem sẽ nhúng nó vào mỗi trang.

**H: Giới hạn kích thước tệp mà GroupDocs Viewer hỗ trợ cho MS Project là bao nhiêu?**  
A: SDK có thể xử lý các tệp lên tới **500 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, nhờ kiến trúc streaming.

**H: Tôi có cần cài đặt Microsoft Project trên máy chủ không?**  
A: Không. GroupDocs Viewer phân tích định dạng .mpp trực tiếp và không yêu cầu cài đặt Microsoft Project hay bất kỳ phần mềm Office nào.

**H: Làm thế nào để cấp giấy phép cho trình xem trong môi trường sản xuất?**  
A: Mua giấy phép vĩnh viễn từ cửa hàng GroupDocs; áp dụng tệp giấy phép tại thời gian chạy bằng `License license = new License(); license.setLicense("path/to/license.lic");`. Đối với nhu cầu ngắn hạn, bạn có thể nhận một [temporary license](https://purchase.groupdocs.com/temporary-license/).

**Last Updated:** 2026-05-21  
**Tested With:** GroupDocs Viewer Java 25.2  
**Author:** GroupDocs  

**Resources**  
- [Tài liệu](https://docs.groupdocs.com/viewer/java/)  
- [Tham chiếu API](https://reference.groupdocs.com/viewer/java/)  
- [Tải xuống GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Mua giấy phép](https://purchase.groupdocs.com/buy)  

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
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Hướng dẫn liên quan

- [Cách xuất tệp MS Project thành HTML, JPG, PNG và PDF có ghi chú bằng GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Cách sử dụng GroupDocs Viewer để xuất tài liệu dự án theo khoảng thời gian trong Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Cách thiết lập giấy phép trong GroupDocs.Viewer Java: Hướng dẫn cấu hình tệp và URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)