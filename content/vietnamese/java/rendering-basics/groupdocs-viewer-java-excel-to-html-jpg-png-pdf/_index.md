---
"date": "2025-04-24"
"description": "Tìm hiểu cách chuyển đổi tệp Excel thành HTML, JPG, PNG và PDF bằng GroupDocs.Viewer Java. Hướng dẫn này bao gồm thiết lập, tùy chọn kết xuất và ứng dụng thực tế."
"title": "Cách sử dụng GroupDocs.Viewer Java để chuyển đổi Excel sang HTML/JPG/PNG/PDF - Hướng dẫn từng bước"
"url": "/vi/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
type: docs
---
# Cách sử dụng GroupDocs.Viewer Java để chuyển đổi Excel sang HTML/JPG/PNG/PDF: Hướng dẫn từng bước

## Giới thiệu

Việc chuyển đổi dữ liệu bảng tính sang nhiều định dạng khác nhau như HTML, JPG, PNG hoặc PDF trong khi vẫn giữ nguyên các chi tiết quan trọng như tiêu đề hàng và cột là điều cần thiết trong nhiều trường hợp. Cho dù bạn đang tạo báo cáo, chia sẻ thông tin với các bên liên quan hay tích hợp bảng tính vào các ứng dụng web, việc chuyển đổi các trang tính Excel có thể là một yêu cầu quan trọng. Hướng dẫn này sẽ hướng dẫn bạn cách GroupDocs.Viewer Java thực hiện các tác vụ này một cách dễ dàng và chính xác.

**Những gì bạn sẽ học được:**
- Thiết lập và sử dụng GroupDocs.Viewer cho Java
- Kết xuất các tệp Excel thành các định dạng HTML, JPG, PNG và PDF
- Cấu hình các tùy chọn để bao gồm tiêu đề hàng và cột trong đầu ra của bạn
- Ứng dụng thực tế của các tài liệu được kết xuất

Chúng ta hãy bắt đầu với các điều kiện tiên quyết cần thiết trước khi bắt tay vào triển khai.

## Điều kiện tiên quyết

Trước khi hiển thị bảng tính bằng GroupDocs.Viewer Java, hãy đảm bảo bạn có:

### Thư viện và phụ thuộc bắt buộc

Thiết lập GroupDocs.Viewer cho Java bằng Maven. Sau đây là cách đưa nó vào dự án của bạn:

**Thiết lập Maven:**
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

### Thiết lập môi trường
- Đảm bảo bạn đã cài đặt Java Development Kit (JDK).
- Sử dụng IDE như IntelliJ IDEA hoặc Eclipse để thuận tiện cho việc phát triển.

### Điều kiện tiên quyết về kiến thức
- Quen thuộc với lập trình Java
- Hiểu biết cơ bản về Maven để quản lý sự phụ thuộc

Với những điều kiện tiên quyết này, chúng ta hãy tiến hành thiết lập GroupDocs.Viewer cho Java và bắt đầu triển khai các tính năng.

## Thiết lập GroupDocs.Viewer cho Java

GroupDocs.Viewer for Java là một thư viện đa năng cho phép bạn hiển thị tài liệu ở nhiều định dạng khác nhau. Sau đây là cách bắt đầu:

### Thông tin cài đặt
Như đã đề cập, hãy sử dụng Maven để thêm GroupDocs.Viewer làm phần phụ thuộc trong dự án của bạn `pom.xml` tài liệu.

### Các bước xin cấp giấy phép
1. **Dùng thử miễn phí:** Tải xuống phiên bản dùng thử từ [Dùng thử miễn phí GroupDocs](https://releases.groupdocs.com/viewer/java/).
2. **Giấy phép tạm thời:** Nhận giấy phép tạm thời cho nhiều tính năng hơn từ [Giấy phép tạm thời của GroupDocs](https://purchase.groupdocs.com/temporary-license/).
3. **Mua:** Để có quyền truy cập và hỗ trợ đầy đủ, hãy mua giấy phép tại [Mua GroupDocs](https://purchase.groupdocs.com/buy).

### Khởi tạo cơ bản
Sau khi cài đặt, bạn có thể khởi tạo GroupDocs.Viewer bằng:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Mã của bạn ở đây để sử dụng trình xem
        }
    }
}
```
Thao tác này sẽ khởi tạo môi trường của bạn, thiết lập để bạn có thể kết xuất tài liệu.

## Hướng dẫn thực hiện

Hãy cùng phân tích từng tính năng và tìm hiểu cách triển khai chúng một cách chi tiết.

### Kết xuất bảng tính sang HTML
**Tổng quan:** Chuyển đổi các bảng tính Excel sang định dạng HTML trong khi vẫn giữ nguyên tiêu đề hàng và cột cho các bài thuyết trình hoặc báo cáo trên web.

#### Thực hiện từng bước:
##### 1. Nhập thư viện cần thiết
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2. Thiết lập thư mục đầu ra
Xác định nơi lưu trữ các tệp đã kết xuất của bạn.
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3. Khởi tạo Viewer và Cấu hình Tùy chọn
Sử dụng GroupDocs.Viewer để hiển thị tài liệu:
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Cho phép hiển thị tiêu đề hàng và cột trong bảng tính.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Hiển thị trang 1 đến 3.
}
```
**Giải thích:** Các `HtmlViewOptions` lớp được sử dụng để cấu hình đầu ra HTML. Thiết lập `setRenderHeadings(true)` đảm bảo rằng các tiêu đề hàng và cột được hiển thị trong HTML được kết xuất.

### Kết xuất bảng tính sang JPG
**Tổng quan:** Chuyển đổi các bảng tính Excel thành các tệp hình ảnh chất lượng cao (JPG) trong khi bao gồm các tiêu đề hàng và cột, lý tưởng cho các bài thuyết trình trực quan hoặc bản in.

#### Thực hiện từng bước:
##### 1. Nhập thư viện cần thiết
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2. Thiết lập thư mục đầu ra
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3. Khởi tạo Viewer và Cấu hình Tùy chọn
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Cho phép hiển thị tiêu đề hàng và cột trong bảng tính.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Hiển thị trang 1 đến 3.
}
```
**Giải thích:** `JpgViewOptions` xử lý cài đặt hình ảnh. `setRenderHeadings(true)` Tùy chọn này đảm bảo rằng tiêu đề được bao gồm trong đầu ra JPG.

### Kết xuất bảng tính thành PNG
**Tổng quan:** Chuyển đổi các bảng tính Excel sang định dạng PNG trong khi vẫn giữ nguyên tiêu đề hàng và cột, phù hợp để xuất ra hình ảnh chất lượng cao.

#### Thực hiện từng bước:
##### 1. Nhập thư viện cần thiết
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2. Thiết lập thư mục đầu ra
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3. Khởi tạo Viewer và Cấu hình Tùy chọn
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Cho phép hiển thị tiêu đề hàng và cột trong bảng tính.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Hiển thị trang 1 đến 3.
}
```
**Giải thích:** `PngViewOptions` được sử dụng cho các thiết lập PNG. Với `setRenderHeadings(true)`, tiêu đề được bao gồm trong hình ảnh đầu ra.

### Kết xuất bảng tính thành PDF
**Tổng quan:** Chuyển đổi các trang tính Excel sang định dạng PDF trong khi vẫn đảm bảo hiển thị tiêu đề hàng và cột, hoàn hảo cho việc lưu trữ hoặc chia sẻ tài liệu.

#### Thực hiện từng bước:
##### 1. Nhập thư viện cần thiết
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2. Thiết lập thư mục đầu ra
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3. Khởi tạo Viewer và Cấu hình Tùy chọn
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Cho phép hiển thị tiêu đề hàng và cột trong bảng tính.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Hiển thị trang 1 đến 3.
}
```
**Giải thích:** `PdfViewOptions` cấu hình cài đặt đầu ra PDF. `setRenderHeadings(true)` Tùy chọn này đảm bảo tiêu đề hiển thị trong tệp PDF cuối cùng.

## Ứng dụng thực tế
Sau đây là một số tình huống thực tế có thể áp dụng các tính năng này:

1. **Báo cáo kinh doanh:** Chia sẻ báo cáo chi tiết với các bên liên quan bằng cách chuyển đổi dữ liệu Excel sang định dạng HTML hoặc PDF để dễ dàng phổ biến và xem.
2. **Hình ảnh hóa dữ liệu:** Chuyển đổi bảng tính sang định dạng hình ảnh như JPG hoặc PNG để trình bày, đảm bảo tiêu đề cung cấp ngữ cảnh cho dữ liệu được trực quan hóa.
3. **Lưu trữ tài liệu:** Sử dụng tính năng chuyển đổi PDF để lưu trữ tài liệu theo định dạng có thể truy cập phổ biến, giữ nguyên mọi thông tin chi tiết cần thiết như tiêu đề.