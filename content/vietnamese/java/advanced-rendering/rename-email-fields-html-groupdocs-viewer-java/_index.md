---
date: '2026-03-24'
description: Tìm hiểu cách chuyển đổi email sang HTML và đổi tên các trường email
  bằng GroupDocs Viewer cho Java. Hướng dẫn này cho thấy cách hiển thị email dưới
  dạng HTML với các tiêu đề tùy chỉnh.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Chuyển đổi Email sang HTML & Đổi tên các trường – GroupDocs Viewer Java
type: docs
url: /vi/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Chuyển Đổi Email Sang HTML & Đổi Tên Trường – GroupDocs Viewer Java

Nếu bạn cần **chuyển đổi email sang HTML** đồng thời tạo giao diện tùy chỉnh cho tiêu đề email, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua các bước chính xác để đổi tên các trường email, **chuyển đổi email sang HTML**, và tùy chỉnh tiêu đề email bằng GroupDocs.Viewer cho Java. Khi hoàn thành, bạn sẽ có một bản HTML sạch sẽ với các tên tiêu đề mà bạn muốn, giúp kết quả dễ đọc hơn và dễ tích hợp vào ứng dụng của bạn.

![Đổi Tên Trường Email Khi Chuyển Đổi Email Sang HTML với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Những Điều Bạn Sẽ Học
- Cách sử dụng GroupDocs.Viewer cho Java để **chuyển đổi email sang HTML**.  
- Kỹ thuật **đổi tên các trường email** như “From”, “To”, “Sent” và “Subject”.  
- Các thực tiễn tốt nhất để thiết lập Maven và cấp phép.  
- Các kịch bản thực tế nơi **tùy chỉnh tiêu đề email** mang lại giá trị.

## Câu Hỏi Nhanh
- **“Chuyển đổi email sang HTML” có nghĩa là gì?** Nó có nghĩa là hiển thị một tệp email (MSG/EML) dưới dạng tài liệu HTML sẵn sàng cho web.  
- **Thư viện nào thực hiện việc chuyển đổi?** GroupDocs.Viewer cho Java (v25.2+).  
- **Có cần giấy phép không?** Bản dùng thử hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi bất kỳ tên tiêu đề nào không?** Có, bất kỳ tiêu đề email tiêu chuẩn nào cũng có thể được ánh xạ lại qua `fieldTextMap`.  
- **Kết quả là HTML hay tài nguyên nhúng?** Bạn có thể chọn tài nguyên nhúng để tạo một tệp duy nhất tự chứa.

## “Chuyển đổi email sang HTML” trong Ngữ Cảnh của GroupDocs.Viewer là gì?
Chuyển đổi email sang HTML có nghĩa là lấy một tệp email thô và tạo ra một trang HTML hiển thị nội dung tin nhắn cùng với siêu dữ liệu của nó. Khi bạn **đổi tên các trường email**, các nhãn mặc định (ví dụ: “From”) sẽ được thay thế bằng văn bản tùy chỉnh (ví dụ: “Người gửi”), giúp bạn phù hợp với thuật ngữ doanh nghiệp hoặc cải thiện tính nhất quán giao diện người dùng.

## Tại Sao Cần Chuyển Đổi Email Sang HTML và Đổi Tên Các Trường Email?
- **Nhận diện thương hiệu nhất quán:** Đồng bộ đầu ra với ngôn ngữ của tổ chức bạn.  
- **Tăng khả năng tìm kiếm:** Các tiêu đề tùy chỉnh có thể được lập chỉ mục hiệu quả hơn trong hệ thống lưu trữ.  
- **Tích hợp UI tốt hơn:** Tùy chỉnh đoạn HTML để nó khớp liền mạch vào các cổng web hoặc bảng điều khiển hỗ trợ.

## Các Điều Kiện Tiên Quyết

### Thư Viện, Phiên Bản và Phụ Thuộc Yêu Cầu
- **GroupDocs.Viewer cho Java** – phiên bản 25.2 trở lên.  
- **Java Development Kit (JDK)** – phiên bản 8+.

### Yêu Cầu Thiết Lập Môi Trường
- **Maven** để quản lý phụ thuộc.  
- Một IDE như IntelliJ IDEA, Eclipse hoặc VS Code.

### Kiến Thức Tiên Quyết
Kiến thức cơ bản về Java và Maven sẽ giúp bạn theo dõi nhanh hơn.

## Cài Đặt GroupDocs.Viewer cho Java

### Cấu Hình Maven
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

### Các Bước Nhận Giấy Phép
- **Dùng Thử Miễn Phí:** Tải bản dùng thử miễn phí từ [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Giấy Phép Tạm Thời:** Nhận giấy phép tạm thời để khám phá đầy đủ tính năng mà không có hạn chế tại [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Mua Bản Quyền:** Để sử dụng lâu dài, hãy cân nhắc mua giấy phép qua [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Khởi Tạo và Cấu Hình Cơ Bản
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Điều chỉnh đường dẫn tệp để trỏ tới file `.msg` của bạn.

## Cách Chuyển Đổi Email Sang HTML và Đổi Tên Các Trường – Từng Bước

### 1. Thiết Lập Đường Dẫn Thư Mục Đầu Ra
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Thay `"YOUR_OUTPUT_DIRECTORY"` bằng thư mục bạn muốn lưu các tệp HTML.*

### 2. Định Nghĩa Định Dạng Đường Dẫn Tệp Trang
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` sẽ được thay thế bằng số trang trong quá trình render.*

### 3. Tạo Bản Ánh Xạ Các Trường Email Thành Tên Mới
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Ở đây chúng ta thay đổi các nhãn mặc định thành các nhãn tùy chỉnh.*

### 4. Cấu Hình Tùy Chọn Xem HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` gói CSS/JS vào trong HTML, trong khi `setFieldTextMap` áp dụng các tên tiêu đề tùy chỉnh.*

### 5. Render Email Thành HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Thay `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` bằng đường dẫn thực tế tới file MSG của bạn.*

#### Mẹo Khắc Phục Sự Cố
- Kiểm tra thư mục đầu ra có quyền ghi không.  
- Đảm bảo file MSG đầu vào tồn tại và đường dẫn đúng.  
- Sử dụng cùng một phiên bản GroupDocs.Viewer (25.2) như đã khai báo trong Maven.

## Ứng Dụng Thực Tiễn
1. **Báo Cáo Email Tùy Chỉnh:** Đồng bộ tiêu đề email với thuật ngữ doanh nghiệp để báo cáo rõ ràng hơn.  
2. **Hệ Thống Lưu Trữ Email:** Cải thiện khả năng tìm kiếm bằng cách sử dụng các tên tiêu đề chuẩn hoá.  
3. **Nền Tảng Hỗ Trợ Khách Hàng:** Trình bày ticket với các nhãn tiêu đề cá nhân hoá, nâng cao trải nghiệm cho nhân viên hỗ trợ.

## Các Yếu Tố Hiệu Suất
- Giải phóng các đối tượng `Viewer` bằng try‑with‑resources để giải phóng bộ nhớ kịp thời.  
- Đánh giá hiệu năng với các batch lớn và cân nhắc xử lý email song song bằng parallel streams nếu cần.

## Kết Luận
Bây giờ bạn đã biết **cách chuyển đổi email sang HTML** đồng thời **đổi tên các trường email** và **tùy chỉnh tiêu đề email** với GroupDocs.Viewer cho Java. Kỹ thuật này cho phép bạn kiểm soát hoàn toàn cách trình bày siêu dữ liệu email trong các đầu ra HTML.

### Các Bước Tiếp Theo
- Thử nghiệm thêm các ánh xạ trường (ví dụ: CC, BCC).  
- Khám phá các định dạng render khác như PDF hoặc PNG.  
- Truy cập [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) để tìm hiểu sâu hơn về API.

## Câu Hỏi Thường Gặp

**Q: Phương pháp này có hoạt động với các định dạng email khác như EML không?**  
A: Có, GroupDocs.Viewer hỗ trợ cả file MSG và EML; logic ánh xạ trường vẫn áp dụng tương tự.

**Q: Tôi có thể xuất HTML mà không có tài nguyên nhúng không?**  
A: Bạn có thể dùng `HtmlViewOptions.forExternalResources(...)` nếu muốn các file CSS/JS riêng biệt.

**Q: Phiên bản GroupDocs.Viewer nào đã được kiểm thử?**  
A: Mã được kiểm thử với GroupDocs.Viewer **25.2**.

**Q: Có thể thay đổi phông chữ hoặc kiểu dáng của các tiêu đề tùy chỉnh không?**  
A: Có thể áp dụng style qua CSS sau khi render, hoặc chèn CSS tùy chỉnh bằng `HtmlViewOptions.getResourcesPath()`.

**Q: Làm sao để lấy đường dẫn tệp HTML đã tạo một cách lập trình?**  
A: Đường dẫn tệp tuân theo mẫu được định nghĩa trong `pageFilePathFormat`; bạn có thể xây dựng nó bằng `String.format` cùng số trang.

## Tài Nguyên
- **Tài Liệu:** Các hướng dẫn chi tiết có sẵn tại [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Tham Khảo API:** Thông tin API chi tiết có thể xem tại [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Tải GroupDocs.Viewer:** Truy cập phiên bản mới nhất qua [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Cập Nhật Lần Cuối:** 2026-03-24  
**Đã Kiểm Thử Với:** GroupDocs.Viewer 25.2  
**Tác Giả:** GroupDocs