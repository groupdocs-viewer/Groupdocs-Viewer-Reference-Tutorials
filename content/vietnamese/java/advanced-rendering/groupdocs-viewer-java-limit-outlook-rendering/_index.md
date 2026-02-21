---
date: '2026-02-21'
description: Tìm hiểu cách đặt số mục tối đa cho mỗi thư mục khi hiển thị tệp Outlook
  bằng GroupDocs.Viewer cho Java, cải thiện hiệu suất cho các tệp PST/OST lớn.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: Cách đặt số mục tối đa cho mỗi thư mục trong việc hiển thị Outlook bằng GroupDocs.Viewer
  cho Java
type: docs
url: /vi/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Giới hạn việc render mục Outlook trong Java bằng GroupDocs.Viewer

Quản lý các tệp dữ liệu Outlook khổng lồ (PST hoặc OST) có thể nhanh chóng trở thành nút thắt hiệu năng. Trong hướng dẫn này, bạn sẽ khám phá cách **đặt số mục tối đa** cho mỗi thư mục khi render bằng GroupDocs.Viewer cho Java, để chỉ xử lý dữ liệu bạn thực sự cần. Bằng cách áp dụng kỹ thuật **giới hạn số mục mỗi thư mục**, ứng dụng của bạn sẽ luôn phản hồi nhanh ngay cả khi xử lý hàng gigabyte dữ liệu email.

![Giới hạn việc render mục Outlook với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Những gì bạn sẽ học
- Cài đặt GroupDocs.Viewer cho Java  
- Cấu hình thư viện để **đặt số mục tối đa** cho mỗi thư mục trong tệp Outlook  
- Các kịch bản thực tế nơi việc giới hạn số mục mỗi thư mục cải thiện tốc độ và giảm tiêu thụ bộ nhớ  

## Câu trả lời nhanh
- **What does “set max items per folder” do?** Nó hạn chế việc render chỉ trong một số lượng mục email đã định nghĩa trong mỗi thư mục Outlook.  
- **Why limit Outlook items?** Để giảm thời gian xử lý và tiêu thụ bộ nhớ cho các hộp thư lớn.  
- **Which version supports this feature?** GroupDocs.Viewer 25.2 và các phiên bản sau.  
- **Do I need a license?** Có, cần có giấy phép dùng thử hoặc mua để sử dụng trong môi trường sản xuất.  
- **Can I change the limit at runtime?** Chắc chắn – chỉ cần sửa giá trị `setMaxItemsInFolder` trước khi render.  

## Cách đặt số mục tối đa cho mỗi thư mục khi render Outlook
Dưới đây là hướng dẫn chi tiết từng bước giải thích **tại sao** bạn có thể muốn giới hạn các mục Outlook, **cái gì** cài đặt này làm, và **cách** cấu hình nó trong dự án Java của bạn.

### “set max items per folder” là gì?
Tùy chọn **set max items** cho trình xem biết dừng lại sau khi đã render một số lượng mục nhất định trong mỗi thư mục. Điều này đặc biệt hữu ích khi bạn chỉ cần xem trước các email gần đây hoặc khi tạo báo cáo không yêu cầu toàn bộ hộp thư.

### Tại sao nên sử dụng cách tiếp cận giới hạn số mục mỗi thư mục?
- **Performance:** Thời gian render nhanh hơn và mức sử dụng CPU thấp hơn.  
- **Scalability:** Xử lý các hộp thư lớn mà không làm cạn kiệt bộ nhớ JVM.  
- **Flexibility:** Điều chỉnh giới hạn dựa trên sở thích người dùng hoặc khả năng của thiết bị.  

## Yêu cầu trước
Đảm bảo bạn có những thứ sau trước khi bắt đầu:

### Thư viện và phụ thuộc cần thiết
1. **Java Development Kit (JDK)** – Cài đặt JDK 8 hoặc mới hơn.  
2. **GroupDocs.Viewer for Java** – Thêm vào như một phụ thuộc trong dự án của bạn.

### Yêu cầu cài đặt môi trường
- Một IDE phù hợp như IntelliJ IDEA, Eclipse, hoặc NetBeans.  
- Maven đã được cài đặt nếu bạn quản lý phụ thuộc qua Maven.

### Kiến thức nền tảng cần có
- Hiểu biết cơ bản về lập trình Java và xử lý tệp.  
- Quen thuộc với các dự án Maven là lợi thế nhưng không bắt buộc.

## Cài đặt GroupDocs.Viewer cho Java
Cài đặt GroupDocs.Viewer trong dự án của bạn bằng Maven:

**Maven Configuration:**
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
- **Purchase**: Đối với việc sử dụng lâu dài, cân nhắc mua giấy phép từ [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).  

### Khởi tạo và cài đặt cơ bản
Sau khi Maven được cấu hình, khởi tạo GroupDocs.Viewer trong ứng dụng Java của bạn bằng cách thiết lập đối tượng viewer. Điều này cho phép bạn tải và render tài liệu.

## Hướng dẫn thực hiện

### Giới hạn các mục được render từ tệp Outlook
Phần này mô tả cách giới hạn các mục được render từ các tệp dữ liệu Outlook bằng GroupDocs.Viewer cho Java.

#### Tổng quan
Bằng cách cấu hình các tùy chọn cụ thể, bạn có thể hạn chế việc render chỉ trong một số lượng mục nhất định cho mỗi thư mục. Tính năng này nâng cao hiệu năng và hiệu quả khi làm việc với các bộ dữ liệu email lớn.

**Bước 1: Thiết lập đường dẫn thư mục đầu ra**
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```
Mã này thiết lập thư mục nơi các tệp HTML đã render sẽ được lưu. Thay `"LimitCountOfItemsToRender"` bằng tên đường dẫn bạn mong muốn.

**Bước 2: Xác định định dạng đường dẫn tệp cho các trang HTML**
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
Tạo một định dạng đặt tên nhất quán cho các trang HTML được tạo trong quá trình render, giúp dễ dàng truy cập và quản lý.

**Bước 3: Cấu hình HtmlViewOptions với tài nguyên nhúng**
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
Tùy chọn này chỉ định cách tài liệu được render với các tài nguyên nhúng, cho phép tích hợp tốt hơn hình ảnh và kiểu dáng.

**Bước 4: Đặt tùy chọn Outlook để giới hạn số mục mỗi thư mục**
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```
Ở đây, chúng tôi **đặt số mục tối đa** là ba. Điều chỉnh số lượng dựa trên yêu cầu của bạn cho kịch bản **giới hạn số mục mỗi thư mục**.

**Bước 5: Tải và render tài liệu**
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```
Sử dụng lớp `Viewer` để tải tệp OST và render nó theo các tùy chọn view đã định nghĩa. Câu lệnh try‑with‑resources đảm bảo các tài nguyên được đóng đúng cách sau khi sử dụng.

### Mẹo khắc phục sự cố
- Đảm bảo tất cả các đường dẫn và thư mục tồn tại trước khi chạy mã của bạn.  
- Xác nhận rằng các phụ thuộc GroupDocs.Viewer được Maven giải quyết đúng cách.  
- Kiểm tra bất kỳ ngoại lệ nào trong quá trình render, có thể chỉ ra vấn đề về định dạng tệp hoặc quyền truy cập.

## Ứng dụng thực tiễn
1. **Email Archiving** – Giới hạn việc render là lý tưởng cho các ứng dụng tập trung vào lưu trữ các email cụ thể thay vì toàn bộ dữ liệu.  
2. **Data Migration** – Khi di chuyển dữ liệu giữa các hệ thống, chỉ render các mục cần thiết để tối ưu hiệu năng và giảm thời gian xử lý.  
3. **Custom Reporting** – Tạo báo cáo bằng cách render chọn lọc nội dung email cần thiết mà không tải toàn bộ thư mục.

## Các cân nhắc về hiệu năng
### Mẹo tối ưu hoá hiệu năng
- Giới hạn số lượng mục mỗi thư mục để giảm việc sử dụng bộ nhớ.  
- Sử dụng tài nguyên nhúng một cách hiệu quả để tránh các cuộc gọi mạng bổ sung trong quá trình render.

### Hướng dẫn sử dụng tài nguyên
- Giám sát bộ nhớ JVM và điều chỉnh cài đặt dựa trên kích thước của các tệp Outlook đang được xử lý.

### Các thực hành tốt nhất cho quản lý bộ nhớ Java
- Sử dụng try‑with‑resources để quản lý tài nguyên tự động.  
- Profiling ứng dụng của bạn để xác định các điểm nghẽn liên quan đến việc xử lý tệp lớn.

## Những lỗi thường gặp & Cách tránh
| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Không có tệp đầu ra được tạo | Đường dẫn thư mục đầu ra không đúng hoặc thiếu quyền | Xác minh `outputDirectory` tồn tại và có thể ghi |
| Quá trình render dừng sau một vài mục | `setMaxItemsInFolder` được đặt quá thấp | Tăng giới hạn hoặc làm cho nó có thể cấu hình |
| Lỗi OutOfMemoryError trên PST lớn | Cài đặt bộ nhớ mặc định không đủ | Tăng dung lượng heap JVM (`-Xmx`) và giữ giới hạn thấp |

## Kết luận
Trong tutorial này, bạn đã học cách **đặt số mục tối đa cho mỗi thư mục** trong các tệp dữ liệu Outlook bằng GroupDocs.Viewer cho Java. Bằng cách làm theo các bước và áp dụng các mẹo hiệu năng, bạn có thể tạo ra các ứng dụng hiệu quả, phù hợp với nhu cầu cụ thể của mình.

### Các bước tiếp theo
- Khám phá các tính năng bổ sung của GroupDocs.Viewer bằng cách tham khảo [tài liệu chính thức](https://docs.groupdocs.com/viewer/java/).  
- Thử nghiệm với các tùy chọn render khác nhau để tìm cấu hình tốt nhất cho yêu cầu của ứng dụng.

Sẵn sàng thử ngay? Bắt đầu triển khai giải pháp này trong dự án của bạn hôm nay và trải nghiệm hiệu quả cải thiện ngay lập tức.

## Câu hỏi thường gặp

**Q: GroupDocs.Viewer Java được dùng để làm gì?**  
A: Đây là một thư viện đa năng được thiết kế để render các định dạng tài liệu khác nhau, bao gồm cả tệp dữ liệu Outlook, thành định dạng HTML hoặc hình ảnh.

**Q: Làm sao để có bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) để nhận quyền truy cập và các tùy chọn tải về.

**Q: Tôi có thể giới hạn việc render mục trong tệp PST không?**  
A: Có, cấu hình tương tự áp dụng cho cả định dạng OST và PST.

**Q: Tôi nên làm gì nếu ứng dụng của tôi chạy chậm trong quá trình render?**  
A: Xem lại giới hạn mục và cài đặt tài nguyên; cân nhắc tối ưu hoá các thực hành quản lý bộ nhớ.

**Q: Tôi có thể tìm hỗ trợ cho các vấn đề liên quan đến GroupDocs.Viewer ở đâu?**  
A: Để được trợ giúp, hãy kiểm tra [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Tài nguyên bổ sung
- [Tài liệu](https://docs.groupdocs.com/viewer/java/)
- [Tham chiếu API](https://reference.groupdocs.com/viewer/java/)
- [Tải về GroupDocs.Viewer cho Java](https://releases.groupdocs.com/viewer/java/)
- [Mua giấy phép](https://purchase.groupdocs.com/buy)
- [Phiên bản dùng thử](https://releases.groupdocs.com/viewer/java/)
- [Đăng ký giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-02-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs