---
"description": "Tìm hiểu cách bật hiển thị theo lớp trong tài liệu PDF bằng GroupDocs.Viewer cho .NET. Nâng cao trải nghiệm xem tài liệu một cách dễ dàng."
"linktitle": "Bật tính năng kết xuất theo lớp trong PDF"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Bật tính năng kết xuất theo lớp trong PDF"
"url": "/vi/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# Bật tính năng kết xuất theo lớp trong PDF

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình bật kết xuất theo lớp trong tài liệu PDF bằng GroupDocs.Viewer cho .NET. Kết xuất theo lớp cho phép hiển thị và thao tác tài liệu nâng cao, mang đến cho người dùng trải nghiệm xem tương tác hơn.

![Bật tính năng kết xuất theo lớp trong PDF với GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt gói hoặc thư viện cần thiết để sử dụng GroupDocs.Viewer cho .NET trong dự án của mình.
2. Visual Studio: Bạn nên cài đặt Visual Studio trên hệ thống của mình để mã hóa và thực thi các ví dụ được cung cấp.
3. Hiểu biết cơ bản về C#: Hướng dẫn này giả định bạn đã quen thuộc với cú pháp và khái niệm của ngôn ngữ lập trình C#.

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
Đảm bảo chỉ định đường dẫn thư mục mà bạn muốn lưu kết quả đã kết xuất.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Bước này thiết lập định dạng cho đường dẫn tệp của từng trang trong kết quả hiển thị. `{0}` là chỗ giữ chỗ cho số trang.
## Bước 3: Kích hoạt kết xuất theo lớp
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Ở đây, chúng tôi tạo ra một `Viewer` đối tượng và chỉ định tài liệu PDF cần xử lý. Sau đó, chúng tôi cấu hình `HtmlViewOptions` với định dạng đường dẫn tệp trang được xác định. Bằng cách thiết lập `EnableLayeredRendering` tài sản để `true` TRONG `PdfOptions`, chúng tôi cho phép hiển thị nhiều lớp cho tài liệu PDF.
## Bước 4: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cuối cùng, chúng tôi in ra thông báo cho biết tài liệu nguồn đã được kết xuất thành công và nhắc người dùng kiểm tra đầu ra trong thư mục đã chỉ định.

## Phần kết luận
Bật kết xuất theo lớp trong tài liệu PDF bằng GroupDocs.Viewer cho .NET giúp tăng cường khả năng xem tài liệu, mang đến cho người dùng trải nghiệm phong phú và tương tác hơn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch tính năng này vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Kết xuất theo lớp trong tài liệu PDF là gì?
Kết xuất theo lớp cho phép tách và thao tác các thành phần khác nhau trong tài liệu PDF, cho phép xem tương tác và nâng cao trải nghiệm của người dùng.
### Tôi có thể tùy chỉnh thư mục đầu ra cho các tài liệu được kết xuất không?
Có, bạn có thể chỉ định bất kỳ đường dẫn thư mục nào cho đầu ra theo yêu cầu của bạn.
### GroupDocs.Viewer có hỗ trợ các định dạng tệp khác ngoài PDF không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm Word, Excel, PowerPoint, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer tương thích với cả môi trường .NET Framework và .NET Core.
### Tôi có thể tìm thêm sự hỗ trợ hoặc trợ giúp ở đâu?
Bạn có thể truy cập diễn đàn GroupDocs.Viewer để được giải đáp thắc mắc hoặc hỗ trợ về thư viện trình xem.