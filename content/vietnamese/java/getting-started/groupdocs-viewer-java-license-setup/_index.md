---
date: '2026-03-08'
description: Tìm hiểu cách nhận giấy phép tạm thời, thiết lập GroupDocs.Viewer cho
  Java bằng cách sử dụng các tệp cục bộ hoặc URL, và kiểm tra tính khả dụng của đường
  dẫn giấy phép.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: Cách lấy giấy phép tạm thời và thiết lập giấy phép trong GroupDocs.Viewer Java
type: docs
url: /vi/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

 for links: we kept same.

Check for image: unchanged.

Now produce final content.# Cách lấy giấy phép tạm thời và thiết lập giấy phép trong GroupDocs.Viewer Java

Quản lý giấy phép một cách hiệu quả là rất quan trọng khi tích hợp các thư viện bên thứ ba như **GroupDocs.Viewer for Java** vào ứng dụng của bạn. Hướng dẫn này sẽ chỉ cho bạn **cách lấy giấy phép tạm thời**, thiết lập nó từ tệp cục bộ hoặc URL HTTP, và xác minh rằng đường dẫn giấy phép là đúng. Khi kết thúc tutorial, bạn sẽ có một cấu hình giấy phép đáng tin cậy, sẵn sàng cho môi trường production, giúp ứng dụng của bạn tuân thủ và hiệu suất tốt.

![File and URL Setup with GroupDocs.Viewer for Java](/viewer/getting-started/file-and-url-setup-png.png)

## Quick Answers
- **Làm thế nào để tôi lấy giấy phép tạm thời?** Yêu cầu một giấy phép từ trang giấy phép tạm thời của GroupDocs và tải xuống tệp *.lic*.
- **Tôi có thể tải giấy phép từ một URL không?** Có – chỉ cần chỉ định `License.setLicense` tới một địa chỉ HTTP trả về tệp giấy phép hợp lệ.
- **Điều gì xảy ra nếu đường dẫn giấy phép bị thiếu?** Thực hiện kiểm tra để hiển thị hướng dẫn và ngăn không cho viewer khởi động.
- **Tôi có cần khởi động lại ứng dụng sau khi thay đổi giấy phép không?** Không, `License.setLicense` có thể được gọi tại thời gian chạy.
- **Phiên bản Java nào được yêu cầu?** Khuyến nghị JDK 8 hoặc cao hơn.

## What is a temporary license?
Một **giấy phép tạm thời** là một khóa có thời hạn do GroupDocs cấp, cho phép bạn đánh giá sản phẩm mà không cần mua giấy phép đầy đủ. Nó hoạt động giống hệt giấy phép vĩnh viễn trong thời gian còn hiệu lực, cho phép bạn thử nghiệm tất cả các tính năng trong môi trường thực tế.

## Why obtain a temporary license?
- **Đánh giá nhanh:** Nhận đầy đủ chức năng ngay lập tức cho các dự án chứng minh khái niệm.
- **Không ràng buộc tài chính:** Kiểm tra trước khi mua.
- **Tích hợp dễ dàng:** Hoạt động với cùng các cuộc gọi API như giấy phép vĩnh viễn.

## Prerequisites
1. **Java Development Kit (JDK):** Phiên bản 8 hoặc cao hơn.  
2. **IDE:** IntelliJ IDEA, Eclipse, hoặc bất kỳ IDE nào hỗ trợ Java.  
3. **Thư viện GroupDocs.Viewer for Java:** Được thêm vào dự án của bạn (xem cấu hình Maven bên dưới).  
4. **Kiến thức Java cơ bản:** Quen thuộc với các lớp, import và xử lý ngoại lệ.

## Setting Up GroupDocs.Viewer for Java
Để bắt đầu, bao gồm thư viện vào dự án Maven của bạn.

### Maven Configuration
Thêm cấu hình sau vào tệp `pom.xml` của bạn:
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

### Acquiring a License
Để sử dụng GroupDocs.Viewer, bạn cần có giấy phép:

- **Dùng thử miễn phí:** Tải xuống từ [trang GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Giấy phép tạm thời:** Yêu cầu một giấy phép tại [trang giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/).  
- **Mua:** Đối với giải pháp lâu dài, hãy cân nhắc mua giấy phép từ [trang mua GroupDocs](https://purchase.groupdocs.com/buy).

### Basic Initialization
Sau khi thư viện đã được thêm, bạn có thể khởi tạo viewer:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## Cách lấy giấy phép tạm thời và thiết lập nó từ tệp
### Overview
Thiết lập giấy phép từ tệp cục bộ là cách tiếp cận đơn giản nhất và hoạt động ngay cả khi ứng dụng chạy offline.

### Implementation Steps
1. **Xác định Đường dẫn Giấy phép** – chỉ đến tệp *.lic* bạn nhận được sau khi yêu cầu giấy phép tạm thời:
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **Áp dụng Giấy phép** – sử dụng lớp `License` để tải nó:
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Mẹo:**  
- Xác minh rằng đường dẫn tệp là tuyệt đối hoặc tương đối so với thư mục làm việc.  
- Đảm bảo tệp có quyền đọc cho người dùng chạy JVM.

## Cách xử lý giấy phép qua URL
### Overview
Giấy phép dựa trên URL rất tiện cho các triển khai trên đám mây, nơi tệp giấy phép được lưu trong một bucket lưu trữ an toàn.

### Implementation Steps
1. **Xác định URL Giấy phép** – thay thế placeholder bằng endpoint thực tế của bạn:
```java
final String licensePath = "http://example.com/license.lic";
```
2. **Phát hiện và Ghi log việc sử dụng URL** – mẫu dưới đây chỉ đơn giản thông báo rằng một URL đã được cung cấp:
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**Mẹo:**  
- Trong môi trường production, bạn sẽ tải tệp xuống (ví dụ, bằng `java.net.HttpURLConnection`) và sau đó gọi `license.setLicense(stream)`.  
- Thêm logic retry và xử lý timeout để đối phó với các vấn đề mạng tạm thời.

## Cách kiểm tra tính khả dụng của giấy phép (xác minh đường dẫn giấy phép)
### Overview
Trước khi cố gắng tải giấy phép, nên **kiểm tra tính khả dụng của giấy phép** để bạn có thể hướng dẫn nhà phát triển hoặc người dùng lấy giấy phép tạm thời khi cần.

### Implementation Steps
1. **Mô phỏng đường dẫn giấy phép bị thiếu**:
```java
final String licensePath = null;
```
2. **Cung cấp hướng dẫn rõ ràng nếu đường dẫn không tồn tại**:
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Mẹo:**  
- Ghi log thông báo này khi khởi động để đội ops biết rằng giấy phép đang thiếu.  
- Cân nhắc thoát ứng dụng hoặc vô hiệu hoá các tính năng viewer cho đến khi cung cấp giấy phép hợp lệ.

## Ứng dụng Thực tế
Hiểu cách **lấy giấy phép tạm thời**, thiết lập nó từ tệp hoặc URL, và **xác minh tính khả dụng của đường dẫn giấy phép** mở ra nhiều kịch bản thực tế:

1. **Hệ thống Quản lý Tài liệu** – nhúng một viewer tự động xác thực giấy phép mỗi khi khởi chạy.  
2. **Nền tảng SaaS Đám mây** – lưu giấy phép trong blob storage được bảo vệ và tải nó qua URL để cập nhật không downtime.  
3. **Triển khai Doanh nghiệp** – sử dụng giấy phép tạm thời trong giai đoạn thí điểm trước khi mua giấy phép quy mô đầy đủ.

## Các cân nhắc về Hiệu suất
- **Sử dụng tài nguyên:** Tải giấy phép một lần khi khởi động ứng dụng; các lần gọi lặp lại sẽ tạo I/O không cần thiết.  
- **Quản lý bộ nhớ:** Đối tượng `License` giữ trạng thái tối thiểu, nhưng luôn đóng các stream nếu bạn tải giấy phép thủ công.

## Kết luận
Bằng cách thực hiện các bước trên, bạn có thể **lấy giấy phép tạm thời**, cấu hình GroupDocs.Viewer cho Java bằng tệp cục bộ hoặc URL HTTP, và **kiểm tra tính khả dụng của giấy phép** để giữ cho ứng dụng của bạn luôn tuân thủ. Nền tảng giấy phép vững chắc này ngăn ngừa lỗi thời gian chạy và cung cấp cho bạn sự linh hoạt để chuyển đổi giữa môi trường phát triển, kiểm thử và production một cách tự tin.

### Câu hỏi thường gặp

1. **Làm thế nào để thiết lập tệp giấy phép cục bộ trong GroupDocs.Viewer Java?**  

   Sử dụng `license.setLicense("path/to/license.lic")` với đường dẫn tệp đúng để áp dụng giấy phép cục bộ.

2. **Tôi có thể tải giấy phép trực tiếp từ một URL không?**  

   Có, nhưng hãy đảm bảo mã của bạn xử lý việc truy cập URL, có thể tải giấy phép tại thời gian chạy hoặc quản lý các vấn đề mạng.

3. **Tôi nên làm gì nếu đường dẫn giấy phép không hợp lệ hoặc bị thiếu?**  

   Thực hiện kiểm tra null hoặc đường dẫn không hợp lệ và cung cấp hướng dẫn hoặc thông báo dự phòng để lấy giấy phép hợp lệ.

4. **Có thể chuyển đổi giữa tệp giấy phép và URL một cách động không?**  

   Chắc chắn, bằng cách thêm logic điều kiện để xử lý cả hai kịch bản dựa trên môi trường hoặc tham số thời gian chạy của bạn.

5. **Các thực tiễn tốt nhất để quản lý giấy phép trong production là gì?**  

   Lưu trữ giấy phép một cách an toàn, kiểm tra tính hợp lệ thường xuyên, và triển khai xử lý lỗi cho các vấn đề liên quan đến giấy phép để đảm bảo dịch vụ không bị gián đoạn.

## Câu hỏi thường gặp

**Q: Giấy phép tạm thời kéo dài bao lâu?**  
A: Thông thường 30 ngày, sau đó bạn có thể yêu cầu gia hạn hoặc nâng cấp lên giấy phép vĩnh viễn.

**Q: Tôi có cần kết nối internet để sử dụng giấy phép dựa trên tệp không?**  
A: Không. Tệp *.lic* cục bộ hoạt động hoàn toàn offline sau khi đã được tải.

**Q: Tôi có thể mã hoá tệp giấy phép để tăng bảo mật không?**  
A: Tệp giấy phép đã được GroupDocs ký; việc mã hoá bổ sung là tùy chọn nhưng không bắt buộc.

**Q: Điều gì sẽ xảy ra nếu giấy phép hết hạn trong khi ứng dụng đang chạy?**  
A: Các thao tác của Viewer sẽ bắt đầu ném ngoại lệ liên quan đến giấy phép; nên kiểm tra thời gian hết hạn khi khởi động.

**Q: Có an toàn không khi lưu URL giấy phép trong source control?**  
A: Tránh commit các URL nhạy cảm; thay vào đó sử dụng biến môi trường hoặc kho cấu hình bảo mật.

---

**Cập nhật lần cuối:** 2026-03-08  
**Đã kiểm thử với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs