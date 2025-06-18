---
"description": "Tìm hiểu cách điều chỉnh kích thước hình ảnh đầu ra cho bản vẽ CAD bằng GroupDocs.Viewer cho .NET. Tăng cường khả năng hiển thị và khả năng sử dụng một cách dễ dàng."
"linktitle": "Điều chỉnh kích thước hình ảnh đầu ra cho bản vẽ CAD"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Điều chỉnh kích thước hình ảnh đầu ra cho bản vẽ CAD"
"url": "/vi/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Điều chỉnh kích thước hình ảnh đầu ra cho bản vẽ CAD

## Giới thiệu
Bản vẽ CAD thường yêu cầu điều chỉnh cụ thể để xem và trình bày tối ưu. GroupDocs.Viewer cho .NET cung cấp một bộ công cụ mạnh mẽ để quản lý và tùy chỉnh đầu ra bản vẽ CAD. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước trong quy trình điều chỉnh kích thước hình ảnh đầu ra cho bản vẽ CAD.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [đây](https://releases.groupdocs.com/viewer/net/).
2. Thư mục tài liệu: Chuẩn bị thư mục chứa tài liệu của bạn.
3. Hiểu biết cơ bản: Làm quen với các khái niệm cơ bản về lập trình .NET.

## Nhập không gian tên
Trước tiên, hãy đảm bảo nhập các không gian tên cần thiết để truy cập các chức năng của GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục đầu ra
Xác định thư mục mà bạn muốn lưu trữ hình ảnh đầu ra của bản vẽ CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Đặt định dạng cho đường dẫn tệp trang. Định dạng này sẽ được sử dụng để đặt tên và lưu từng trang dưới dạng tệp HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Điều chỉnh kích thước hình ảnh
Bên trong khối sử dụng cho đối tượng Viewer, điều chỉnh kích thước hình ảnh cho bản vẽ CAD bằng cách thiết lập các tùy chọn phù hợp:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Bước 4: Hiển thị thư mục đầu ra
Sau khi kết xuất tài liệu, hiển thị thông báo cho biết kết xuất thành công và cung cấp vị trí của thư mục đầu ra:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Điều chỉnh kích thước hình ảnh đầu ra cho bản vẽ CAD là rất quan trọng để tăng cường khả năng hiển thị và khả năng sử dụng của chúng. Với GroupDocs.Viewer cho .NET, quy trình này trở nên hợp lý và hiệu quả, cho phép bạn tùy chỉnh đầu ra theo yêu cầu cụ thể của mình.
## Câu hỏi thường gặp
### Tôi có thể điều chỉnh kích thước hình ảnh đầu ra cho các loại tài liệu khác ngoài bản vẽ CAD không?
Có, GroupDocs.Viewer for .NET hỗ trợ nhiều loại tài liệu khác nhau và bạn có thể điều chỉnh kích thước hình ảnh đầu ra cho hầu hết các định dạng tài liệu.
### GroupDocs.Viewer cho .NET có tương thích với các phiên bản khác nhau của .NET framework không?
Có, GroupDocs.Viewer cho .NET tương thích với nhiều phiên bản của .NET framework, đảm bảo tính linh hoạt và khả năng sử dụng trên nhiều môi trường khác nhau.
### Có tùy chọn cấp phép nào dành cho GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể khám phá nhiều lựa chọn cấp phép khác nhau, bao gồm giấy phép tạm thời và giấy phép thương mại, tùy theo nhu cầu của bạn.
### Tôi có thể tùy chỉnh định dạng đầu ra của tài liệu đã kết xuất không?
Hoàn toàn đúng, GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn tùy chỉnh khác nhau, cho phép bạn điều chỉnh định dạng đầu ra theo hướng dẫn của mình.
### Tôi có thể tìm thêm hỗ trợ hoặc trợ giúp về GroupDocs.Viewer cho .NET ở đâu?
Bạn có thể truy cập diễn đàn GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ, đặt câu hỏi và tham gia cộng đồng.