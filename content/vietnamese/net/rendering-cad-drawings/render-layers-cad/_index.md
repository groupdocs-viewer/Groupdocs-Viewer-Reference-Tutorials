---
title: Kết xuất các lớp trong bản vẽ CAD
linktitle: Kết xuất các lớp trong bản vẽ CAD
second_title: API GroupDocs.Viewer .NET
description: Kết xuất bản vẽ CAD một cách liền mạch trong các ứng dụng .NET bằng GroupDocs.Viewer dành cho .NET. Khám phá các tùy chọn kết xuất, tùy chỉnh các lớp và hơn thế nữa.
weight: 13
url: /vi/net/rendering-cad-drawings/render-layers-cad/
---
## Giới thiệu
GroupDocs.Viewer dành cho .NET là một công cụ mạnh mẽ cho phép các nhà phát triển tích hợp liền mạch khả năng kết xuất tài liệu vào các ứng dụng .NET của họ. Cho dù bạn cần kết xuất bản vẽ CAD, tệp PDF, tài liệu Microsoft Office hay hơn thế nữa, GroupDocs.Viewer đều cung cấp giải pháp toàn diện.
## Điều kiện tiên quyết
Trước khi bắt đầu sử dụng GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
- Môi trường phát triển .NET được thiết lập trên máy của bạn.
-  Đã cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
-  Truy cập vào tài liệu GroupDocs.Viewer cho .NET để tham khảo, có thể tìm thấy[đây](https://tutorials.groupdocs.com/viewer/net/).

## Nhập không gian tên
Để bắt đầu sử dụng GroupDocs.Viewer cho .NET, bạn cần nhập các vùng tên cần thiết trong dự án của mình. Thực hiện theo các bước sau:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Hãy chia ví dụ được cung cấp thành nhiều bước:
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
## Bước 4: Đặt tùy chọn chế độ xem HTML
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
## Bước 7: Xuất ra vị trí tài liệu được hiển thị
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Với GroupDocs.Viewer dành cho .NET, việc hiển thị bản vẽ CAD trong ứng dụng .NET của bạn trở thành một quy trình liền mạch. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tích hợp khả năng kết xuất tài liệu vào dự án của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với tất cả các loại bản vẽ CAD không?
Có, GroupDocs.Viewer hỗ trợ hiển thị nhiều định dạng bản vẽ CAD, bao gồm DWG và DXF.
### Tôi có thể tùy chỉnh các tùy chọn kết xuất cho bản vẽ CAD không?
Hoàn toàn có thể, GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh khác nhau, chẳng hạn như chỉ định các lớp để hiển thị hoặc đặt định dạng đầu ra.
### GroupDocs.Viewer có yêu cầu kết nối Internet để hiển thị tài liệu không?
Không, GroupDocs.Viewer thực hiện hiển thị cục bộ mà không cần kết nối internet.
### Có bản dùng thử miễn phí GroupDocs.Viewer cho .NET không?
 Có, bạn có thể truy cập bản dùng thử miễn phí GroupDocs.Viewer cho .NET[đây](https://releases.groupdocs.com/).
### Tôi có thể nhận hỗ trợ cho GroupDocs.Viewer cho .NET ở đâu?
 Đối với bất kỳ hỗ trợ hoặc thắc mắc kỹ thuật nào, bạn có thể truy cập diễn đàn GroupDocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9).