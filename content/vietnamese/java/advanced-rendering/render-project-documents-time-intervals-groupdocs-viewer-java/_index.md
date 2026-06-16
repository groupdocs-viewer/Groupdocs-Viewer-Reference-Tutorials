---
date: '2026-03-29'
description: Tìm hiểu cách tạo chế độ xem HTML cho tệp MPP bằng GroupDocs Viewer trong
  Java, hiển thị tài liệu dự án theo khoảng thời gian với mã từng bước.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Tạo chế độ xem HTML cho tệp MPP bằng GroupDocs Viewer (Java)
type: docs
url: /vi/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cách Sử Dụng GroupDocs Viewer Để Kết Xuất Tài Liệu Dự Án Theo Khoảng Thời Gian Trong Java

Trong hướng dẫn này, bạn sẽ học cách **create html view mpp** với GroupDocs Viewer cho Java, cho phép bạn kết xuất chỉ các phần của tệp Microsoft Project nằm trong một khoảng thời gian cụ thể. Chúng tôi sẽ hướng dẫn cài đặt Maven, cấu hình mã, và các kịch bản thực tế để bạn có thể nhúng các chế độ xem thời gian chính xác trực tiếp vào ứng dụng của mình.

![Kết Xuất Tài Liệu Dự Án Theo Khoảng Thời Gian với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Câu trả lời nhanh
- **Tính năng này làm gì?** Nó chỉ kết xuất phần của tệp Microsoft Project nằm giữa ngày bắt đầu và ngày kết thúc.  
- **Định dạng đầu ra nào được sử dụng?** HTML với các tài nguyên được nhúng, hoàn hảo cho tích hợp web.  
- **Tôi có cần giấy phép không?** Phiên bản dùng thử miễn phí đủ cho việc đánh giá; cần giấy phép đầy đủ cho môi trường sản xuất.  
- **Tôi có thể thay đổi khoảng thời gian tại thời gian chạy không?** Có—điều chỉnh các giá trị `setStartDate` và `setEndDate` trong tùy chọn kết xuất.  
- **Điều này có được hỗ trợ trên mọi phiên bản Java không?** Hoạt động với Java 8+ miễn là bạn sử dụng GroupDocs.Viewer 25.2 hoặc mới hơn.

## Cách tạo html view mpp cho Tài Liệu Dự Án
GroupDocs Viewer có thể chuyển đổi các tệp Microsoft Project (`.mpp`, `.mpt`) thành các trang HTML. Bằng cách cấu hình ngày bắt đầu và ngày kết thúc trong tùy chọn kết xuất, bạn giới hạn đầu ra chỉ trong khoảng thời gian bạn quan tâm, giúp giảm kích thước tệp và tăng tốc độ tải trang.

## “How to Use GroupDocs” là gì trong ngữ cảnh này?
GroupDocs Viewer là một thư viện Java chuyển đổi hơn 100 định dạng tệp thành các biểu diễn thân thiện với web. Khi bạn **how to use GroupDocs** cho các tệp dự án, bạn có khả năng trích xuất, trực quan hoá và chia sẻ dữ liệu lịch trình mà không cần Microsoft Project ở phía máy khách.

## Tại sao phải kết xuất tài liệu dự án theo khoảng thời gian?
- **Phân tích tập trung:** Hiển thị chỉ giai đoạn bạn quan tâm (ví dụ: Q3 2024).  
- **Hiệu suất:** Đầu ra HTML nhỏ hơn đồng nghĩa với tốc độ tải trang nhanh hơn.  
- **Tích hợp:** Nhúng các chế độ xem thời gian vào bảng điều khiển, cổng báo cáo, hoặc công cụ quản lý dự án tùy chỉnh.  

## Yêu cầu trước
- **GroupDocs.Viewer for Java** phiên bản 25.2 hoặc cao hơn.  
- Java Development Kit (JDK) 8 hoặc mới hơn.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  
- Kiến thức cơ bản về Maven.  

## Cài đặt GroupDocs.Viewer cho Java

### Phụ thuộc Maven

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

### Các bước lấy giấy phép

1. **Free Trial** – Tải phiên bản dùng thử từ [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Nhận giấy phép tạm thời để thử nghiệm mở rộng qua [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Đối với việc sử dụng sản xuất không giới hạn, mua giấy phép tại [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Khởi tạo Viewer Cơ bản

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

## Hướng dẫn triển khai từng bước

### 1. Xác định Thư mục Đầu ra

Tạo một thư mục để lưu các trang HTML được tạo:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Tại sao?* Giữ các tệp đã kết xuất được tổ chức giúp dễ dàng phục vụ chúng từ máy chủ web hoặc nhúng vào giao diện người dùng.

### 2. Khởi tạo Viewer với Tệp Dự Án của Bạn

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Tại sao?* Tải tài liệu chuẩn bị bộ phân tích nội bộ và cho phép truy cập các siêu dữ liệu đặc thù của dự án.

### 3. Lấy Thông tin Xem cho Các Tệp Dự Án

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Tại sao?* `ProjectManagementViewInfo` cung cấp cho bạn ngày bắt đầu và ngày kết thúc của lịch trình, mà bạn sẽ sử dụng sau này để giới hạn phạm vi kết xuất.

### 4. Cấu hình Tùy chọn Kết xuất HTML (Tạo HTML từ Dự Án)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Tại sao?* Đặt `StartDate` và `EndDate` cho GroupDocs biết chỉ tạo dữ liệu **generate html view mpp** trong khoảng thời gian đó.

### 5. Thực thi Quy trình Kết xuất

```java
viewer.view(viewOptions);
```

*Tại sao?* Lệnh này tạo ra một loạt các trang HTML tự chứa, đại diện cho phần thời gian đã chọn của lịch trình dự án của bạn.

## Những Sai Lầm Thường Gặp & Khắc Phục
- **Incorrect file paths** – Kiểm tra lại rằng cả tệp nguồn `.mpp` và thư mục đầu ra đều tồn tại.  
- **Unsupported file type** – Đảm bảo tài liệu là định dạng Project được hỗ trợ (ví dụ: `.mpp`, `.mpt`).  
- **License errors** – Giấy phép dùng thử có thể đặt giới hạn kết xuất; chuyển sang giấy phép đầy đủ để sử dụng không giới hạn.  

## Ứng dụng Thực tế
1. **Project Timeline Analysis** – Hiển thị cho các bên liên quan chỉ giai đoạn hiện tại.  
2. **Automated Reporting** – Tạo báo cáo HTML có thời gian giới hạn cho các cập nhật trạng thái hàng tuần.  
3. **Integration with Dashboards** – Nhúng các trang đã kết xuất vào công cụ BI hoặc cổng tùy chỉnh.  
4. **Archival** – Lưu một bản chụp nhanh thân thiện với web của lịch trình dự án để tham khảo trong tương lai.  

## Mẹo Hiệu Suất
- Sử dụng tùy chọn *embedded resources* để mỗi trang HTML tự chứa, giảm số yêu cầu HTTP.  
- Đối với các dự án rất lớn, cân nhắc kết xuất theo các khối ngày nhỏ hơn để giữ mức sử dụng bộ nhớ thấp.  
- Xóa các tệp tạm sau khi phục vụ chúng để tránh bão hòa ổ đĩa.  

## Kết luận
Bây giờ bạn đã biết **how to use GroupDocs** Viewer để kết xuất tài liệu dự án trong một khoảng thời gian cụ thể và **generate HTML from project** dữ liệu trong Java. Khả năng này giúp đơn giản hoá việc trực quan hoá thời gian, cải thiện hiệu quả báo cáo, và tích hợp mượt mà với các ứng dụng web hiện đại.

### Các bước tiếp theo
- Khám phá các tính năng Viewer bổ sung như đánh dấu watermark, bảo vệ bằng mật khẩu, hoặc tùy chỉnh CSS.  
- Kết hợp quy trình kết xuất này với một REST API để cung cấp các chế độ xem thời gian theo yêu cầu.  

## Câu hỏi thường gặp

**Q: GroupDocs.Viewer hỗ trợ những định dạng tệp nào?**  
A: GroupDocs.Viewer hỗ trợ nhiều định dạng bao gồm Microsoft Project (MPP), PDF, Word, Excel, PowerPoint và nhiều hơn nữa.

**Q: Làm sao để bắt đầu với phiên bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Bạn có thể tải phiên bản dùng thử từ [here](https://releases.groupdocs.com/viewer/java/).

**Q: Tôi có thể kết xuất tài liệu mà không nhúng tài nguyên không?**  
A: Có, bạn có thể chọn một tùy chọn HTML view khác tham chiếu tới tài nguyên bên ngoài thay vì nhúng chúng.

**Q: Nếu tài liệu của tôi quá lớn để kết xuất thì sao?**  
A: Hãy cân nhắc chia tài liệu thành các phần nhỏ hơn hoặc chỉ kết xuất khoảng thời gian cần thiết, như đã minh họa ở trên.

**Q: Làm sao để xử lý lỗi kết xuất?**  
A: Kiểm tra tất cả các cài đặt cấu hình, đảm bảo bạn có giấy phép hợp lệ, và tham khảo tài liệu GroupDocs để biết mã lỗi chi tiết.

## Tài nguyên
- **Tài liệu**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Tham chiếu API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Tải xuống**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Mua**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Dùng thử miễn phí**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Giấy phép tạm thời**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Hỗ trợ**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-03-29  
**Kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs  

---