---
title: Kết xuất tệp văn bản (.txt)
linktitle: Kết xuất tệp văn bản (.txt)
second_title: API GroupDocs.Viewer .NET
description: Khám phá khả năng chuyển đổi liền mạch các tệp văn bản thành nhiều định dạng bằng GroupDocs.Viewer cho .NET. Nâng cao khả năng quản lý tài liệu của bạn một cách dễ dàng.
weight: 10
url: /vi/net/rendering-text-files/render-txt/
---
## Giới thiệu
Trong lĩnh vực quản lý và thao tác tài liệu, GroupDocs.Viewer dành cho .NET nổi lên như một công cụ mạnh mẽ, cung cấp vô số chức năng để hiển thị các định dạng tài liệu khác nhau một cách hiệu quả. Bài viết này đi sâu vào sự phức tạp của việc sử dụng GroupDocs.Viewer cho .NET để hiển thị các tệp văn bản (.txt) thành nhiều định dạng. Cho dù bạn muốn chuyển đổi tệp văn bản thành HTML, JPG, PNG hay PDF, GroupDocs.Viewer đều trang bị cho bạn những công cụ cần thiết để hoàn thành các tác vụ này một cách liền mạch.
## Điều kiện tiên quyết
Trước khi đi sâu vào quá trình chuyển đổi, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
 Đảm bảo bạn đã cài đặt GroupDocs.Viewer for .NET trong môi trường phát triển của mình. Bạn có thể tải xuống các tập tin cần thiết từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
### 2. Làm quen cơ bản với .NET Framework
Làm quen với những kiến thức cơ bản về .NET framework, bao gồm cách thiết lập một dự án và sử dụng các thư viện trong cơ sở mã của bạn.
### 3. Tệp văn bản mẫu
Chuẩn bị các tệp văn bản mẫu (.txt) mà bạn định chuyển đổi. Những tập tin này sẽ đóng vai trò là đầu vào cho quá trình chuyển đổi.

## Nhập không gian tên
Trước khi đi sâu vào quá trình chuyển đổi, hãy đảm bảo nhập các vùng tên cần thiết vào dự án của bạn. Điều này cho phép bạn truy cập liền mạch các chức năng do GroupDocs.Viewer cung cấp cho .NET.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Hãy chia nhỏ từng ví dụ thành nhiều bước để hướng dẫn bạn thực hiện quá trình chuyển đổi một cách hiệu quả:

## Bước 1: Xác định đường dẫn đầu ra HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Chỉ định đường dẫn đầy đủ cho tệp đầu ra HTML.
## Bước 2: Kết xuất tệp văn bản thành HTML nhiều trang
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Khởi tạo một`Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình`HtmlViewOptions` cho các tài nguyên được nhúng và hiển thị tệp văn bản thành HTML nhiều trang.
## Bước 3: Xác định đường dẫn đầu ra HTML một trang
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Chỉ định đường dẫn đầy đủ cho tệp đầu ra HTML một trang.
## Bước 4: Kết xuất tệp văn bản thành HTML một trang
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Khởi tạo một`Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình`HtmlViewOptions` dành cho các tài nguyên được nhúng và thiết lập`RenderToSinglePage` thành sự thật. Kết xuất tệp văn bản thành HTML một trang.
## Bước 5: Xác định đường dẫn đầu ra JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Chỉ định đường dẫn đầy đủ cho tệp đầu ra JPG.
## Bước 6: Kết xuất tệp văn bản thành JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Khởi tạo một`Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình`JpgViewOptions` cho đường dẫn đầu ra và hiển thị tệp văn bản sang định dạng JPG.
## Bước 7: Xác định đường dẫn đầu ra PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Chỉ định đường dẫn đầy đủ cho tệp đầu ra PNG.
## Bước 8: Kết xuất tệp văn bản thành PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Khởi tạo một`Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình`PngViewOptions` cho đường dẫn đầu ra và hiển thị tệp văn bản thành định dạng PNG.
## Bước 9: Xác định đường dẫn đầu ra PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Chỉ định đường dẫn đầy đủ cho tệp đầu ra PDF.
## Bước 10: Kết xuất tệp văn bản thành PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Khởi tạo một`Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình`PdfViewOptions` cho đường dẫn đầu ra và hiển thị tệp văn bản thành định dạng PDF.

## Phần kết luận
Tóm lại, GroupDocs.Viewer dành cho .NET trao quyền cho các nhà phát triển dễ dàng hiển thị các tệp văn bản thành nhiều định dạng khác nhau, bao gồm HTML, JPG, PNG và PDF. Bằng cách làm theo hướng dẫn từng bước được nêu trong bài viết này, bạn có thể tích hợp liền mạch GroupDocs.Viewer vào các ứng dụng .NET của mình, nâng cao khả năng quản lý tài liệu.
## Câu hỏi thường gặp
### Câu hỏi: GroupDocs.Viewer dành cho .NET có tương thích với tất cả các phiên bản của .NET framework không?
Có, GroupDocs.Viewer for .NET được thiết kế để tương thích với nhiều phiên bản .NET framework, đảm bảo tính linh hoạt và linh hoạt trong quá trình phát triển.
### Câu hỏi: Tôi có thể tùy chỉnh giao diện đầu ra của tài liệu được kết xuất không?
Tuyệt đối! GroupDocs.Viewer cung cấp các tùy chọn tùy chỉnh mở rộng, cho phép nhà phát triển điều chỉnh giao diện của tài liệu được hiển thị theo sở thích và yêu cầu của họ.
### Câu hỏi: Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
 Có, bạn có thể khám phá các chức năng của GroupDocs.Viewer dành cho .NET bằng cách truy cập bản dùng thử miễn phí có sẵn trên[trang mạng]( https://releases.groupdocs.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ hoặc tìm kiếm trợ giúp với GroupDocs.Viewer dành cho .NET?
 Nếu có bất kỳ thắc mắc, hỗ trợ hoặc trợ giúp nào về GroupDocs.Viewer cho .NET, bạn có thể truy cập diễn đàn hỗ trợ chuyên dụng có thể truy cập được[đây](https://forum.groupdocs.com/c/viewer/9).
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho GroupDocs.Viewer cho .NET không?
Có, giấy phép tạm thời có sẵn để mua, cung cấp cho người dùng sự linh hoạt và thuận tiện trong việc sử dụng GroupDocs.Viewer cho .NET trong khoảng thời gian cụ thể.