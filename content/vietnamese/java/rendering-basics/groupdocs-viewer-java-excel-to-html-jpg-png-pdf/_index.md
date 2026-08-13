---
date: '2026-06-05'
description: Tìm hiểu cách chuyển đổi Excel sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer
  Java. Hướng dẫn từng bước này bao gồm cài đặt, các tùy chọn render, và các trường
  hợp sử dụng thực tế.
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: Cách chuyển đổi Excel sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer Java
type: docs
url: /vi/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# Cách Chuyển Đổi Excel sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer Java

Chuyển đổi Excel sang HTML là một nhu cầu phổ biến khi bạn cần hiển thị dữ liệu bảng tính trên web đồng thời giữ nguyên tiêu đề hàng và cột. Trong hướng dẫn này, bạn sẽ học cách GroupDocs.Viewer cho Java đơn giản hoá **convert excel to html** cũng như cách render cùng một workbook sang các định dạng JPG, PNG và PDF. Chúng tôi sẽ đi qua các yêu cầu trước, cài đặt thư viện và từng kịch bản render với các đoạn mã sẵn sàng cho môi trường production.

## Câu trả lời nhanh
- **GroupDocs.Viewer có thể render Excel sang nhiều định dạng không?** Có – HTML, JPG, PNG và PDF được hỗ trợ ngay từ đầu.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép vĩnh viễn cần thiết cho môi trường production.  
- **Tiêu đề hàng và cột có được giữ lại không?** Đặt `setRenderHeadings(true)` trên view options để bao gồm chúng.  
- **Yêu cầu phiên bản Java nào?** Java 8 trở lên; thư viện tương thích với Java 11, 17 và các phiên bản sau.  
- **Quá trình chuyển đổi có nhanh cho các workbook lớn không?** GroupDocs.Viewer có thể xử lý bảng tính 200 trang trong chưa đầy một giây trên phần cứng máy chủ tiêu chuẩn.

## “convert excel to html” là gì?
**Convert excel to html** có nghĩa là chuyển đổi một workbook Excel thành tài liệu HTML sẵn sàng cho web trong khi giữ nguyên bố cục, công thức và tiêu đề gốc. Điều này cho phép nhúng liền mạch các bảng tính vào các trang web hoặc cổng thông tin mà không yêu cầu người dùng cuối phải cài đặt Excel.

## Tại sao nên sử dụng GroupDocs.Viewer Java để render Excel?
GroupDocs.Viewer Java hỗ trợ **hơn 50 định dạng đầu vào và đầu ra**, bao gồm DOCX, XLSX, PPTX, HTML, JPG, PNG và PDF. Nó xử lý các workbook hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại tốc độ chuyển đổi lên tới **10 × nhanh hơn** so với nhiều giải pháp mã nguồn mở. Thư viện còn cung cấp kiểm soát chi tiết về các tùy chọn render như hiển thị tiêu đề, kích thước trang và chất lượng hình ảnh.

## Yêu cầu trước

- **Java Development Kit (JDK) 8+** được cài đặt và cấu hình trong IDE của bạn (IntelliJ IDEA, Eclipse, v.v.).  
- **Maven** để quản lý phụ thuộc.  
- Kiến thức cơ bản về cú pháp Java và `pom.xml` của Maven.  
- Giấy phép **GroupDocs.Viewer Java** đang hoạt động (dùng thử hoặc bản đầy đủ).

### Thư viện và phụ thuộc cần thiết
Thêm phụ thuộc GroupDocs.Viewer Java vào `pom.xml` của bạn:

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

### Cài đặt môi trường
- Xác minh `java -version` trả về 1.8 hoặc mới hơn.  
- Mở IDE yêu thích và tạo một dự án Maven.

Hãy bắt đầu với các yêu cầu trước khi chúng ta đi vào triển khai.

![chuyển đổi tệp Excel sang HTML, JPG, PNG và PDF với GroupDocs.Viewer cho Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## Cài đặt GroupDocs.Viewer Java

### Thông tin cài đặt
Bao gồm phụ thuộc Maven được hiển thị ở trên trong `pom.xml` của dự án. Sau khi chạy `mvn clean install`, thư viện sẽ có sẵn trên classpath của bạn.

### Các bước mua giấy phép
1. **Dùng thử miễn phí:** Tải phiên bản dùng thử từ [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
2. **Giấy phép tạm thời:** Nhận giấy phép tạm thời để thử nghiệm kéo dài từ [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
3. **Mua bản đầy đủ:** Được giấy phép đầy đủ cho môi trường production tại [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Khởi tạo cơ bản
Lớp `Viewer` là điểm vào cho mọi thao tác render. Khởi tạo nó rất đơn giản:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

Điều này tạo một thể hiện `Viewer` được liên kết với tệp giấy phép cục bộ, sẵn sàng xử lý các tệp Excel.

## Hướng dẫn triển khai

Dưới đây chúng tôi sẽ đề cập tới mỗi mục tiêu render. Đối với mỗi định dạng, chúng tôi sẽ **nhập các lớp cần thiết**, **đặt thư mục đầu ra**, và cuối cùng **cấu hình view options** với `setRenderHeadings(true)` để giữ tiêu đề hàng/cột.

### Render bảng tính sang HTML
**Làm thế nào để chuyển đổi một workbook Excel sang HTML bằng GroupDocs.Viewer Java?**  
Để chuyển đổi workbook Excel sang HTML, tải tệp bằng Viewer, tạo một thể hiện `HtmlViewOptions`, bật render tiêu đề, và gọi phương thức `view`. Quá trình sẽ ghi mỗi worksheet vào các tệp HTML riêng, giữ nguyên định dạng ô, công thức và bố cục gốc để hiển thị chính xác trên web.

#### Hướng dẫn từng bước
**1. Nhập các thư viện cần thiết**  
`HtmlViewOptions` cấu hình cách workbook được render sang HTML, cho phép tùy chỉnh tiêu đề, kiểu dáng và bố cục trang.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Đặt thư mục đầu ra**  
Chỉ định thư mục nơi các trang HTML được tạo sẽ được ghi.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Khởi tạo Viewer và cấu hình tùy chọn**  
Tạo một thể hiện `Viewer`, đặt `setRenderHeadings(true)`, và gọi `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Giải thích:** `HtmlViewOptions` điều khiển đầu ra HTML. Bật `setRenderHeadings(true)` đảm bảo rằng hàng và cột đầu tiên (thường là tiêu đề) xuất hiện trong HTML kết quả, giúp dữ liệu ngay lập tức dễ hiểu.

### Render bảng tính sang JPG
**Làm thế nào để render một sheet Excel thành ảnh JPG với tiêu đề được bao gồm?**  
Render một sheet Excel thành JPG bao gồm việc khởi tạo Viewer với workbook, tạo đối tượng `JpgViewOptions`, đặt `renderHeadings` thành true, và gọi `view`. Thư viện rasterize mỗi trang ở DPI được chỉ định, tạo ra các tệp JPG độ phân giải cao vẫn giữ cấu trúc visual và tiêu đề của bảng tính.

#### Hướng dẫn từng bước
**1. Nhập các thư viện cần thiết**  
`JpgViewOptions` định nghĩa các cài đặt cho việc render worksheet thành ảnh JPG, bao gồm DPI, chất lượng và khả năng hiển thị tiêu đề.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Đặt thư mục đầu ra**  
Xác định nơi các tệp JPG sẽ được lưu.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Khởi tạo Viewer và cấu hình tùy chọn**  
Tạo Viewer, bật render tiêu đề, và thực hiện chuyển đổi.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Giải thích:** `JpgViewOptions` cho phép bạn kiểm soát DPI và chất lượng. Với `setRenderHeadings(true)`, các ảnh kết quả vẫn giữ các hàng và cột tiêu đề, rất quan trọng cho báo cáo và bài thuyết trình.

### Render bảng tính sang PNG
**Quy trình chuyển đổi Excel sang PNG trong khi giữ tiêu đề cột là gì?**  
Để tạo ảnh PNG từ tệp Excel, sử dụng Viewer để mở workbook, tạo một thể hiện `PngViewOptions`, bật render tiêu đề, và thực thi `view`. Đầu ra PNG cung cấp chất lượng không mất dữ liệu, giữ nguyên mọi kiểu ô và hàng tiêu đề, lý tưởng cho lưu trữ hoặc xử lý ảnh tiếp theo.

#### Hướng dẫn từng bước
**1. Nhập các thư viện cần thiết**  
`PngViewOptions` điều khiển việc render worksheet sang ảnh PNG, cung cấp nén không mất dữ liệu và tùy chọn tiêu đề.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Đặt thư mục đầu ra**  
Chọn thư mục cho đầu ra PNG.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Khởi tạo Viewer và cấu hình tùy chọn**  
Tạo Viewer, bật render tiêu đề, và gọi `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Giải thích:** Khi gọi `setRenderHeadings(true)`, các tệp PNG sẽ bao gồm các hàng và cột tiêu đề gốc, bảo toàn ngữ cảnh cho người dùng downstream.

### Render bảng tính sang PDF
**Làm thế nào để chuyển đổi tệp Excel sang PDF với tiêu đề hàng và cột hiển thị?**  
Chuyển đổi Excel sang PDF rất đơn giản: khởi tạo Viewer với tệp nguồn, cấu hình một đối tượng `PdfViewOptions` để render tiêu đề, và gọi `view`. PDF kết quả phản ánh bố cục của workbook, bao gồm tiêu đề hàng và cột, đồng thời hỗ trợ đồ họa vector cho việc in ấn và phân phối sắc nét.

#### Hướng dẫn từng bước
**1. Nhập các thư viện cần thiết**  
`PdfViewOptions` chỉ định các tham số tạo PDF như kích thước trang, lề và render tiêu đề.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Đặt thư mục đầu ra**  
Chỉ định thư mục đích cho tài liệu PDF.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Khởi tạo Viewer và cấu hình tùy chọn**  
Tạo một `Viewer`, bật render tiêu đề, và thực hiện chuyển đổi.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Giải thích:** Đặt `setRenderHeadings(true)` trên `PdfViewOptions` đảm bảo rằng hàng và cột đầu tiên xuất hiện trong PDF cuối cùng, làm cho tài liệu sẵn sàng cho việc in ấn hoặc lưu trữ.

## Ứng dụng thực tế
Các kịch bản thực tế nơi **convert excel to html**, **excel to pdf java**, hoặc **convert spreadsheet to image** trở nên vô giá:

1. **Báo cáo doanh nghiệp:** Tạo dashboard HTML hoặc báo cáo PDF từ mô hình tài chính mà không cần sao chép thủ công.  
2. **Trực quan hoá dữ liệu:** Nhúng ảnh JPG/PNG của bảng tính vào slide deck, đảm bảo tiêu đề cung cấp ngữ cảnh ngay lập tức.  
3. **Lưu trữ tài liệu:** Lưu trữ workbook Excel dưới dạng PDF để tuân thủ quy định, đồng thời giữ nguyên bố cục và tiêu đề gốc.  
4. **Cổng thông tin web:** Phục vụ phiên bản HTML của bảng tính trực tiếp trong trình duyệt, cho phép lọc tương tác bằng JavaScript.

## Câu hỏi thường gặp

**Q: Tôi có thể chuyển đổi các tệp Excel được bảo vệ bằng mật khẩu không?**  
A: Có. Chỉ cần truyền mật khẩu vào constructor của `Viewer`, thư viện sẽ giải mã workbook trước khi render.

**Q: GroupDocs.Viewer có hỗ trợ workbook có macro (.xlsm) không?**  
A: Hoàn toàn. Viewer xử lý macro như dữ liệu; chúng sẽ bị bỏ qua trong quá trình render, đảm bảo chuyển đổi an toàn.

**Q: Kích thước tệp tối đa được hỗ trợ là bao nhiêu?**  
A: Thư viện có thể xử lý các tệp lên tới **2 GB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, nhờ kiến trúc streaming.

**Q: Có thể render chỉ một worksheet cụ thể không?**  
A: Có. Sử dụng `ViewOptions.setPageNumber(pageIndex)` để chỉ định một sheet khi tạo HTML, JPG, PNG hoặc PDF.

**Q: Làm sao để kiểm soát chất lượng ảnh JPG?**  
A: Đặt `JpgViewOptions.setQuality(90)` (giá trị 0‑100) để cân bằng giữa kích thước tệp và độ sắc nét.

## Kết luận
Bạn đã có một hướng dẫn hoàn chỉnh, sẵn sàng cho production để **convert excel to html**, **excel to pdf java**, và **convert spreadsheet to image** bằng GroupDocs.Viewer Java. Bằng cách làm theo các bước trên, bạn có thể tích hợp việc render bảng tính vào bất kỳ backend Java nào, cung cấp báo cáo HTML, ảnh độ phân giải cao, hoặc PDF lưu trữ với tiêu đề được giữ tự động.

---

**Cập nhật lần cuối:** 2026-06-05  
**Kiểm tra với:** GroupDocs.Viewer Java 23.12  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan

- [Cách Chuyển Đổi DOCX sang HTML bằng GroupDocs.Viewer cho Java: Hướng Dẫn Từng Bước](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Render HTML Đáp Ứng với GroupDocs.Viewer cho Java: Hướng Dẫn Toàn Diện](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – Chuyển Đổi ODF sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer cho Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)