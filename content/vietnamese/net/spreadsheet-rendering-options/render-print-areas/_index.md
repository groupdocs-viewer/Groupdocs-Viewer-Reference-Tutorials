---
"description": "Khám phá GroupDocs.Viewer cho .NET và dễ dàng hiển thị các vùng in ở nhiều định dạng tài liệu khác nhau. Hãy dùng thử miễn phí ngay!"
"linktitle": "Kết xuất vùng in"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị vùng in với GroupDocs.Viewer cho .NET"
"url": "/vi/net/spreadsheet-rendering-options/render-print-areas/"
"weight": 17
---

# Hiển thị vùng in với GroupDocs.Viewer cho .NET

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện này về cách tận dụng GroupDocs.Viewer cho .NET để hiển thị vùng in trong tài liệu của bạn. Nếu bạn là nhà phát triển .NET đang tìm kiếm giải pháp mạnh mẽ để hiển thị tài liệu, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình hiển thị vùng in bằng GroupDocs.Viewer, đảm bảo trải nghiệm liền mạch trong ứng dụng của bạn.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
- Có kiến thức cơ bản về phát triển C# và .NET.
- GroupDocs.Viewer cho .NET đã được cài đặt. Bạn có thể tải xuống [đây](https://releases.groupdocs.com/viewer/net/).
- Một tài liệu mẫu (ví dụ: "SAMPLE.XLSX") trong thư mục tài liệu bạn chỉ định.
## Nhập không gian tên
Hãy đảm bảo nhập các không gian tên cần thiết vào mã C# của bạn để triển khai đúng cách:
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
Tạo định dạng cho đường dẫn tệp trang, kết hợp thư mục đầu ra và chỗ giữ chỗ cho số trang:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo GroupDocs.Viewer
Khởi tạo lớp Viewer với đường dẫn đến tài liệu mẫu của bạn:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
Cấu hình tùy chọn chế độ xem HTML, chỉ định định dạng đường dẫn tệp trang và bật tùy chọn để hiển thị vùng in:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Bước 5: Kết xuất tài liệu
Gọi `View` phương pháp để hiển thị tài liệu với các tùy chọn được chỉ định:
```csharp
viewer.View(options);
```
## Bước 6: Hiển thị thông báo thành công
In thông báo thành công, cho biết tài liệu nguồn đã được kết xuất thành công:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách sử dụng GroupDocs.Viewer cho .NET để hiển thị vùng in trong tài liệu của bạn. Công cụ mạnh mẽ này mở ra những khả năng mới để hiển thị tài liệu trong các ứng dụng .NET của bạn.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với các định dạng tài liệu khác nhau không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, DOCX, XLSX, v.v. Tham khảo [tài liệu](https://tutorials.groupdocs.com/viewer/net/) để có danh sách đầy đủ.
### Tôi có thể dùng thử GroupDocs.Viewer trước khi mua không?
Chắc chắn rồi! Bạn có thể khám phá công cụ này với bản dùng thử miễn phí [đây](https://releases.groupdocs.com/).
### Tôi có thể tìm kiếm sự hỗ trợ hoặc trợ giúp cho bất kỳ vấn đề nào ở đâu?
Ghé thăm [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để kết nối với cộng đồng và nhận được sự hỗ trợ.
### Có tùy chọn cấp phép tạm thời nào không?
Có, bạn có thể xin giấy phép tạm thời [đây](https://purchase.groupdocs.com/temporary-license/).
### Tôi có thể mua GroupDocs.Viewer cho .NET ở đâu?
Bạn có thể thực hiện mua hàng của bạn [đây](https://purchase.groupdocs.com/buy).