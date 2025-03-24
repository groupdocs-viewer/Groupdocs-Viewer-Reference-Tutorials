---
title: Hiển thị HTML đáp ứng
linktitle: Hiển thị HTML đáp ứng
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị HTML phản hồi bằng Groupdocs.Viewer dành cho .NET, đảm bảo trải nghiệm xem tối ưu trên các thiết bị.
weight: 13
url: /vi/net/rendering-documents-html/render-responsive-html/
---
## Giới thiệu
Groupdocs.Viewer cho .NET là một thư viện mạnh mẽ cho phép các nhà phát triển hiển thị các định dạng tài liệu khác nhau thành HTML đáp ứng. Hướng dẫn này sẽ hướng dẫn bạn qua quá trình hiển thị HTML đáp ứng bằng Groupdocs.Viewer cho .NET. Khi kết thúc hướng dẫn này, bạn sẽ có thể chuyển đổi liền mạch các tài liệu thành HTML để thích ứng với các kích thước màn hình khác nhau, đảm bảo trải nghiệm xem tối ưu trên các thiết bị.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo rằng bạn có những điều sau:
1.  Groupdocs.Viewer for .NET Library: Tải xuống và cài đặt thư viện từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Đảm bảo bạn có môi trường phát triển phù hợp được thiết lập để phát triển .NET.
3. Tệp tài liệu: Chuẩn bị các tệp tài liệu mà bạn muốn hiển thị thành HTML đáp ứng.

## Nhập không gian tên
Để bắt đầu hiển thị HTML đáp ứng, hãy nhập các vùng tên cần thiết vào dự án của bạn:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Hãy chia quá trình kết xuất thành nhiều bước:
## Bước 1: Đặt thư mục đầu ra
Xác định thư mục nơi bạn muốn lưu các trang HTML được hiển thị:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Chỉ định định dạng đặt tên tệp HTML cho mỗi trang:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
Tạo một thể hiện của lớp Viewer và chỉ định tài liệu sẽ được hiển thị:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Mã kết xuất sẽ ở đây
}
```
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
Thiết lập các tùy chọn chế độ xem HTML, bao gồm bật hiển thị phản hồi:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderResponsive = true;
```
## Bước 5: Kết xuất tài liệu thành HTML
Sử dụng phương thức View của đối tượng Viewer để hiển thị tài liệu thành HTML:
```csharp
viewer.View(options);
```
## Bước 6: Xuất thông báo thành công
Hiển thị thông báo cho biết tài liệu đã được kết xuất thành công:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Tóm lại, Groupdocs.Viewer cho .NET cung cấp một giải pháp liền mạch để hiển thị tài liệu thành HTML đáp ứng. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng chuyển đổi tài liệu của mình sang định dạng HTML thích ứng với các kích thước màn hình khác nhau, đảm bảo trải nghiệm xem tối ưu cho người dùng của bạn.
## Câu hỏi thường gặp
### Groupdocs.Viewer for .NET có tương thích với tất cả các định dạng tài liệu không?
Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu bao gồm DOCX, PDF, PPTX, XLSX, v.v.
### Tôi có thể tùy chỉnh giao diện của HTML được hiển thị không?
Có, bạn có thể tùy chỉnh các tùy chọn hiển thị khác nhau như hướng trang, chất lượng và hình mờ theo yêu cầu của bạn.
### Groupdocs.Viewer cho .NET có yêu cầu giấy phép sử dụng thương mại không?
 Có, cần có giấy phép thương mại để sử dụng Groupdocs.Viewer cho .NET trong môi trường sản xuất. Bạn có thể mua giấy phép từ[trang mạng](https://purchase.groupdocs.com/buy).
### Có bản dùng thử miễn phí nào dành cho Groupdocs.Viewer dành cho .NET không?
 Có, bạn có thể tận dụng bản dùng thử miễn phí Groupdocs.Viewer dành cho .NET từ[trang mạng](https://releases.groupdocs.com/).
### Tôi có thể nhận hỗ trợ cho Groupdocs.Viewer cho .NET ở đâu?
Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Groupdocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9).