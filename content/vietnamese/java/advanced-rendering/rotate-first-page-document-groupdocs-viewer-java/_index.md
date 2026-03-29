---
date: '2026-03-29'
description: Tìm hiểu cách xoay trang 90 độ trong Java bằng GroupDocs Viewer, bao
  gồm cài đặt, mã nguồn và các mẹo hiệu suất.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Xoay trang 90 độ với GroupDocs Viewer cho Java
type: docs
url: /vi/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Xoay trang 90 độ với GroupDocs Viewer cho Java

Khi bạn cần **xoay trang 90 độ** trong một tài liệu—cho dù đó là PDF, tệp Word, hay bảng tính—việc thực hiện nó bằng chương trình giúp tiết kiệm thời gian và loại bỏ lỗi thủ công. Trong hướng dẫn nâng cao này, chúng tôi sẽ hướng dẫn các bước chính xác để xoay trang đầu tiên của bất kỳ tài liệu nào được hỗ trợ bằng **GroupDocs Viewer for Java**. Khi hoàn thành, bạn sẽ có một đoạn mã có thể tái sử dụng và chèn vào dự án của mình.  
Chúng tôi cũng sẽ thảo luận lý do xoay trang trong Java quan trọng, các kịch bản phổ biến nơi kỹ thuật này tỏa sáng, và cách giữ cho thao tác nhẹ nhàng.

![Xoay Trang Đầu Tiên của Tài liệu với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Câu trả lời nhanh
- **“rotate page 90 degrees” có nghĩa là gì?** Nó xoay trang đã chọn theo chiều kim đồng hồ một phần tư vòng.  
- **Thư viện nào xử lý việc xoay?** GroupDocs Viewer for Java cung cấp phương thức `rotatePage`.  
- **Tôi có thể xoay các trang PDF bằng Java không?** Có—sử dụng cùng một lời gọi `rotatePage`; nó hoạt động cho PDF, DOCX, XLSX và hơn nữa.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép trả phí cần thiết cho môi trường sản xuất.  
- **Hoạt động này có tốn bộ nhớ không?** Không khi bạn đóng instance `Viewer` kịp thời; xem các mẹo hiệu năng bên dưới.

## “rotate page 90 degrees” là gì?
Xoay một trang 90 độ sẽ thay đổi hướng của trang từ dọc sang ngang (hoặc ngược lại) mà không thay đổi nội dung bên dưới. Điều này đặc biệt hữu ích cho các bài thuyết trình, in đồ họa chỉ ngang, hoặc chỉnh sửa tài liệu quét bị chụp lệch.

## Tại sao phải xoay trang bằng chương trình với GroupDocs Viewer cho Java?
GroupDocs Viewer trừu tượng hoá những phức tạp của việc xử lý hàng chục định dạng tệp. Nó cho phép bạn áp dụng các biến đổi ở mức trang—như xoay—trong khi giữ nguyên tệp gốc. API có cú pháp mượt, an toàn đa luồng, và hoạt động trên bất kỳ môi trường Java 8+ nào, làm cho nó trở thành lựa chọn đáng tin cậy cho tự động hoá cấp doanh nghiệp.

## Yêu cầu trước
- **GroupDocs.Viewer for Java** (phiên bản mới nhất)
- **JDK 8** hoặc mới hơn
- **Maven** (hoặc Gradle) để quản lý phụ thuộc
- Một IDE như IntelliJ IDEA hoặc Eclipse
- Kiến thức cơ bản về Java I/O

## Cài đặt GroupDocs.Viewer cho Java

Thêm repository và dependency của GroupDocs vào `pom.xml` của bạn. Đoạn mã này không thay đổi so với hướng dẫn gốc:

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
- **Free trial** – tải xuống từ trang GroupDocs.  
- **Temporary license** – yêu cầu nếu bạn cần thời gian đánh giá kéo dài.  
- **Full license** – mua để triển khai trong môi trường sản xuất.

### Khởi tạo Viewer cơ bản
Đoạn mã sau cho thấy cách tối thiểu để tạo một instance `Viewer`. Giữ nguyên như đã hiển thị:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Cách xoay trang PDF trong Java với GroupDocs Viewer
Mặc dù API hoạt động trên nhiều định dạng, PDF là trường hợp sử dụng phổ biến nhất cho việc xoay trang. Phương thức `rotatePage` giống nhau được sử dụng, vì vậy bạn chỉ cần chỉ định viewer tới tệp PDF và chỉ số trang.

## Thực hiện từng bước: Xoay Trang Đầu Tiên 90 Độ

### 1. Nhập các gói cần thiết
Các import này cung cấp quyền truy cập vào các tùy chọn render PDF và enum xoay.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Định nghĩa vị trí đầu ra và tạo Viewer
Thay thế các đường dẫn placeholder bằng thư mục thực tế của bạn.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Cấu hình tùy chọn xem PDF và áp dụng xoay
Phương thức `rotatePage` nhận số trang (đánh số từ 1) và một giá trị enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Render tài liệu
Cuối cùng, gọi `view` để tạo PDF đã xoay.

```java
viewer.view(viewOptions);
```

#### Cách hoạt động
- **PdfViewOptions** cho Viewer biết xuất ra tệp PDF.  
- **rotatePage(int, Rotation)** chỉ xoay trang bạn chỉ định, các trang còn lại không bị ảnh hưởng.  
- Phương thức hỗ trợ `ON_90_DEGREE`, `ON_180_DEGREE`, và `ON_270_DEGREE`.

## Các vấn đề thường gặp và giải pháp

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| **FileNotFoundException** | Đường dẫn không đúng hoặc thư mục thiếu | Xác minh `YOUR_OUTPUT_DIRECTORY` và `YOUR_DOCUMENT_DIRECTORY` tồn tại và có thể đọc được. |
| **Unsupported file format** | Định dạng tệp không được hỗ trợ | Kiểm tra trang [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Không thấy sự xoay | Nhớ rằng `rotatePage` sử dụng chỉ số **1‑based**. |
| **Out‑of‑memory errors on large docs** | Lỗi thiếu bộ nhớ khi xử lý tài liệu lớn | Xử lý tài liệu tuần tự hoặc sử dụng pool luồng với độ đồng thời giới hạn. |

## Ứng dụng thực tiễn

1. **Điều chỉnh bài thuyết trình** – Chuyển đổi slide dọc sang ngang ngay lập tức.  
2. **Sửa chữa tài liệu hàng loạt** – Tự động sửa các PDF quét bị chụp lệch.  
3. **Đầu ra sẵn sàng in** – Đảm bảo đồ họa ngang in đúng trên giấy dọc.

## Mẹo hiệu năng

- **Đóng tài nguyên kịp thời** – Khối `try‑with‑resources` tự động giải phóng `Viewer`.  
- **Xử lý batch** – Khi xử lý nhiều tệp, tái sử dụng một instance `Viewer` cho mỗi luồng để giảm overhead.  
- **Giám sát bộ nhớ** – Đối với tài liệu lớn hơn 100 MB, cân nhắc stream đầu ra ra đĩa thay vì giữ trong bộ nhớ.

## Câu hỏi thường gặp

**Q: Tôi có thể xoay nhiều trang cùng lúc không?**  
A: Có—gọi `rotatePage()` cho mỗi số trang cần xoay.

**Q: Có cách nào để hoàn tác việc xoay sau khi render không?**  
A: Không trực tiếp. Bạn cần render lại tài liệu mà không áp dụng tùy chọn xoay.

**Q: Định dạng tệp nào hỗ trợ xoay trang trong GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, và nhiều định dạng khác được liệt kê trong tài liệu chính thức.

**Q: Làm sao tôi có thể xoay trang trong một loạt tài liệu tự động?**  
A: Đặt mã trong vòng lặp duyệt qua một tập hợp các đường dẫn tệp, áp dụng logic `rotatePage` cho mỗi tệp.

**Q: Thực hành tốt nhất để xử lý lỗi khi xoay là gì?**  
A: Bao quanh việc sử dụng Viewer trong khối `try‑catch`, ghi log ngoại lệ, và tùy chọn tiếp tục xử lý tệp tiếp theo.

## Tài nguyên

- **Tài liệu**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Tham khảo API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Tải xuống**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Mua**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Dùng thử miễn phí**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Giấy phép tạm thời**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Hỗ trợ**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-03-29  
**Kiểm thử với:** GroupDocs Viewer 25.2 for Java  
**Tác giả:** GroupDocs