---
"description": "Tìm hiểu cách hiển thị tài liệu có chú thích bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch."
"linktitle": "Kết xuất tài liệu với các bình luận"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất tài liệu với các bình luận"
"url": "/vi/net/rendering-options/render-document-comments/"
"weight": 13
---

# Kết xuất tài liệu với các bình luận

## Giới thiệu
GroupDocs.Viewer for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tích hợp liền mạch khả năng kết xuất tài liệu vào các ứng dụng .NET của họ. Cho dù bạn cần hiển thị tài liệu Word, bảng tính Excel, bản trình bày PowerPoint, tệp PDF hay các định dạng khác, GroupDocs.Viewer đều cung cấp một giải pháp đơn giản.
Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc kết xuất tài liệu có chú thích bằng GroupDocs.Viewer cho .NET. Chúng tôi sẽ hướng dẫn bạn qua các điều kiện tiên quyết, nhập không gian tên và cung cấp hướng dẫn từng bước để kết xuất tài liệu có chú thích, đảm bảo rằng bạn nắm rõ từng khái niệm.
## Điều kiện tiên quyết
Trước khi bắt đầu dựng tài liệu có chú thích bằng GroupDocs.Viewer cho .NET, hãy đảm bảo rằng bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
### Thiết lập môi trường phát triển .NET
Đảm bảo bạn đã thiết lập môi trường phát triển cho phát triển .NET. Bạn sẽ cần một IDE tương thích như Visual Studio và .NET SDK được cài đặt trên máy của bạn.
### GroupDocs.Viewer để cài đặt .NET
Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ trang web hoặc sử dụng liên kết tải xuống được cung cấp:
[Tải xuống GroupDocs.Viewer cho .NET](https://releases.groupdocs.com/viewer/net/)

## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án .NET của bạn. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để hiển thị tài liệu với các chú thích.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Thiết lập thư mục đầu ra nơi tài liệu được kết xuất có chú thích sẽ được lưu.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Xác định định dạng đường dẫn tệp cho từng trang của tài liệu được hiển thị bằng chú thích.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
Tạo một phiên bản của `Viewer` lớp, truyền đường dẫn đến tài liệu với các chú thích làm tham số.
```csharp
using (Viewer viewer = new Viewer("Path to Your Document with Comments"))
{
    // Tùy chọn kết xuất
}
```
## Bước 4: Cấu hình Tùy chọn Kết xuất
Chỉ định các tùy chọn hiển thị, bao gồm cài đặt cho tài nguyên nhúng và bình luận.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderComments = true;
```
## Bước 5: Kết xuất tài liệu với chú thích
Gọi `View` phương pháp của `Viewer` đối tượng, truyền các tùy chọn kết xuất.
```csharp
viewer.View(options);
```
## Bước 6: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu có bình luận đã được hiển thị thành công.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày quy trình kết xuất tài liệu có chú thích bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước và đảm bảo đáp ứng các điều kiện tiên quyết, bạn có thể tích hợp liền mạch các khả năng kết xuất tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể hiển thị tài liệu có định dạng phức tạp không?
Có, GroupDocs.Viewer hỗ trợ hiển thị tài liệu với nhiều thành phần định dạng khác nhau, bao gồm bảng, hình ảnh và phông chữ.
### GroupDocs.Viewer có tương thích với các định dạng tài liệu khác nhau không?
Hoàn toàn đúng, GroupDocs.Viewer có thể hiển thị nhiều định dạng tài liệu, bao gồm PDF, DOCX, XLSX, PPTX, v.v.
### Tôi có thể tùy chỉnh tùy chọn kết xuất theo yêu cầu cụ thể không?
Có, GroupDocs.Viewer cung cấp các tùy chọn kết xuất linh hoạt cho phép bạn tùy chỉnh đầu ra theo nhu cầu của ứng dụng.
### GroupDocs.Viewer có hỗ trợ hiển thị tài liệu từ nguồn bên ngoài không?
Có, bạn có thể kết xuất tài liệu từ nhiều nguồn khác nhau, bao gồm tệp cục bộ, luồng và URL.
### Có phiên bản dùng thử nào cho GroupDocs.Viewer không?
Có, bạn có thể bắt đầu dùng thử miễn phí GroupDocs.Viewer để khám phá các tính năng và khả năng của nó.