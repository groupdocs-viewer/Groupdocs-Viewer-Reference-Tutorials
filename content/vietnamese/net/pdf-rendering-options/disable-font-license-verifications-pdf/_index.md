---
"description": "Mở khóa khả năng xem tài liệu liền mạch trong .NET của bạn với GroupDocs.Viewer cho .NET. Dễ dàng tích hợp và tùy chỉnh kết xuất tài liệu với sự phụ thuộc tối thiểu."
"linktitle": "Tắt xác minh giấy phép phông chữ trong PDF"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Tắt xác minh giấy phép phông chữ trong PDF"
"url": "/vi/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
---

# Tắt xác minh giấy phép phông chữ trong PDF

## Giới thiệu
Trong lĩnh vực phát triển .NET, việc quản lý và thao tác tài liệu thường là khía cạnh quan trọng của nhiều ứng dụng. Cho dù đó là xem PDF, tài liệu Word hay các loại tệp khác, việc có các công cụ mạnh mẽ để xử lý các tác vụ này một cách hiệu quả là điều cần thiết. Đây là lúc GroupDocs.Viewer for .NET phát huy tác dụng. Thư viện mạnh mẽ này cung cấp cho các nhà phát triển khả năng tích hợp liền mạch chức năng xem tài liệu vào các ứng dụng .NET của họ.

![Tắt xác minh giấy phép phông chữ trong PDF bằng GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## Điều kiện tiên quyết
Trước khi bắt đầu sử dụng GroupDocs.Viewer cho .NET, bạn cần phải đáp ứng một số điều kiện tiên quyết sau:
### 1. Cài đặt Visual Studio
Trước tiên và quan trọng nhất, hãy đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. Bạn có thể tải xuống từ trang web của Microsoft nếu bạn chưa cài đặt.
### 2. Tải GroupDocs.Viewer cho .NET
Đi đến [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/) để có được phiên bản mới nhất của GroupDocs.Viewer cho .NET. Làm theo hướng dẫn cài đặt được cung cấp để thiết lập trong môi trường phát triển của bạn.
### 3. Xin giấy phép tạm thời
Để mở khóa toàn bộ tiềm năng của GroupDocs.Viewer cho .NET trong quá trình phát triển và thử nghiệm, bạn nên xin giấy phép tạm thời. Bạn có thể yêu cầu một giấy phép từ [đây](https://purchase.groupdocs.com/temporary-license/).

## Nhập không gian tên
Sau khi hoàn tất các điều kiện tiên quyết, bạn đã sẵn sàng để bắt đầu sử dụng GroupDocs.Viewer cho .NET trong các dự án của mình. Bắt đầu bằng cách nhập các không gian tên cần thiết vào cơ sở mã của bạn.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hiểu rõ hơn:
## Bước 1: Xác định thư mục đầu ra
Bắt đầu bằng cách xác định thư mục mà bạn muốn lưu trữ các trang tài liệu đã kết xuất.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Thiết lập định dạng cho đường dẫn tệp của từng trang trong tài liệu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Bước 3: Khởi tạo đối tượng Viewer
Tạo một thể hiện của lớp Viewer, truyền đường dẫn đến tài liệu bạn muốn xem.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
Xác định các tùy chọn để xem tài liệu dưới dạng HTML, chỉ định định dạng cho các tài nguyên được nhúng (ví dụ: hình ảnh).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Bước 5: Vô hiệu hóa xác minh giấy phép phông chữ
Bật tùy chọn tắt xác minh giấy phép phông chữ để đảm bảo hiển thị mượt mà.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Bước 6: Xem Tài liệu
Gọi phương thức View của đối tượng Viewer, truyền các tùy chọn đã cấu hình.
```csharp
viewer.View(options);
```
## Bước 7: Hiển thị thư mục đầu ra
Thông báo cho người dùng về vị trí lưu trữ các trang tài liệu đã kết xuất.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
GroupDocs.Viewer for .NET cung cấp cho các nhà phát triển một giải pháp toàn diện để tích hợp khả năng xem tài liệu vào các ứng dụng .NET của họ một cách dễ dàng. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể sử dụng hiệu quả thư viện mạnh mẽ này để nâng cao quy trình quản lý tài liệu của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có thể xử lý nhiều định dạng tài liệu không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, Microsoft Word, Excel, PowerPoint, v.v.
### GroupDocs.Viewer cho .NET có phù hợp với ứng dụng web không?
Hoàn toàn có thể, GroupDocs.Viewer có thể được tích hợp liền mạch vào cả ứng dụng máy tính để bàn và web được phát triển bằng công nghệ .NET.
### GroupDocs.Viewer có yêu cầu bất kỳ sự phụ thuộc bổ sung nào không?
Không, GroupDocs.Viewer cho .NET có rất ít sự phụ thuộc và có thể dễ dàng tích hợp vào các dự án hiện có của bạn.
### Tôi có thể tùy chỉnh giao diện của tài liệu được kết xuất không?
Có, GroupDocs.Viewer cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện và cách thức hiển thị của tài liệu sao cho phù hợp với yêu cầu cụ thể của bạn.
### Có hỗ trợ kỹ thuật cho GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể tìm kiếm sự hỗ trợ và hướng dẫn từ nhóm hỗ trợ tận tâm thông qua [diễn đàn](https://forum.groupdocs.com/c/viewer/9).