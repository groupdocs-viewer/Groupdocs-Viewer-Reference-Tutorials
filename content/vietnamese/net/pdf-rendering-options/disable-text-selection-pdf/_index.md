---
title: Vô hiệu hóa lựa chọn văn bản trong PDF
linktitle: Vô hiệu hóa lựa chọn văn bản trong PDF
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách tắt tính năng chọn văn bản trong PDF bằng GroupDocs.Viewer dành cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
weight: 13
url: /vi/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Giới thiệu
GroupDocs.Viewer cho .NET là API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển tích hợp khả năng xem tài liệu vào các ứng dụng .NET của họ một cách dễ dàng. Một trong những chức năng chính được GroupDocs.Viewer cung cấp là khả năng tắt tính năng chọn văn bản trong tài liệu PDF. Tính năng này đặc biệt hữu ích trong các tình huống mà bạn cần ngăn người dùng sao chép văn bản từ các tài liệu nhạy cảm, đảm bảo tính bảo mật và toàn vẹn của tài liệu.
## Điều kiện tiên quyết
Trước khi chúng tôi đi sâu vào hướng dẫn từng bước về cách tắt tính năng chọn văn bản trong PDF bằng GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Cài đặt GroupDocs.Viewer cho .NET: Đảm bảo rằng bạn đã tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
2. Thư mục tài liệu: Chuẩn bị một thư mục nơi tài liệu của bạn sẽ được lưu trữ. Bạn sẽ cần chỉ định thư mục này trong đoạn mã để hiển thị tài liệu PDF.

## Nhập không gian tên
Trước tiên, bạn cần nhập các vùng tên cần thiết để truy cập các chức năng do GroupDocs.Viewer cung cấp cho .NET. Đây là cách bạn có thể làm điều đó:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy chia nhỏ quy trình tắt tính năng chọn văn bản trong tài liệu PDF bằng GroupDocs.Viewer dành cho .NET thành nhiều bước:
## Bước 1: Chỉ định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
 Ở bước này, thay thế`"Your Document Directory"` với đường dẫn thư mục chứa tài liệu PDF của bạn.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bước này xác định định dạng cho đường dẫn tệp của các trang HTML được hiển thị. Mỗi trang của tài liệu PDF sẽ được chuyển đổi thành tệp HTML có số trang tuần tự.
## Bước 3: Kết xuất tài liệu PDF khi tắt tính năng chọn văn bản
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Thay thế`"Path to Your PDF Document"` với đường dẫn thực tế tới tệp PDF của bạn. Đoạn mã này khởi tạo một`Viewer` đối tượng, định cấu hình các tùy chọn chế độ xem HTML để nhúng tài nguyên và tắt tính năng chọn văn bản bằng cách cài đặt`RenderTextAsImage` tài sản để`true`.
## Bước 4: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Sau khi hiển thị tài liệu PDF, bước này sẽ hiển thị thông báo thành công cùng với thư mục lưu trữ các trang HTML được hiển thị.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách tắt tính năng chọn văn bản trong tài liệu PDF bằng GroupDocs.Viewer dành cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp liền mạch tính năng này vào các ứng dụng .NET của mình, đảm bảo tính bảo mật tài liệu và nâng cao trải nghiệm người dùng.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh thư mục đầu ra cho các trang HTML được hiển thị không?
Có, bạn có thể chỉ định bất kỳ đường dẫn thư mục nào mà bạn muốn lưu trữ các trang HTML được hiển thị.
### GroupDocs.Viewer cho .NET có tương thích với các phiên bản .NET framework khác nhau không?
Có, GroupDocs.Viewer cho .NET tương thích với nhiều phiên bản khác nhau của .NET framework, bao gồm .NET Core và .NET Framework.
### Việc tắt lựa chọn văn bản có ảnh hưởng đến các chức năng khác của tài liệu PDF không?
Không, việc tắt tính năng chọn văn bản chỉ ngăn người dùng chọn và sao chép văn bản từ tài liệu. Các chức năng khác vẫn còn nguyên.
### Tôi có thể bật lại lựa chọn văn bản sau khi hiển thị tài liệu không?
 Có, bạn có thể kích hoạt lựa chọn văn bản bằng cách cài đặt`RenderTextAsImage` tài sản để`false` trong các tùy chọn chế độ xem HTML.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
 Có, bạn có thể truy cập bản dùng thử miễn phí của GroupDocs.Viewer dành cho .NET từ[trang mạng](https://releases.groupdocs.com/).