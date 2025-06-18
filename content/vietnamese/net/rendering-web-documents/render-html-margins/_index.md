---
"description": "Tìm hiểu cách hiển thị HTML với lề tùy chỉnh trong .NET bằng GroupDocs.Viewer. Cải thiện khả năng trình bày tài liệu một cách dễ dàng."
"linktitle": "Hiển thị HTML với Lề do Người dùng Xác định"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị HTML với Lề do Người dùng Xác định"
"url": "/vi/net/rendering-web-documents/render-html-margins/"
"weight": 11
---

# Hiển thị HTML với Lề do Người dùng Xác định

## Giới thiệu
Trong lĩnh vực phát triển .NET, việc hiển thị HTML với lề do người dùng xác định là một khía cạnh quan trọng để tạo ra các tài liệu hấp dẫn về mặt hình ảnh. Cho dù đó là điều chỉnh lề cho một trang web hay cấu hình bố cục in, việc kiểm soát chính xác các lề sẽ nâng cao khả năng trình bày nội dung tổng thể. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc sử dụng GroupDocs.Viewer cho .NET để đạt được chức năng này một cách liền mạch.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Cài đặt thư viện GroupDocs.Viewer cho .NET. Bạn có thể tải xuống từ [trang web](https://releases.groupdocs.com/viewer/net/).
2. Môi trường .NET: Có môi trường làm việc để phát triển .NET.
3. Tài liệu HTML: Chuẩn bị một tài liệu HTML mà bạn muốn hiển thị với lề tùy chỉnh.

## Nhập không gian tên
Trước khi bắt đầu, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Bước 1: Thiết lập thư mục đầu ra
Xác định thư mục mà bạn muốn lưu các tập tin đã kết xuất:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Thiết lập định dạng cho đường dẫn tệp của các trang được hiển thị:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## Bước 3: Điều chỉnh lề cho kết xuất JPG
Cấu hình lề để hiển thị HTML sang định dạng JPG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## Bước 4: Điều chỉnh lề cho kết xuất PNG
Tương tự như vậy, hãy điều chỉnh lề để hiển thị HTML sang định dạng PNG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## Bước 5: Điều chỉnh lề để kết xuất PDF
Để hiển thị PDF, hãy thiết lập lề cho phù hợp:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```

## Phần kết luận
Tùy chỉnh lề khi hiển thị tài liệu HTML trong .NET bằng GroupDocs.Viewer cho phép các nhà phát triển tùy chỉnh cách trình bày nội dung một cách chính xác. Bằng cách làm theo hướng dẫn này, bạn có thể dễ dàng điều chỉnh lề cho các định dạng đầu ra JPG, PNG hoặc PDF, tăng cường tính hấp dẫn trực quan và khả năng đọc của tài liệu.
## Câu hỏi thường gặp
### GroupDocs.Viewer for .NET có tương thích với các định dạng HTML khác không?
GroupDocs.Viewer hỗ trợ nhiều định dạng HTML, đảm bảo khả năng tương thích với nhiều tài liệu HTML khác nhau.
### Tôi có thể điều chỉnh lề động dựa trên nội dung tài liệu không?
Có, bạn có thể điều chỉnh lề theo chương trình dựa trên thuộc tính của tài liệu hoặc hướng dẫn của người dùng.
### Có bất kỳ hạn chế nào đối với việc điều chỉnh biên độ không?
GroupDocs.Viewer cung cấp tính linh hoạt trong việc điều chỉnh lề, cho phép tùy chỉnh trong phạm vi hợp lý.
### GroupDocs.Viewer có hỗ trợ các định dạng đầu ra khác ngoài JPG, PNG và PDF không?
Có, GroupDocs.Viewer hỗ trợ hiển thị ở nhiều định dạng khác nhau, bao gồm TIFF, SVG, v.v.
### Tôi có thể tìm kiếm thêm sự hỗ trợ hoặc báo cáo các vấn đề liên quan đến GroupDocs.Viewer bằng cách nào?
Bạn có thể truy cập diễn đàn GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ và thảo luận.