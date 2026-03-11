---
date: '2026-01-15'
description: Tìm hiểu cách sử dụng GroupDocs Viewer để tạo HTML từ tài liệu dự án
  trong các khoảng thời gian cụ thể. Hướng dẫn này bao gồm cài đặt, mã nguồn và các
  trường hợp sử dụng thực tế.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Cách sử dụng GroupDocs Viewer để hiển thị tài liệu dự án theo khoảng thời gian
  trong Java
type: docs
url: /vi/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cách Sử Dụng GroupDocs Viewer Để Kết Xuất Tài Liệu Dự Án Theo Khoảng Thời Gian Trong Java

Nếu bạn đang tìm kiếm **cách sử dụng GroupDocs** để kết xuất lịch trình dự án trong một khoảng thời gian tập trung, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn toàn bộ quy trình — từ cài đặt Maven đến tạo HTML từ tài liệu dự án — để bạn có thể nhúng các chế độ xem thời gian chính xác trực tiếp vào ứng dụng của mình.

![Kết Xuất Tài Liệu Dự Án Theo Khoảng Thời Gian với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Câu Trả Lời Nhanh

- **Tính năng này làm gì?** Nó chỉ kết xuất phần của tệp Microsoft Project nằm giữa ngày bắt đầu và ngày kết thúc.  
- **Định dạng đầu ra nào được sử dụng?** HTML với tài nguyên nhúng, hoàn hảo cho việc tích hợp web.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi khoảng ngày tại thời gian chạy không?** Có — điều chỉnh các giá trị `setStartDate` và `setEndDate` trong tùy chọn kết xuất.  
- **Có được hỗ trợ trên mọi phiên bản Java không?** Hoạt động với Java 8+ miễn là bạn sử dụng GroupDocs.Viewer 25.2 hoặc mới hơn.

## “Cách Sử Dụng GroupDocs” là gì trong ngữ cảnh này?

GroupDocs Viewer là một thư viện Java chuyển đổi hơn 100 định dạng tệp thành các biểu diễn thân thiện với web. Khi bạn **cách sử dụng GroupDocs** cho các tệp dự án, bạn có khả năng trích xuất, trực quan hoá và chia sẻ dữ liệu lịch trình mà không cần Microsoft Project ở phía máy khách.

## Tại sao cần kết xuất tài liệu dự án theo khoảng thời gian?

- **Phân tích tập trung:** Hiển thị chỉ giai đoạn bạn quan tâm (ví dụ: Q3 2024).  
- **Hiệu suất:** Đầu ra HTML nhỏ hơn đồng nghĩa với tốc độ tải trang nhanh hơn.  
- **Tích hợp:** Nhúng các chế độ xem thời gian vào bảng điều khiển, cổng báo cáo hoặc công cụ quản lý dự án tùy chỉnh.  

## Yêu Cầu Trước

- **GroupDocs.Viewer for Java** phiên bản 25.2 hoặc cao hơn.  
- Java Development Kit (JDK) 8 hoặc mới hơn.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  
- Kiến thức cơ bản về Maven.  

## Cài Đặt GroupDocs.Viewer cho Java

### Phụ Thuộc Maven

Thêm kho lưu trữ và phụ thuộc vào tệp `pom.xml` của bạn:

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

1. **Bản Dùng Thử** – Tải phiên bản dùng thử từ [trang tải xuống của GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Giấy Phép Tạm Thời** – Nhận giấy phép tạm thời để thử nghiệm mở rộng qua [liên kết này](https://purchase.groupdocs.com/temporary-license/).  
3. **Mua** – Đối với việc sử dụng sản xuất không giới hạn, mua giấy phép tại [trang mua GroupDocs](https://purchase.groupdocs.com/buy).

### Khởi Tạo Viewer Cơ Bản

Đoạn mã sau cho thấy cách tạo một thể hiện `Viewer` trỏ tới tệp Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Hướng Dẫn Thực Hiện Từng Bước

### 1. Xác Định Thư Mục Đầu Ra

Tạo một thư mục để lưu các trang HTML được tạo:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*​Tại sao?* Giữ các tệp đã kết xuất có tổ chức giúp dễ dàng phục vụ chúng từ máy chủ web hoặc nhúng vào giao diện người dùng.

### 2. Khởi Tạo Viewer với Tệp Dự Án Của Bạn

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*​Tại sao?* Tải tài liệu chuẩn bị bộ phân tích nội bộ và cho phép truy cập siêu dữ liệu đặc thù của dự án.

### 3. Lấy Thông Tin Xem cho Tệp Dự Án

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*​Tại sao?* `ProjectManagementViewInfo` cung cấp ngày bắt đầu và kết thúc của lịch trình, mà bạn sẽ dùng sau này để giới hạn phạm vi kết xuất.

### 4. Cấu Hình Tùy Chọn Kết Xuất HTML (Tạo HTML từ Dự Án)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*​Tại sao?* Đặt `StartDate` và `EndDate` cho GroupDocs biết **tạo HTML từ dữ liệu dự án** chỉ trong khoảng thời gian đó.

### 5. Thực Hiện Quy Trình Kết Xuất

```java
viewer.view(viewOptions);
```

*​Tại sao?* Lệnh này tạo ra một loạt các trang HTML tự chứa, đại diện cho phần thời gian đã chọn của lịch trình dự án.

## Các Rủi Ro Thường Gặp & Khắc Phục Sự Cố

- **Đường dẫn tệp không đúng** – Kiểm tra lại xem cả tệp nguồn `.mpp` và thư mục đầu ra có tồn tại không.  
- **Kiểu tệp không được hỗ trợ** – Đảm bảo tài liệu là định dạng Dự án được hỗ trợ (ví dụ: `.mpp`, `.mpt`).  
- **Lỗi giấy phép** – Giấy phép dùng thử có thể áp đặt giới hạn kết xuất; chuyển sang giấy phép đầy đủ để sử dụng không giới hạn.  

## Ứng Dụng Thực Tiễn

1. **Phân Tích Dòng Thời Gian Dự Án** – Hiển thị cho các bên liên quan chỉ giai đoạn hiện tại.  
2. **Báo Cáo Tự Động** – Tạo báo cáo HTML có thời gian giới hạn cho các cập nhật trạng thái hàng tuần.  
3. **Tích Hợp với Bảng Điều Khiển** – Nhúng các trang đã kết xuất vào công cụ BI hoặc cổng tùy chỉnh.  
4. **Lưu Trữ** – Lưu một ảnh chụp nhanh thân thiện với web của lịch trình dự án để tham khảo trong tương lai.  

## Mẹo Tối Ưu Hiệu Suất

- Sử dụng tùy chọn *embedded resources* để mỗi trang HTML tự chứa, giảm số yêu cầu HTTP.  
- Đối với các dự án rất lớn, cân nhắc kết xuất thành các đoạn ngày nhỏ hơn để giảm mức sử dụng bộ nhớ.  
- Xóa các tệp tạm sau khi phục vụ để tránh bão hòa ổ đĩa.  

## Kết Luận

Bạn đã biết **cách sử dụng GroupDocs** Viewer để kết xuất tài liệu dự án trong một khoảng thời gian cụ thể và **tạo HTML từ dữ liệu dự án** trong Java. Khả năng này giúp đơn giản hoá việc hiển thị dòng thời gian, cải thiện hiệu quả báo cáo và tích hợp mượt mà với các ứng dụng web hiện đại.

### Các Bước Tiếp Theo
- Khám phá các tính năng Viewer bổ sung như đánh dấu bản quyền, bảo vệ bằng mật khẩu, hoặc tùy chỉnh CSS.  
- Kết hợp quy trình kết xuất này với một REST API để phục vụ các chế độ xem thời gian theo yêu cầu.  

## Câu Hỏi Thường Gặp

**Q: GroupDocs.Viewer hỗ trợ những định dạng tệp nào?**  
A: GroupDocs.Viewer hỗ trợ đa dạng các định dạng bao gồm Microsoft Project (MPP), PDF, Word, Excel, PowerPoint và nhiều hơn nữa.

**Q: Làm thế nào để bắt đầu với bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Bạn có thể tải phiên bản dùng thử từ [đây](https://releases.groupdocs.com/viewer/java/).

**Q: Tôi có thể kết xuất tài liệu mà không nhúng tài nguyên không?**  
A: Có, bạn có thể chọn một tùy chọn hiển thị HTML khác tham chiếu tới tài nguyên bên ngoài thay vì nhúng chúng.

**Q: Nếu tài liệu của tôi quá lớn để kết xuất thì sao?**  
A: Hãy cân nhắc chia tài liệu thành các phần nhỏ hơn hoặc chỉ kết xuất khoảng ngày cần thiết, như đã trình bày ở trên.

**Q: Làm thế nào để xử lý lỗi kết xuất?**  
A: Kiểm tra tất cả các cài đặt cấu hình, đảm bảo bạn có giấy phép hợp lệ, và tham khảo tài liệu GroupDocs để biết mã lỗi chi tiết.

## Tài Nguyên
- **Tài liệu**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Tham chiếu API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Tải xuống**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Mua**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Bản dùng thử miễn phí**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Giấy phép tạm thời**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Hỗ trợ**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-01-15  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs