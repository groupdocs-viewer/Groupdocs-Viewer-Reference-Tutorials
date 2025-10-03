---
"description": "Tìm hiểu cách hiển thị các trang đã chọn từ tài liệu bằng Groupdocs.Viewer cho .NET. Hướng dẫn từng bước có kèm ví dụ về mã."
"linktitle": "Hiển thị các trang đã chọn"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị các trang đã chọn"
"url": "/vi/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Hiển thị các trang đã chọn

## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách sử dụng Groupdocs.Viewer cho .NET để hiển thị các trang đã chọn từ một tài liệu. Cho dù bạn là một nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn từng bước này sẽ hướng dẫn bạn thực hiện quy trình một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

### 1. Cài đặt

Đảm bảo rằng bạn đã cài đặt Groupdocs.Viewer cho .NET trong môi trường phát triển của mình. Nếu không, bạn có thể tải xuống từ [Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).

## Nhập không gian tên

Trong tệp mã C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức cần thiết. Bạn có thể thực hiện việc này bằng cách sử dụng `using` chỉ thị:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ chúng ta hãy chia nhỏ mã ví dụ được cung cấp thành nhiều bước:

## Bước 1: Thiết lập thư mục đầu ra

Xác định thư mục mà bạn muốn lưu các trang đã kết xuất. Thay thế `"Your Document Directory"` với đường dẫn thư mục mong muốn.

```csharp
string outputDirectory = "Your Document Directory";
```

## Bước 2: Xác định định dạng đường dẫn tệp trang

Chỉ định định dạng cho đường dẫn tệp của các trang được hiển thị. Điều này sẽ được sử dụng để lưu từng trang dưới dạng tệp HTML trong thư mục đầu ra.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Bước 3: Khởi tạo đối tượng Viewer

Tạo một thể hiện của lớp Viewer, truyền đường dẫn của tài liệu bạn muốn hiển thị làm đối số.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Bước 4: Cấu hình Tùy chọn chế độ xem HTML

Thiết lập tùy chọn chế độ xem HTML để hiển thị. Trong ví dụ này, chúng tôi đang cấu hình tùy chọn để nhúng tài nguyên vào đầu ra HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Bước 5: Hiển thị các trang đã chọn

Chỉ định số trang bạn muốn hiển thị. Trong trường hợp này, chúng ta sẽ hiển thị các trang từ 1 đến 3. Sau đó, gọi phương thức View trên đối tượng Viewer, truyền các tùy chọn và số trang làm đối số.

```csharp
viewer.View(options, 1, 3);
```

## Bước 6: Xuất kết quả

Cuối cùng, hiển thị thông báo cho biết tài liệu đã được kết xuất thành công và vị trí lưu tệp đầu ra.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận

Xin chúc mừng! Bạn đã học thành công cách kết xuất các trang đã chọn từ một tài liệu bằng Groupdocs.Viewer cho .NET. Với kiến thức này, giờ đây bạn có thể dễ dàng tích hợp khả năng kết xuất tài liệu vào các ứng dụng .NET của mình.

## Câu hỏi thường gặp

### H: Tôi có thể hiển thị các trang từ nhiều loại tài liệu khác nhau, chẳng hạn như PDF hoặc hình ảnh không?

A: Có, Groupdocs.Viewer for .NET hỗ trợ hiển thị các trang từ nhiều định dạng tài liệu khác nhau, bao gồm PDF, tài liệu Microsoft Office và tệp hình ảnh.

### H: Có phiên bản dùng thử để kiểm tra trước khi mua không?

A: Có, bạn có thể truy cập phiên bản dùng thử miễn phí của Groupdocs.Viewer cho .NET từ [trang web](https://releases.groupdocs.com/).

### H: Tôi có thể tùy chỉnh định dạng đầu ra khác ngoài HTML không?

A: Đúng vậy, Groupdocs.Viewer cho .NET cung cấp các tùy chọn để hiển thị các trang dưới dạng hình ảnh, PDF, v.v., ngoài HTML.

### H: Tôi có thể xin giấy phép tạm thời cho mục đích thử nghiệm như thế nào?

A: Giấy phép tạm thời có thể được xin từ [trang giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/) trên trang web Groupdocs.

### H: Tôi có thể tìm kiếm sự hỗ trợ hoặc nhận trợ giúp ở đâu khi gặp phải vấn đề này?

A: Bạn có thể ghé thăm [Diễn đàn Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để được cộng đồng và nhà phát triển hỗ trợ và hướng dẫn.