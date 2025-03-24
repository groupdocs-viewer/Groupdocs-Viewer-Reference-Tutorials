---
title: Bảo vệ tệp PDF được hiển thị bằng mật khẩu
linktitle: Bảo vệ tệp PDF được hiển thị bằng mật khẩu
second_title: API GroupDocs.Viewer .NET
description: Dễ dàng bảo vệ các tệp PDF được hiển thị của bạn bằng mật khẩu bằng Groupdocs.Viewer cho .NET. Giữ tài liệu của bạn an toàn và bí mật.
weight: 12
url: /vi/net/rendering-documents-pdf/protect-pdf/
---

# Bảo vệ tệp PDF được hiển thị bằng mật khẩu

## Giới thiệu
Trong hướng dẫn này, bạn sẽ tìm hiểu cách sử dụng Groupdocs.Viewer cho .NET để bảo vệ tệp PDF được hiển thị bằng mật khẩu. Bằng cách thêm các biện pháp bảo mật, bạn có thể kiểm soát quyền truy cập vào tài liệu PDF của mình, đảm bảo tính bảo mật và toàn vẹn.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Groupdocs.Viewer for .NET Library: Tải xuống và cài đặt thư viện từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển hoạt động để phát triển .NET.

## Nhập không gian tên
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Xác định thư mục đầu ra và đường dẫn tệp
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Bước 2: Khởi tạo đối tượng Viewer và đặt tùy chọn bảo mật
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Bước 3: Đặt tùy chọn xem PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Bước 4: Kết xuất tài liệu với các tùy chọn bảo mật
```csharp
    viewer.View(options);
}
```
## Bước 5: Kiểm tra tài liệu được kết xuất
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bằng cách làm theo các bước này, bạn có thể bảo vệ tệp PDF được hiển thị bằng mật khẩu bằng Groupdocs.Viewer cho .NET. Điều này đảm bảo rằng tài liệu của bạn vẫn an toàn và chỉ những người dùng được ủy quyền mới có thể truy cập được.

## Phần kết luận
Bảo mật tài liệu PDF là điều cần thiết để duy trì tính bảo mật và toàn vẹn. Với Groupdocs.Viewer dành cho .NET, bạn có thể dễ dàng bảo vệ các tệp PDF được hiển thị bằng mật khẩu, kiểm soát quyền truy cập vào thông tin nhạy cảm.

## Câu hỏi thường gặp
### Tôi có thể bảo vệ tệp PDF với các cấp độ quyền khác nhau không?
Có, bạn có thể chỉ định các quyền khác nhau để xem, in, sao chép, v.v. đồng thời bảo vệ tệp PDF bằng mật khẩu.
### Groupdocs.Viewer có tương thích với nhiều định dạng tệp khác nhau không?
Tuyệt đối! Groupdocs.Viewer hỗ trợ hiển thị nhiều định dạng tệp, bao gồm DOCX, XLSX, PPTX, PDF, v.v.
### Tôi có thể tích hợp Groupdocs.Viewer vào ứng dụng .NET hiện có của mình không?
Chắc chắn! Groupdocs.Viewer cung cấp API để tích hợp liền mạch vào các ứng dụng .NET, cung cấp khả năng xem tài liệu mạnh mẽ.
### Groupdocs.Viewer có cung cấp hỗ trợ cho các dịch vụ lưu trữ đám mây không?
Có, Groupdocs.Viewer hỗ trợ tích hợp với các dịch vụ lưu trữ đám mây phổ biến như Dropbox, Google Drive và Amazon S3, cho phép bạn hiển thị các tài liệu được lưu trữ trên đám mây.
### Có phiên bản dùng thử cho Groupdocs.Viewer không?
 Có, bạn có thể bắt đầu với Groupdocs.Viewer bằng cách truy cập phiên bản dùng thử miễn phí từ[trang mạng](https://releases.groupdocs.com/).