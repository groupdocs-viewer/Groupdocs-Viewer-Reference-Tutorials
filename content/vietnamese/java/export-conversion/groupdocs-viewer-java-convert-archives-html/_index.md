---
date: '2026-08-03'
description: Tìm hiểu cách chuyển đổi zip sang html bằng GroupDocs.Viewer Java, đặt
  số mục trên mỗi trang, nhúng tài nguyên html, và chuyển đổi hàng loạt các tệp lưu
  trữ một cách hiệu quả.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Tìm hiểu cách chuyển đổi zip sang html bằng GroupDocs.Viewer Java,
  đặt số mục trên mỗi trang, nhúng tài nguyên html, và chuyển đổi hàng loạt các tệp
  lưu trữ một cách hiệu quả. Tham khảo mã từng bước và các mẹo về hiệu năng.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Chuyển đổi zip sang html và đặt số mục trên mỗi trang với GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Chuyển đổi zip sang html và đặt số mục trên mỗi trang với GroupDocs.Viewer
  Java
type: docs
url: /vi/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Chuyển đổi zip sang html và đặt số mục mỗi trang với GroupDocs.Viewer Java

Trong nhiều ứng dụng web, bạn cần hiển thị nội dung của một tệp ZIP hoặc RAR trực tiếp trong trình duyệt. Với GroupDocs.Viewer for Java, bạn có thể **convert zip to html** trong một bước duy nhất, kiểm soát số mục lưu trữ xuất hiện trên mỗi trang, nhúng tất cả hình ảnh và CSS hỗ trợ, và thậm chí xử lý hàng chục tệp lưu trữ theo lô. Hướng dẫn này sẽ đưa bạn qua toàn bộ quy trình, từ thiết lập Maven đến việc render đa trang, và giải thích lý do mỗi cài đặt quan trọng đối với hiệu năng và khả năng sử dụng.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Câu trả lời nhanh
- **“set items per page” kiểm soát gì?** Nó xác định bao nhiêu tệp hoặc thư mục từ một lưu trữ sẽ xuất hiện trên mỗi trang HTML được tạo.  
- **Có thể nhúng hình ảnh và CSS trực tiếp vào HTML không?** Có – sử dụng tùy chọn `forEmbeddedResources` để nhúng tài nguyên HTML.  
- **Có thể thực hiện chuyển đổi hàng loạt không?** Chắc chắn; bạn có thể lặp qua một bộ sưu tập các lưu trữ và render mỗi cái với cùng một cài đặt.  
- **Có cần Maven để sử dụng GroupDocs.Viewer không?** Có, thêm phụ thuộc Maven `groupdocs-viewer` như được hiển thị bên dưới.  
- **Các định dạng đầu ra nào được hỗ trợ?** HTML một trang và HTML đa trang đều khả dụng, và thư viện hỗ trợ hơn 50 loại lưu trữ đầu vào.

## “set items per page” là gì trong GroupDocs.Viewer?
Cài đặt **set items per page** thuộc về các tùy chọn render lưu trữ. Nó cho viewer biết bao nhiêu mục lưu trữ (tệp hoặc thư mục) sẽ được hiển thị trên mỗi trang HTML khi bạn tạo một tài liệu HTML đa trang. Điều chỉnh giá trị này giúp cân bằng kích thước trang và tốc độ điều hướng, đặc biệt với các lưu trữ lớn.

## Tại sao nhúng resources html?
Việc nhúng tài nguyên (hình ảnh, CSS, phông chữ) trực tiếp vào tệp HTML tạo ra một tài liệu duy nhất, di động, có thể mở mà không cần các tệp bên ngoài. Điều này lý tưởng cho tệp đính kèm email, xem offline, hoặc nhúng kết quả vào các trang web khác. Cách tiếp cận này cũng đơn giản hoá việc triển khai vì không cần quản lý các đường dẫn tài sản bên ngoài.

## Yêu cầu trước

- **Required libraries:** Bao gồm GroupDocs.Viewer phiên bản 25.2 trở lên.  
- **Environment:** Java Development Kit (JDK) đã được cài đặt và cấu hình.  
- **Knowledge:** Kiến thức cơ bản về Java và quản lý phụ thuộc Maven.  

## Cài đặt Maven GroupDocs Viewer

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

### Nhận giấy phép
GroupDocs.Viewer cung cấp **free trial link**, giấy phép tạm thời, hoặc tùy chọn mua đầy đủ. Hãy chọn lựa phù hợp với thời gian dự án của bạn.

### Khởi tạo cơ bản
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cách render lưu trữ thành html một trang
Viewer là lớp cốt lõi tải tài liệu hoặc lưu trữ để render.

Để tạo một tệp HTML duy nhất chứa toàn bộ lưu trữ, tạo một thể hiện `Viewer` cho tệp ZIP và sử dụng `HtmlViewOptions.forEmbeddedResources()` để nhúng tất cả hình ảnh, CSS và phông chữ. Render lưu trữ với các tùy chọn này tạo ra một trang tự chứa, phù hợp cho email hoặc sử dụng offline.

### Bước 1: Xác định thư mục đầu ra
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Bước 2: Đặt tên tệp cho đầu ra một trang
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Bước 3: Khởi tạo viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Bước 4: Cấu hình tùy chọn render (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 5: Render thành một trang duy nhất
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cách render lưu trữ thành html đa trang và đặt số mục mỗi trang
`HtmlViewOptions` cấu hình cách viewer render đầu ra HTML, bao gồm phân trang và nhúng tài nguyên.

Để chia một lưu trữ thành nhiều trang, tạo `HtmlViewOptions.forEmbeddedResources()` và đặt kích thước trang mong muốn bằng `options.setItemsPerPage(20)`. Viewer sẽ tạo các tệp HTML riêng biệt, mỗi tệp hiển thị tối đa số mục đã chỉ định, giúp cải thiện việc điều hướng cho các lưu trữ lớn và đảm bảo tải nhanh hơn.

### Bước 1: Tái sử dụng thư mục đầu ra
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Bước 2: Xác định định dạng tên tệp cho nhiều trang
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Bước 3: Khởi tạo lại viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Bước 4: Cấu hình tùy chọn đa trang (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 5: Đặt số mục mỗi trang (từ khóa chính trong hành động)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Ứng dụng thực tiễn

- **Document management systems:** Thêm chức năng xem trước lưu trữ mà không cần cài đặt viewer bổ sung.  
- **Web portals:** Cung cấp cho người dùng cách nhanh, không cần tải xuống để khám phá các tài liệu được đóng gói.  
- **Collaboration tools:** Cho phép các nhóm kiểm tra lưu trữ chia sẻ trực tiếp trong trình duyệt.  

## Các cân nhắc về hiệu năng

- **Resource management:** Giữ mức sử dụng bộ nhớ thấp bằng cách xử lý lưu trữ dưới dạng stream; viewer có thể xử lý các lưu trữ lên tới 500 MB mà không cần tải toàn bộ tệp vào bộ nhớ.  
- **Batch convert archives:** Lặp qua danh sách các tệp lưu trữ và gọi cùng logic render để tối đa hoá thông lượng.  
- **Caching strategy:** Lưu HTML đã render trong cache nếu cùng một lưu trữ được truy cập thường xuyên, giảm thời gian xử lý lặp lại tới 70 %.  

## Câu hỏi thường gặp

**Q: GroupDocs.Viewer Java là gì?**  
A: GroupDocs.Viewer Java là một thư viện phía máy chủ cho phép render hơn 50 định dạng tài liệu và lưu trữ — bao gồm ZIP và RAR — sang HTML, PDF hoặc các tệp hình ảnh mà không cần ứng dụng bên ngoài.

**Q: Làm sao tôi có thể nhận bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Truy cập [free trial link](https://releases.groupdocs.com/viewer/java/) để tải về và thử nghiệm.

**Q: Tôi có thể chuyển đổi các loại tài liệu khác ngoài lưu trữ không?**  
A: Có, viewer hỗ trợ PDF, Word, Excel, PowerPoint và hơn 35 định dạng bổ sung.

**Q: Tôi nên làm gì nếu quá trình render chậm?**  
A: Giảm số mục mỗi trang, bật streaming, hoặc xử lý các lưu trữ theo lô nhỏ hơn để cải thiện tốc độ.

**Q: Tôi có thể nhận hỗ trợ ở đâu?**  
A: Liên hệ qua [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Có thể nhúng CSS và hình ảnh trực tiếp vào HTML không?**  
A: Chắc chắn—sử dụng `HtmlViewOptions.forEmbeddedResources` như trong các ví dụ.

**Q: Làm sao tôi batch convert một thư mục chứa các lưu trữ?**  
A: Lặp qua từng tệp bằng vòng `for`, áp dụng cùng cấu hình `Viewer` và `HtmlViewOptions` cho mỗi lần lặp.

## Tài nguyên

- **Documentation:** Tìm hiểu sâu hơn về chức năng với [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API reference:** Khám phá toàn bộ API tại [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Tải các binary mới nhất từ [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and licensing:** Xem các tùy chọn trên [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and community:** Tham gia thảo luận trên [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Cập nhật lần cuối:** 2026-08-03  
**Kiểm tra với:** GroupDocs.Viewer 25.2  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan

- [Cách chuyển đổi zip sang HTML và render thư mục zip trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [chuyển đổi zip sang pdf với GroupDocs.Viewer Java - Tên tệp tùy chỉnh](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Cách chuyển đổi DOCX sang HTML bằng GroupDocs.Viewer cho Java: Hướng dẫn từng bước](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)