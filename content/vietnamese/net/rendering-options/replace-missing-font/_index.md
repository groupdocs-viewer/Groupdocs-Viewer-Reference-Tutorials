---
"description": "Tìm hiểu cách thay thế phông chữ bị thiếu trong tài liệu .NET một cách dễ dàng bằng GroupDocs.Viewer. Đảm bảo kết xuất chính xác với các bước đơn giản."
"linktitle": "Thay thế phông chữ bị thiếu"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Thay thế phông chữ bị thiếu"
"url": "/vi/net/rendering-options/replace-missing-font/"
"weight": 20
type: docs
---
# Thay thế phông chữ bị thiếu

## Giới thiệu
Trong thế giới phát triển .NET, việc xử lý tài liệu hiệu quả là rất quan trọng. GroupDocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để xem nhiều định dạng tài liệu khác nhau trong các ứng dụng .NET của bạn. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng GroupDocs.Viewer for .NET để thay thế phông chữ bị thiếu trong tài liệu. Cho dù bạn đang xử lý PDF, bản trình bày PowerPoint hay tài liệu Word, GroupDocs.Viewer đều đơn giản hóa quy trình, đảm bảo rằng tài liệu của bạn được hiển thị chính xác, ngay cả khi thiếu phông chữ.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo bạn có những điều sau:
1. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt thư viện GroupDocs.Viewer từ trang web](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển .NET, chẳng hạn như Visual Studio.
3. Kiến thức cơ bản về C#: Có hiểu biết về ngôn ngữ lập trình C# và .NET framework.

## Nhập không gian tên
Trong mã C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các chức năng của GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, chúng ta hãy cùng tìm hiểu quy trình thay thế phông chữ bị thiếu trong tài liệu bằng GroupDocs.Viewer cho .NET.
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Thiết lập thư mục nơi các trang tài liệu được kết xuất sẽ được lưu.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Chỉ định định dạng để đặt tên cho các tệp HTML đầu ra. Trong ví dụ này, mỗi trang sẽ được lưu dưới dạng tệp HTML với quy ước đặt tên "page_{page_number}.html".
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Khởi tạo một phiên bản mới của lớp Viewer, truyền đường dẫn đến tệp tài liệu (trong trường hợp này là bản trình bày PowerPoint bị thiếu phông chữ) làm tham số.
## Bước 4: Thiết lập Tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Tạo một phiên bản của HtmlViewOptions và cấu hình nó để nhúng tài nguyên vào đầu ra HTML. Chỉ định tên phông chữ mặc định để sử dụng thay thế cho phông chữ bị thiếu.
## Bước 5: Kết xuất tài liệu
```csharp
viewer.View(options);
```
Gọi phương thức View của đối tượng Viewer, truyền các tùy chọn chế độ xem HTML. Thao tác này sẽ hiển thị các trang tài liệu bằng các tùy chọn đã chỉ định.
## Bước 6: Hiển thị đường dẫn đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
In ra thông báo cho biết tài liệu đã được hiển thị thành công và cung cấp đường dẫn lưu các tệp HTML đầu ra.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng GroupDocs.Viewer cho .NET để thay thế các phông chữ bị thiếu trong tài liệu. Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng tài liệu của mình được hiển thị chính xác, ngay cả khi một số phông chữ không khả dụng. GroupDocs.Viewer đơn giản hóa quy trình, cho phép bạn tập trung vào việc xây dựng các ứng dụng .NET mạnh mẽ mà không phải lo lắng về các vấn đề tương thích phông chữ.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể xử lý các loại vấn đề khác liên quan đến phông chữ không?
Có, GroupDocs.Viewer cung cấp nhiều chức năng liên quan đến phông chữ, bao gồm thay thế phông chữ và phát hiện phông chữ.
### GroupDocs.Viewer có tương thích với tất cả các nền tảng .NET không?
GroupDocs.Viewer hỗ trợ nhiều loại .NET framework, bao gồm .NET Core và .NET Standard.
### Tôi có thể tùy chỉnh phông chữ mặc định trong GroupDocs.Viewer không?
Hoàn toàn có thể, bạn có thể chỉ định bất kỳ phông chữ nào bạn chọn làm phông chữ thay thế mặc định cho các phông chữ bị thiếu.
### GroupDocs.Viewer có hỗ trợ xử lý hàng loạt tài liệu không?
Có, GroupDocs.Viewer cho phép bạn xử lý nhiều tài liệu cùng lúc, rất lý tưởng cho các tình huống xử lý hàng loạt.
### Tôi có thể tìm thêm sự hỗ trợ hoặc trợ giúp cho GroupDocs.Viewer ở đâu?
Bạn có thể truy cập diễn đàn GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ hoặc giải đáp thắc mắc.