---
"description": "Kết xuất bản vẽ CAD liền mạch trong các ứng dụng .NET với GroupDocs.Viewer cho .NET. Khám phá các tùy chọn kết xuất, tùy chỉnh các lớp và nhiều hơn nữa."
"linktitle": "Kết xuất các lớp trong bản vẽ CAD"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất các lớp trong bản vẽ CAD"
"url": "/vi/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
type: docs
---
# Kết xuất các lớp trong bản vẽ CAD

## Giới thiệu
GroupDocs.Viewer for .NET là một công cụ mạnh mẽ cho phép các nhà phát triển tích hợp liền mạch khả năng kết xuất tài liệu vào các ứng dụng .NET của họ. Cho dù bạn cần kết xuất bản vẽ CAD, PDF, tài liệu Microsoft Office hay nhiều hơn nữa, GroupDocs.Viewer đều cung cấp một giải pháp toàn diện.
## Điều kiện tiên quyết
Trước khi bắt đầu sử dụng GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
- Môi trường phát triển .NET được thiết lập trên máy của bạn.
- GroupDocs.Viewer cho .NET đã được cài đặt. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
- Truy cập vào GroupDocs.Viewer cho tài liệu hướng dẫn .NET, có thể tìm thấy [đây](https://tutorials.groupdocs.com/viewer/net/).

## Nhập không gian tên
Để bắt đầu sử dụng GroupDocs.Viewer cho .NET, bạn cần nhập các không gian tên cần thiết vào dự án của mình. Thực hiện theo các bước sau:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước:
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Khối mã tiếp tục...
}
```
## Bước 4: Thiết lập Tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Bước 5: Xác định lớp CAD
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Bước 6: Kết xuất tài liệu
```csharp
viewer.View(options);
```
## Bước 7: Xuất Vị trí Tài liệu được Kết xuất
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Với GroupDocs.Viewer cho .NET, việc kết xuất bản vẽ CAD trong các ứng dụng .NET của bạn trở thành một quá trình liền mạch. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tích hợp các khả năng kết xuất tài liệu vào các dự án của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với mọi loại bản vẽ CAD không?
Có, GroupDocs.Viewer hỗ trợ hiển thị nhiều định dạng bản vẽ CAD, bao gồm DWG và DXF.
### Tôi có thể tùy chỉnh các tùy chọn kết xuất cho bản vẽ CAD không?
Hoàn toàn có thể, GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh khác nhau, chẳng hạn như chỉ định các lớp để hiển thị hoặc thiết lập định dạng đầu ra.
### GroupDocs.Viewer có yêu cầu kết nối Internet để hiển thị tài liệu không?
Không, GroupDocs.Viewer thực hiện kết xuất cục bộ mà không cần kết nối internet.
### Có bản dùng thử miễn phí nào cho GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể truy cập dùng thử miễn phí GroupDocs.Viewer cho .NET [đây](https://releases.groupdocs.com/).
### Tôi có thể nhận hỗ trợ cho GroupDocs.Viewer dành cho .NET ở đâu?
Đối với bất kỳ hỗ trợ kỹ thuật hoặc thắc mắc nào, bạn có thể truy cập diễn đàn GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9).