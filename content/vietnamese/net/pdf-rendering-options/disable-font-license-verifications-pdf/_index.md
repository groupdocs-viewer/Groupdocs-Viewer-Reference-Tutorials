---
title: Tắt xác minh giấy phép phông chữ trong PDF
linktitle: Tắt xác minh giấy phép phông chữ trong PDF
second_title: API GroupDocs.Viewer .NET
description: Mở khóa khả năng xem tài liệu liền mạch trong .NET của bạn với GroupDocs.Viewer dành cho .NET. Dễ dàng tích hợp và tùy chỉnh kết xuất tài liệu với mức độ phụ thuộc tối thiểu.
type: docs
weight: 12
url: /vi/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## Giới thiệu
Trong lĩnh vực phát triển .NET, việc quản lý và thao tác với tài liệu thường là một khía cạnh quan trọng của nhiều ứng dụng. Cho dù đó là xem tệp PDF, tài liệu Word hay các loại tệp khác, việc có các công cụ mạnh mẽ để xử lý các tác vụ này một cách hiệu quả là điều cần thiết. Đây là lúc GroupDocs.Viewer dành cho .NET phát huy tác dụng. Thư viện mạnh mẽ này cung cấp cho các nhà phát triển khả năng tích hợp liền mạch chức năng xem tài liệu vào các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào sử dụng GroupDocs.Viewer cho .NET, bạn cần phải có một số điều kiện tiên quyết:
### 1. Cài đặt Visual Studio
Trước hết, hãy đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. Bạn có thể tải xuống từ trang web của Microsoft nếu chưa có.
### 2. Tải GroupDocs.Viewer cho .NET
 Đi tới[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/) để có phiên bản mới nhất của GroupDocs.Viewer cho .NET. Làm theo hướng dẫn cài đặt được cung cấp để thiết lập nó trong môi trường phát triển của bạn.
### 3. Xin giấy phép tạm thời
 Để khai thác toàn bộ tiềm năng của GroupDocs.Viewer cho .NET trong quá trình phát triển và thử nghiệm, bạn nên có giấy phép tạm thời. Bạn có thể yêu cầu một từ[đây](https://purchase.groupdocs.com/temporary-license/).

## Nhập không gian tên
Sau khi hoàn thành các điều kiện tiên quyết, bạn đã sẵn sàng bắt đầu sử dụng GroupDocs.Viewer cho .NET trong dự án của mình. Bắt đầu bằng cách nhập các không gian tên cần thiết vào cơ sở mã của bạn.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Hãy chia ví dụ được cung cấp thành nhiều bước để hiểu rõ hơn:
## Bước 1: Xác định thư mục đầu ra
Bắt đầu bằng cách xác định thư mục nơi bạn muốn lưu trữ các trang tài liệu được hiển thị.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Đặt định dạng cho đường dẫn tệp của các trang riêng lẻ của tài liệu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Bước 3: Khởi tạo đối tượng Viewer
Tạo một thể hiện của lớp Viewer, chuyển đường dẫn đến tài liệu bạn muốn xem.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
Xác định các tùy chọn để xem tài liệu dưới dạng HTML, chỉ định định dạng cho các tài nguyên được nhúng (ví dụ: hình ảnh).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Bước 5: Vô hiệu hóa xác minh giấy phép phông chữ
Bật tùy chọn tắt xác minh giấy phép phông chữ để đảm bảo hiển thị mượt mà.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Bước 6: Xem tài liệu
Gọi phương thức View của đối tượng Viewer, chuyển các tùy chọn đã cấu hình.
```csharp
viewer.View(options);
```
## Bước 7: Hiển thị thư mục đầu ra
Thông báo cho người dùng về vị trí lưu trữ các trang tài liệu được hiển thị.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
GroupDocs.Viewer dành cho .NET cung cấp cho các nhà phát triển một giải pháp toàn diện để tích hợp khả năng xem tài liệu vào các ứng dụng .NET của họ một cách dễ dàng. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể sử dụng hiệu quả thư viện mạnh mẽ này để nâng cao quy trình quản lý tài liệu của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có thể xử lý nhiều định dạng tài liệu không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, Microsoft Word, Excel, PowerPoint, v.v.
### GroupDocs.Viewer cho .NET có phù hợp với các ứng dụng web không?
Hoàn toàn có thể, GroupDocs.Viewer có thể được tích hợp liền mạch vào cả ứng dụng máy tính để bàn và web được phát triển bằng công nghệ .NET.
### GroupDocs.Viewer có yêu cầu bất kỳ sự phụ thuộc bổ sung nào không?
Không, GroupDocs.Viewer dành cho .NET có mức độ phụ thuộc tối thiểu và có thể dễ dàng tích hợp vào các dự án hiện có của bạn.
### Tôi có thể tùy chỉnh giao diện của tài liệu được hiển thị không?
Có, GroupDocs.Viewer cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện và hoạt động của tài liệu được hiển thị cho phù hợp với yêu cầu cụ thể của bạn.
### Có hỗ trợ kỹ thuật cho GroupDocs.Viewer dành cho .NET không?
 Có, bạn có thể tìm kiếm sự trợ giúp và hướng dẫn từ nhóm hỗ trợ tận tâm thông qua[diễn đàn](https://forum.groupdocs.com/c/viewer/9).