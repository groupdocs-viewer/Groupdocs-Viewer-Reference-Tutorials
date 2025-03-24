---
title: Thay thế phông chữ bị thiếu
linktitle: Thay thế phông chữ bị thiếu
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách thay thế phông chữ bị thiếu trong tài liệu .NET một cách dễ dàng bằng GroupDocs.Viewer. Đảm bảo hiển thị chính xác với các bước đơn giản.
weight: 20
url: /vi/net/rendering-options/replace-missing-font/
---
## Giới thiệu
Trong thế giới phát triển .NET, việc xử lý tài liệu hiệu quả là rất quan trọng. GroupDocs.Viewer cho .NET cung cấp giải pháp mạnh mẽ để xem các định dạng tài liệu khác nhau trong các ứng dụng .NET của bạn. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng GroupDocs.Viewer cho .NET để thay thế các phông chữ bị thiếu trong tài liệu. Cho dù bạn đang xử lý tệp PDF, bản trình bày PowerPoint hay tài liệu Word, GroupDocs.Viewer đều đơn giản hóa quy trình, đảm bảo rằng tài liệu của bạn được hiển thị chính xác, ngay cả khi thiếu phông chữ.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có những điều sau:
1. GroupDocs.Viewer for .NET: Tải xuống và cài đặt thư viện GroupDocs.Viewer từ trang web](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển .NET, chẳng hạn như Visual Studio.
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# và .NET framework.

## Nhập không gian tên
Trong mã C# của bạn, hãy nhập các vùng tên cần thiết để truy cập các chức năng của GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy xem quy trình thay thế phông chữ bị thiếu trong tài liệu bằng GroupDocs.Viewer cho .NET.
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Đặt thư mục nơi các trang tài liệu được hiển thị sẽ được lưu.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Chỉ định định dạng đặt tên cho các tệp HTML đầu ra. Trong ví dụ này, mỗi trang sẽ được lưu dưới dạng tệp HTML với quy ước đặt tên là "trang_{page_number}.html".
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Khởi tạo một phiên bản mới của lớp Viewer, chuyển đường dẫn đến tệp tài liệu (trong trường hợp này là bản trình bày PowerPoint thiếu phông chữ) làm tham số.
## Bước 4: Đặt tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Tạo một phiên bản của HtmlViewOptions và định cấu hình nó để nhúng tài nguyên vào đầu ra HTML. Chỉ định tên phông chữ mặc định để sử dụng thay thế cho các phông chữ bị thiếu.
## Bước 5: Kết xuất tài liệu
```csharp
viewer.View(options);
```
Gọi phương thức View của đối tượng Viewer, chuyển các tùy chọn dạng xem HTML. Điều này sẽ hiển thị các trang tài liệu bằng cách sử dụng các tùy chọn đã chỉ định.
## Bước 6: Hiển thị đường dẫn đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
In thông báo cho biết việc hiển thị tài liệu thành công và cung cấp đường dẫn lưu tệp HTML đầu ra.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng GroupDocs.Viewer cho .NET để thay thế các phông chữ bị thiếu trong tài liệu. Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng tài liệu của mình được hiển thị chính xác, ngay cả khi không có sẵn một số phông chữ nhất định. GroupDocs.Viewer đơn giản hóa quy trình, cho phép bạn tập trung vào việc xây dựng các ứng dụng .NET mạnh mẽ mà không phải lo lắng về các vấn đề tương thích phông chữ.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể xử lý các loại vấn đề khác liên quan đến phông chữ không?
Có, GroupDocs.Viewer cung cấp nhiều chức năng liên quan đến phông chữ, bao gồm thay thế phông chữ và phát hiện phông chữ.
### GroupDocs.Viewer có tương thích với tất cả các khung .NET không?
GroupDocs.Viewer hỗ trợ nhiều khung .NET, bao gồm .NET Core và .NET Standard.
### Tôi có thể tùy chỉnh thay thế phông chữ mặc định trong GroupDocs.Viewer không?
Hoàn toàn có thể, bạn có thể chỉ định bất kỳ phông chữ nào bạn chọn làm phông chữ thay thế mặc định cho các phông chữ bị thiếu.
### GroupDocs.Viewer có hỗ trợ xử lý hàng loạt tài liệu không?
Có, GroupDocs.Viewer cho phép bạn xử lý nhiều tài liệu cùng lúc, lý tưởng cho các tình huống xử lý hàng loạt.
### Tôi có thể tìm thêm trợ giúp hoặc hỗ trợ cho GroupDocs.Viewer ở đâu?
 Bạn có thể truy cập diễn đàn GroupDocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9) cho bất kỳ yêu cầu trợ giúp hoặc hỗ trợ.