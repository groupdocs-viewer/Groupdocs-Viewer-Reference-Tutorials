---
"description": "Tìm hiểu cách chuyển đổi các tệp lưu trữ RAR sang định dạng HTML, JPG, PNG hoặc PDF bằng GroupDocs.Viewer cho .NET. Dễ dàng xem và chia sẻ nội dung của các tệp lưu trữ RAR."
"linktitle": "Kết xuất Lưu trữ RAR"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất Lưu trữ RAR"
"url": "/vi/net/rendering-archive-files/render-rar/"
"weight": 13
---

# Kết xuất Lưu trữ RAR

## Giới thiệu
Lưu trữ RAR là định dạng phổ biến để nén và lưu trữ nhiều tệp và thư mục vào một vùng chứa duy nhất. Việc kết xuất lưu trữ RAR thành nhiều định dạng khác nhau như HTML, JPG, PNG hoặc PDF có thể rất cần thiết để xem hoặc chia sẻ nội dung của các lưu trữ này. Trong hướng dẫn này, chúng ta sẽ khám phá cách kết xuất lưu trữ RAR bằng GroupDocs.Viewer cho .NET.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Cài đặt thư viện GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
2. Lưu trữ mẫu RAR: Chuẩn bị một lưu trữ mẫu RAR để kết xuất.

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
## Bước 2: Kết xuất thành HTML
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
## Bước 4: Kết xuất thành PNG
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
Việc kết xuất các tệp lưu trữ RAR thành nhiều định dạng khác nhau trở nên đơn giản với GroupDocs.Viewer for .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng chuyển đổi các tệp lưu trữ RAR sang các định dạng HTML, JPG, PNG hoặc PDF, cho phép dễ dàng xem và chia sẻ nội dung của chúng.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có thể xử lý được các tệp lưu trữ RAR được mã hóa không?
Có, GroupDocs.Viewer cho .NET hỗ trợ việc kết xuất các tệp lưu trữ RAR được mã hóa với điều kiện là mật khẩu cần thiết được cung cấp trong quá trình kết xuất.
### Có thể tùy chỉnh giao diện đầu ra của tài liệu đã kết xuất không?
Hoàn toàn đúng! GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn tùy chỉnh cho phép người dùng tùy chỉnh giao diện của tài liệu được hiển thị theo hướng dẫn của họ.
### GroupDocs.Viewer cho .NET có hỗ trợ hiển thị các định dạng lưu trữ khác ngoài RAR không?
Có, GroupDocs.Viewer for .NET hỗ trợ hiển thị nhiều định dạng lưu trữ khác nhau bao gồm ZIP, TAR, 7z, v.v.
### Tôi có thể tích hợp GroupDocs.Viewer cho .NET vào ứng dụng web của mình không?
Chắc chắn rồi! GroupDocs.Viewer cho .NET cung cấp các API phù hợp để tích hợp vào cả ứng dụng trên máy tính để bàn và web.
### Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể sử dụng bản dùng thử miễn phí của GroupDocs.Viewer cho .NET từ [trang web](https://releases.groupdocs.com/).