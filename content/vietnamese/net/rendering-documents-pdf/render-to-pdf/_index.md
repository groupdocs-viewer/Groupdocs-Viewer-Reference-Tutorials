---
title: Kết xuất tài liệu thành PDF
linktitle: Kết xuất tài liệu thành PDF
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị tài liệu sang PDF bằng GroupDocs.Viewer cho .NET. Hướng dẫn từng bước bao gồm các điều kiện tiên quyết và Câu hỏi thường gặp.
weight: 10
url: /vi/net/rendering-documents-pdf/render-to-pdf/
---

# Kết xuất tài liệu thành PDF

## Giới thiệu
GroupDocs.Viewer for .NET là một công cụ mạnh mẽ để hiển thị các định dạng tài liệu khác nhau thành PDF. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình.
## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  GroupDocs.Viewer for .NET Library: Bạn có thể tải xuống thư viện từ[đây](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Đảm bảo bạn đã cài đặt phiên bản .NET Framework thích hợp trên máy của mình.
3. Tệp tài liệu: Chuẩn bị các tệp tài liệu bạn muốn kết xuất. Các định dạng được hỗ trợ bao gồm DOCX, PDF, PPTX, XLSX, v.v.

## Nhập không gian tên:
Trước khi đi sâu vào mã, hãy đảm bảo bạn nhập các không gian tên cần thiết:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy chia quá trình kết xuất thành nhiều bước:
## Bước 1: Xác định thư mục đầu ra và đường dẫn tệp
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
 Đảm bảo thay thế`"Your Document Directory"` với thư mục mà bạn muốn lưu tệp PDF được hiển thị.
## Bước 2: Khởi tạo đối tượng người xem
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Mã của bạn ở đây
}
```
 Thay thế`TestFiles.SAMPLE_DOCX` với đường dẫn đến tệp tài liệu của bạn.
## Bước 3: Đặt tùy chọn xem PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Bước 4: Kết xuất tài liệu thành PDF
```csharp
viewer.View(options);
```
## Bước 5: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Sau khi làm theo các bước này, bạn sẽ hiển thị thành công tài liệu của mình sang PDF bằng GroupDocs.Viewer cho .NET.

## Phần kết luận
Kết xuất tài liệu sang PDF là một yêu cầu phổ biến trong các ứng dụng khác nhau. Với GroupDocs.Viewer dành cho .NET, quá trình này trở nên liền mạch và hiệu quả, cho phép bạn xử lý nhiều định dạng tài liệu một cách dễ dàng.
## Câu hỏi thường gặp
### Tôi có thể kết xuất các tài liệu không phải DOCX sang PDF không?
Có, GroupDocs.Viewer for .NET hỗ trợ nhiều định dạng khác nhau như PDF, PPTX, XLSX, v.v.
### Có sẵn phiên bản dùng thử không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.groupdocs.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ nếu gặp bất kỳ vấn đề nào?
 Bạn có thể truy cập diễn đàn GroupDocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ.
### Tôi có cần giấy phép tạm thời cho mục đích thử nghiệm không?
 Có, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.groupdocs.com/temporary-license/).
### Tôi có thể mua giấy phép đầy đủ ở đâu?
 Bạn có thể mua giấy phép từ[đây](https://purchase.groupdocs.com/buy).