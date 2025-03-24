---
title: Kết xuất thư mục lưu trữ
linktitle: Kết xuất thư mục lưu trữ
second_title: API GroupDocs.Viewer .NET
description: Tích hợp GroupDocs.Viewer cho .NET một cách liền mạch vào các ứng dụng .NET của bạn để có khả năng hiển thị và xem tài liệu hiệu quả.
weight: 11
url: /vi/net/rendering-archive-files/render-archive-folder/
---
## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc truy cập và xem tài liệu một cách liền mạch là rất quan trọng đối với các doanh nghiệp cũng như cá nhân. May mắn thay, với sự tiến bộ của công nghệ, các nhà phát triển hiện có sẵn các công cụ mạnh mẽ để tích hợp khả năng xem tài liệu vào ứng dụng của họ một cách dễ dàng. Một công cụ như vậy là GroupDocs.Viewer cho .NET, một thư viện đa năng cho phép các nhà phát triển hiển thị các định dạng tài liệu khác nhau trong các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào việc tích hợp GroupDocs.Viewer cho .NET vào dự án của bạn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### Kiến thức về lập trình C#
Để sử dụng hiệu quả GroupDocs.Viewer cho .NET, cần có hiểu biết cơ bản về ngôn ngữ lập trình C#. Làm quen với các khái niệm như lớp, phương thức và biến.
### Cài đặt GroupDocs.Viewer cho .NET
Đảm bảo rằng bạn đã tải xuống và cài đặt GroupDocs.Viewer cho .NET. Bạn có thể lấy thư viện từ nguồn được cung cấp[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
### Thiết lập môi trường phát triển
Có môi trường phát triển được định cấu hình với Visual Studio hoặc bất kỳ IDE ưa thích nào để phát triển .NET.

## Nhập không gian tên
Trước khi kết hợp GroupDocs.Viewer cho .NET vào dự án của bạn, hãy nhập các vùng tên cần thiết để truy cập chức năng của nó một cách liền mạch:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy chia nhỏ quá trình hiển thị thư mục lưu trữ bằng GroupDocs.Viewer cho .NET thành các bước có thể quản lý được:
## Bước 1: Xác định thư mục đầu ra
Chỉ định thư mục nơi bạn muốn lưu tài liệu được hiển thị.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Đặt định dạng để đặt tên cho các tệp trang riêng lẻ.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng người xem
Tạo một phiên bản của lớp Viewer, chuyển đường dẫn đến tệp lưu trữ làm tham số.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP_WITH_FOLDERS))
```
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
Thiết lập các tùy chọn xem HTML, bao gồm định dạng cho tài nguyên được nhúng và thư mục đích trong kho lưu trữ.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.ArchiveOptions.Folder = "ThirdFolderWithItems";
```
## Bước 5: Kết xuất thư mục lưu trữ
Gọi phương thức View của đối tượng Viewer, chuyển các tùy chọn dạng xem HTML đã được định cấu hình.
```csharp
viewer.View(options);
```
## Bước 6: Hiển thị thông báo thành công
Thông báo cho người dùng rằng quá trình kết xuất tài liệu đã hoàn tất và cung cấp thư mục đầu ra.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Việc kết hợp GroupDocs.Viewer dành cho .NET vào các ứng dụng .NET của bạn sẽ mở ra vô số khả năng hiển thị tài liệu liền mạch. Bằng cách làm theo các bước đã nêu, bạn có thể dễ dàng tích hợp khả năng xem tài liệu, nâng cao chức năng của ứng dụng.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có tương thích với tất cả các định dạng tài liệu không?
GroupDocs.Viewer dành cho .NET hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v. Tham khảo tài liệu để có danh sách đầy đủ.
### Tôi có thể tùy chỉnh giao diện của tài liệu được hiển thị không?
Có, GroupDocs.Viewer dành cho .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện của tài liệu được hiển thị, chẳng hạn như hình mờ, xoay trang và thu phóng.
### GroupDocs.Viewer dành cho .NET có cung cấp hỗ trợ cho các dịch vụ lưu trữ đám mây không?
Có, bạn có thể tích hợp GroupDocs.Viewer cho .NET với các dịch vụ lưu trữ đám mây phổ biến như Dropbox, Google Drive và Amazon S3 để truy xuất và hiển thị tài liệu liền mạch.
### Có phiên bản dùng thử nào để đánh giá không?
Có, bạn có thể tận dụng bản dùng thử miễn phí GroupDocs.Viewer dành cho .NET để khám phá các tính năng và khả năng của nó trước khi đưa ra quyết định mua hàng.
### Tôi có thể tìm kiếm trợ giúp ở đâu nếu gặp bất kỳ vấn đề nào hoặc có câu hỏi liên quan đến GroupDocs.Viewer cho .NET?
 Bạn có thể ghé thăm[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để tìm kiếm sự hỗ trợ từ cộng đồng và nhóm GroupDocs.