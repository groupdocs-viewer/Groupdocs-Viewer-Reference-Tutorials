---
date: '2026-04-06'
description: Tìm hiểu cách hiển thị HTML, cách hiển thị HTML mà không bao gồm phông
  Arial và tối ưu hoá việc hiển thị HTML bằng GroupDocs.Viewer cho Java. Hướng dẫn
  từng bước cho việc chuyển đổi docx sang HTML trong Java.
keywords:
- how to render html
- convert docx to html
- embed resources html
- groupdocs viewer html
- optimize html rendering
title: Cách hiển thị HTML và loại trừ phông chữ Arial với GroupDocs.Viewer Java
type: docs
url: /vi/java/custom-rendering/exclude-arial-font-groupdocs-viewer-java/
weight: 1
---

# Cách Render HTML và Loại Trừ Phông Chữ Arial với GroupDocs.Viewer Java

Rendering documents to HTML is a common requirement for web‑based applications, but unwanted fonts can break visual consistency. In this tutorial, you’ll learn **how to render html** while excluding the Arial font, ensuring your output matches your design guidelines. We'll also cover how to **convert docx to html**, embed resources in the generated pages, and **optimize html rendering** for better performance.

![Loại Trừ Phông Chữ Arial trong Render HTML với GroupDocs.Viewer cho Java](/viewer/custom-rendering/exclude-arial-font-in-html-rendering-java.png)

**Bạn Sẽ Học:**
- Cách cấu hình GroupDocs.Viewer cho Java để render tài liệu dưới dạng HTML.
- Quá trình loại bỏ các phông chữ cụ thể như Arial trong quá trình chuyển đổi tài liệu.
- Các thực tiễn tốt nhất và các cân nhắc về hiệu suất khi sử dụng GroupDocs.Viewer Java.

## Câu trả lời nhanh
- **Cách render html?** Sử dụng `HtmlViewOptions` với GroupDocs.Viewer Java để tạo các trang HTML tự chứa.  
- **Tôi có thể loại bỏ phông chữ Arial không?** Có — gọi `viewOptions.getFontsToExclude().add("Arial")`.  
- **Phiên bản thư viện nào?** Hướng dẫn này sử dụng GroupDocs.Viewer cho Java 25.2 (hoặc bản phát hành ổn định mới nhất).  
- **Các định dạng đầu vào được hỗ trợ?** DOCX, PDF, PPTX, XLSX và nhiều hơn nữa.  
- **Cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.

## Cách Render HTML với GroupDocs.Viewer Java
Trước khi đi vào mã, hãy hiểu tại sao việc render HTML lại có giá trị. Đầu ra HTML cho phép bạn hiển thị tài liệu trực tiếp trong trình duyệt mà không cần các trình xem bên ngoài, làm cho nó trở nên lý tưởng cho các cổng thông tin web, tích hợp CMS và bản xem trước thân thiện với thiết bị di động.

## Yêu cầu trước

- **Thư viện & Phiên bản**: Bạn sẽ cần GroupDocs.Viewer cho Java phiên bản 25.2.
- **Cài đặt môi trường**: Môi trường phát triển Java (IDE như IntelliJ IDEA hoặc Eclipse) và Maven đã được cài đặt trên máy của bạn.
- **Kiến thức nền**: Hiểu biết cơ bản về lập trình Java và quen thuộc với cấu hình dự án Maven.

## Cài đặt GroupDocs.Viewer cho Java

Để bắt đầu, thêm phụ thuộc cần thiết cho GroupDocs.Viewer vào tệp `pom.xml` của bạn bằng Maven:

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

### Các bước lấy giấy phép
- **Dùng thử miễn phí**: Tải bản dùng thử miễn phí từ [GroupDocs Free Trials](https://releases.groupdocs.com/viewer/java/).
- **Giấy phép tạm thời**: Đăng ký giấy phép tạm thời qua [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) để thử nghiệm kéo dài.
- **Mua**: Mua giấy phép đầy đủ trên [Purchase Page](https://purchase.groupdocs.com/buy) khi đã hài lòng với khả năng của GroupDocs.Viewer.

### Khởi tạo và Cấu hình Cơ bản

Sau khi thiết lập dự án Maven, tạo một lớp Java mới và nhập các gói GroupDocs cần thiết. Cấu hình này là cần thiết để khởi tạo viewer và render tài liệu.

## Cách Loại Trừ Phông Chữ Arial Khi Render HTML

### Tổng quan
Việc loại bỏ các phông chữ cụ thể cho phép bạn kiểm soát chặt chẽ hơn đầu ra hình ảnh của quá trình chuyển đổi HTML, giúp bạn **tối ưu hóa render html** cho tốc độ và tính nhất quán thương hiệu.

### Thực hiện theo từng bước

#### 1. Xác định Thư mục Đầu ra
Bắt đầu bằng cách chỉ định nơi sẽ lưu các tệp HTML:

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
```

Đường dẫn này xác định nơi các tài liệu HTML đã render sẽ được lưu trữ.

#### 2. Thiết lập Đường dẫn Tệp Trang HTML
Xác định cách đặt tên tệp cho mỗi trang:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

Biến chỗ `{0}` cho phép đặt tên tệp động dựa trên số trang, đảm bảo lưu trữ có tổ chức.

#### 3. Cấu hình Tùy chọn View với Tài nguyên Nhúng
Tạo một đối tượng `HtmlViewOptions` xác định cách xử lý render HTML:

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

Cấu hình này đảm bảo tất cả tài nguyên được nhúng trong các tệp HTML, làm cho chúng **tự chứa** và lý tưởng cho các kịch bản **embed resources html**.

#### 4. Loại Trừ Các Phông Chữ Cụ Thể
Thêm phông chữ bạn muốn loại bỏ (trong trường hợp này là Arial) khỏi quá trình render trong đầu ra:

```java
viewOptions.getFontsToExclude().add("Arial");
```

Việc loại bỏ phông chữ có thể quan trọng để duy trì tính nhất quán thiết kế và giảm kích thước tệp.

#### 5. Render Tài liệu bằng Viewer
Cuối cùng, sử dụng lớp `Viewer` để render tài liệu của bạn sang định dạng HTML:

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

Câu lệnh try‑with‑resources đảm bảo `viewer` được đóng đúng cách sau khi render.

### Mẹo Khắc phục Sự cố
- **Vấn đề thường gặp**: Đảm bảo các đường dẫn đúng và có thể truy cập; đường dẫn sai có thể gây lỗi không tìm thấy tệp.
- **Mẹo hiệu suất**: Khi render tài liệu lớn, theo dõi việc sử dụng bộ nhớ vì tài nguyên nhúng có thể làm tăng thời gian tải.

## Cách Chuyển Đổi DOCX sang HTML Sử dụng GroupDocs.Viewer
Cấu hình `HtmlViewOptions` tương tự hoạt động cho bất kỳ định dạng nào được hỗ trợ, bao gồm DOCX. Chỉ cần trỏ constructor `Viewer` tới tệp `.docx`, và thư viện sẽ thực hiện chuyển đổi đồng thời tuân theo cài đặt loại trừ phông chữ.

## Tại Sao Điều Này Quan Trọng: Các Trường Hợp Thực Tế

1. **Báo cáo doanh nghiệp** – Loại bỏ phông chữ mặc định để giữ báo cáo phù hợp với hướng dẫn thương hiệu.  
2. **Tài liệu giáo dục** – Tùy chỉnh render phông chữ để cải thiện khả năng đọc trên các thiết bị.  
3. **Tài liệu pháp lý** – Duy trì giao diện đồng nhất cho các bản trình bày HTML sẵn sàng cho tòa án.  
4. **Danh sách thương mại điện tử** – Đảm bảo mô tả sản phẩm tuân theo tiêu chuẩn thương hiệu.  
5. **Tích hợp CMS** – Cung cấp các bản xem trước sạch sẽ, kiểm soát phông chữ trong hệ thống quản lý nội dung.

## Tối Ưu Hiệu Suất Render HTML

### Mẹo để Chuyển Đổi Nhanh Hơn
- **Sử dụng Đường dẫn Tệp Hiệu quả**: Giữ cấu trúc thư mục nông để giảm tải I/O.
- **Giới hạn Tài nguyên Nhúng**: Chỉ nhúng CSS/JS cần thiết để giữ HTML nhẹ.

### Thực hành tốt cho Quản lý Bộ nhớ Java
- **Đóng Viewer Kịp thời**: Mẫu `try‑with‑resources` giải phóng bộ nhớ ngay khi render hoàn tất.
- **Giám sát Tải Ứng dụng**: Đánh giá JVM khi xử lý nhiều tài liệu hoặc tài liệu lớn để tránh lỗi hết bộ nhớ.

## Câu Hỏi Thường Gặp

**Q1: GroupDocs.Viewer được dùng để làm gì?**  
A1: Đây là một thư viện mạnh mẽ cho phép các nhà phát triển render tài liệu ở nhiều định dạng như HTML, hình ảnh hoặc PDF.

**Q2: Làm sao để loại bỏ các phông chữ khác ngoài Arial?**  
A2: Sử dụng phương thức `getFontsToExclude().add("FONT_NAME")` với tên phông chữ mong muốn.

**Q3: GroupDocs.Viewer có thể xử lý chuyển đổi tài liệu lớn một cách hiệu quả không?**  
A3: Có, bằng cách tối ưu hóa việc xử lý tài nguyên và thực hành quản lý bộ nhớ như đã mô tả trong hướng dẫn này.

**Q4: Một số vấn đề thường gặp khi thiết lập GroupDocs.Viewer là gì?**  
A4: Các vấn đề thường gặp bao gồm cấu hình đường dẫn sai hoặc thiếu phụ thuộc Maven. Kiểm tra lại tất cả các đường dẫn và đảm bảo các tọa độ Maven đúng.

**Q5: Tôi có thể tìm thêm tài nguyên về việc sử dụng GroupDocs.Viewer với Java ở đâu?**  
A5: Truy cập [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) để xem các hướng dẫn chi tiết và tài liệu API.

**Q6: Cách này có hoạt động cho việc chuyển đổi DOCX sang HTML trong Java không?**  
A6: Hoàn toàn có—chỉ cần trỏ constructor `Viewer` tới tệp `.docx`, và logic loại trừ phông chữ sẽ được áp dụng.

**Q7: Làm sao tôi có thể **tối ưu hóa render html** hơn cho thiết bị di động?**  
A7: Xem xét việc giảm thiểu (minify) HTML đã tạo và cung cấp CSS đáp ứng cùng với các tài nguyên nhúng.

**Q8: Có bắt buộc có giấy phép cho các bản dựng phát triển không?**  
A8: Bản dùng thử miễn phí đủ cho phát triển và thử nghiệm; giấy phép thương mại cần thiết cho triển khai sản xuất.

## Tài Nguyên
- **Tài liệu**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Tham chiếu API**: [GroupDocs Viewer Java API](https://reference.groupdocs.com/viewer/java/)
- **Tải GroupDocs.Viewer**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Mua Giấy phép**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Dùng thử và Giấy phép Tạm thời**: [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/) | [Request a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Hỗ trợ**: Nếu cần trợ giúp thêm, truy cập [GroupDocs Support Page](https://support.groupdocs.com/hc/en-us/).

---

**Cập nhật lần cuối:** 2026-04-06  
**Được kiểm tra với:** GroupDocs.Viewer for Java 25.2  
**Tác giả:** GroupDocs