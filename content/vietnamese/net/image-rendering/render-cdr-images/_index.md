---
title: Kết xuất hình ảnh CDR
linktitle: Kết xuất hình ảnh CDR
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị hình ảnh CDR thành HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET. Dễ dàng chuyển đổi các tập tin CorelDRAW với hướng dẫn này.
weight: 12
url: /vi/net/image-rendering/render-cdr-images/
---

# Kết xuất hình ảnh CDR

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình hiển thị hình ảnh CDR (CorelDRAW) bằng GroupDocs.Viewer cho .NET. CDR là định dạng tệp chủ yếu được liên kết với CorelDRAW, trình chỉnh sửa đồ họa vector. Với GroupDocs.Viewer, bạn có thể dễ dàng chuyển đổi các tệp CDR thành nhiều định dạng khác nhau như HTML, JPG, PNG và PDF.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
1.  GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Thư mục tài liệu: Chuẩn bị một thư mục nơi bạn muốn lưu hình ảnh được hiển thị.
3. Kiến thức cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# để hiểu các ví dụ về mã.
## Nhập không gian tên
Trước khi đi sâu vào các ví dụ về mã, hãy nhập các vùng tên cần thiết vào tệp C# của bạn:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Bây giờ, hãy chia từng ví dụ thành nhiều bước:
## Hiển thị sang HTML
1. Xác định thư mục đầu ra nơi bạn muốn lưu các tệp HTML được hiển thị:
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
## Hiển thị sang JPG
1. Xác định định dạng đường dẫn file cho file JPG:
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
## Hiển thị sang PNG
1. Xác định định dạng đường dẫn file cho file PNG:
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
## Hiển thị sang PDF
1. Xác định định dạng đường dẫn file cho PDF:
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
3.  Theo tùy chọn, bạn có thể chỉ định các tùy chọn hiển thị hoặc hiển thị các trang cụ thể bằng cách chuyển các tham số bổ sung tới`viewer.View()` phương pháp.
## Phần kết luận
Hiển thị hình ảnh CDR sang nhiều định dạng khác nhau như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể chuyển đổi các tệp CDR sang các định dạng khác nhau một cách hiệu quả dựa trên yêu cầu của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có tương thích với tất cả các phiên bản của tệp CDR không?
GroupDocs.Viewer for .NET hỗ trợ hiển thị các tệp CDR được tạo bởi các phiên bản CorelDRAW khác nhau.
### Tôi có thể tùy chỉnh đầu ra của tệp được hiển thị không?
Có, GroupDocs.Viewer for .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh đầu ra, chẳng hạn như điều chỉnh chất lượng hình ảnh, đặt hình mờ, v.v.
### GroupDocs.Viewer dành cho .NET có yêu cầu bất kỳ sự phụ thuộc bên ngoài nào không?
Không, GroupDocs.Viewer dành cho .NET là một thư viện độc lập và không yêu cầu bất kỳ phần phụ thuộc bên ngoài nào để hiển thị tài liệu.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của GroupDocs.Viewer cho .NET từ[đây](https://releases.groupdocs.com/).
### Tôi có thể nhận hỗ trợ cho GroupDocs.Viewer cho .NET ở đâu?
 Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng GroupDocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9).