---
date: '2026-02-23'
description: Tìm hiểu cách thiết lập số mục mỗi trang, nhúng tài nguyên HTML và chuyển
  đổi hàng loạt các tệp lưu trữ thành HTML đơn trang hoặc đa trang bằng GroupDocs.Viewer
  Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Đặt số mục mỗi trang: Chuyển đổi các tệp lưu trữ sang HTML bằng GroupDocs.Viewer
  Java'
type: docs
url: /vi/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

 produce final output.# Đặt Số Mục Trên Mỗi Trang: Chuyển Đổi Tập Tin Nén Sang HTML với GroupDocs.Viewer Java

Việc chuyển đổi các tệp nén như ZIP hoặc RAR sang HTML thân thiện với web là một nhu cầu thường gặp khi bạn muốn chia sẻ hoặc xem xét tài liệu trực tiếp trong trình duyệt. Trong hướng dẫn này, bạn sẽ học **cách đặt số mục trên mỗi trang** khi render các tệp nén, cách nhúng tài nguyên HTML để tạo ra đầu ra tự chứa, và cách chuyển đổi hàng loạt các tệp nén một cách hiệu quả với GroupDocs.Viewer Java.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Câu trả lời nhanh
- **“set items per page” kiểm soát gì?** Nó xác định có bao nhiêu tệp hoặc thư mục trong một tệp nén xuất hiện trên mỗi trang HTML được tạo.  
- **Tôi có thể nhúng hình ảnh và CSS trực tiếp vào HTML không?** Có – sử dụng tùy chọn `forEmbeddedResources` để nhúng tài nguyên HTML.  
- **Có thể thực hiện chuyển đổi hàng loạt không?** Chắc chắn; bạn có thể lặp qua một tập hợp các tệp nén và render mỗi tệp với cùng một cài đặt.  
- **Có cần Maven để sử dụng GroupDocs.Viewer không?** Có, thêm phụ thuộc `maven groupdocs viewer` như được hiển thị bên dưới.  
- **Các định dạng đầu ra nào được hỗ trợ?** HTML Java đơn trang và HTML Java đa trang đều có sẵn.

## “set items per page” là gì trong GroupDocs.Viewer?
Cài đặt **set items per page** thuộc về các tùy chọn render tệp nén. Nó cho viewer biết bao nhiêu mục trong tệp nén (tệp hoặc thư mục) sẽ được hiển thị trên mỗi trang HTML khi bạn tạo một tài liệu HTML đa trang. Điều chỉnh giá trị này giúp bạn cân bằng kích thước trang và tốc độ điều hướng, đặc biệt đối với các tệp nén lớn.

## Tại sao phải nhúng tài nguyên HTML?
Việc nhúng tài nguyên (hình ảnh, CSS, phông chữ) trực tiếp vào tệp HTML tạo ra một tài liệu duy nhất, di động, có thể mở mà không cần các tệp bên ngoài. Điều này lý tưởng cho tệp đính kèm email, xem offline, hoặc nhúng đầu ra vào các trang web khác.

## Yêu cầu trước

- **Thư viện yêu cầu:** Bao gồm GroupDocs.Viewer phiên bản 25.2 trở lên.  
- **Môi trường:** Java Development Kit (JDK) đã được cài đặt và cấu hình.  
- **Kiến thức:** Kiến thức cơ bản về Java và quản lý phụ thuộc Maven.  

## Cài đặt Maven GroupDocs Viewer

Thêm repository GroupDocs và phụ thuộc viewer vào file `pom.xml` của bạn:

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

### Nhận giấy phép
GroupDocs.Viewer cung cấp **liên kết dùng thử miễn phí**, giấy phép tạm thời, hoặc tùy chọn mua đầy đủ. Hãy chọn lựa phù hợp với thời gian dự án của bạn.

### Khởi tạo cơ bản
Sau khi cài đặt Maven, đưa viewer vào mã của bạn:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cách Render Tập Tin Nén Sang HTML Đơn Trang

### Bước 1: Xác định Thư mục Đầu ra
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Bước 2: Đặt Tên Tệp cho Đầu ra Đơn Trang
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Bước 3: Khởi tạo Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Bước 4: Cấu hình Tùy chọn Render (nhúng tài nguyên HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 5: Render dưới dạng Một Trang
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cách Render Tập Tin Nén Sang HTML Đa Trang và Đặt Số Mục Trên Mỗi Trang

### Bước 1: Tái sử dụng Thư mục Đầu ra
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Bước 2: Xác định Định dạng Tên Tệp cho Nhiều Trang
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Bước 3: Khởi tạo Viewer Lại
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Bước 4: Cấu hình Tùy chọn Đa Trang (nhúng tài nguyên HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 5: Đặt Số Mục Trên Mỗi Trang (từ khóa chính trong hành động)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Ứng dụng Thực tiễn

- **Hệ thống Quản lý Tài liệu:** Thêm chức năng xem trước tệp nén mà không cần cài đặt các viewer bổ sung.  
- **Cổng thông tin Web:** Cung cấp cho người dùng cách nhanh chóng, không cần tải xuống để khám phá các tài liệu được đóng gói.  
- **Công cụ Hợp tác:** Cho phép các nhóm kiểm tra các tệp nén được chia sẻ trực tiếp trong trình duyệt.  

## Các lưu ý về Hiệu suất

- **Quản lý tài nguyên:** Giám sát việc sử dụng bộ nhớ; cân nhắc tinh chỉnh garbage‑collector của JVM cho các batch lớn.  
- **Chuyển đổi hàng loạt các tệp nén:** Lặp qua danh sách các tệp nén và gọi cùng một logic render để tối đa hoá thông lượng.  
- **Chiến lược cache:** Lưu HTML đã render vào cache nếu cùng một tệp nén được truy cập thường xuyên.  

## Câu hỏi Thường gặp

**Q: GroupDocs.Viewer Java là gì?**  
A: Một thư viện đa năng để render tài liệu—bao gồm cả tệp nén—sang các định dạng như HTML, PDF và hình ảnh.

**Q: Làm sao tôi có thể nhận bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Truy cập [liên kết dùng thử miễn phí](https://releases.groupdocs.com/viewer/java/) để tải xuống và thử nghiệm.

**Q: Tôi có thể chuyển đổi các loại tài liệu khác ngoài tệp nén không?**  
A: Có, viewer hỗ trợ PDF, Word, Excel và nhiều định dạng khác.

**Q: Tôi nên làm gì nếu quá trình render chậm?**  
A: Giảm số mục trên mỗi trang, bật streaming, hoặc xử lý các tệp nén theo batch nhỏ hơn.

**Q: Tôi có thể nhận hỗ trợ ở đâu?**  
A: Liên hệ qua [diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9).

**Q: Có thể nhúng CSS và hình ảnh trực tiếp vào HTML không?**  
A: Chắc chắn—sử dụng `HtmlViewOptions.forEmbeddedResources` như trong các ví dụ.

**Q: Làm sao tôi chuyển đổi hàng loạt một thư mục chứa các tệp nén?**  
A: Duyệt qua từng tệp bằng vòng lặp `for`, áp dụng cùng cấu hình `Viewer` và `HtmlViewOptions` cho mỗi lần lặp.

## Tài nguyên

- **Tài liệu:** Tìm hiểu sâu hơn về chức năng với [tài liệu GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Tham chiếu API:** Khám phá toàn bộ API tại [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Tải xuống:** Nhận các binary mới nhất từ [trang tải xuống](https://releases.groupdocs.com/viewer/java/).  
- **Mua và Cấp phép:** Xem các tùy chọn trên [trang mua](https://purchase.groupdocs.com/buy).  
- **Hỗ trợ và Cộng đồng:** Tham gia thảo luận trên [diễn đàn GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Cập nhật lần cuối:** 2026-02-23  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2  
**Tác giả:** GroupDocs