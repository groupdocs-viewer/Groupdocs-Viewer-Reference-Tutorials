---
title: Kết xuất số liệu Visio
linktitle: Kết xuất số liệu Visio
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị số liệu Visio bằng GroupDocs.Viewer cho .NET với tính năng toàn diện này. Nâng cao khả năng xem tài liệu trong các ứng dụng .NET của bạn.
type: docs
weight: 10
url: /vi/net/rendering-visio-documents/render-visio-figures/
---
## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc kết xuất tài liệu đóng một vai trò quan trọng trong nhiều ứng dụng khác nhau. Cho dù đó là hiển thị tài liệu trên trang web hay chuyển đổi chúng sang các định dạng khác nhau, việc hiển thị hiệu quả là điều cần thiết. GroupDocs.Viewer dành cho .NET cung cấp giải pháp mạnh mẽ để xem và thao tác tài liệu trong các ứng dụng .NET. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc hiển thị các số liệu Visio bằng GroupDocs.Viewer cho .NET, chia nhỏ quy trình thành các bước đơn giản.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Thiết lập môi trường: Đảm bảo bạn có môi trường làm việc để phát triển .NET.
2.  GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Hiểu biết cơ bản về C#: Làm quen với các nguyên tắc cơ bản của ngôn ngữ lập trình C#.
4. Tài liệu Visio mẫu: Chuẩn bị sẵn tài liệu Visio mẫu để hiển thị.

## Nhập không gian tên
Trong dự án C# của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Hiển thị sang HTML
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
- Thư mục đầu ra: Xác định thư mục nơi HTML được hiển thị sẽ được lưu.
- Định dạng đường dẫn tệp trang: Chỉ định định dạng đường dẫn cho trang HTML.
- Khởi tạo trình xem: Khởi tạo đối tượng Trình xem bằng đường dẫn đến tài liệu Visio.
- Tùy chọn chế độ xem HTML: Định cấu hình các tùy chọn để hiển thị HTML.
- Tùy chọn hiển thị Visio: Đặt các tùy chọn cụ thể cho hiển thị Visio, chẳng hạn như chỉ hiển thị hình và chiều rộng hình.
## 2. Hiển thị sang JPG
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
- Tương tự như hiển thị sang HTML, định cấu hình các tùy chọn hiển thị sang định dạng JPG.
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
- Cấu hình để hiển thị sang định dạng PNG tuân theo mẫu tương tự như hiển thị JPG.
## 4. Hiển thị sang PDF
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
- Để hiển thị thành PDF, hãy định cấu hình các tùy chọn dành riêng cho định dạng PDF.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách hiển thị số liệu Visio bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp liền mạch khả năng kết xuất tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm và năng suất của người dùng.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh các tùy chọn hiển thị cho số liệu Visio không?
Có, GroupDocs.Viewer dành cho .NET cung cấp các tùy chọn mở rộng để tùy chỉnh kết xuất, bao gồm chiều rộng hình, chỉ hiển thị hình, v.v.
### GroupDocs.Viewer cho .NET có phù hợp để hiển thị tài liệu quy mô lớn không?
Hoàn toàn có thể, GroupDocs.Viewer dành cho .NET được tối ưu hóa để xử lý hiệu quả việc hiển thị tài liệu quy mô lớn.
### GroupDocs.Viewer có hỗ trợ các định dạng tài liệu khác ngoài Visio không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Microsoft Office, AutoCAD, v.v.
### Tôi có thể tích hợp GroupDocs.Viewer vào các ứng dụng web không?
Có, GroupDocs.Viewer có thể được tích hợp liền mạch vào các ứng dụng web để xem và thao tác với tài liệu.
### Có phiên bản dùng thử để thử nghiệm trước khi mua không?
Có, bạn có thể tận dụng bản dùng thử miễn phí từ[trang mạng](https://releases.groupdocs.com/) để kiểm tra khả năng của GroupDocs.Viewer dành cho .NET.