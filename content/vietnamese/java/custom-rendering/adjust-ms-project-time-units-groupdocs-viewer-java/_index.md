---
"date": "2025-04-24"
"description": "Tìm hiểu cách điều chỉnh đơn vị thời gian của MS Project bằng GroupDocs.Viewer cho Java. Hợp lý hóa quy trình kết xuất tài liệu dự án của bạn một cách hiệu quả và chính xác."
"title": "Cách điều chỉnh đơn vị thời gian của MS Project bằng GroupDocs.Viewer Java&#58; Hướng dẫn từng bước"
"url": "/vi/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/"
"weight": 1
---

# Cách điều chỉnh đơn vị thời gian của MS Project bằng GroupDocs.Viewer Java: Hướng dẫn từng bước
## Giới thiệu
Bạn có thấy mệt mỏi khi phải tự tay điều chỉnh đơn vị thời gian trong tài liệu MS Project trước khi chuyển chúng sang định dạng HTML không? Quá trình này có thể rất tẻ nhạt và dễ xảy ra lỗi, đặc biệt là khi xử lý các dự án lớn. Với **GroupDocs.Viewer cho Java**, bạn có thể dễ dàng điều chỉnh cài đặt đơn vị thời gian theo chương trình, đảm bảo độ chính xác và hiệu quả.
Trong hướng dẫn này, chúng tôi sẽ trình bày cách thay đổi đơn vị thời gian của tài liệu MS Project thành ngày bằng GroupDocs.Viewer Java. Đến cuối hướng dẫn này, bạn sẽ có thể:
- Thiết lập môi trường để hiển thị các tệp MS Project bằng GroupDocs.Viewer.
- Điều chỉnh đơn vị thời gian quản lý dự án trực tiếp trong mã của bạn.
- Tích hợp những điều chỉnh này một cách liền mạch vào ứng dụng của bạn.
Trước khi bắt đầu, hãy đảm bảo rằng bạn đã chuẩn bị mọi thứ để bắt đầu nhé!
## Điều kiện tiên quyết
### Thư viện và phụ thuộc bắt buộc
Để làm theo hướng dẫn này, bạn sẽ cần những thứ sau:
- **GroupDocs.Viewer cho Java** thư viện (phiên bản 25.2 trở lên).
- Maven được cài đặt trên máy của bạn để quản lý sự phụ thuộc.
- Hiểu biết cơ bản về lập trình Java.
### Yêu cầu thiết lập môi trường
Đảm bảo môi trường phát triển của bạn được thiết lập bằng JDK (Java Development Kit) và một IDE như IntelliJ IDEA hoặc Eclipse hỗ trợ các dự án Maven.
### Điều kiện tiên quyết về kiến thức
Sự quen thuộc cơ bản với cú pháp Java, xử lý tệp trong Java và làm việc với các phụ thuộc Maven sẽ có lợi. Tuy nhiên, hướng dẫn này nhằm mục đích làm cho quy trình trở nên đơn giản cho mọi cấp độ kỹ năng.
## Thiết lập GroupDocs.Viewer cho Java
Để bắt đầu sử dụng GroupDocs.Viewer cho Java, bạn cần thêm nó như một phần phụ thuộc vào dự án của bạn `pom.xml` tài liệu:
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
### Các bước xin cấp giấy phép
GroupDocs cung cấp bản dùng thử miễn phí các thư viện của họ, cho phép bạn khám phá các tính năng trước khi mua hoặc đăng ký giấy phép tạm thời:
- **Dùng thử miễn phí**: Thăm nom [Dùng thử miễn phí GroupDocs](https://releases.groupdocs.com/viewer/java/) để tải xuống và bắt đầu sử dụng thư viện.
- **Giấy phép tạm thời**: Để thử nghiệm mở rộng, hãy yêu cầu [giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/).
- **Mua**: Nếu bạn quyết định GroupDocs.Viewer phù hợp với dự án của mình, hãy mua trực tiếp từ họ [mua trang](https://purchase.groupdocs.com/buy).
### Khởi tạo và thiết lập cơ bản
Sau khi sự phụ thuộc được thiết lập trong Maven của bạn `pom.xml`, bạn đã sẵn sàng để bắt đầu viết mã. Khởi tạo một phiên bản Viewer với đường dẫn đến tệp MS Project của bạn và chuẩn bị để kết xuất.
## Hướng dẫn thực hiện
Chúng ta hãy cùng tìm hiểu cách bạn có thể điều chỉnh đơn vị thời gian cho các tài liệu MS Project bằng GroupDocs.Viewer Java. Chúng tôi sẽ chia nhỏ từng bước.
### Tổng quan về tính năng: Điều chỉnh đơn vị thời gian trong tài liệu MS Project
Tính năng này cho phép bạn thay đổi cài đặt đơn vị thời gian quản lý dự án từ mặc định (thường là phút) thành ngày, giúp HTML được kết xuất của bạn thân thiện hơn với người dùng và phù hợp với các tiêu chuẩn báo cáo thông thường.
#### Bước 1: Xác định định dạng đường dẫn tệp trang và thư mục đầu ra
Đầu tiên, hãy chỉ định nơi lưu trữ các tệp HTML đã kết xuất:
```java
import java.nio.file.Path;
// Chỉ định thư mục đầu ra cho các tập tin HTML
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
Sử dụng thư mục này để giải quyết đường dẫn tệp một cách linh hoạt cho từng trang trong tài liệu MS Project của bạn:
```java
// Xác định định dạng cho đường dẫn tệp của mỗi trang được hiển thị
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
#### Bước 2: Khởi tạo tùy chọn xem
Tạo tùy chọn chế độ xem với các tài nguyên được nhúng, cho phép bạn chỉ định cách xem và hiển thị dự án:
```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Thiết lập tùy chọn chế độ xem HTML để hiển thị
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
#### Bước 3: Điều chỉnh cài đặt đơn vị thời gian
Chỉ định đơn vị thời gian cho quản lý dự án được đặt thành ngày, thường phù hợp hơn cho các bài thuyết trình và báo cáo:
```java
import com.groupdocs.viewer.options.TimeUnit;
// Thay đổi đơn vị thời gian quản lý dự án thành NGÀY
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```
#### Bước 4: Kết xuất tài liệu MS Project
Cuối cùng, sử dụng lớp Viewer để hiển thị tài liệu của bạn với các tùy chọn chế độ xem được chỉ định:
```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Hiển thị tài liệu dự án dưới dạng HTML bằng cách sử dụng tùy chọn chế độ xem
    viewer.view(viewOptions);
}
```
### Mẹo khắc phục sự cố
- Đảm bảo đường dẫn thư mục đầu ra của bạn được chỉ định chính xác và có thể ghi được.
- Xác minh rằng đường dẫn tệp MS Project là chính xác và có thể truy cập được.
- Nếu xảy ra sự cố hiển thị, hãy kiểm tra xem lớp Viewer có đưa ra bất kỳ ngoại lệ nào không.
## Ứng dụng thực tế
Sau đây là một số trường hợp sử dụng thực tế mà việc điều chỉnh đơn vị thời gian trong tài liệu MS Project có thể đặc biệt hữu ích:
1. **Báo cáo dự án**: Dành cho những bên liên quan thích tóm tắt hàng ngày hơn là thông tin chi tiết từng phút.
2. **Tích hợp với Bảng điều khiển**: Khi nhúng mốc thời gian của dự án vào bảng thông tin kinh doanh yêu cầu chi tiết theo từng ngày.
3. **Cập nhật tự động**: Dành cho các hệ thống cần cập nhật trạng thái dự án tự động hàng ngày.
## Cân nhắc về hiệu suất
Khi làm việc với các tệp MS Project lớn, hãy cân nhắc những điều sau để có hiệu suất tối ưu:
- Sử dụng tài nguyên nhúng một cách hạn chế nếu chỉ cần sử dụng thường xuyên một số phần nhất định của tài liệu.
- Theo dõi mức sử dụng bộ nhớ khi xử lý nhiều dự án hoặc dự án rất lớn cùng lúc.
- Sử dụng hiệu quả chức năng thu gom rác của Java để quản lý việc phân bổ và hủy phân bổ tài nguyên.
## Phần kết luận
Bây giờ bạn đã biết cách điều chỉnh đơn vị thời gian của MS Project bằng GroupDocs.Viewer cho Java. Tính năng này hợp lý hóa quy trình kết xuất tài liệu dự án, giúp chúng dễ truy cập hơn và dễ tích hợp hơn vào các hệ thống rộng hơn. 
Hãy khám phá các tính năng khác của GroupDocs.Viewer để nâng cao hơn nữa giải pháp quản lý tài liệu của bạn.
Sẵn sàng tiến xa hơn nữa? Hãy thử áp dụng giải pháp này vào dự án tiếp theo của bạn!
## Phần Câu hỏi thường gặp
**1. GroupDocs.Viewer for Java được sử dụng để làm gì?**
GroupDocs.Viewer for Java cho phép các nhà phát triển kết xuất tài liệu ở nhiều định dạng khác nhau, bao gồm cả tệp MS Project, thành định dạng HTML hoặc hình ảnh để xem.
**2. Tôi có thể sử dụng GroupDocs.Viewer cho các loại tài liệu khác không?**
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu khác nhau ngoài MS Project, chẳng hạn như PDF, tài liệu Word và bảng tính.
**3. Tôi phải xử lý việc cấp phép cho GroupDocs.Viewer như thế nào?**
GroupDocs cung cấp nhiều tùy chọn cấp phép khác nhau, bao gồm bản dùng thử miễn phí, giấy phép tạm thời để thử nghiệm mở rộng và giấy phép vĩnh viễn sau khi mua.
**4. Tôi phải làm gì nếu gặp lỗi khi kết xuất tệp dự án của mình?**
Kiểm tra đường dẫn tệp, đảm bảo bạn có quyền ghi vào thư mục đầu ra và xem xét mọi ngoại lệ do GroupDocs.Viewer đưa ra để tìm gợi ý khắc phục sự cố.
**5. Tôi có thể tùy chỉnh cách hiển thị tài liệu bằng GroupDocs.Viewer không?**
Chắc chắn rồi! GroupDocs.Viewer cung cấp nhiều tùy chọn để tùy chỉnh kết xuất, bao gồm thiết lập đơn vị thời gian cho các dự án, chọn tài nguyên để nhúng, v.v.
## Tài nguyên
- [Tài liệu](https://docs.groupdocs.com/viewer/java/)
- [Tài liệu tham khảo API](https://reference.groupdocs.com/viewer/java/)
- [Tải xuống GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Mua giấy phép](https://purchase.groupdocs.com/buy)