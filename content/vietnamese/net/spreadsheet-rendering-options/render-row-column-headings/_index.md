---
"description": "Cải thiện khả năng xem tài liệu trong .NET! Học cách hiển thị tiêu đề hàng và cột bằng GroupDocs.Viewer cho .NET. Khám phá đầu ra HTML, JPG, PNG và PDF."
"linktitle": "Hiển thị tiêu đề hàng và cột"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị tiêu đề hàng và cột"
"url": "/vi/net/spreadsheet-rendering-options/render-row-column-headings/"
"weight": 18
---

# Hiển thị tiêu đề hàng và cột

## Giới thiệu
Bạn có muốn nâng cao trải nghiệm xem tài liệu của mình trong các ứng dụng .NET không? Với GroupDocs.Viewer cho .NET, bạn có thể dễ dàng hiển thị tiêu đề hàng và cột từ các tệp bảng tính của mình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình hiển thị tiêu đề hàng và cột bằng các định dạng đầu ra khác nhau như HTML, JPG, PNG và PDF.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
- Đã cài đặt GroupDocs.Viewer cho thư viện .NET.
- Một tệp XLSX mẫu dùng cho mục đích thử nghiệm.
- Có kiến thức cơ bản về phát triển C# và .NET.
## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo bạn nhập các không gian tên cần thiết để sử dụng GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Thiết lập thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. Kết xuất thành HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. Kết xuất sang JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Kết xuất thành PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. Kết xuất thành PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## Phần kết luận
Xin chúc mừng! Bạn đã kết xuất thành công tiêu đề hàng và cột từ bảng tính của mình bằng GroupDocs.Viewer cho .NET. Thử nghiệm với các định dạng đầu ra khác nhau để phù hợp với nhu cầu của ứng dụng.
## Những câu hỏi thường gặp
### H: Tôi có thể tùy chỉnh thư mục đầu ra cho các tài liệu được kết xuất không?
A: Có, bạn có thể thiết lập thư mục đầu ra mong muốn của mình trong mã nơi `outputDirectory` biến được định nghĩa.
### H: GroupDocs.Viewer có tương thích với các định dạng bảng tính khác không?
A: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng bảng tính khác nhau, bao gồm XLS, XLSX, CSV, v.v.
### H: Tôi có thể xử lý các trường hợp ngoại lệ trong quá trình kết xuất như thế nào?
A: Bạn có thể triển khai các khối try-catch để xử lý các ngoại lệ và ghi nhật ký hoặc hiển thị các thông báo phù hợp cho người dùng.
### H: Có yêu cầu cấp phép nào khi sử dụng GroupDocs.Viewer trong ứng dụng của tôi không?
A: Có, bạn cần có giấy phép hợp lệ. Bạn có thể xin giấy phép tạm thời để thử nghiệm hoặc mua giấy phép đầy đủ để sản xuất.
### H: Tôi có thể tìm thêm sự hỗ trợ hoặc thảo luận trong cộng đồng ở đâu?
A: Ghé thăm [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ và thảo luận.