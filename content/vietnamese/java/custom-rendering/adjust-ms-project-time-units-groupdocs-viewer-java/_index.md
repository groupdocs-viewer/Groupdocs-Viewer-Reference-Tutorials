---
date: '2026-01-28'
description: Tìm hiểu cách điều chỉnh đơn vị thời gian trong MS Project bằng GroupDocs
  Viewer Java. Tối ưu hoá quy trình hiển thị tài liệu dự án của bạn một cách hiệu
  quả và chính xác.
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 'Cách điều chỉnh đơn vị thời gian trong MS Project bằng GroupDocs Viewer Java:
  Hướng dẫn từng bước'
type: docs
url: /vi/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Cách Điều Chỉnh Đơn Vị Thời Gian MS Project Sử Dụng groupdocs viewer java: Hướng Dẫn Từng Bước

## Giới thiệu
Bạn có mệt mỏi vì phải điều chỉnh thủ công các đơn vị thời gian trong tài liệu MS Project của mình trước khi chuyển đổi chúng sang định dạng HTML không? Quá trình này có thể tẻ nhạt và dễ gây lỗi, đặc biệt khi làm việc với các dự án lớn. Với **groupdocs viewer java**, bạn có thể dễ dàng điều chỉnh cài đặt đơn vị thời gian một cách lập trình, đảm bảo độ chính xác và hiệu quả.

![Điều Chỉnh Đơn Vị Thời Gian MS Project với GroupDocs.Viewer cho Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

Trong hướng dẫn này, chúng tôi sẽ trình bày cách chuyển đổi đơn vị thời gian của tài liệu MS Project sang ngày bằng cách sử dụng groupdocs viewer java. Khi kết thúc bài học, bạn sẽ có thể:
- Cài đặt môi trường của bạn để chuyển đổi các tệp MS Project bằng GroupDocs.Viewer.
- Điều chỉnh đơn vị thời gian quản lý dự án trực tiếp trong mã của bạn.
- Tích hợp các điều chỉnh này một cách liền mạch vào ứng dụng của bạn.

Trước khi chúng ta bắt đầu, hãy chắc chắn rằng bạn đã sẵn sàng mọi thứ cần thiết!

## Câu trả lời nhanh
- **Thư viện nào xử lý việc chuyển đổi MS Project?** groupdocs viewer java
- **Đơn vị thời gian nào có thể được đặt?** Ngày (via `TimeUnit.DAYS`)
- **Tôi có cần giấy phép không?** Có sẵn bản dùng thử hoặc giấy phép tạm thời; giấy phép vĩnh viễn cần thiết cho môi trường sản xuất.
- **IDE nào phù hợp nhất?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse) hỗ trợ Maven.
- **Maven có bắt buộc không?** Có, Maven đơn giản hoá việc quản lý phụ thuộc cho groupdocs viewer java.

## groupdocs viewer java là gì?
groupdocs viewer java là một SDK Java cho phép các nhà phát triển chuyển đổi đa dạng các định dạng tài liệu — bao gồm các tệp MS Project — sang các định dạng thân thiện với web như HTML hoặc hình ảnh. Nó trừu tượng hoá các phức tạp của việc phân tích tệp, cho phép bạn tập trung vào logic nghiệp vụ.

## Tại sao cần điều chỉnh đơn vị thời gian với groupdocs viewer java?
Việc chuyển đổi đơn vị thời gian từ mặc định (thường là phút) sang ngày giúp kết quả chuyển đổi dễ đọc hơn cho các bên liên quan, phù hợp với chu kỳ báo cáo thông thường và giảm bớt sự lộn xộn trực quan trong các báo cáo HTML. Điều này đặc biệt có giá trị khi nhúng lịch trình dự án vào bảng điều khiển hoặc tạo các bản tóm tắt trạng thái hàng ngày.

## Yêu cầu trước
### Thư viện và phụ thuộc cần thiết
Để làm theo hướng dẫn này, bạn sẽ cần các thành phần sau:
- Thư viện **groupdocs viewer java** (phiên bản 25.2 trở lên).
- Maven được cài đặt trên máy của bạn để quản lý phụ thuộc.
- Kiến thức cơ bản về lập trình Java.

### Yêu cầu cài đặt môi trường
Đảm bảo môi trường phát triển của bạn đã được cài đặt JDK (Java Development Kit) và một IDE như IntelliJ IDEA hoặc Eclipse hỗ trợ các dự án Maven.

### Kiến thức nền tảng
Sự quen thuộc cơ bản với cú pháp Java, xử lý tệp trong Java và làm việc với các phụ thuộc Maven sẽ hữu ích. Tuy nhiên, hướng dẫn này nhằm làm cho quá trình trở nên đơn giản cho mọi cấp độ kỹ năng.

## Cài đặt groupdocs viewer java
Để bắt đầu sử dụng groupdocs viewer java, thêm nó như một phụ thuộc trong tệp `pom.xml` của dự án:

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

### Các bước nhận giấy phép
groupdocs cung cấp bản dùng thử miễn phí cho các thư viện của họ, cho phép bạn khám phá các tính năng trước khi mua hoặc yêu cầu giấy phép tạm thời:
- **Bản dùng thử**: Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) để tải xuống và bắt đầu sử dụng thư viện.
- **Giấy phép tạm thời**: Để thử nghiệm kéo dài, yêu cầu một [temporary license](https://purchase.groupdocs.com/temporary-license/).
- **Mua**: Nếu bạn quyết định groupdocs.viewer java phù hợp với dự án của mình, mua trực tiếp từ [buy page](https://purchase.groupdocs.com/buy) của họ.

### Khởi tạo và cài đặt cơ bản
Khi phụ thuộc đã được thiết lập trong `pom.xml` của Maven, bạn đã sẵn sàng để bắt đầu viết mã. Khởi tạo một thể hiện Viewer với đường dẫn tới tệp MS Project của bạn và chuẩn bị cho việc chuyển đổi.

## Hướng dẫn triển khai
Hãy khám phá cách bạn có thể điều chỉnh đơn vị thời gian cho tài liệu MS Project bằng cách sử dụng groupdocs viewer java. Chúng tôi sẽ chia thành các bước từng bước.

### Tổng quan tính năng: Điều chỉnh đơn vị thời gian trong tài liệu MS Project
Tính năng này cho phép bạn thay đổi cài đặt đơn vị thời gian quản lý dự án từ mặc định (thường là phút) sang ngày, làm cho HTML được chuyển đổi trở nên thân thiện hơn với người dùng và phù hợp với tiêu chuẩn báo cáo thông thường.

#### Bước 1: Xác định thư mục đầu ra và định dạng đường dẫn tệp trang
Đầu tiên, chỉ định nơi các tệp HTML đã chuyển đổi sẽ được lưu:

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

Sử dụng thư mục này để giải quyết đường dẫn tệp một cách động cho mỗi trang của tài liệu MS Project của bạn:

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### Bước 2: Khởi tạo View Options
Tạo các tùy chọn xem với tài nguyên nhúng, cho phép bạn chỉ định cách dự án sẽ được xem và chuyển đổi:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### Bước 3: Điều chỉnh cài đặt đơn vị thời gian
Chỉ định rằng đơn vị thời gian cho quản lý dự án được đặt thành ngày, thường phù hợp hơn cho các bài thuyết trình và báo cáo:

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### Bước 4: Chuyển đổi tài liệu MS Project
Cuối cùng, sử dụng lớp Viewer để chuyển đổi tài liệu của bạn với các tùy chọn xem đã chỉ định:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### Mẹo khắc phục sự cố
- Đảm bảo đường dẫn thư mục đầu ra của bạn được chỉ định đúng và có quyền ghi.
- Xác minh rằng đường dẫn tệp MS Project là đúng và có thể truy cập.
- Nếu gặp vấn đề chuyển đổi, kiểm tra bất kỳ ngoại lệ nào được lớp Viewer ném ra.

## Ứng dụng thực tiễn
Dưới đây là một số trường hợp thực tế mà việc điều chỉnh đơn vị thời gian trong tài liệu MS Project có thể đặc biệt hữu ích:
1. **Báo cáo dự án** – Các bên liên quan thường ưu tiên bản tóm tắt hàng ngày hơn là chi tiết mức phút.
2. **Tích hợp với bảng điều khiển** – Nhúng lịch trình vào các bảng điều khiển kinh doanh yêu cầu độ chi tiết ở mức ngày.
3. **Cập nhật tự động** – Các hệ thống cần làm mới trạng thái dự án hàng ngày một cách tự động.

## Các cân nhắc về hiệu năng
Khi làm việc với các tệp MS Project lớn, hãy cân nhắc các yếu tố sau để đạt hiệu năng tối ưu:
- Sử dụng tài nguyên nhúng một cách hạn chế nếu chỉ một số phần của tài liệu cần thường xuyên.
- Giám sát việc sử dụng bộ nhớ khi xử lý đồng thời nhiều dự án hoặc các dự án rất lớn.
- Tận dụng bộ thu gom rác của Java một cách hiệu quả để quản lý việc cấp phát và giải phóng tài nguyên.

## Kết luận
Bạn đã học cách điều chỉnh đơn vị thời gian MS Project bằng cách sử dụng groupdocs viewer java. Tính năng này giúp đơn giản hoá quá trình chuyển đổi tài liệu dự án, làm cho chúng dễ tiếp cận hơn và dễ tích hợp vào các hệ thống rộng hơn.

Hãy cân nhắc khám phá các khả năng khác của groupdocs viewer java để nâng cao giải pháp quản lý tài liệu của bạn hơn nữa. Sẵn sàng tiến xa hơn? Hãy thử triển khai giải pháp này trong dự án tiếp theo của bạn!

## Phần Câu hỏi thường gặp
**1. GroupDocs.Viewer for Java được dùng để làm gì?**  
GroupDocs.Viewer for Java cho phép các nhà phát triển chuyển đổi tài liệu sang các định dạng khác nhau, bao gồm các tệp MS Project, thành định dạng HTML hoặc hình ảnh để xem.

**2. Tôi có thể sử dụng GroupDocs.Viewer cho các loại tài liệu khác không?**  
Có, GroupDocs.Viewer hỗ trợ một loạt các định dạng tài liệu ngoài MS Project, chẳng hạn như PDF, tài liệu Word và bảng tính.

**3. Làm thế nào để tôi quản lý giấy phép cho GroupDocs.Viewer?**  
GroupDocs cung cấp các tùy chọn giấy phép khác nhau, bao gồm bản dùng thử miễn phí, giấy phép tạm thời cho việc thử nghiệm kéo dài và giấy phép vĩnh viễn khi mua.

**4. Nếu tôi gặp lỗi khi chuyển đổi các tệp dự án của mình thì sao?**  
Kiểm tra các đường dẫn tệp, đảm bảo bạn có quyền ghi vào thư mục đầu ra và xem xét bất kỳ ngoại lệ nào được GroupDocs.Viewer ném ra để tìm gợi ý khắc phục.

**5. Tôi có thể tùy chỉnh cách tài liệu được chuyển đổi với GroupDocs.Viewer không?**  
Chắc chắn! GroupDocs.Viewer cung cấp nhiều tùy chọn để tùy chỉnh quá trình chuyển đổi, bao gồm việc đặt đơn vị thời gian cho dự án, chọn tài nguyên cần nhúng và nhiều hơn nữa.

## Tài nguyên
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase a License](https://purchase.groupdocs.com/buy)

---

**Last Updated:** 2026-01-28  
**Tested With:** groupdocs viewer java 25.2  
**Author:** GroupDocs