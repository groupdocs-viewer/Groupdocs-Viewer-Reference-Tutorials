---
title: Kết xuất kho lưu trữ RAR
linktitle: Kết xuất kho lưu trữ RAR
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị kho lưu trữ RAR thành định dạng HTML, JPG, PNG hoặc PDF bằng GroupDocs.Viewer cho .NET. Dễ dàng xem và chia sẻ nội dung của kho lưu trữ RAR.
weight: 13
url: /vi/net/rendering-archive-files/render-rar/
---
## Giới thiệu
Kho lưu trữ RAR là định dạng phổ biến để nén và lưu trữ nhiều tệp và thư mục vào một vùng chứa duy nhất. Việc hiển thị các kho lưu trữ RAR thành nhiều định dạng khác nhau như HTML, JPG, PNG hoặc PDF có thể cần thiết để xem hoặc chia sẻ nội dung của các kho lưu trữ này. Trong hướng dẫn này, chúng ta sẽ khám phá cách hiển thị các kho lưu trữ RAR bằng GroupDocs.Viewer cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Cài đặt thư viện GroupDocs.Viewer cho .NET từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
2. Lưu trữ RAR mẫu: Chuẩn bị sẵn một kho lưu trữ RAR mẫu để hiển thị.

## Nhập không gian tên
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Kết xuất sang HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 3: Kết xuất sang JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 4: Kết xuất sang PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 5: Kết xuất thành PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Phần kết luận
Việc hiển thị các kho lưu trữ RAR thành nhiều định dạng khác nhau được thực hiện đơn giản với GroupDocs.Viewer dành cho .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng chuyển đổi các kho lưu trữ RAR sang định dạng HTML, JPG, PNG hoặc PDF, cho phép dễ dàng xem và chia sẻ nội dung của chúng.
## Câu hỏi thường gặp
### GroupDocs.Viewer dành cho .NET có thể xử lý các kho lưu trữ RAR được mã hóa không?
Có, GroupDocs.Viewer for .NET hỗ trợ hiển thị các kho lưu trữ RAR được mã hóa miễn là cung cấp mật khẩu cần thiết trong quá trình kết xuất.
### Có thể tùy chỉnh giao diện đầu ra của tài liệu được kết xuất không?
Tuyệt đối! GroupDocs.Viewer dành cho .NET cung cấp các tùy chọn tùy chỉnh mở rộng cho phép người dùng điều chỉnh giao diện của tài liệu được hiển thị theo sở thích của họ.
### GroupDocs.Viewer dành cho .NET có hỗ trợ hiển thị các định dạng lưu trữ khác ngoài RAR không?
Có, GroupDocs.Viewer cho .NET hỗ trợ hiển thị nhiều định dạng lưu trữ khác nhau bao gồm ZIP, TAR, 7z, v.v.
### Tôi có thể tích hợp GroupDocs.Viewer dành cho .NET vào ứng dụng web của mình không?
Chắc chắn! GroupDocs.Viewer cho .NET cung cấp các API phù hợp để tích hợp vào cả ứng dụng web và máy tính để bàn.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
 Có, bạn có thể tận dụng bản dùng thử miễn phí GroupDocs.Viewer cho .NET từ[trang mạng](https://releases.groupdocs.com/).