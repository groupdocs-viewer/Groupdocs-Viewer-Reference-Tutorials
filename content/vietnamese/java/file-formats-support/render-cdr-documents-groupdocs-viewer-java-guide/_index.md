---
date: '2026-08-19'
description: Tìm hiểu cách chuyển đổi cdr sang html, cũng như jpg, png và pdf, bằng
  cách sử dụng GroupDocs.Viewer cho Java. Bao gồm cài đặt, ví dụ mã, và mẹo hiệu suất.
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: Tìm hiểu cách chuyển đổi cdr sang html, jpg, png và pdf bằng GroupDocs.Viewer
  cho Java. Hướng dẫn từng bước với cài đặt, đoạn mã mẫu, và các thực hành tốt nhất
  về hiệu suất.
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: Chuyển đổi cdr sang html, jpg, png, pdf với GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: Chuyển đổi cdr sang html, jpg, png, pdf với GroupDocs.Viewer Java
type: docs
url: /vi/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# Chuyển đổi cdr sang html, jpg, png, pdf với GroupDocs.Viewer Java

Nếu bạn cần **convert cdr to html** (hoặc sang JPG, PNG và PDF) một cách nhanh chóng và đáng tin cậy, bạn đã đến đúng hướng dẫn. Trong hướng dẫn này, chúng tôi sẽ đi qua mọi thứ bạn cần — từ cài đặt GroupDocs.Viewer cho Java đến việc render các tệp CorelDRAW (CDR) thành các trang HTML thân thiện với web, hình ảnh chất lượng cao và PDF có thể đọc được trên mọi nền tảng. Khi kết thúc, bạn sẽ có thể tích hợp các chuyển đổi này vào bất kỳ ứng dụng Java nào chỉ với vài dòng mã.

![Render CDR Files với GroupDocs.Viewer cho Java](/viewer/file-formats-support/render-cdr-files.png)

[Render CDR Files với GroupDocs.Viewer cho Java](/viewer/file-formats-support/render-cdr-files.png)

## Câu trả lời nhanh
- **Thư viện nào chuyển đổi CDR sang HTML?** GroupDocs.Viewer for Java.  
- **Tôi cũng có thể chuyển đổi CDR sang JPG, PNG và PDF không?** Có — sử dụng cùng API Viewer với các tùy chọn view khác nhau.  
- **Tôi có cần giấy phép không?** Một bản dùng thử miễn phí hoặc giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được yêu cầu?** JDK 8 hoặc mới hơn.  
- **Có hỗ trợ chuyển đổi hàng loạt không?** Chắc chắn — chỉ cần lặp qua các tệp bằng cùng một instance Viewer.

## “convert cdr to html” là gì?
Chuyển đổi cdr sang html có nghĩa là biến đổi tệp vector CorelDRAW thành mã HTML tiêu chuẩn, tùy chọn nhúng hình ảnh và kiểu dáng để thiết kế có thể được xem trực tiếp trong trình duyệt web mà không cần phần mềm thiết kế gốc. Quá trình này bảo tồn bố cục, màu sắc và các hình dạng vector gốc bằng cách chuyển chúng thành các phần tử SVG có thể mở rộng hoặc hình ảnh raster được nhúng trong HTML, cho phép hiển thị chính xác trên mọi trình duyệt đồng thời giữ kích thước tệp thấp.

## Tại sao chuyển đổi cdr sang html, jpg, png hoặc pdf?
Bạn có thể render một nguồn CDR duy nhất thành bốn định dạng được hỗ trợ rộng rãi, mỗi định dạng phục vụ một mục đích riêng: HTML cho việc xem trước web ngay lập tức, JPG/PNG cho hình ảnh raster, và PDF cho tài liệu có thể in và lưu trữ. Sự linh hoạt này cho phép bạn cung cấp loại tệp tối ưu cho bất kỳ khách hàng nào, giảm việc sao lưu dữ liệu và bảo đảm tài sản của bạn luôn sẵn sàng cho tương lai.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Thư viện và phụ thuộc** – GroupDocs.Viewer đã được thêm vào dự án Maven của bạn.  
2. **Java Development Kit (JDK)** – phiên bản 8 hoặc mới hơn đã được cài đặt.  
3. **Kiến thức cơ bản về Java** – để hiểu các đoạn mã mẫu.

### Thư viện, phiên bản và phụ thuộc cần thiết

Thêm cấu hình Maven sau vào tệp `pom.xml` của bạn (giữ nguyên như trong hướng dẫn gốc):

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

GroupDocs.Viewer cung cấp bản dùng thử miễn phí, giấy phép tạm thời cho việc thử nghiệm, hoặc các tùy chọn mua bản đầy đủ:

- **Free trial** – Tải xuống từ [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **Temporary license** – Yêu cầu một giấy phép tại [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase** – Nhận giấy phép vĩnh viễn qua [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Cài đặt GroupDocs.Viewer cho Java

Viewer là lớp cốt lõi chịu trách nhiệm tải tài liệu và cung cấp các phương thức render cho mọi định dạng đầu ra được hỗ trợ.

### Cài đặt với Maven
Đoạn mã Maven ở trên sẽ tự động tải về tất cả các JAR cần thiết. Chỉ cần chạy `mvn clean install` sau khi lưu tệp.

### Khởi tạo giấy phép
`Viewer` là lớp cốt lõi chịu trách nhiệm tải tài liệu và cung cấp các phương thức render cho mọi định dạng đầu ra được hỗ trợ. Khởi tạo giấy phép của bạn trước khi render bất kỳ tài liệu nào:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Hướng dẫn triển khai

Dưới đây là các ví dụ từng bước cho mỗi định dạng đầu ra. Các khối mã giống hệt với hướng dẫn gốc; chúng tôi chỉ thêm phần giải thích xung quanh chúng.

### Cách chuyển đổi cdr sang html với GroupDocs.Viewer

Tải tệp CDR và gọi API render HTML – đó là tất cả những gì bạn cần để tạo markup sẵn sàng cho web. Quy trình yêu cầu thiết lập đường dẫn tệp, tạo một instance `HtmlViewOptions`, và gọi `viewer.view()`. Mô hình hai bước này hoạt động cho bất kỳ kích thước tài liệu nào và bảo tồn độ chính xác vector.

#### Render tài liệu cdr sang HTML
**Tổng quan:** Chuyển đổi các tệp CDR của bạn thành HTML thân thiện với web để dễ dàng chia sẻ.

**Bước 1 – thiết lập đường dẫn tệp**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Bước 2 – khởi tạo viewer và render**

HtmlViewOptions cấu hình việc render HTML, cho phép bạn nhúng tài nguyên hoặc lưu chúng riêng biệt. Đoạn mã dưới đây render mỗi trang thành một tệp HTML riêng trong khi nhúng hình ảnh dưới dạng chuỗi Base64.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Cách chuyển đổi cdr sang jpg với GroupDocs.Viewer

Bạn có thể tạo ra các hình ảnh JPEG chất lượng cao từ nguồn CDR chỉ trong hai dòng mã. Đầu tiên, cấu hình `JpgViewOptions` với chất lượng mong muốn, sau đó gọi `viewer.view()`. Cách tiếp cận này lý tưởng cho ảnh thu nhỏ, tệp đính kèm email, hoặc bất kỳ trường hợp nào cần hình raster gọn nhẹ.

#### Render tài liệu cdr sang JPG
**Tổng quan:** Tạo ra các hình ảnh JPEG chất lượng cao từ nguồn CDR của bạn.

**Bước 1 – thiết lập đường dẫn tệp**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Bước 2 – khởi tạo viewer và render**

JpgViewOptions định nghĩa các thiết lập render JPEG, chẳng hạn như chất lượng nén và cách đặt tên đầu ra. Ví dụ dưới đây lưu mỗi trang thành một tệp JPEG riêng.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Cách chuyển đổi cdr sang png với GroupDocs.Viewer

Đầu ra PNG cung cấp cho bạn các hình ảnh raster không mất dữ liệu, hoàn hảo cho lưu trữ hoặc xử lý đồ họa tiếp theo. Sử dụng `PngViewOptions` để giữ nguyên mọi pixel, sau đó render tài liệu trang theo trang.

#### Render tài liệu cdr sang PNG
**Tổng quan:** Tạo ra các hình ảnh PNG không mất dữ liệu cho mục đích lưu trữ hoặc thiết kế.

**Bước 1 – thiết lập đường dẫn tệp**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Bước 2 – khởi tạo viewer và render**

PngViewOptions chỉ định các tham số render PNG, bao gồm hỗ trợ nền trong suốt. Đoạn mã tự động tạo một PNG cho mỗi trang.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Cách chuyển đổi cdr sang pdf với GroupDocs.Viewer

Chuyển đổi một tệp CDR thành PDF mang lại cho bạn một tài liệu có thể đọc được trên mọi nền tảng, sẵn sàng in. `PdfViewOptions` xử lý việc chuyển đổi vector sang raster nội bộ, bảo tồn bố cục và phông chữ mà không cần Adobe Illustrator.

#### Render tài liệu cdr sang PDF
**Tổng quan:** Chuyển các tệp CDR của bạn thành PDF có thể đọc được trên mọi nền tảng.

**Bước 1 – thiết lập đường dẫn tệp**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Bước 2 – khởi tạo viewer và render**

PdfViewOptions kiểm soát việc tạo PDF, cho phép nhúng phông chữ và tùy chỉnh bố cục trang. Đoạn mã tạo một PDF duy nhất chứa tất cả các trang.

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Ứng dụng thực tế

- **Web portals:** Sử dụng chuyển đổi HTML để nhúng thiết kế CDR trực tiếp vào trang web của bạn.  
- **Image galleries:** Triển khai đầu ra JPG/PNG cho các bộ sưu tập tải nhanh hoặc catalog sản phẩm.  
- **Document sharing:** Cung cấp PDF cho khách hàng cần phiên bản có thể in, chỉ đọc.  
- **Archiving:** Lưu trữ đa dạng định dạng để đảm bảo khả năng truy cập trong tương lai bất kể thay đổi phần mềm.  
- **Cross‑platform integration:** Đưa các tệp đã tạo vào các dịch vụ downstream như OCR, analytics, hoặc hệ thống quản lý tài sản số.

## Các cân nhắc về hiệu năng

- **Dispose of Viewer instances** kịp thời (như trong ví dụ try‑with‑resources) để giải phóng bộ nhớ.  
- **Batch processing:** Lặp qua một tập hợp các tệp CDR bằng cùng một cấu hình Viewer để giảm tải.  
- **Resource allocation:** GroupDocs.Viewer có thể render tài liệu lên tới 500 trang mà không cần tải toàn bộ tệp vào bộ nhớ, nhưng các bản vẽ phức tạp có thể cần tăng kích thước heap. Giám sát việc sử dụng CPU và RAM trong quá trình chuyển đổi quy mô lớn.

## Những khó khăn thường gặp và mẹo khắc phục

- **Missing fonts:** Nếu đầu ra trông khác nhau, hãy đảm bảo các phông chữ cần thiết có sẵn trên máy chủ hoặc nhúng chúng qua `PdfViewOptions`.  
- **Large files:** Đối với các tệp CDR vượt quá 200 MB, hãy cân nhắc xử lý trang‑theo‑trang để tránh `OutOfMemoryError`.  
- **Incorrect image quality:** Điều chỉnh giá trị `setQuality` trong `JpgViewOptions` nếu JPEG xuất hiện quá nén.  
- **License errors:** Kiểm tra lại đường dẫn tệp giấy phép và đảm bảo phiên bản giấy phép khớp với phiên bản thư viện Viewer của bạn.

## Kết luận

Chúng tôi đã chỉ cho bạn cách **convert cdr to html**, cũng như sang JPG, PNG và PDF, bằng cách sử dụng GroupDocs.Viewer cho Java. Bằng cách làm theo các đoạn mã ngắn gọn và các mẹo thực hành tốt, bạn có thể nhúng các chuyển đổi này vào bất kỳ quy trình làm việc nào dựa trên Java, cung cấp các đầu ra linh hoạt, chất lượng cao cho người dùng.

### Các bước tiếp theo
- Thử nghiệm các tùy chọn render nâng cao như kích thước trang tùy chỉnh hoặc watermark.  
- Kết hợp quy trình chuyển đổi với một REST API để cung cấp dịch vụ chuyển đổi tệp theo yêu cầu.  
- Tham gia cộng đồng và đặt câu hỏi tại [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## Câu hỏi thường gặp

**Q: Tôi có thể chuyển đổi các tệp CDR được bảo mật bằng mật khẩu không?**  
A: Có. Tải tệp bằng một instance `Viewer` chấp nhận tham số mật khẩu (xem tài liệu API).

**Q: Có giới hạn về số trang có thể chuyển đổi cùng một lúc không?**  
A: Không có giới hạn cứng, nhưng các tệp rất lớn có thể yêu cầu nhiều bộ nhớ hơn; hãy cân nhắc xử lý trang‑theo‑trang.

**Q: Đầu ra HTML có bao gồm phông chữ được nhúng không?**  
A: Khi sử dụng `HtmlViewOptions.forEmbeddedResources`, phông chữ được nhúng dưới dạng Base64, đảm bảo hiển thị nhất quán trên mọi trình duyệt.

**Q: Làm sao kiểm soát chất lượng JPEG?**  
A: `JpgViewOptions` cung cấp phương thức `setQuality(int)` cho phép bạn chỉ định giá trị từ 1‑100.

**Q: Tôi có thể chuyển đổi tệp CDR trên máy chủ Linux không?**  
A: Hoàn toàn có thể — GroupDocs.Viewer không phụ thuộc vào nền tảng miễn là JDK đã được cài đặt.

---

**Last Updated:** 2026-08-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Các hướng dẫn liên quan

- [Cách chuyển đổi Excel sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [Cách chuyển đổi CF2 sang PDF, HTML, JPG, PNG với GroupDocs.Viewer cho Java](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)
- [Cách chuyển đổi pdf sang html và tối ưu chất lượng hình ảnh trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)