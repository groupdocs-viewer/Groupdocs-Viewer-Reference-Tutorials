---
"description": "Tích hợp GroupDocs.Viewer cho .NET một cách liền mạch vào các ứng dụng .NET của bạn để có khả năng hiển thị và xem tài liệu hiệu quả."
"linktitle": "Kết xuất thư mục lưu trữ"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất thư mục lưu trữ"
"url": "/vi/net/rendering-archive-files/render-archive-folder/"
"weight": 11
type: docs
---
# Kết xuất thư mục lưu trữ

## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc truy cập và xem tài liệu một cách liền mạch là điều vô cùng quan trọng đối với cả doanh nghiệp và cá nhân. May mắn thay, với sự tiến bộ của công nghệ, các nhà phát triển hiện có các công cụ mạnh mẽ để tích hợp khả năng xem tài liệu vào ứng dụng của họ một cách dễ dàng. Một trong những công cụ như vậy là GroupDocs.Viewer for .NET, một thư viện đa năng cho phép các nhà phát triển hiển thị nhiều định dạng tài liệu khác nhau trong các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi bắt đầu tích hợp GroupDocs.Viewer cho .NET vào dự án của bạn, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:
### Kiến thức về lập trình C#
Để sử dụng hiệu quả GroupDocs.Viewer cho .NET, cần có hiểu biết cơ bản về ngôn ngữ lập trình C#. Làm quen với các khái niệm như lớp, phương thức và biến.
### Cài đặt GroupDocs.Viewer cho .NET
Đảm bảo rằng bạn đã tải xuống và cài đặt GroupDocs.Viewer cho .NET. Bạn có thể lấy thư viện từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
### Thiết lập môi trường phát triển
Có môi trường phát triển được cấu hình bằng Visual Studio hoặc bất kỳ IDE nào bạn thích để phát triển .NET.

## Nhập không gian tên
Trước khi tích hợp GroupDocs.Viewer cho .NET vào dự án của bạn, hãy nhập các không gian tên cần thiết để truy cập chức năng của nó một cách liền mạch:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, chúng ta hãy chia nhỏ quy trình hiển thị thư mục lưu trữ bằng GroupDocs.Viewer cho .NET thành các bước dễ quản lý:
## Bước 1: Xác định thư mục đầu ra
Chỉ định thư mục mà bạn muốn lưu tài liệu đã kết xuất.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Đặt định dạng để đặt tên cho từng tệp trang riêng lẻ.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
Tạo một thể hiện của lớp Viewer, truyền đường dẫn đến tệp lưu trữ dưới dạng tham số.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP_WITH_FOLDERS))
```
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
Thiết lập tùy chọn chế độ xem HTML, bao gồm định dạng cho tài nguyên nhúng và thư mục đích trong kho lưu trữ.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.ArchiveOptions.Folder = "ThirdFolderWithItems";
```
## Bước 5: Hiển thị thư mục lưu trữ
Gọi phương thức View của đối tượng Viewer, truyền các tùy chọn chế độ xem HTML đã cấu hình.
```csharp
viewer.View(options);
```
## Bước 6: Hiển thị thông báo thành công
Thông báo cho người dùng rằng quá trình kết xuất tài liệu đã hoàn tất và cung cấp thư mục đầu ra.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Việc tích hợp GroupDocs.Viewer cho .NET vào các ứng dụng .NET của bạn sẽ mở ra một thế giới khả năng cho việc kết xuất tài liệu liền mạch. Bằng cách làm theo các bước được nêu, bạn có thể dễ dàng tích hợp khả năng xem tài liệu, nâng cao chức năng của các ứng dụng của bạn.
## Câu hỏi thường gặp
### GroupDocs.Viewer for .NET có tương thích với mọi định dạng tài liệu không?
GroupDocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v. Tham khảo tài liệu để biết danh sách đầy đủ.
### Tôi có thể tùy chỉnh giao diện của tài liệu được kết xuất không?
Có, GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện của tài liệu được hiển thị, chẳng hạn như thêm hình mờ, xoay trang và thu phóng.
### GroupDocs.Viewer for .NET có hỗ trợ dịch vụ lưu trữ đám mây không?
Có, bạn có thể tích hợp GroupDocs.Viewer cho .NET với các dịch vụ lưu trữ đám mây phổ biến như Dropbox, Google Drive và Amazon S3 để truy xuất và hiển thị tài liệu liền mạch.
### Có phiên bản dùng thử nào để đánh giá không?
Có, bạn có thể dùng thử miễn phí GroupDocs.Viewer dành cho .NET để khám phá các tính năng và khả năng của phần mềm này trước khi quyết định mua.
### Tôi có thể tìm kiếm sự trợ giúp ở đâu nếu gặp bất kỳ sự cố hoặc có câu hỏi nào liên quan đến GroupDocs.Viewer cho .NET?
Bạn có thể ghé thăm [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để tìm kiếm sự hỗ trợ từ cộng đồng và nhóm GroupDocs.