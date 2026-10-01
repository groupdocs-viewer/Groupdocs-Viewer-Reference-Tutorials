---
date: '2026-09-30'
description: Tìm hiểu cách xoay trang 90 độ trong Java bằng GroupDocs Viewer, bao
  gồm setup, code và performance tips.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Xoay trang 90 độ trong Java bằng GroupDocs Viewer. Hướng dẫn step‑by‑step,
  performance tips và real‑world use cases cho developers.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Xoay trang 90 độ với GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Xoay trang 90 độ với GroupDocs Viewer for Java
type: docs
url: /vi/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Xoay trang 90 độ với GroupDocs Viewer cho Java

Nếu bạn cần **xoay trang 90 độ** trong một tài liệu—bất kể đó là PDF, tệp Word hay bảng tính—việc thực hiện bằng chương trình trong Java giúp tiết kiệm thời gian, loại bỏ lỗi thủ công và cho phép bạn nhúng thao tác này vào các quy trình tự động. Trong hướng dẫn nâng cao này, bạn sẽ học cách xoay trang đầu tiên của bất kỳ tài liệu nào được hỗ trợ bằng **GroupDocs Viewer cho Java**, lý do tính năng này quan trọng trong các dự án thực tế, và cách giữ cho quá trình nhẹ nhàng và tiết kiệm bộ nhớ.

![Xoay trang đầu tiên của tài liệu bằng GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Câu trả lời nhanh
- **Ý nghĩa của “xoay trang 90 độ” là gì?** Nó xoay trang đã chọn theo chiều kim đồng hồ một phần tư vòng.  
- **Thư viện nào thực hiện việc xoay?** GroupDocs Viewer cho Java cung cấp phương thức `rotatePage`.  
- **Tôi có thể xoay các trang PDF bằng Java không?** Có—sử dụng cùng lệnh `rotatePage`; nó hoạt động với PDF, DOCX, XLSX và các định dạng khác.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép trả phí cần thiết cho môi trường sản xuất.  
- **Hoạt động này có tốn nhiều bộ nhớ không?** Không, nếu bạn đóng nhanh đối tượng `Viewer`; xem các mẹo hiệu năng bên dưới.

## “Xoay trang 90 độ” là gì?
Xoay một trang 90 độ sẽ thay đổi hướng của trang từ dọc sang ngang (hoặc ngược lại) mà không thay đổi nội dung bên trong. Điều này hữu ích cho các bài thuyết trình, in đồ họa chỉ có dạng ngang, hoặc chỉnh sửa tài liệu quét bị chụp lệch. Việc xoay được thực hiện trong quá trình render, giữ nguyên file gốc.

## Tại sao phải xoay trang bằng chương trình với GroupDocs Viewer cho Java?
GroupDocs Viewer hỗ trợ **hơn 50 định dạng đầu vào và đầu ra**—bao gồm PDF, DOCX, PPTX, XLSX và nhiều loại ảnh—do đó bạn có thể render bất kỳ tài liệu nào mà không cần bộ chuyển đổi bên ngoài. API mượt mà, an toàn đa luồng và chạy trên bất kỳ môi trường Java 8+ nào, là lựa chọn đáng tin cậy cho tự động hoá cấp doanh nghiệp phải xử lý hàng chục loại file một cách nhất quán.

## Yêu cầu trước

- GroupDocs Viewer cho Java (phiên bản mới nhất)
- JDK 8 hoặc mới hơn
- Maven (hoặc Gradle) để quản lý phụ thuộc
- IDE như IntelliJ IDEA hoặc Eclipse
- Kiến thức cơ bản về Java I/O

## Cài đặt GroupDocs.Viewer cho Java

Thêm kho lưu trữ GroupDocs và phụ thuộc vào file `pom.xml` của bạn. Đoạn mã này không thay đổi so với hướng dẫn gốc:

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

### Cách lấy giấy phép
- **Bản dùng thử** – tải xuống từ trang GroupDocs.  
- **Giấy phép tạm thời** – yêu cầu nếu bạn cần thời gian đánh giá kéo dài.  
- **Giấy phép đầy đủ** – mua để triển khai trong môi trường sản xuất.

### Khởi tạo Viewer cơ bản
Lớp `Viewer` là điểm vào để tải tài liệu và cung cấp các phương thức render và chuyển đổi. Giữ nguyên mã như đã hiển thị:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Cách xoay trang PDF bằng Java với GroupDocs Viewer
Tải tệp mục tiêu bằng `Viewer`, chỉ định số trang, và gọi `rotatePage`. Phương thức này hoạt động với PDF, DOCX, PPTX, XLSX và bất kỳ định dạng nào khác được thư viện hỗ trợ. Sau khi xoay, bạn có thể render tài liệu thành PDF mới hoặc truyền trực tiếp tới client, đảm bảo file gốc không bị thay đổi.

## Hướng dẫn từng bước: xoay trang đầu tiên 90 độ

### 1. Nhập các gói cần thiết
`PdfViewOptions` chỉ cho Viewer xuất ra file PDF, trong khi enum `Rotation` định nghĩa góc xoay. Cả hai lớp đều thuộc gói `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Xác định vị trí đầu ra và tạo Viewer
Thay thế các đường dẫn placeholder bằng thư mục thực tế của bạn. Hàm khởi tạo `Viewer` nhận một đối tượng `File` trỏ tới tài liệu nguồn.

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
Phương thức `rotatePage(int, Rotation)` nhận một chỉ số trang **bắt đầu từ 1** và một giá trị enum `Rotation`. Trong ví dụ này chúng ta dùng `Rotation.ON_90_DEGREE` để xoay trang đầu tiên theo chiều kim đồng hồ.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Kết xuất tài liệu
Gọi `view` với các tùy chọn đã cấu hình sẽ ghi PDF đã xoay vào thư mục đầu ra.

```java
viewer.view(viewOptions);
```

#### Cách hoạt động
- **PdfViewOptions** chỉ định Viewer tạo file PDF đầu ra.  
- **rotatePage(int, Rotation)** xoay chỉ trang được chỉ định, các trang khác không thay đổi.  
- Phương thức hỗ trợ ba hằng số xoay: `ON_90_DEGREE`, `ON_180_DEGREE`, và `ON_270_DEGREE`.

## Các vấn đề thường gặp và giải pháp
| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| **FileNotFoundException** | Đường dẫn không đúng hoặc thư mục thiếu | Kiểm tra `YOUR_OUTPUT_DIRECTORY` và `YOUR_DOCUMENT_DIRECTORY` tồn tại và có quyền đọc. |
| **Unsupported file format** | Cố gắng xoay định dạng không được Viewer hỗ trợ | Kiểm tra trang [định dạng được hỗ trợ bởi GroupDocs Viewer]. |
| **No rotation visible** | Sử dụng số trang sai (đánh số từ 0) | Nhớ rằng `rotatePage` sử dụng chỉ số **bắt đầu từ 1**. |
| **Out‑of‑memory errors on large docs** | Render nhiều tệp lớn trong một luồng duy nhất | Xử lý tài liệu tuần tự hoặc sử dụng pool luồng với độ đồng thời giới hạn. |

## Ứng dụng thực tế

1. **Điều chỉnh bài thuyết trình** – Chuyển đổi slide dọc sang ngang ngay lập tức để có hiệu quả hình ảnh tốt hơn.  
2. **Sửa chữa tài liệu hàng loạt** – Tự động sửa các PDF quét bị chụp lệch, tiết kiệm hàng giờ công việc thủ công.  
3. **Đầu ra sẵn sàng in** – Đảm bảo đồ họa ngang in đúng trên giấy dọc mà không cần xoay thủ công trong driver máy in.  

## Mẹo hiệu năng

- **Đóng tài nguyên kịp thời** – Khối `try‑with‑resources` tự động giải phóng `Viewer`, giải phóng bộ nhớ.  
- **Xử lý batch** – Tái sử dụng một thể hiện `Viewer` cho mỗi luồng để giảm chi phí khởi tạo.  
- **Giám sát bộ nhớ** – Đối với tài liệu lớn hơn 100 MB, stream đầu ra ra đĩa thay vì giữ toàn bộ file trong bộ nhớ; GroupDocs Viewer có thể xử lý file 200 MB với dưới 250 MB RAM.  

## Câu hỏi thường gặp

**Hỏi: Tôi có thể xoay nhiều trang cùng lúc không?**  
**Đáp:** Có—gọi `rotatePage()` cho mỗi số trang cần xoay, có thể trong vòng lặp hoặc bằng cách chuỗi các lời gọi.

**Hỏi: Có cách nào để hoàn tác việc xoay sau khi render không?**  
**Đáp:** Không trực tiếp. Bạn cần render lại tài liệu mà không áp dụng tùy chọn xoay.

**Hỏi: Những định dạng file nào hỗ trợ xoay trang trong GroupDocs Viewer?**  
**Đáp:** DOCX, PDF, PPTX, XLSX và nhiều định dạng khác được liệt kê trong tài liệu chính thức.

**Hỏi: Làm sao để xoay trang trong một loạt tài liệu một cách tự động?**  
**Đáp:** Đặt logic xoay trong vòng lặp duyệt qua tập hợp các đường dẫn file, áp dụng cùng cấu hình `rotatePage` cho mỗi file.

**Hỏi: Thực hành tốt nhất để xử lý lỗi khi xoay là gì?**  
**Đáp:** Bao quanh việc sử dụng Viewer bằng khối `try‑catch`, ghi log chi tiết ngoại lệ, và tùy chọn tiếp tục xử lý file tiếp theo để tránh một lỗi duy nhất làm dừng toàn bộ batch.

## Tài nguyên

- **Tài liệu**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Tham chiếu API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Tải GroupDocs Viewer cho Java**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Mua giấy phép**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Dùng thử miễn phí**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Yêu cầu giấy phép tạm thời**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Diễn đàn GroupDocs**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-09-30  
**Kiểm tra với:** GroupDocs Viewer 25.2 for Java  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan

- [Cách xoay các trang PDF cụ thể với GroupDocs.Viewer cho Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Tải tài liệu từ URL trong Java – Hướng dẫn GroupDocs.Viewer](/viewer/java/document-loading/)
- [Các chế độ xem tài liệu Java của GroupDocs Viewer](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)