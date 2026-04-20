---
date: '2026-03-19'
description: Tìm hiểu cách chuyển đổi XLSX sang HTML trong Java bằng cách hiển thị
  các vùng in của bảng tính với GroupDocs.Viewer – một giải pháp xem trước nhanh chóng
  và tập trung.
keywords:
- Java spreadsheet print areas rendering
- rendering print areas with GroupDocs.Viewer for Java
- efficient document preview solutions
title: Chuyển đổi XLSX sang HTML với GroupDocs.Viewer (Vùng in)
type: docs
url: /vi/java/advanced-rendering/java-groupdocs-viewer-render-print-areas-spreadsheet/
weight: 1
---

# Chuyển đổi XLSX sang HTML trong Java – Kết xuất khu vực in của bảng tính với GroupDocs.Viewer

Nếu bạn cần **chuyển đổi XLSX sang HTML** nhanh chóng đồng thời chỉ hiển thị những phần quan trọng của workbook, việc kết xuất các khu vực in đã được định nghĩa là cách tốt nhất. Hướng dẫn này sẽ chỉ cho bạn cách xây dựng giải pháp preview bằng Java, trích xuất chỉ các khu vực in từ tệp Excel và xuất ra các trang HTML sạch, tự chứa bằng **GroupDocs.Viewer for Java**. Bạn sẽ thấy tại sao cách tiếp cận này giúp tăng tốc độ tải, giảm băng thông và giữ giao diện UI gọn gàng—hoàn hảo cho các portal, dashboard và bất kỳ trình xem tài liệu web nào.

![Kết xuất khu vực in của bảng tính với GroupDocs.Viewer for Java](/viewer/advanced-rendering/spreadsheet-print-areas-rendering-java.png)

## Câu trả lời nhanh
- **“Chuyển đổi XLSX sang HTML” có nghĩa là gì?** Đó là việc chuyển đổi một workbook Excel thành các trang HTML sẵn sàng cho web một cách lập trình.  
- **Tại sao chỉ kết xuất khu vực in của Excel?** Nó cô lập dữ liệu quan trọng nhất, giảm thời gian kết xuất và băng thông.  
- **Có cần giấy phép để thử không?** Có bản dùng thử miễn phí hoặc giấy phép tạm thời; giấy phép đầy đủ cần thiết cho môi trường production.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc mới hơn (Java 11 được khuyến nghị).  
- **Có thể nhúng preview vào trang web không?** Có—sử dụng tùy chọn embedded‑resources để tạo các trang HTML tự chứa.

## “Chuyển đổi XLSX sang HTML” là gì?
Chuyển đổi tệp XLSX sang HTML có nghĩa là lấy bố cục trực quan của bảng tính và xuất nó dưới dạng markup HTML mà các trình duyệt có thể hiển thị mà không cần Excel. Đây là kỹ thuật cốt lõi để **preview bảng tính** trong các ứng dụng web, cho phép người dùng xem dữ liệu ngay lập tức và an toàn.

## Tại sao chỉ kết xuất khu vực in của Excel?
- **Hiệu năng:** Payload HTML nhỏ hơn tải nhanh hơn.  
- **Rõ ràng:** Người dùng chỉ thấy các phần được đánh dấu để in, tránh lộn xộn.  
- **Bảo mật:** Các worksheet không mong muốn sẽ bị ẩn khỏi preview.  

## Yêu cầu trước
- **GroupDocs.Viewer for Java** v25.2 hoặc mới hơn.  
- Maven đã được cài đặt trên máy phát triển của bạn.  
- JDK 8 hoặc mới hơn (Java 11 được khuyến nghị).  
- Một IDE (IntelliJ IDEA, Eclipse, hoặc VS Code).  

## Cài đặt GroupDocs.Viewer for Java
Thêm repository và dependency của GroupDocs vào file `pom.xml` của bạn:

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
Bắt đầu với **bản dùng thử miễn phí** hoặc yêu cầu **giấy phép tạm thời** để đánh giá. Khi đã sẵn sàng cho production, mua giấy phép đầy đủ để mở khóa tất cả tính năng và loại bỏ các hạn chế của bản dùng thử.

### Khởi tạo cơ bản
Dưới đây là đoạn mã tối thiểu cần thiết để mở một bảng tính bằng GroupDocs.Viewer:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer object with the path to your spreadsheet
try (Viewer viewer = new Viewer("path/to/your/spreadsheet.xlsx")) {
    // Further configurations will be discussed in upcoming sections.
}
```

## Cách chuyển đổi XLSX sang HTML với GroupDocs.Viewer
Dưới đây là hướng dẫn từng bước để **kết xuất khu vực in của Excel** chỉ, tạo ra các tệp HTML tự chứa.

### Bước 1: Định nghĩa thư mục đầu ra và định dạng đường dẫn tệp
Đầu tiên, cho Viewer biết nơi ghi các trang HTML đã tạo.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Set the output directory path
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");

// Define a file path format for the rendered pages
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Giải thích:* `outputDirectory` là thư mục sẽ chứa tất cả các tệp preview. `pageFilePathFormat` sử dụng placeholder (`{0}`) mà Viewer sẽ thay thế bằng số trang.

### Bước 2: Cấu hình HTML View Options cho việc kết xuất khu vực in
Cấu hình Viewer để nhúng tài nguyên (CSS, hình ảnh) trực tiếp và tập trung vào các khu vực in đã định nghĩa.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
import com.groupdocs.viewer.options.SpreadsheetOptions;

// Configure HTML view options with embedded resources and print area rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forRenderingPrintArea());
```

*Giải thích:* `HtmlViewOptions.forEmbeddedResources` tạo một tệp HTML duy nhất cho mỗi trang, chứa toàn bộ CSS/JS nội tuyến, giúp triển khai đơn giản hơn. `forRenderingPrintArea()` chỉ báo cho engine **kết xuất khu vực in của Excel**.

### Bước 3: Tải bảng tính và thực hiện kết xuất
Cuối cùng, chỉ định Viewer tới workbook của bạn và gọi quá trình kết xuất.

```java
// Replace with your actual document path
Path documentPath = Paths.get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_PRINT_AREAS.xlsx");

try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Render to HTML using the configured view options
    viewer.view(viewOptions);
}
```

*Giải thích:* Phương thức `view()` xử lý workbook theo các tùy chọn đã thiết lập, xuất ra các tệp HTML chỉ hiển thị các phần khu vực in.

## Các vấn đề thường gặp và giải pháp
- **Lỗi đường dẫn tệp:** Kiểm tra lại các đường dẫn là tuyệt đối hoặc tương đối đúng so với thư mục làm việc của dự án.  
- **Vấn đề quyền truy cập:** Đảm bảo tiến trình Java có quyền đọc tệp nguồn và ghi vào thư mục đầu ra.  
- **Không có khu vực in:** Xác nhận rằng bảng tính thực sự đã định nghĩa khu vực in (Page Layout → Print Area trong Excel).  

## Ứng dụng thực tiễn
1. **Hệ thống quản lý tài liệu:** Hiển thị preview sạch sẽ của báo cáo cho người dùng cuối mà không tải toàn bộ workbook.  
2. **Dashboard tài chính:** Tự động tạo ảnh chụp HTML của các bảng tài chính quan trọng được đánh dấu làm khu vực in.  
3. **Nền tảng học tập:** Cung cấp cho sinh viên các view tập trung vào dữ liệu bài tập.  
4. **Cổng thông tin CRM:** Nổi bật các chỉ số khách hàng trong khi ẩn các worksheet nội bộ.  
5. **Notebook khoa học dữ liệu:** Nhúng preview bảng tính ngắn gọn trong tài liệu.  

## Mẹo tối ưu hiệu năng
- **Tinh chỉnh bộ nhớ:** Đối với workbook rất lớn, tăng heap JVM (`-Xmx2g` hoặc cao hơn).  
- **Lazy loading:** Nếu chỉ cần vài trang đầu, dừng kết xuất sau số trang cần thiết.  
- **Xử lý song song:** Kết xuất nhiều workbook đồng thời bằng các instance `Viewer` riêng biệt (mỗi instance trong một thread).  

## Cách preview bảng tính mà không dùng khu vực in
Nếu sau này bạn muốn hiển thị toàn bộ workbook, chỉ cần bỏ qua lời gọi `SpreadsheetOptions.forRenderingPrintArea()` và sử dụng `SpreadsheetOptions` mặc định. Điều này sẽ cho bạn trải nghiệm **chuyển đổi bảng tính sang HTML** đầy đủ.

## Kết luận
Bạn đã học cách **chuyển đổi XLSX sang HTML** trong Java đồng thời chỉ kết xuất các khu vực in đã định nghĩa của bảng tính. Kỹ thuật này làm cho preview nhanh hơn, gọn gàng hơn và an toàn hơn—hoàn hảo cho các ứng dụng web và doanh nghiệp hiện đại.

### Các bước tiếp theo
- Thử nghiệm các định dạng view khác (PDF, PNG) bằng `PdfViewOptions` hoặc `PngViewOptions`.  
- Kết hợp việc tạo preview với xác thực để bảo vệ dữ liệu nhạy cảm.  
- Khám phá toàn bộ API `SpreadsheetOptions` để tùy chỉnh kích thước trang, lưới và hơn thế nữa.  

## Câu hỏi thường gặp

**H: Lợi ích chính của việc kết xuất chỉ khu vực in của Excel là gì?**  
Đ: Nó giảm bớt sự lộn xộn và tăng tốc độ kết xuất, cung cấp một preview tập trung vào dữ liệu quan trọng nhất.

**H: Tôi có thể kết xuất các worksheet không phải in được không?**  
Đ: Có—bỏ qua `SpreadsheetOptions.forRenderingPrintArea()` và dùng các tùy chọn mặc định để kết xuất toàn bộ workbook.

**H: GroupDocs.Viewer có hỗ trợ các định dạng bảng tính khác không?**  
Đ: Nó hỗ trợ XLS, XLSX, CSV, ODS và một số định dạng khác. Xem tài liệu chính thức để biết danh sách đầy đủ.

**H: Làm sao cải thiện tốc độ kết xuất cho các tệp rất lớn?**  
Đ: Tăng kích thước heap JVM, chỉ kết xuất các trang cần thiết và cân nhắc xử lý đa luồng.

**H: Các khu vực in của tôi không hiển thị—cần kiểm tra gì?**  
Đ: Đảm bảo khu vực in đã được định nghĩa trong tệp nguồn (Excel → Page Layout → Print Area) và bạn đang dùng phiên bản GroupDocs.Viewer mới nhất.

## Tài nguyên
- **Tài liệu:** [GroupDocs.Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Tham chiếu API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Tải về:** [Get GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Mua giấy phép:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Bản dùng thử:** [Start with a Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Giấy phép tạm thời:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Hỗ trợ:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-03-19  
**Kiểm thử với:** GroupDocs.Viewer for Java 25.2  
**Tác giả:** GroupDocs  

---