---
"description": "Tìm hiểu cách vô hiệu hóa lựa chọn văn bản trong PDF bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch."
"linktitle": "Tắt tính năng chọn văn bản trong PDF"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Tắt tính năng chọn văn bản trong PDF"
"url": "/vi/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
---

# Tắt tính năng chọn văn bản trong PDF

## Giới thiệu
GroupDocs.Viewer for .NET là một API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển tích hợp khả năng xem tài liệu vào các ứng dụng .NET của họ một cách dễ dàng. Một trong những chức năng chính do GroupDocs.Viewer cung cấp là khả năng vô hiệu hóa lựa chọn văn bản trong các tài liệu PDF. Tính năng này đặc biệt hữu ích trong các tình huống mà bạn cần ngăn người dùng sao chép văn bản từ các tài liệu nhạy cảm, đảm bảo tính bảo mật và toàn vẹn của tài liệu.

![Tắt tính năng chọn văn bản trong PDF bằng GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn từng bước về cách tắt tính năng chọn văn bản trong PDF bằng GroupDocs.Viewer cho .NET, hãy đảm bảo rằng bạn đã đáp ứng các điều kiện tiên quyết sau:
1. Cài đặt GroupDocs.Viewer cho .NET: Đảm bảo rằng bạn đã tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
2. Thư mục tài liệu: Chuẩn bị một thư mục nơi tài liệu của bạn sẽ được lưu trữ. Bạn sẽ cần chỉ định thư mục này trong đoạn mã để hiển thị tài liệu PDF.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết để truy cập các chức năng do GroupDocs.Viewer cung cấp cho .NET. Sau đây là cách bạn có thể thực hiện:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, chúng ta hãy chia nhỏ quy trình vô hiệu hóa tính năng chọn văn bản trong tài liệu PDF bằng GroupDocs.Viewer cho .NET thành nhiều bước:
## Bước 1: Chỉ định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Trong bước này, thay thế `"Your Document Directory"` bằng đường dẫn thư mục chứa tài liệu PDF của bạn.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bước này xác định định dạng cho đường dẫn tệp của các trang HTML được hiển thị. Mỗi trang của tài liệu PDF sẽ được chuyển đổi thành tệp HTML có số trang tuần tự.
## Bước 3: Hiển thị tài liệu PDF với tùy chọn chọn văn bản bị vô hiệu hóa
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Thay thế `"Path to Your PDF Document"` với đường dẫn thực tế đến tệp PDF của bạn. Đoạn mã này khởi tạo một `Viewer` đối tượng, cấu hình tùy chọn chế độ xem HTML để nhúng tài nguyên và vô hiệu hóa lựa chọn văn bản bằng cách thiết lập `RenderTextAsImage` tài sản để `true`.
## Bước 4: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Sau khi kết xuất tài liệu PDF, bước này sẽ hiển thị thông báo thành công cùng với thư mục lưu trữ các trang HTML đã kết xuất.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách vô hiệu hóa lựa chọn văn bản trong tài liệu PDF bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp liền mạch tính năng này vào các ứng dụng .NET của mình, đảm bảo tính bảo mật của tài liệu và nâng cao trải nghiệm của người dùng.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh thư mục đầu ra cho các trang HTML được hiển thị không?
Có, bạn có thể chỉ định bất kỳ đường dẫn thư mục nào mà bạn muốn lưu trữ các trang HTML đã kết xuất.
### GroupDocs.Viewer cho .NET có tương thích với các phiên bản khác nhau của .NET framework không?
Có, GroupDocs.Viewer cho .NET tương thích với nhiều phiên bản khác nhau của .NET framework, bao gồm .NET Core và .NET Framework.
### Việc tắt tính năng chọn văn bản có ảnh hưởng đến các chức năng khác của tài liệu PDF không?
Không, việc vô hiệu hóa lựa chọn văn bản chỉ ngăn người dùng chọn và sao chép văn bản từ tài liệu. Các chức năng khác vẫn còn nguyên vẹn.
### Tôi có thể bật lại tính năng chọn văn bản sau khi kết xuất tài liệu không?
Có, bạn có thể bật tính năng chọn văn bản bằng cách chỉ cần thiết lập `RenderTextAsImage` tài sản để `false` trong các tùy chọn chế độ xem HTML.
### Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể truy cập bản dùng thử miễn phí của GroupDocs.Viewer cho .NET từ [trang web](https://releases.groupdocs.com/).