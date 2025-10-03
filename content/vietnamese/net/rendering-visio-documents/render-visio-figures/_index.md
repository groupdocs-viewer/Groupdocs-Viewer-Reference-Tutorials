---
"description": "Tìm hiểu cách hiển thị hình ảnh Visio bằng GroupDocs.Viewer cho .NET với hướng dẫn toàn diện này. Nâng cao khả năng xem tài liệu trong các ứng dụng .NET của bạn."
"linktitle": "Render hình ảnh Visio"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Render hình ảnh Visio"
"url": "/vi/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
type: docs
---
# Render hình ảnh Visio

## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc kết xuất tài liệu đóng vai trò quan trọng trong nhiều ứng dụng khác nhau. Cho dù là hiển thị tài liệu trên trang web hay chuyển đổi chúng sang các định dạng khác nhau, thì việc kết xuất hiệu quả là điều cần thiết. GroupDocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để xem và thao tác tài liệu trong các ứng dụng .NET. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc kết xuất các hình ảnh Visio bằng GroupDocs.Viewer for .NET, chia nhỏ quy trình thành các bước đơn giản.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. Thiết lập môi trường: Đảm bảo bạn có môi trường làm việc để phát triển .NET.
2. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Hiểu biết cơ bản về C#: Làm quen với những kiến thức cơ bản về ngôn ngữ lập trình C#.
4. Mẫu tài liệu Visio: Chuẩn bị sẵn một tài liệu Visio mẫu để kết xuất.

## Nhập không gian tên
Trong dự án C# của bạn, hãy bắt đầu bằng cách nhập các không gian tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Kết xuất sang HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Thư mục đầu ra: Xác định thư mục nơi mã HTML được kết xuất sẽ được lưu.
- Định dạng đường dẫn tệp trang: Chỉ định định dạng đường dẫn cho trang HTML.
- Khởi tạo Viewer: Khởi tạo đối tượng Viewer bằng đường dẫn đến tài liệu Visio.
- Tùy chọn chế độ xem HTML: Cấu hình các tùy chọn để hiển thị HTML.
- Tùy chọn kết xuất Visio: Đặt tùy chọn cụ thể cho kết xuất Visio, chẳng hạn như chỉ kết xuất hình ảnh và chiều rộng hình ảnh.
## 2. Kết xuất sang JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Tương tự như khi hiển thị sang HTML, hãy cấu hình các tùy chọn để hiển thị sang định dạng JPG.
## 3. Kết xuất sang PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Cấu hình để kết xuất sang định dạng PNG tuân theo mô hình tương tự như kết xuất JPG.
## 4. Kết xuất thành PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Để hiển thị thành PDF, hãy cấu hình các tùy chọn cụ thể cho định dạng PDF.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách kết xuất hình ảnh Visio bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp liền mạch các khả năng kết xuất tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm người dùng và năng suất.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh các tùy chọn kết xuất cho hình ảnh Visio không?
Có, GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn để tùy chỉnh kết xuất, bao gồm chiều rộng hình, chỉ hiển thị hình và nhiều tùy chọn khác.
### GroupDocs.Viewer cho .NET có phù hợp để dựng tài liệu quy mô lớn không?
Đúng vậy, GroupDocs.Viewer cho .NET được tối ưu hóa để xử lý hiệu quả việc hiển thị tài liệu quy mô lớn.
### GroupDocs.Viewer có hỗ trợ các định dạng tài liệu khác ngoài Visio không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Microsoft Office, AutoCAD, v.v.
### Tôi có thể tích hợp GroupDocs.Viewer vào các ứng dụng web không?
Có, GroupDocs.Viewer có thể được tích hợp liền mạch vào các ứng dụng web để xem và xử lý tài liệu.
### Có phiên bản dùng thử để kiểm tra trước khi mua không?
Có, bạn có thể tận dụng bản dùng thử miễn phí từ [trang web](https://releases.groupdocs.com/) để kiểm tra khả năng của GroupDocs.Viewer cho .NET.