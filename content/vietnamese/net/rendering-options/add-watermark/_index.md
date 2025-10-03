---
"description": "Tìm hiểu cách thêm hình mờ vào tài liệu một cách liền mạch bằng GroupDocs.Viewer cho .NET. Tăng cường bảo mật và xây dựng thương hiệu cho tài liệu bằng hướng dẫn dễ làm theo này."
"linktitle": "Thêm hình mờ vào tài liệu"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Thêm hình mờ vào tài liệu"
"url": "/vi/net/rendering-options/add-watermark/"
"weight": 10
type: docs
---
# Thêm hình mờ vào tài liệu

## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc quản lý và xem nhiều định dạng tài liệu khác nhau một cách liền mạch là điều cần thiết đối với nhiều doanh nghiệp và cá nhân. May mắn thay, với các công cụ như GroupDocs.Viewer cho .NET, việc xử lý tài liệu trở nên dễ dàng. Thư viện .NET mạnh mẽ này cho phép các nhà phát triển dễ dàng tích hợp chức năng xem tài liệu vào ứng dụng của họ, cho phép người dùng xem tài liệu mà không cần phần mềm gốc đã tạo ra chúng.
## Điều kiện tiên quyết
Trước khi bắt đầu sử dụng GroupDocs.Viewer cho .NET để thêm hình mờ vào tài liệu, hãy đảm bảo bạn có những điều sau:
1. Thiết lập môi trường: Thiết lập môi trường phát triển có cài đặt .NET Framework hoặc .NET Core.
2. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt thư viện GroupDocs.Viewer cho .NET từ [trang tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Tệp tài liệu: Chuẩn bị các tệp tài liệu bạn muốn làm việc, chẳng hạn như DOCX, PDF hoặc các tệp khác.
4. Kiến thức cơ bản về C#: Cần phải quen thuộc với ngôn ngữ lập trình C# để triển khai các ví dụ mã.

## Nhập không gian tên
Trước khi bắt đầu thêm hình mờ vào tài liệu bằng GroupDocs.Viewer cho .NET, hãy đảm bảo nhập các không gian tên cần thiết vào mã C# của bạn. Bước này cho phép bạn truy cập các lớp và phương thức do thư viện cung cấp một cách liền mạch.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, chúng ta hãy cùng tìm hiểu quy trình thêm hình mờ vào tài liệu bằng GroupDocs.Viewer cho .NET. Thực hiện theo các bước sau để tích hợp liền mạch chức năng hình mờ vào ứng dụng của bạn.
## Bước 1: Thiết lập thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Chỉ định thư mục mà bạn muốn lưu các tập tin đầu ra sau khi áp dụng hình mờ.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Đặt định dạng cho đường dẫn tệp của các trang được hiển thị. Trong ví dụ này, các tệp HTML có số trang sẽ được tạo.
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Mã tiếp tục ở bước tiếp theo...
}
```
Tạo một thể hiện của lớp Viewer, truyền đường dẫn đến tệp tài liệu dưới dạng tham số. Trong ví dụ này, chúng tôi sử dụng tệp DOCX mẫu.
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Cấu hình các tùy chọn chế độ xem HTML, bao gồm cả văn bản hình mờ mà bạn muốn thêm vào tài liệu.
## Bước 5: Xem Tài liệu có Hình mờ
```csharp
viewer.View(options);
```
Gọi phương thức View của đối tượng Viewer, truyền các tùy chọn đã cấu hình. Thao tác này sẽ hiển thị tài liệu có hình mờ đã chỉ định.
## Bước 6: Hiển thị đường dẫn thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc kết xuất tài liệu thành công và chỉ ra thư mục lưu các tệp đầu ra.

## Phần kết luận
GroupDocs.Viewer for .NET cung cấp một cách thuận tiện để thêm hình mờ vào tài liệu theo chương trình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch chức năng hình mờ vào các ứng dụng .NET của mình, tăng cường bảo mật và thương hiệu cho tài liệu.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh giao diện của hình mờ không?
Có, bạn có thể tùy chỉnh nhiều thuộc tính khác nhau của hình mờ, chẳng hạn như văn bản, phông chữ, màu sắc, kích thước và vị trí.
### GroupDocs.Viewer có hỗ trợ xem tài liệu từ các nguồn từ xa không?
Có, GroupDocs.Viewer hỗ trợ xem tài liệu từ bộ nhớ cục bộ cũng như URL từ xa.
### Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [đây](https://releases.groupdocs.com/).
### Tôi có thể thêm hình mờ vào nhiều trang của một tài liệu không?
Hoàn toàn có thể, GroupDocs.Viewer cho phép thêm hình mờ vào từng trang hoặc toàn bộ các trang của tài liệu.
### Tôi có thể nhận được hỗ trợ hoặc trợ giúp như thế nào nếu gặp bất kỳ vấn đề nào?
Bạn có thể tìm kiếm sự trợ giúp và hỗ trợ từ diễn đàn cộng đồng GroupDocs [đây](https://forum.groupdocs.com/c/viewer/9).