---
date: '2025-12-20'
description: Tìm hiểu cách giới hạn số mục trong thư mục Outlook bằng cách cấu hình
  số mục tối đa mỗi thư mục trong GroupDocs.Viewer cho Java, nâng cao hiệu suất khi
  hiển thị các tệp PST/OST lớn.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: Cách thiết lập số mục tối đa mỗi thư mục trong việc hiển thị Outlook bằng GroupDocs.Viewer
  cho Java
type: docs
url: /vi/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Giới hạn việc hiển thị mục Outlook trong Java bằng GroupDocs.Viewer

Quản lý các tệp dữ liệu Outlook khổng lồ (PST hoặc OST) có thể nhanh chóng trở thành nút thắt hiệu năng. Trong hướng dẫn này, bạn sẽ khám phá cách **max items per folder** khi hiển thị bằng GroupDocs.Viewer cho Java, để chỉ xử lý dữ liệu bạn thực sự cần. Bằng cách áp dụng kỹ thuật **limit items outlook folder**, ứng dụng của bạn vẫn phản hồi nhanh ngay cả khi có hàng gigabyte dữ liệu email.

![Giới hạn việc hiển thị mục Outlook với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Những gì bạn sẽ học
- Cài đặt GroupDocs.Viewer cho Java
- Cấu hình thư viện để **max items per folder** trong các tệp Outlook
- Các kịch bản thực tế nơi việc giới hạn mục trong mỗi thư mục cải thiện tốc độ và giảm sử dụng bộ nhớ

Hãy cùng đi qua quá trình cài đặt và triển khai từng bước.

## Câu trả lời nhanh
- **max items per folder** làm gì? Nó giới hạn việc hiển thị tới một số lượng nhất định các mục email trong mỗi thư mục Outlook.  
- **Why limit items outlook folder?** Để giảm thời gian xử lý và tiêu thụ bộ nhớ cho các hộp thư lớn.  
- **Which version supports this feature?** GroupDocs.Viewer 25.2 and later.  
- **Do I need a license?** Có, cần có giấy phép dùng thử hoặc mua để sử dụng trong môi trường sản xuất.  
- **Can I change the limit at runtime?** Chắc chắn – chỉ cần sửa giá trị `setMaxItemsInFolder` trước khi hiển thị.

## Tổng quan
Gặp khó khăn trong việc quản lý các tệp dữ liệu Outlook lớn như PST hoặc OST? Hướng dẫn này trình bày cách giới hạn số lượng mục được xử lý khi hiển thị các tệp này bằng GroupDocs.Viewer cho Java, nâng cao hiệu quả và khả năng phản hồi của ứng dụng.

### “max items per folder” là gì?
Cài đặt **max items per folder** chỉ cho trình xem dừng lại sau khi đã hiển thị một số lượng mục nhất định trong mỗi thư mục. Điều này đặc biệt hữu ích khi bạn chỉ cần xem trước các email gần đây hoặc khi bạn tạo báo cáo không yêu cầu toàn bộ hộp thư.

### Tại sao nên sử dụng cách tiếp cận limit items outlook folder?
- **Hiệu năng:** Thời gian hiển thị nhanh hơn và sử dụng CPU thấp hơn.  
- **Khả năng mở rộng:** Xử lý các hộp thư lớn hơn mà không làm cạn kiệt bộ nhớ JVM.  
- **Linh hoạt:** Điều chỉnh giới hạn dựa trên sở thích của người dùng hoặc khả năng của thiết bị.

## Yêu cầu trước
Đảm bảo bạn có những thứ sau trước khi bắt đầu:

### Thư viện và phụ thuộc cần thiết:
1. **Java Development Kit (JDK)**: Cài đặt JDK 8 hoặc mới hơn.  
2. **GroupDocs.Viewer for Java**: Thêm vào dự án như một phụ thuộc.

### Yêu cầu thiết lập môi trường:
- Một IDE phù hợp như IntelliJ IDEA, Eclipse hoặc NetBeans.  
- Maven đã được cài đặt nếu bạn quản lý phụ thuộc qua Maven.

### Kiến thức yêu cầu:
- Hiểu biết cơ bản về lập trình Java và xử lý tệp.  
- Quen thuộc với các dự án Maven là lợi thế nhưng không bắt buộc.

## Cài đặt GroupDocs.Viewer cho Java
Cài đặt GroupDocs.Viewer trong dự án của bạn bằng Maven:

**Cấu hình Maven:**  
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
- **Free Trial**: Tải bản dùng thử miễn phí từ [GroupDocs](https://releases.groupdocs.com/viewer/java/) để khám phá các tính năng của thư viện.  
- **Temporary License**: Nhận giấy phép tạm thời để truy cập đầy đủ mà không có giới hạn đánh giá tại [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase**: Đối với việc sử dụng lâu dài, hãy cân nhắc mua giấy phép từ [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Khởi tạo và cài đặt cơ bản
Sau khi Maven được cấu hình, khởi tạo GroupDocs.Viewer trong ứng dụng Java của bạn bằng cách thiết lập đối tượng viewer. Điều này cho phép bạn tải và hiển thị tài liệu.

## Hướng dẫn triển khai

### Giới hạn các mục được hiển thị từ tệp Outlook
Phần này chi tiết cách giới hạn các mục được hiển thị từ các tệp dữ liệu Outlook bằng GroupDocs.Viewer cho Java.

#### Tổng quan
Bằng cách cấu hình các tùy chọn cụ thể, bạn có thể giới hạn việc hiển thị tới một số lượng nhất định các mục trong mỗi thư mục. Tính năng này nâng cao hiệu năng và hiệu quả khi xử lý các bộ dữ liệu email lớn.

**Bước 1: Thiết lập đường dẫn thư mục đầu ra**  
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```
Đoạn mã này thiết lập thư mục nơi các tệp HTML đã hiển thị sẽ được lưu. Thay thế `"LimitCountOfItemsToRender"` bằng tên đường dẫn bạn mong muốn.

**Bước 2: Xác định định dạng đường dẫn tệp cho các trang HTML**  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
Tạo một định dạng đặt tên nhất quán cho các trang HTML được tạo trong quá trình hiển thị, đảm bảo dễ dàng truy cập và quản lý.

**Bước 3: Cấu hình HtmlViewOptions với tài nguyên nhúng**  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
Tùy chọn này chỉ định cách tài liệu được hiển thị với các tài nguyên nhúng, cho phép tích hợp tốt hơn các hình ảnh và kiểu dáng.

**Bước 4: Đặt tùy chọn Outlook để giới hạn mục trong mỗi thư mục**  
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```
Ở đây, chúng tôi **max items per folder** thành ba. Điều chỉnh số lượng dựa trên yêu cầu của bạn cho kịch bản **limit items outlook folder**.

**Bước 5: Tải và hiển thị tài liệu**  
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```
Sử dụng lớp `Viewer` để tải tệp OST và hiển thị nó theo các tùy chọn xem đã định nghĩa. Câu lệnh try‑with‑resources đảm bảo các tài nguyên được đóng đúng cách sau khi sử dụng.

### Mẹo khắc phục sự cố
- Đảm bảo tất cả các đường dẫn và thư mục tồn tại trước khi chạy mã của bạn.  
- Xác nhận rằng các phụ thuộc của GroupDocs.Viewer được Maven giải quyết đúng cách.  
- Kiểm tra bất kỳ ngoại lệ nào trong quá trình hiển thị, có thể cho thấy vấn đề với định dạng tệp hoặc quyền truy cập.

## Ứng dụng thực tế
1. **Email Archiving** – Giới hạn việc hiển thị mục là lý tưởng cho các ứng dụng tập trung vào việc lưu trữ các email cụ thể thay vì toàn bộ bộ dữ liệu.  
2. **Data Migration** – Khi di chuyển dữ liệu giữa các hệ thống, chỉ hiển thị các mục cần thiết để tối ưu hiệu năng và giảm thời gian xử lý.  
3. **Custom Reporting** – Tạo báo cáo bằng cách chọn lọc hiển thị nội dung email cần thiết mà không tải toàn bộ thư mục.

## Các cân nhắc về hiệu năng
### Mẹo tối ưu hóa hiệu năng
- Giới hạn số lượng mục trong mỗi thư mục để giảm việc sử dụng bộ nhớ.  
- Sử dụng tài nguyên nhúng một cách hiệu quả để tránh các cuộc gọi mạng bổ sung trong quá trình hiển thị.

### Hướng dẫn sử dụng tài nguyên
- Giám sát bộ nhớ JVM và điều chỉnh cài đặt dựa trên kích thước của các tệp Outlook đang được xử lý.

### Các thực hành tốt nhất cho quản lý bộ nhớ Java
- Sử dụng try‑with‑resources để quản lý tài nguyên tự động.  
- Thực hiện profiling ứng dụng để xác định các nút thắt liên quan đến việc xử lý tệp lớn.

## Kết luận
Trong hướng dẫn này, bạn đã học cách hiệu quả **max items per folder** trong các tệp dữ liệu Outlook bằng GroupDocs.Viewer cho Java. Bằng cách thực hiện các bước này và cân nhắc các mẹo về hiệu năng, bạn có thể tạo các ứng dụng hiệu quả phù hợp với nhu cầu cụ thể.

### Các bước tiếp theo
- Khám phá các tính năng bổ sung của GroupDocs.Viewer bằng cách tham khảo [tài liệu chính thức](https://docs.groupdocs.com/viewer/java/).  
- Thử nghiệm các tùy chọn hiển thị khác nhau để tìm cấu hình tốt nhất cho yêu cầu của ứng dụng của bạn.

Sẵn sàng thử chưa? Bắt đầu triển khai giải pháp này trong các dự án của bạn ngay hôm nay và trải nghiệm hiệu quả cải thiện ngay lập tức.

## Câu hỏi thường gặp

**Q: GroupDocs.Viewer Java được dùng để làm gì?**  
A: Đó là một thư viện đa năng được thiết kế để hiển thị nhiều định dạng tài liệu, bao gồm các tệp dữ liệu Outlook, thành định dạng HTML hoặc hình ảnh.

**Q: Làm thế nào để tôi có được bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) để có quyền truy cập và các tùy chọn tải xuống.

**Q: Tôi có thể giới hạn việc hiển thị mục trong các tệp PST không?**  
A: Có, cùng một cấu hình áp dụng cho cả định dạng tệp OST và PST.

**Q: Tôi nên làm gì nếu ứng dụng của tôi chạy chậm trong quá trình hiển thị?**  
A: Xem lại giới hạn mục và cài đặt tài nguyên; cân nhắc tối ưu các thực hành quản lý bộ nhớ.

**Q: Tôi có thể tìm hỗ trợ cho các vấn đề của GroupDocs.Viewer ở đâu?**  
A: Để được hỗ trợ, hãy kiểm tra [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Tài nguyên bổ sung
- [Tài liệu](https://docs.groupdocs.com/viewer/java/)
- [Tham chiếu API](https://reference.groupdocs.com/viewer/java/)
- [Tải GroupDocs.Viewer cho Java](https://releases.groupdocs.com/viewer/java/)
- [Mua giấy phép](https://purchase.groupdocs.com/buy)
- [Phiên bản dùng thử miễn phí](https://releases.groupdocs.com/viewer/java/)
- [Đơn xin giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2025-12-20  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs