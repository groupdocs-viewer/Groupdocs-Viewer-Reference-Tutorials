---
"date": "2025-04-24"
"description": "Tìm hiểu cách chuyển đổi các tệp RAR thành các định dạng có thể truy cập như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho Java. Hướng dẫn từng bước này bao gồm mọi thứ từ thiết lập đến hiển thị các thư mục cụ thể."
"title": "Kết xuất các tệp RAR thành HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho Java"
"url": "/vi/java/rendering-basics/render-rar-files-groupdocs-viewer-java/"
"weight": 1
type: docs
---
# Kết xuất các tệp RAR sang nhiều định dạng khác nhau bằng GroupDocs.Viewer cho Java

Mở khóa tiềm năng của kho lưu trữ RAR của bạn bằng cách chuyển đổi chúng thành các định dạng có thể truy cập như HTML, JPG, PNG và PDF với GroupDocs.Viewer for Java. Hướng dẫn này sẽ hướng dẫn bạn từng bước, cho phép quản lý và trình bày tài liệu liền mạch.

## Những gì bạn sẽ học được
- Kết xuất các tệp RAR thành nhiều định dạng bằng GroupDocs.Viewer cho Java.
- Ví dụ mã từng bước để chuyển đổi RAR sang HTML, JPG, PNG và PDF.
- Truy xuất thông tin chế độ xem từ kho lưu trữ RAR.
- Hiển thị các thư mục cụ thể trong tệp RAR.

Hãy cùng khám phá nhé!

### Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. **Bộ phát triển Java (JDK)**: Yêu cầu phiên bản 8 trở lên.
2. **Maven**Hướng dẫn này sử dụng Maven để quản lý sự phụ thuộc.
3. **GroupDocs.Viewer cho Thư viện Java**: Chúng tôi sẽ sử dụng phiên bản 25.2.

#### Thiết lập môi trường
- Đảm bảo môi trường phát triển của bạn được thiết lập với JDK và Maven đã cài đặt.
- Sự quen thuộc với các khái niệm lập trình Java cơ bản sẽ giúp bạn theo dõi dễ dàng hơn.

### Thiết lập GroupDocs.Viewer cho Java
Để tích hợp GroupDocs.Viewer vào dự án của bạn, hãy thêm các phụ thuộc sau vào `pom.xml` tài liệu:

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

#### Mua lại giấy phép
- **Dùng thử miễn phí**: Tải xuống bản dùng thử miễn phí từ [Trang web GroupDocs](https://releases.groupdocs.com/viewer/java/).
- **Giấy phép tạm thời**: Nhận giấy phép tạm thời cho các tính năng mở rộng tại [Trang giấy phép GroupDocs](https://purchase.groupdocs.com/temporary-license/).
- **Mua**: Để sử dụng lâu dài, hãy mua giấy phép thông qua [Trang mua hàng của GroupDocs](https://purchase.groupdocs.com/buy).

#### Khởi tạo cơ bản
Sau khi thiết lập môi trường và các phụ thuộc, hãy khởi tạo GroupDocs.Viewer như sau:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/file.rar")) {
            // Mã kết xuất của bạn ở đây
        }
    }
}
```

### Hướng dẫn thực hiện
Chúng ta sẽ khám phá cách chuyển đổi các tệp RAR thành nhiều định dạng khác nhau, mỗi định dạng có một bộ cấu hình riêng.

#### Chuyển đổi RAR sang HTML
**Tổng quan**: Chuyển đổi tệp RAR thành tài liệu HTML để xem trên web.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class RenderRarToHtml {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options); // Kết xuất tệp RAR sang định dạng HTML
        }
    }
}
```
- **Giải thích**: Các `HtmlViewOptions` lớp này được sử dụng với các tài nguyên nhúng, cho phép hiển thị toàn bộ trang web bao gồm CSS và hình ảnh.

#### Chuyển đổi RAR sang JPG
**Tổng quan**: Chuyển đổi tệp RAR thành hình ảnh JPEG, lý tưởng để xem trước hình thu nhỏ.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;

public class RenderRarToJpg {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.jpg");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options); // Chuyển đổi tệp RAR sang định dạng JPG
        }
    }
}
```
- **Giải thích**: `JpgViewOptions` chỉ định đường dẫn đầu ra và xử lý việc kết xuất hình ảnh.

#### Kết xuất RAR sang PNG
**Tổng quan**: Chuyển đổi tệp tin RAR thành hình ảnh PNG để xem trước chất lượng cao.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

public class RenderRarToPng {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.png");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options); // Kết xuất tệp RAR thành định dạng PNG
        }
    }
}
```
- **Giải thích**: Tương tự như JPG, `PngViewOptions` được sử dụng để hiển thị từng trang của RAR dưới dạng hình ảnh PNG.

#### Chuyển đổi RAR sang PDF
**Tổng quan**Tạo tài liệu PDF từ các tệp RAR để chia sẻ và in ấn dễ dàng.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class RenderRarToPdf {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result.pdf");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options); // Chuyển đổi tệp RAR sang định dạng PDF
        }
    }
}
```
- **Giải thích**: `PdfViewOptions` cấu hình đường dẫn đầu ra cho tài liệu PDF.

#### Nhận thông tin xem cho RAR
**Tổng quan**: Truy xuất siêu dữ liệu và thông tin cấu trúc từ kho lưu trữ RAR.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ArchiveViewInfo;

public class GetViewInfoForRar {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            ViewInfo info = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
            System.out.println("File type: " + info.getFileType());
            System.out.println("Pages count: " + info.getPages().size());

            readFolders(viewer, "");
        }
    }

    private static void readFolders(Viewer viewer, String folder) {
        ViewInfoOptions options = ViewInfoOptions.forHtmlView();
        options.getArchiveOptions().setFolder(folder);

        ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(options);
        for (String subFolder : viewInfo.getFolders()) {
            System.out.println(" - " + subFolder);
            readFolders(viewer, subFolder);
        }
    }
}
```
- **Giải thích**: Đoạn mã này sẽ lấy và in loại tệp và số trang trong tệp lưu trữ RAR.

#### Hiển thị thư mục cụ thể của kho lưu trữ RAR
**Tổng quan**: Tập trung vào việc chuyển đổi các thư mục cụ thể trong tệp RAR sang định dạng HTML.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class RenderSpecificArchiveFolder {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderSpecificArchiveFolder");
        Path pageFilePathFormat = outputDirectory.resolve("archive_folder_page_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            options.getArchiveOptions().setFolder("TargetFolderName"); // Chỉ định thư mục bạn muốn hiển thị
            viewer.view(options); // Hiển thị nội dung thư mục được chỉ định thành HTML
        }
    }
}
```
- **Giải thích**: Sử dụng `HtmlViewOptions` với các thiết lập thư mục cụ thể để nhắm mục tiêu và hiển thị từng thư mục trong kho lưu trữ RAR.

Bằng cách làm theo các bước sau, bạn có thể sử dụng GroupDocs.Viewer for Java một cách hiệu quả để quản lý và chuyển đổi các tệp RAR sang nhiều định dạng khác nhau.

## Phần kết luận

Hướng dẫn này cung cấp cho bạn kiến thức để dễ dàng chuyển đổi các tệp lưu trữ RAR sang các định dạng có thể truy cập như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer for Java. Bạn sẽ tìm hiểu chi tiết triển khai từng bước, bao gồm hiển thị các thư mục cụ thể và truy xuất thông tin lưu trữ, nâng cao khả năng quản lý tài liệu của bạn. Cho dù để xem trên web, xem trước hay chia sẻ, các kỹ thuật này sẽ hợp lý hóa cách bạn xử lý các tệp RAR trong các ứng dụng Java của mình.

### Câu hỏi thường gặp

1. **Tôi có thể chuyển đổi các tệp RAR được bảo vệ bằng mật khẩu bằng GroupDocs.Viewer cho Java không?**  

Có, nhưng bạn cần cung cấp mật khẩu trong tùy chọn để mở khóa và xem các kho lưu trữ được bảo vệ.

2. **Có thể chỉ hiển thị các trang hoặc thư mục cụ thể trong tệp RAR không?**  

Hoàn toàn có thể, bạn có thể chỉ định các thư mục hoặc trang để hiển thị bằng các tùy chọn chuyên dụng như `setFolder()` trong cài đặt hiển thị.

3. **GroupDocs.Viewer hỗ trợ những định dạng đầu ra nào cho tệp RAR?**  

Ứng dụng này hỗ trợ các định dạng HTML, JPG, PNG và PDF, cung cấp các tùy chọn linh hoạt để xem và chia sẻ.

4. **Tôi có cần giấy phép để sử dụng GroupDocs.Viewer cho Java không?**  

Có bản dùng thử miễn phí; để có đầy đủ tính năng và sử dụng lâu dài, bạn nên mua giấy phép hoặc xin giấy phép tạm thời.

5. **Tôi có thể tự động chuyển đổi RAR trong ứng dụng Java không?**  

Có, bạn có thể nhúng các ví dụ mã được cung cấp vào các dự án Java của mình để tự động chuyển đổi hàng loạt một cách liền mạch.