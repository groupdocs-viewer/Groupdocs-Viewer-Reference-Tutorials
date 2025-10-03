---
"description": "Tìm hiểu cách tích hợp Groupdocs.Viewer cho .NET vào ứng dụng của bạn để hiển thị, lật và xoay tài liệu một cách liền mạch."
"linktitle": "Lật và Xoay Trang"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Lật và Xoay Trang"
"url": "/vi/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# Lật và Xoay Trang

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào các chức năng của Groupdocs.Viewer cho .NET, đặc biệt tập trung vào việc lật và xoay trang. Groupdocs.Viewer cho .NET là một công cụ mạnh mẽ được thiết kế để hiển thị tài liệu ở nhiều định dạng khác nhau trong các ứng dụng .NET. Cho dù bạn đang phát triển hệ thống quản lý tài liệu hay cần tích hợp khả năng xem tài liệu vào phần mềm của mình, Groupdocs.Viewer cho .NET đều cung cấp một giải pháp hiệu quả.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
### Cài đặt Groupdocs.Viewer cho .NET
Để sử dụng Groupdocs.Viewer cho .NET, bạn cần cài đặt gói thông qua NuGet Package Manager. Bạn có thể tìm thấy hướng dẫn cài đặt chi tiết trong [tài liệu](https://tutorials.groupdocs.com/viewer/net/).

## Nhập không gian tên
Đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình để sử dụng Groupdocs.Viewer cho .NET một cách hiệu quả.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Chúng ta hãy chia nhỏ quy trình lật và xoay trang bằng Groupdocs.Viewer cho .NET thành các bước đơn giản:
## Bước 1: Thiết lập thư mục đầu ra và đường dẫn tệp
Xác định thư mục mà bạn muốn lưu tệp đầu ra và chỉ định đường dẫn đến tệp đầu ra.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Bước 2: Khởi tạo đối tượng Viewer
Tạo một thể hiện của lớp Viewer bằng cách truyền đường dẫn đến tài liệu bạn muốn xem.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Bước 3: Cấu hình Tùy chọn chế độ xem
Thiết lập các tùy chọn chế độ xem, chẳng hạn như chỉ định định dạng tệp đầu ra và bất kỳ cài đặt bổ sung nào như xoay trang.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Bước 4: Kết xuất tài liệu
Gọi phương thức View của đối tượng Viewer và truyền các tùy chọn chế độ xem.
```csharp
viewer.View(viewOptions);
```
## Bước 5: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công và chỉ định thư mục đầu ra để xác minh.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Tóm lại, Groupdocs.Viewer for .NET cung cấp các khả năng mạnh mẽ để hiển thị tài liệu, bao gồm lật và xoay trang. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch các tính năng này vào ứng dụng .NET của mình, nâng cao trải nghiệm xem tài liệu cho người dùng.
## Câu hỏi thường gặp
### Groupdocs.Viewer cho .NET có tương thích với mọi định dạng tài liệu không?
Có, Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm DOCX, PDF, PPTX, v.v.
### Tôi có thể tùy chỉnh các tùy chọn xem ngoài việc lật và xoay trang không?
Đúng vậy, Groupdocs.Viewer cho .NET cung cấp nhiều tùy chọn tùy chỉnh để xem tài liệu, cho phép bạn tùy chỉnh trải nghiệm theo yêu cầu của mình.
### Có bản dùng thử miễn phí của Groupdocs.Viewer dành cho .NET không?
Có, bạn có thể dùng thử miễn phí Groupdocs.Viewer cho .NET bằng cách truy cập [trang web](https://releases.groupdocs.com/).
### Tôi có thể nhận được hỗ trợ cho Groupdocs.Viewer dành cho .NET như thế nào?
Bạn có thể tìm kiếm sự hỗ trợ và tham gia với cộng đồng thông qua [Diễn đàn Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Tôi có thể lấy giấy phép tạm thời cho Groupdocs.Viewer dành cho .NET ở đâu?
Giấy phép tạm thời cho Groupdocs.Viewer cho .NET có thể được lấy từ [trang mua hàng](https://purchase.groupdocs.com/temporary-license/).