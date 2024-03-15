---
title: Bật hiển thị lớp trong PDF
linktitle: Bật hiển thị lớp trong PDF
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách bật hiển thị lớp trong tài liệu PDF bằng GroupDocs.Viewer dành cho .NET. Nâng cao trải nghiệm xem tài liệu một cách dễ dàng.
type: docs
weight: 15
url: /vi/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình cho phép hiển thị theo lớp trong tài liệu PDF bằng GroupDocs.Viewer cho .NET. Kết xuất theo lớp cho phép hiển thị và thao tác tài liệu nâng cao, cung cấp cho người dùng trải nghiệm xem tương tác hơn.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt gói hoặc thư viện cần thiết để sử dụng GroupDocs.Viewer cho .NET trong dự án của bạn.
2. Visual Studio: Bạn nên cài đặt Visual Studio trên hệ thống của mình để mã hóa và thực thi các ví dụ được cung cấp.
3. Hiểu biết cơ bản về C#: Hướng dẫn này giả định bạn đã làm quen với cú pháp và khái niệm của ngôn ngữ lập trình C#.

## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án của bạn:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Đảm bảo chỉ định đường dẫn thư mục nơi bạn muốn lưu đầu ra được hiển thị.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Bước này đặt định dạng cho đường dẫn tệp của từng trang riêng lẻ trong kết quả được hiển thị.`{0}` là một trình giữ chỗ cho số trang.
## Bước 3: Kích hoạt kết xuất lớp
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Ở đây, chúng tôi tạo ra một`Viewer` đối tượng và chỉ định tài liệu PDF cần xử lý. Sau đó chúng tôi cấu hình`HtmlViewOptions` với định dạng đường dẫn tệp trang được xác định. Bằng cách thiết lập`EnableLayeredRendering` tài sản để`true` TRONG`PdfOptions`, chúng tôi kích hoạt hiển thị theo lớp cho tài liệu PDF.
## Bước 4: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cuối cùng, chúng tôi in một thông báo cho biết việc hiển thị thành công tài liệu nguồn và nhắc người dùng kiểm tra đầu ra trong thư mục đã chỉ định.

## Phần kết luận
Kích hoạt tính năng hiển thị theo lớp trong tài liệu PDF bằng GroupDocs.Viewer dành cho .NET nâng cao khả năng xem tài liệu, cung cấp cho người dùng trải nghiệm phong phú hơn và mang tính tương tác hơn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch tính năng này vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Kết xuất lớp trong tài liệu PDF là gì?
Kết xuất theo lớp cho phép tách và thao tác các thành phần khác nhau trong tài liệu PDF, cho phép xem tương tác và nâng cao trải nghiệm người dùng.
### Tôi có thể tùy chỉnh thư mục đầu ra cho các tài liệu được hiển thị không?
Có, bạn có thể chỉ định bất kỳ đường dẫn thư mục nào cho đầu ra theo yêu cầu của mình.
### GroupDocs.Viewer có hỗ trợ các định dạng tệp khác ngoài PDF không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm Word, Excel, PowerPoint, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer tương thích với cả môi trường .NET Framework và .NET Core.
### Tôi có thể tìm thêm hỗ trợ hoặc hỗ trợ ở đâu?
Bạn có thể truy cập diễn đàn GroupDocs.Viewer nếu có bất kỳ thắc mắc hoặc hỗ trợ nào liên quan đến thư viện trình xem.