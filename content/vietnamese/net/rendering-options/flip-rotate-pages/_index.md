---
title: Lật và xoay trang
linktitle: Lật và xoay trang
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách tích hợp Groupdocs.Viewer dành cho .NET vào các ứng dụng của bạn để hiển thị, lật và xoay tài liệu liền mạch.
type: docs
weight: 12
url: /vi/net/rendering-options/flip-rotate-pages/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào các chức năng của Groupdocs.Viewer dành cho .NET, đặc biệt tập trung vào việc lật và xoay các trang. Groupdocs.Viewer cho .NET là một công cụ mạnh mẽ được thiết kế để hiển thị tài liệu ở nhiều định dạng khác nhau trong các ứng dụng .NET. Cho dù bạn đang phát triển hệ thống quản lý tài liệu hay cần tích hợp khả năng xem tài liệu vào phần mềm của mình, Groupdocs.Viewer for .NET đều cung cấp giải pháp hiệu quả.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
### Cài đặt Groupdocs.Viewer cho .NET
 Để sử dụng Groupdocs.Viewer cho .NET, bạn cần cài đặt gói thông qua Trình quản lý gói NuGet. Bạn có thể tìm thấy hướng dẫn cài đặt chi tiết trong[tài liệu](https://reference.groupdocs.com/viewer/net/).

## Nhập không gian tên
Đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình để sử dụng Groupdocs.Viewer cho .NET một cách hiệu quả.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Hãy chia nhỏ quá trình lật và xoay trang bằng Groupdocs.Viewer cho .NET thành các bước đơn giản:
## Bước 1: Đặt thư mục đầu ra và đường dẫn tệp
Xác định thư mục nơi bạn muốn lưu tệp đầu ra và chỉ định đường dẫn tệp đầu ra.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Bước 2: Khởi tạo đối tượng Viewer
Tạo một phiên bản của lớp Viewer bằng cách chuyển đường dẫn đến tài liệu bạn muốn xem.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Bước 3: Định cấu hình tùy chọn xem
Thiết lập các tùy chọn xem, chẳng hạn như chỉ định định dạng tệp đầu ra và bất kỳ cài đặt bổ sung nào như xoay trang.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Bước 4: Kết xuất tài liệu
Gọi phương thức View của đối tượng Viewer và chuyển các tùy chọn xem.
```csharp
viewer.View(viewOptions);
```
## Bước 5: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công và chỉ định thư mục đầu ra để xác minh.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Tóm lại, Groupdocs.Viewer for .NET cung cấp các khả năng mạnh mẽ để hiển thị tài liệu, bao gồm lật và xoay trang. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch các tính năng này vào các ứng dụng .NET của mình, nâng cao trải nghiệm xem tài liệu cho người dùng của bạn.
## Câu hỏi thường gặp
### Groupdocs.Viewer for .NET có tương thích với tất cả các định dạng tài liệu không?
Có, Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm DOCX, PDF, PPTX, v.v.
### Tôi có thể tùy chỉnh các tùy chọn xem ngoài việc lật và xoay trang không?
Hoàn toàn có thể, Groupdocs.Viewer dành cho .NET cung cấp nhiều tùy chọn tùy chỉnh khác nhau để xem tài liệu, cho phép bạn điều chỉnh trải nghiệm theo yêu cầu của mình.
### Có bản dùng thử miễn phí nào dành cho Groupdocs.Viewer dành cho .NET không?
 Có, bạn có thể tận dụng bản dùng thử miễn phí của Groupdocs.Viewer dành cho .NET bằng cách truy cập[trang mạng](https://releases.groupdocs.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Groupdocs.Viewer cho .NET?
 Bạn có thể tìm kiếm sự trợ giúp và tham gia với cộng đồng thông qua[Diễn đàn Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Tôi có thể lấy giấy phép tạm thời cho Groupdocs.Viewer cho .NET ở đâu?
 Giấy phép tạm thời cho Groupdocs.Viewer cho .NET có thể được lấy từ[trang mua hàng](https://purchase.groupdocs.com/temporary-license/).