---
title: Tải tài liệu từ đĩa cục bộ
linktitle: Tải tài liệu từ đĩa cục bộ
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị liền mạch các tài liệu từ ổ đĩa cục bộ của bạn bằng Groupdocs.Viewer dành cho .NET. Nâng cao ứng dụng .NET của bạn bằng tài liệu hiệu quả.
weight: 10
url: /vi/net/loading-documents/loading-document-local-disk/
---
## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc hiển thị tài liệu hiệu quả là điều cần thiết cho nhiều ứng dụng khác nhau. Groupdocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để hiển thị tài liệu trực tiếp từ đĩa cục bộ của bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tải tài liệu từ đĩa cục bộ của bạn bằng Groupdocs.Viewer cho .NET. Cho dù bạn là nhà phát triển dày dặn kinh nghiệm hay mới bắt đầu, hướng dẫn từng bước này sẽ giúp bạn tích hợp liền mạch việc hiển thị tài liệu vào các ứng dụng .NET của mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Groupdocs.Viewer for .NET: Tải xuống và cài đặt phiên bản mới nhất từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển .NET: Đảm bảo bạn đã thiết lập môi trường phát triển .NET đang hoạt động trên hệ thống của mình.
3. Tài liệu cục bộ: Lưu trữ cục bộ các tài liệu bạn muốn hiển thị trên đĩa của bạn.

## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết để truy cập các chức năng của Groupdocs.Viewer cho .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Tải tài liệu từ đĩa cục bộ
Bắt đầu bằng cách thiết lập thư mục đầu ra nơi lưu các trang HTML được hiển thị.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 2: Khởi tạo tài liệu Viewer và Render
Khởi tạo đối tượng Viewer bằng đường dẫn của tài liệu và hiển thị nó bằng các tùy chọn xem HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 3: Hiển thị đầu ra
Sau khi kết xuất hoàn tất, hiển thị thông báo cho biết kết xuất thành công tài liệu nguồn và vị trí của tệp đầu ra.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách tải tài liệu từ ổ đĩa cục bộ của mình bằng Groupdocs.Viewer cho .NET. Công cụ mạnh mẽ này mở ra vô số khả năng hiển thị tài liệu trong các ứng dụng .NET của bạn.
## Câu hỏi thường gặp
### Tôi có thể hiển thị tài liệu có định dạng khác nhau bằng Groupdocs.Viewer cho .NET không?
Có, Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu bao gồm DOCX, PDF, XLSX, PPTX, v.v.
### Groupdocs.Viewer cho .NET có tương thích với tất cả các khung .NET không?
Groupdocs.Viewer cho .NET tương thích với hầu hết các khung .NET bao gồm .NET Core, .NET Framework và .NET Standard.
### Tôi có thể tùy chỉnh các tùy chọn hiển thị cho tài liệu của mình không?
Tuyệt đối! Groupdocs.Viewer for .NET cung cấp các tùy chọn tùy chỉnh mở rộng cho phép bạn điều chỉnh quy trình kết xuất theo yêu cầu cụ thể của mình.
### Có phiên bản dùng thử nào cho Groupdocs.Viewer cho .NET không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.groupdocs.com/).
### Tôi có thể tìm hỗ trợ hoặc tài nguyên bổ sung cho Groupdocs.Viewer dành cho .NET ở đâu?
 Để được hỗ trợ và có thêm tài nguyên, hãy truy cập Groupdocs.Viewer dành cho .NET[diễn đàn](https://forum.groupdocs.com/c/viewer/9).