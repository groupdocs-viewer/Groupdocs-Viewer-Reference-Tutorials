---
title: Kết xuất vùng in bằng GroupDocs.Viewer cho .NET
linktitle: Hiển thị vùng in
second_title: API GroupDocs.Viewer .NET
description: Khám phá GroupDocs.Viewer dành cho .NET và dễ dàng hiển thị các vùng in ở nhiều định dạng tài liệu khác nhau. Hãy thử dùng thử miễn phí ngay bây giờ! #GroupDocs.Viewer
type: docs
weight: 17
url: /vi/net/spreadsheet-rendering-options/render-print-areas/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện này về cách tận dụng GroupDocs.Viewer dành cho .NET để hiển thị các vùng in trong tài liệu của bạn. Nếu bạn là nhà phát triển .NET đang tìm kiếm giải pháp mạnh mẽ để kết xuất tài liệu thì bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình hiển thị vùng in bằng GroupDocs.Viewer, đảm bảo trải nghiệm liền mạch trong ứng dụng của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về phát triển C# và .NET.
-  Đã cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống[đây](https://releases.groupdocs.com/viewer/net/).
- Một tài liệu mẫu (ví dụ: "SAMPLE.XLSX") trong thư mục tài liệu được chỉ định của bạn.
## Nhập không gian tên
Đảm bảo nhập các không gian tên cần thiết trong mã C# của bạn để triển khai đúng cách:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục tài liệu
Bắt đầu bằng cách chỉ định thư mục đầu ra cho các trang HTML được hiển thị:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Tạo định dạng cho đường dẫn tệp trang, kết hợp thư mục đầu ra và phần giữ chỗ cho số trang:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo GroupDocs.Viewer
Khởi tạo lớp Viewer bằng đường dẫn đến tài liệu mẫu của bạn:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
Định cấu hình tùy chọn chế độ xem HTML, chỉ định định dạng đường dẫn tệp trang và bật tùy chọn hiển thị vùng in:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Bước 5: Kết xuất tài liệu
 Gọi`View` phương thức hiển thị tài liệu với các tùy chọn đã chỉ định:
```csharp
viewer.View(options);
```
## Bước 6: Hiển thị thông báo thành công
In thông báo thành công, cho biết tài liệu nguồn đã được hiển thị thành công:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách sử dụng GroupDocs.Viewer dành cho .NET để hiển thị các vùng in trong tài liệu của mình. Công cụ mạnh mẽ này mở ra những khả năng mới cho việc hiển thị tài liệu trong các ứng dụng .NET của bạn.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với các định dạng tài liệu khác nhau không?
 Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, DOCX, XLSX, v.v. Tham khảo đến[tài liệu](https://reference.groupdocs.com/viewer/net/) để có danh sách đầy đủ.
### Tôi có thể dùng thử GroupDocs.Viewer trước khi mua hàng không?
 Tuyệt đối! Bạn có thể khám phá công cụ này với bản dùng thử miễn phí có sẵn[đây](https://releases.groupdocs.com/).
### Tôi có thể tìm sự hỗ trợ hoặc tìm kiếm sự trợ giúp cho bất kỳ vấn đề nào ở đâu?
 Tham quan[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)để kết nối với cộng đồng và nhận được sự trợ giúp.
### Có sẵn tùy chọn giấy phép tạm thời không?
 Có, bạn có thể có được giấy phép tạm thời[đây](https://purchase.groupdocs.com/temporary-license/).
### Tôi có thể mua GroupDocs.Viewer cho .NET ở đâu?
 Bạn có thể thực hiện mua hàng của bạn[đây](https://purchase.groupdocs.com/buy).