---
"description": "Tìm hiểu cách chuyển đổi hình ảnh CDR sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET. Dễ dàng chuyển đổi tệp CorelDRAW với hướng dẫn này."
"linktitle": "Kết xuất hình ảnh CDR"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất hình ảnh CDR"
"url": "/vi/net/image-rendering/render-cdr-images/"
"weight": 12
---

# Kết xuất hình ảnh CDR

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình kết xuất hình ảnh CDR (CorelDRAW) bằng GroupDocs.Viewer cho .NET. CDR là định dạng tệp chủ yếu liên quan đến CorelDRAW, một trình chỉnh sửa đồ họa vector. Với GroupDocs.Viewer, bạn có thể dễ dàng chuyển đổi các tệp CDR thành nhiều định dạng khác nhau như HTML, JPG, PNG và PDF.

![Kết xuất hình ảnh CDR với GroupDocs.Viewer cho .NET](/viewer/image-rendering/render-cdr-images.png)

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
2. Thư mục tài liệu: Chuẩn bị thư mục mà bạn muốn lưu hình ảnh đã kết xuất.
3. Kiến thức cơ bản về C#: Cần phải quen thuộc với ngôn ngữ lập trình C# để hiểu các ví dụ mã.
## Nhập không gian tên
Trước khi tìm hiểu các ví dụ mã, hãy nhập các không gian tên cần thiết vào tệp C# của bạn:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Bây giờ, chúng ta hãy chia nhỏ từng ví dụ thành nhiều bước:
## Kết xuất sang HTML
1. Xác định thư mục đầu ra mà bạn muốn lưu các tệp HTML đã kết xuất:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Chỉ định định dạng đường dẫn tệp cho tệp HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Sử dụng lớp Viewer để hiển thị tệp CDR thành HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Kết xuất sang JPG
1. Xác định định dạng đường dẫn tệp cho tệp JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Sử dụng lớp Viewer để hiển thị tệp CDR thành JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Kết xuất sang PNG
1. Xác định định dạng đường dẫn tệp cho tệp PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Sử dụng lớp Viewer để hiển thị tệp CDR thành PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Kết xuất sang PDF
1. Xác định định dạng đường dẫn tệp cho PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Sử dụng lớp Viewer để hiển thị tệp CDR thành PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Tùy chọn, bạn có thể chỉ định các tùy chọn hiển thị hoặc hiển thị các trang cụ thể bằng cách truyền các tham số bổ sung cho `viewer.View()` phương pháp.
## Phần kết luận
Việc kết xuất hình ảnh CDR sang nhiều định dạng khác nhau như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể chuyển đổi hiệu quả các tệp CDR sang các định dạng khác nhau dựa trên yêu cầu của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer for .NET có tương thích với mọi phiên bản tệp CDR không?
GroupDocs.Viewer for .NET hỗ trợ hiển thị các tệp CDR được tạo bởi các phiên bản CorelDRAW khác nhau.
### Tôi có thể tùy chỉnh đầu ra của các tập tin được kết xuất không?
Có, GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn để tùy chỉnh đầu ra, chẳng hạn như điều chỉnh chất lượng hình ảnh, đặt hình mờ, v.v.
### GroupDocs.Viewer cho .NET có yêu cầu bất kỳ sự phụ thuộc bên ngoài nào không?
Không, GroupDocs.Viewer cho .NET là một thư viện độc lập và không yêu cầu bất kỳ sự phụ thuộc bên ngoài nào để hiển thị tài liệu.
### Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của GroupDocs.Viewer cho .NET từ [đây](https://releases.groupdocs.com/).
### Tôi có thể nhận hỗ trợ cho GroupDocs.Viewer dành cho .NET ở đâu?
Bạn có thể nhận được sự hỗ trợ từ diễn đàn cộng đồng GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9).