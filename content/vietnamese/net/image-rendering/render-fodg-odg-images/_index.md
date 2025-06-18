---
"description": "Tìm hiểu cách hiển thị hình ảnh FODG và ODG sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET. Cải thiện khả năng xử lý tài liệu của bạn."
"linktitle": "Kết xuất hình ảnh FODG và ODG"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất hình ảnh FODG và ODG"
"url": "/vi/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# Kết xuất hình ảnh FODG và ODG

## Giới thiệu
Trong thế giới phát triển phần mềm, việc xử lý hiệu quả các định dạng tài liệu là tối quan trọng. GroupDocs.Viewer for .NET là một công cụ mạnh mẽ được thiết kế để đơn giản hóa quá trình kết xuất hình ảnh FODG và ODG trong các ứng dụng .NET. Hướng dẫn này sẽ hướng dẫn bạn các bước cần thiết để kết xuất các hình ảnh này thành nhiều định dạng khác nhau, chẳng hạn như HTML, JPG, PNG và PDF, bằng cách sử dụng GroupDocs.Viewer for .NET.

![Hiển thị hình ảnh FODG và ODG với GroupDocs.Viewer cho .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [đây](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Đảm bảo rằng bạn đã cài đặt .NET Framework trên hệ thống của mình.
3. Kiến thức cơ bản về C#: Sự quen thuộc với ngôn ngữ lập trình C# sẽ rất hữu ích.

## Nhập không gian tên
Trước khi bắt đầu triển khai, hãy nhập các không gian tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Bước 1: Thiết lập thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Thay thế `"Your Document Directory"` với đường dẫn thư mục mà bạn muốn lưu hình ảnh đã kết xuất.
## Bước 2: Kết xuất thành HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Bước này sẽ chuyển hình ảnh FODG sang định dạng HTML.
## Bước 3: Kết xuất sang JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ở đây, hình ảnh FODG được hiển thị ở định dạng JPG.
## Bước 4: Kết xuất thành PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Bước này chuyển đổi hình ảnh FODG sang định dạng PNG.
## Bước 5: Kết xuất thành PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Cuối cùng, hình ảnh FODG được chuyển thành định dạng PDF.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách kết xuất hình ảnh FODG và ODG thành nhiều định dạng khác nhau bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo các bước này, bạn có thể tích hợp liền mạch các khả năng kết xuất tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có tương thích với tất cả các phiên bản .NET Framework không?
GroupDocs.Viewer cho .NET tương thích với nhiều phiên bản .NET Framework, bao gồm cả phiên bản mới nhất.
### Tôi có thể hiển thị tài liệu không đồng bộ bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer cho .NET cung cấp khả năng hiển thị không đồng bộ để cải thiện hiệu suất.
### GroupDocs.Viewer cho .NET có hỗ trợ hiển thị tài liệu được mã hóa không?
Có, GroupDocs.Viewer cho .NET hỗ trợ hiển thị các tài liệu được mã hóa với khóa giải mã phù hợp.
### Có thể tùy chỉnh đầu ra kết xuất bằng GroupDocs.Viewer cho .NET không?
Đúng vậy, GroupDocs.Viewer for .NET cung cấp nhiều tùy chọn tùy chỉnh khác nhau để điều chỉnh đầu ra kết xuất theo yêu cầu của bạn.
### Tôi có thể hiển thị tài liệu từ các vị trí lưu trữ từ xa bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer for .NET hỗ trợ hiển thị tài liệu từ cả vị trí lưu trữ cục bộ và từ xa.