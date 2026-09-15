---
date: '2026-09-15'
description: Tìm hiểu cách chuyển đổi eml sang html với định dạng ngày giờ tùy chỉnh
  và độ lệch múi giờ bằng GroupDocs.Viewer cho Java—lý tưởng cho việc lưu trữ email
  và các cổng hỗ trợ.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Chuyển đổi eml sang html với định dạng ngày giờ tùy chỉnh và độ lệch
  múi giờ bằng GroupDocs.Viewer cho Java. Thực hiện theo hướng dẫn từng bước này để
  hiển thị email một cách chính xác.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Chuyển đổi eml sang html với ngày giờ tùy chỉnh trong java bằng GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Chuyển đổi eml sang html với ngày giờ tùy chỉnh trong java bằng GroupDocs.Viewer
type: docs
url: /vi/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi eml sang html với datetime tùy chỉnh trong java bằng GroupDocs.Viewer

Trong các hệ thống hỗ trợ và lưu trữ hiện đại, **chuyển đổi eml sang html** nhanh chóng đồng thời bảo toàn thời gian chính xác là một khả năng không thể thiếu. Hướng dẫn này sẽ chỉ cho bạn cách hiển thị email EML dưới dạng HTML, áp dụng **định dạng datetime tùy chỉnh**, và thiết lập **độ lệch múi giờ** bằng GroupDocs.Viewer cho Java. Khi hoàn thành, bạn sẽ có một đoạn mã có thể tái sử dụng, tạo ra các hiển thị email chính xác, sẵn sàng cho web cho bất kỳ quy trình **chuyển đổi email sang html** nào.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Câu trả lời nhanh
- **GroupDocs.Viewer có thể chuyển đổi EML sang HTML không?** Có – API sẽ render các tệp EML trực tiếp sang HTML mà không cần client mail bên ngoài.  
- **Tôi có cần giấy phép cho môi trường production không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép trả phí là bắt buộc cho triển khai production.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc mới hơn được hỗ trợ đầy đủ.  
- **Làm sao để thay đổi định dạng ngày hiển thị?** Gọi `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **Tôi có thể điều chỉnh múi giờ không?** Có, sử dụng `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Convert eml sang html là gì?
`Convert eml to html` là quá trình chuyển đổi một tệp email EML thành tài liệu HTML để trình duyệt hiển thị. Việc chuyển đổi tệp EML sang HTML biến nội dung email thô (bao gồm header, body và attachment) thành định dạng thân thiện với web mà các trình duyệt có thể hiển thị mà không cần plugin bổ sung. Điều này giúp dễ dàng nhúng email vào các ứng dụng web, kho lưu trữ, hoặc bảng điều khiển hỗ trợ.

## Tại sao nên dùng GroupDocs.Viewer cho nhiệm vụ này?
GroupDocs.Viewer hỗ trợ **hơn 50 định dạng đầu vào và đầu ra**, bao gồm EML, MSG, PST và PDF, và có thể render các email hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ. Động cơ không phụ thuộc này loại bỏ nhu cầu sử dụng Outlook hoặc các parser bên thứ ba, cho phép bạn kiểm soát **định dạng datetime tùy chỉnh** và **độ lệch múi giờ** trong khi vẫn giữ mức tiêu thụ tài nguyên thấp.

## Yêu cầu trước
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ và một IDE Java (IntelliJ IDEA, Eclipse, VS Code)  
- Maven để quản lý phụ thuộc  

## Cài đặt GroupDocs.Viewer cho Java

### Cấu hình Maven
Thêm repository của GroupDocs và dependency Viewer vào tệp `pom.xml` của bạn.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### Mua giấy phép
Bắt đầu với bản dùng thử miễn phí hoặc yêu cầu giấy phép tạm thời để thử nghiệm mở rộng. Mua giấy phép đầy đủ cho môi trường production.

### Khởi tạo cơ bản
Tạo một thể hiện `Viewer` trỏ tới tệp EML bạn muốn chuyển đổi.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Chuyển đổi eml sang html với datetime tùy chỉnh trong java

Các bước sau sẽ hướng dẫn bạn render một tệp EML sang HTML đồng thời áp dụng định dạng datetime tùy chỉnh và độ lệch múi giờ.

### Bước 1: thiết lập thư mục đầu ra và đường dẫn tệp
Xác định nơi sẽ lưu HTML được tạo.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Giải thích:* `Path.of()` tạo tham chiếu tới thư mục sẽ lưu HTML. `resolve()` thêm tên tệp.

### Bước 2: khởi tạo viewer với tệp email
Khởi tạo lớp `Viewer` cho tệp EML mục tiêu.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Giải thích:* Thể hiện `Viewer` trỏ tới tệp EML bạn muốn chuyển đổi.

### Bước 3: cấu hình HtmlViewOptions
Tạo một đối tượng `HtmlViewOptions` gói hình ảnh và các tài nguyên khác trực tiếp vào đầu ra HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Giải thích:* `forEmbeddedResources()` gói hình ảnh và các tài nguyên khác trực tiếp vào đầu ra HTML.

### Bước 4: đặt định dạng datetime tùy chỉnh *(custom datetime java)*
`setDateTimeFormat` thiết lập mẫu ngày‑giờ được sử dụng khi render thời gian của email.  
Xác định mẫu sẽ được dùng cho tất cả các timestamp trong HTML đã render.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Giải thích:* Mẫu này hiển thị tháng, ngày, năm, giờ, phút, chỉ báo AM/PM và độ lệch múi giờ (`zzz`).

### Bước 5: đặt độ lệch múi giờ *(timezone offset java)*
`setTimeZoneOffset` chỉ định múi giờ sẽ được áp dụng cho tất cả các timestamp của email.  
Điều chỉnh timestamp theo múi giờ mong muốn.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Giải thích:* Điều chỉnh các timestamp đã render sang múi giờ mong muốn. Thay `"GMT+1"` bằng bất kỳ định danh múi giờ hợp lệ nào.

### Cách điều chỉnh múi giờ email trong java
Nếu bạn cần **điều chỉnh múi giờ email** vượt ra ngoài các độ lệch đơn giản—ví dụ xử lý thay đổi giờ mùa hè—bạn có thể lấy đối tượng `TimeZone` thích hợp từ API `java.util.TimeZone` bằng các ID khu vực như `"Europe/Paris"` hoặc `"America/New_York"` và truyền nó vào `setTimeZoneOffset`. Điều này đảm bảo các timestamp của email luôn phản ánh đúng thời gian địa phương.

### Bước 6: render tài liệu
Thực thi quá trình chuyển đổi và tạo ra tệp HTML cuối cùng.

```java
viewer.view(options);
```
*Giải thích:* Thực hiện chuyển đổi, tạo ra tệp HTML với các cài đặt datetime tùy chỉnh của bạn.

## Định dạng datetime tùy chỉnh ảnh hưởng như thế nào đến HTML đã render?
Định dạng datetime tùy chỉnh quyết định cách mỗi timestamp email xuất hiện trong HTML được tạo, ảnh hưởng đến khả năng đọc và tuân thủ locale. Bằng cách chỉ định mẫu như `"MMM dd, yyyy hh:mm a zzz"`, bạn đảm bảo mọi ngày đều được hiển thị nhất quán, bao gồm viết tắt tháng, ngày, năm, giờ, phút, chỉ báo AM/PM và độ lệch múi giờ rõ ràng, điều này rất quan trọng đối với các đội hỗ trợ toàn cầu.

## Các định dạng tệp nào mà GroupDocs.Viewer hỗ trợ cho việc render email?
GroupDocs.Viewer có thể render các tệp **EML, MSG, PST, MBOX và EMLX** sang HTML, PDF, PNG và JPEG. Nó hỗ trợ hơn 50 định dạng tài liệu và hình ảnh tổng cộng, cho phép bạn chuyển đổi email sang bất kỳ đầu ra web‑friendly phổ biến nào mà không cần bộ chuyển đổi bổ sung.

## Làm sao để batch chuyển đổi nhiều tệp eml?
Đặt tất cả các tệp EML vào một thư mục duy nhất, lặp qua từng tệp bằng cấu trúc `for` hoặc `foreach`, tái sử dụng cùng một thể hiện `HtmlViewOptions`, và gọi `viewer.view` cho mỗi tệp. Cách này giảm thiểu việc tạo đối tượng mới và tăng tốc chuyển đổi hàng loạt.

## Mẹo khắc phục sự cố
- **FileNotFoundException:** Kiểm tra lại các đường dẫn được dùng trong `Viewer` và `Path.of()`.  
- **Timestamp không đúng:** Đảm bảo ID `TimeZone` khớp với khu vực mục tiêu của bạn.  
- **Thiếu hình ảnh:** Xác nhận bạn đã dùng `HtmlViewOptions.forEmbeddedResources()`; nếu không, các tài nguyên bên ngoài có thể bị bỏ qua.  

## Ứng dụng thực tiễn
1. **Lưu trữ email:** Lưu các bản sao HTML có thể tìm kiếm của email để kiểm toán tuân thủ.  
2. **Cổng hỗ trợ khách hàng:** Hiển thị ticket đến với thời gian địa phương chính xác cho các đại lý trên toàn thế giới.  
3. **Tài liệu pháp lý:** Tạo bản ghi email sẵn sàng cho tòa án với timestamp chuẩn hoá.  

## Lưu ý về hiệu năng
- Triển khai trên máy chủ chuyên dụng cho các chuyển đổi hàng loạt.  
- Giám sát việc sử dụng heap Java; tăng `-Xmx` nếu gặp `OutOfMemoryError`.  
- Lưu cache HTML đã render khi cùng một email được yêu cầu nhiều lần để giảm tải CPU.  

## Kết luận
Bạn đã có một phương pháp hoàn chỉnh, sẵn sàng cho production để **chuyển đổi eml sang html** với định dạng datetime tùy chỉnh và độ lệch múi giờ bằng GroupDocs.Viewer cho Java. Giải pháp này cải thiện khả năng đọc, đảm bảo độ chính xác của timestamp, và dễ dàng tích hợp vào quy trình lưu trữ, hỗ trợ hoặc pháp lý.

**Bước tiếp theo:** Khám phá các tùy chọn Viewer khác như chèn CSS tùy chỉnh, phân trang, hoặc chuyển đổi sang PDF để tùy biến đầu ra hơn nữa cho nhu cầu ứng dụng của bạn.

## Câu hỏi thường gặp

**Q: Làm sao để xử lý các tệp eml có đính kèm?**  
A: Các đính kèm sẽ được nhúng tự động khi bạn sử dụng `HtmlViewOptions.forEmbeddedResources()`. Bạn cũng có thể trích xuất chúng qua API Viewer nếu cần các tệp riêng.

**Q: Tôi có thể thay đổi mẫu HTML hoặc thêm CSS tùy chỉnh không?**  
A: Có, sau khi render bạn có thể chỉnh sửa tệp HTML đã tạo hoặc chèn CSS programmatically trước khi lưu.

**Q: Có thể render nhiều tệp eml trong một batch không?**  
A: Đóng gói logic render trong một vòng lặp và tái sử dụng cùng một thể hiện `HtmlViewOptions` cho mỗi tệp.

**Q: Nếu tôi cần hỗ trợ các định dạng email khác như msg thì sao?**  
A: GroupDocs.Viewer cũng hỗ trợ MSG, PST và các container email khác—chỉ cần thay đổi phần mở rộng tệp trong hàm khởi tạo `Viewer`.

**Q: Tôi có cần giấy phép riêng cho mỗi máy chủ không?**  
A: Giấy phép được tính theo triển khai; tham khảo hướng dẫn giấy phép của GroupDocs cho các kịch bản đa‑máy chủ.

## Tài nguyên

- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download](https://releases.groupdocs.com/viewer/java/)  
- [Purchase](https://purchase.groupdocs.com/buy)  
- [Free Trial](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**Last updated:** 2026-09-15  
**Tested with:** GroupDocs.Viewer 25.2 (Java)  
**Author:** GroupDocs

## Hướng dẫn liên quan

- [Convert Email to HTML & Rename Fields – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)  
- [java convert msg to pdf – Optimize Email-to-PDF Rendering with GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)  
- [Groupdocs Viewer Java Responsive Html Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}