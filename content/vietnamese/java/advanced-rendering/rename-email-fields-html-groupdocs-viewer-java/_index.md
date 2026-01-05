---
date: '2026-01-05'
description: Tìm hiểu cách đổi tên các trường email, chuyển email sang HTML và tùy
  chỉnh tiêu đề email bằng GroupDocs.Viewer cho Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Cách Đổi Tên Các Trường Email Khi Chuyển Đổi Email Sang HTML Bằng GroupDocs.Viewer
  Java
type: docs
url: /vi/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Cách Đổi Tên Trường Email Khi Kết Xuất Email Thành HTML với GroupDocs.Viewer Java

Bạn có thắc mắc **cách đổi tên email** khi chuyển đổi email sang HTML không? Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước để đổi tên các trường email, **chuyển đổi email sang HTML**, và **tùy chỉnh tiêu đề email** bằng cách sử dụng GroupDocs.Viewer cho Java. Khi kết thúc, bạn sẽ có một bản HTML sạch sẽ với các tên tiêu đề bạn mong muốn, giúp kết quả dễ đọc hơn và dễ tích hợp vào ứng dụng của bạn.

![Đổi Tên Trường Email Khi Chuyển Đổi Email Sang HTML với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Những Điều Bạn Sẽ Học
- Cách sử dụng GroupDocs.Viewer cho Java để **chuyển đổi email sang HTML**.  
- Kỹ thuật **đổi tên trường email** như “From”, “To”, “Sent”, và “Subject”.  
- Các thực hành tốt nhất để thiết lập Maven và cấp phép.  
- Các kịch bản thực tế nơi **tùy chỉnh tiêu đề email** mang lại giá trị.

## Câu Trả Lời Nhanh
- **Câu hỏi “cách đổi tên email” có nghĩa là gì?** Nó đề cập đến việc ánh xạ các tên tiêu đề email mặc định sang các nhãn tùy chỉnh trong quá trình kết xuất.  
- **Thư viện nào thực hiện việc chuyển đổi?** GroupDocs.Viewer cho Java (v25.2+).  
- **Tôi có cần giấy phép không?** Bản dùng thử hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi bất kỳ tên tiêu đề nào không?** Có, bất kỳ tiêu đề email tiêu chuẩn nào cũng có thể được ánh xạ lại qua `fieldTextMap`.  
- **Đầu ra là HTML hay tài nguyên nhúng?** Bạn có thể chọn tài nguyên nhúng để có một tệp tự chứa duy nhất.

## “Cách Đổi Tên Email” là gì trong Ngữ Cảnh của GroupDocs.Viewer?
Đổi tên các trường email có nghĩa là thay thế các nhãn mặc định (ví dụ: “From”) bằng văn bản tùy chỉnh (ví dụ: “Sender”) khi email được kết xuất thành HTML. Điều này hữu ích để đồng nhất đầu ra với thuật ngữ công ty hoặc cải thiện khả năng đọc của người dùng cuối.

## Tại Sao Chuyển Đổi Email Sang HTML và Tùy Chỉnh Tiêu Đề Email?
- **Nhận diện thương hiệu nhất quán:** Phù hợp ngôn ngữ của tổ chức bạn trong mọi giao tiếp.  
- **Tăng khả năng tìm kiếm:** Các tiêu đề tùy chỉnh có thể được lập chỉ mục hiệu quả hơn trong hệ thống lưu trữ.  
- **Tích hợp UI tốt hơn:** Tùy chỉnh đoạn HTML để phù hợp liền mạch với các cổng web hoặc bảng điều khiển hỗ trợ.

## Yêu Cầu Trước

### Thư Viện, Phiên Bản và Phụ Thuộc Yêu Cầu
- **GroupDocs.Viewer cho Java** – phiên bản 25.2 trở lên.  
- **Java Development Kit (JDK)** – phiên bản 8+.

### Yêu Cầu Thiết Lập Môi Trường
- **Maven** để quản lý phụ thuộc.  
- Một IDE như IntelliJ IDEA, Eclipse, hoặc VS Code.

### Kiến Thức Yêu Cầu
Kiến thức cơ bản về Java và Maven sẽ giúp bạn theo dõi nhanh chóng.

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
- **Bản Dùng Thử:** Tải bản dùng thử miễn phí từ [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Giấy Phép Tạm Thời:** Nhận giấy phép tạm thời để khám phá đầy đủ tính năng mà không có giới hạn tại [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Mua:** Để sử dụng lâu dài, cân nhắc mua giấy phép qua [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

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
Điều chỉnh đường dẫn tệp để trỏ tới tệp `.msg` của bạn.

## Hướng Dẫn Triển Khai

### Đổi Tên Trường Email – Các Bước Thực Hiện

#### 1. Thiết Lập Đường Dẫn Thư Mục Đầu Ra
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Thay thế `"YOUR_OUTPUT_DIRECTORY"` bằng thư mục mà bạn muốn lưu các tệp HTML.*

#### 2. Định Nghĩa Định Dạng Đường Dẫn Tệp Trang
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` sẽ được thay thế bằng số trang trong quá trình kết xuất.*

#### 3. Tạo Bản Ánh Xạ Các Trường Email Thành Tên Mới
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

#### 4. Cấu Hình Tùy Chọn Xem HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` gộp CSS/JS vào trong HTML, trong khi `setFieldTextMap` áp dụng các tên tiêu đề tùy chỉnh.*

#### 5. Kết Xuất Email Thành HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Thay thế `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` bằng đường dẫn thực tế tới tệp MSG của bạn.*

#### Mẹo Khắc Phục Sự Cố
- Kiểm tra thư mục đầu ra có quyền ghi.  
- Đảm bảo tệp MSG đầu vào tồn tại và đường dẫn đúng.  
- Sử dụng cùng phiên bản GroupDocs.Viewer (25.2) như đã khai báo trong Maven.

## Ứng Dụng Thực Tiễn
1. **Báo Cáo Email Tùy Chỉnh:** Đồng nhất tiêu đề email với thuật ngữ công ty để báo cáo rõ ràng hơn.  
2. **Hệ Thống Lưu Trữ Email:** Cải thiện khả năng tìm kiếm bằng cách sử dụng các tên tiêu đề chuẩn hoá.  
3. **Nền Tảng Hỗ Trợ Khách Hàng:** Trình bày các ticket với nhãn tiêu đề cá nhân hoá để cải thiện trải nghiệm cho nhân viên hỗ trợ.

## Các Yếu Tố Hiệu Suất
- Giải phóng các đối tượng `Viewer` bằng try‑with‑resources để giải phóng bộ nhớ kịp thời.  
- Phân tích hiệu năng các batch lớn và cân nhắc xử lý email bằng parallel streams nếu cần.

## Kết Luận
Bây giờ bạn đã biết **cách đổi tên trường email** khi **chuyển đổi email sang HTML** và **tùy chỉnh tiêu đề email** với GroupDocs.Viewer cho Java. Kỹ thuật này cho phép bạn kiểm soát hoàn toàn cách trình bày siêu dữ liệu email trong các đầu ra HTML.

### Các Bước Tiếp Theo
- Thử nghiệm các ánh xạ trường bổ sung (ví dụ: CC, BCC).  
- Khám phá các định dạng kết xuất khác như PDF hoặc PNG.  
- Truy cập [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) để hiểu sâu hơn về API.

## Phần Câu Hỏi Thường Gặp
1. **Tôi có thể đổi tên tất cả tiêu đề email bằng phương pháp này không?**  
   - Có, bạn có thể ánh xạ bất kỳ tiêu đề email tiêu chuẩn nào thành tên mới theo yêu cầu của mình.  
2. **Có thể sử dụng GroupDocs.Viewer mà không có giấy phép không?**  
   - Có phiên bản dùng thử để thử nghiệm, nhưng phiên bản đầy đủ yêu cầu giấy phép hợp lệ.  
3. **Làm sao để xử lý khối lượng lớn email một cách hiệu quả với GroupDocs.Viewer?**  
   - Xem xét xử lý batch và tối ưu tài nguyên hệ thống để quản lý tập dữ liệu lớn một cách hiệu quả.  
4. **Tôi có thể tích hợp giải pháp này vào ứng dụng Java hiện có không?**  
   - Chắc chắn, việc tích hợp rất đơn giản bằng cách sử dụng các phụ thuộc Maven.  
5. **Tôi có thể tìm hỗ trợ ở đâu nếu gặp vấn đề?**  
   - Truy cập [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) để nhận hỗ trợ từ cộng đồng và chính thức.

## Câu Hỏi Thường Gặp
**Q: Phương pháp này có hoạt động với các định dạng email khác như EML không?**  
A: Có, GroupDocs.Viewer hỗ trợ cả tệp MSG và EML; logic ánh xạ trường vẫn áp dụng.

**Q: Tôi có thể xuất HTML mà không có tài nguyên nhúng không?**  
A: Bạn có thể sử dụng `HtmlViewOptions.forExternalResources(...)` nếu muốn các tệp CSS/JS riêng biệt.

**Q: Phiên bản GroupDocs.Viewer nào đã được kiểm tra?**  
A: Mã đã được kiểm tra với GroupDocs.Viewer **25.2**.

**Q: Có thể thay đổi phông chữ hoặc kiểu dáng của các tiêu đề tùy chỉnh không?**  
A: Có thể áp dụng kiểu dáng qua CSS sau khi kết xuất, hoặc bạn có thể chèn CSS tùy chỉnh bằng cách sử dụng `HtmlViewOptions.getResourcesPath()`.

**Q: Làm sao để lấy đường dẫn tệp HTML đã tạo một cách lập trình?**  
A: Đường dẫn tệp tuân theo mẫu được định nghĩa trong `pageFilePathFormat`; bạn có thể xây dựng nó bằng `String.format` với số trang.

## Tài Nguyên
- **Documentation:** Hướng dẫn chi tiết có sẵn tại [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Thông tin chi tiết về API có thể tìm thấy trên [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Truy cập phiên bản mới nhất qua [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Cập Nhật Cuối Cùng:** 2026-01-05  
**Được Kiểm Tra Với:** GroupDocs.Viewer 25.2  
**Tác Giả:** GroupDocs