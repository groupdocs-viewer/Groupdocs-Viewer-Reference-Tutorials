---
"description": "Khám phá khả năng chuyển đổi liền mạch các tệp văn bản thành nhiều định dạng bằng GroupDocs.Viewer cho .NET. Nâng cao khả năng quản lý tài liệu của bạn một cách dễ dàng."
"linktitle": "Hiển thị tệp văn bản (.txt)"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị tệp văn bản (.txt)"
"url": "/vi/net/rendering-text-files/render-txt/"
"weight": 10
---

# Hiển thị tệp văn bản (.txt)

## Giới thiệu
Trong lĩnh vực quản lý và xử lý tài liệu, GroupDocs.Viewer for .NET nổi lên như một công cụ mạnh mẽ, cung cấp vô số chức năng để hiển thị nhiều định dạng tài liệu một cách hiệu quả. Bài viết này đi sâu vào sự phức tạp của việc sử dụng GroupDocs.Viewer for .NET để hiển thị các tệp văn bản (.txt) thành nhiều định dạng. Cho dù bạn muốn chuyển đổi các tệp văn bản thành HTML, JPG, PNG hay PDF, GroupDocs.Viewer đều trang bị cho bạn các công cụ cần thiết để hoàn thành các tác vụ này một cách liền mạch.
## Điều kiện tiên quyết
Trước khi bắt đầu quá trình chuyển đổi, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
Đảm bảo bạn đã cài đặt GroupDocs.Viewer cho .NET trong môi trường phát triển của mình. Bạn có thể tải xuống các tệp cần thiết từ [trang web](https://releases.groupdocs.com/viewer/net/).
### 2. Kiến thức cơ bản về .NET Framework
Làm quen với những kiến thức cơ bản về .NET framework, bao gồm cách thiết lập dự án và sử dụng các thư viện trong cơ sở mã của bạn.
### 3. Các tập tin văn bản mẫu
Chuẩn bị các tệp văn bản mẫu (.txt) mà bạn định chuyển đổi. Các tệp này sẽ đóng vai trò là đầu vào cho quá trình chuyển đổi.

## Nhập không gian tên
Trước khi bắt đầu quá trình chuyển đổi, hãy đảm bảo nhập các không gian tên cần thiết vào dự án của bạn. Điều này cho phép bạn truy cập các chức năng do GroupDocs.Viewer cung cấp cho .NET một cách liền mạch.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Chúng ta hãy chia nhỏ từng ví dụ thành nhiều bước để hướng dẫn bạn thực hiện quy trình chuyển đổi hiệu quả:

## Bước 1: Xác định Đường dẫn đầu ra HTML
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
Khởi tạo một `Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình `HtmlViewOptions` để nhúng tài nguyên và chuyển đổi tệp văn bản thành HTML nhiều trang.
## Bước 3: Xác định Đường dẫn đầu ra HTML một trang
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
Khởi tạo một `Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình `HtmlViewOptions` cho các tài nguyên nhúng và thiết lập `RenderToSinglePage` thành đúng. Kết xuất tệp văn bản thành HTML một trang.
## Bước 5: Xác định Đường dẫn đầu ra JPG
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
Khởi tạo một `Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình `JpgViewOptions` để có đường dẫn đầu ra và chuyển tệp văn bản thành định dạng JPG.
## Bước 7: Xác định Đường dẫn đầu ra PNG
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
Khởi tạo một `Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình `PngViewOptions` để có đường dẫn đầu ra và hiển thị tệp văn bản thành định dạng PNG.
## Bước 9: Xác định đường dẫn đầu ra PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Chỉ định đường dẫn đầy đủ cho tệp PDF đầu ra.
## Bước 10: Chuyển đổi tệp văn bản thành PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Khởi tạo một `Viewer` đối tượng có đường dẫn đến tệp văn bản. Cấu hình `PdfViewOptions` để có đường dẫn đầu ra và chuyển đổi tệp văn bản thành định dạng PDF.

## Phần kết luận
Tóm lại, GroupDocs.Viewer for .NET trao quyền cho các nhà phát triển dễ dàng chuyển đổi các tệp văn bản thành nhiều định dạng khác nhau, bao gồm HTML, JPG, PNG và PDF. Bằng cách làm theo hướng dẫn từng bước được nêu trong bài viết này, bạn có thể tích hợp GroupDocs.Viewer vào các ứng dụng .NET của mình một cách liền mạch, nâng cao khả năng quản lý tài liệu.
## Câu hỏi thường gặp
### H: GroupDocs.Viewer cho .NET có tương thích với tất cả các phiên bản của .NET framework không?
Có, GroupDocs.Viewer cho .NET được thiết kế để tương thích với nhiều phiên bản .NET framework, đảm bảo tính linh hoạt và đa năng trong quá trình phát triển.
### H: Tôi có thể tùy chỉnh giao diện đầu ra của tài liệu đã kết xuất không?
Hoàn toàn có thể! GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh, cho phép các nhà phát triển tùy chỉnh giao diện của tài liệu được hiển thị theo hướng dẫn và yêu cầu của họ.
### H: Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể khám phá các chức năng của GroupDocs.Viewer cho .NET bằng cách truy cập bản dùng thử miễn phí có sẵn trên [trang web]( https://releases.groupdocs.com/).
### H: Tôi có thể nhận được hỗ trợ hoặc tìm kiếm trợ giúp với GroupDocs.Viewer cho .NET như thế nào?
Đối với bất kỳ thắc mắc, hỗ trợ hoặc trợ giúp nào liên quan đến GroupDocs.Viewer cho .NET, bạn có thể truy cập diễn đàn hỗ trợ chuyên dụng có thể truy cập [đây](https://forum.groupdocs.com/c/viewer/9).
### H: Tôi có thể mua giấy phép tạm thời cho GroupDocs.Viewer dành cho .NET không?
Có, giấy phép tạm thời có thể mua, giúp người dùng có sự linh hoạt và tiện lợi khi sử dụng GroupDocs.Viewer cho .NET trong những khoảng thời gian cụ thể.