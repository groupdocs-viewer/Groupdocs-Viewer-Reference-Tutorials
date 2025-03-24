---
title: Kết xuất ghi chú và điều chỉnh đơn vị thời gian (MS Project)
linktitle: Kết xuất ghi chú và điều chỉnh đơn vị thời gian (MS Project)
second_title: API GroupDocs.Viewer .NET
description: Kết xuất chính các tài liệu MS Project bằng GroupDocs.Viewer cho .NET. Kết xuất ghi chú, điều chỉnh đơn vị thời gian và khám phá các định dạng đầu ra khác nhau một cách dễ dàng.
weight: 11
url: /vi/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Giới thiệu
GroupDocs.Viewer cho .NET là API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển xem và thao tác các định dạng tài liệu khác nhau trong ứng dụng .NET của họ. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc hiển thị ghi chú và điều chỉnh đơn vị thời gian cụ thể cho tài liệu MS Project.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Đảm bảo bạn đã tải xuống và cài đặt thư viện GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển ưa thích của bạn với sự hỗ trợ .NET.
3. Tài liệu MS Project: Chuẩn bị sẵn tài liệu MS Project mẫu để thử nghiệm.
## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết để bắt đầu hiển thị tài liệu MS Project:
## Bước 1: Nhập không gian tên
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Bây giờ chúng ta đã nhập các không gian tên cần thiết, hãy chia từng ví dụ thành nhiều bước để hiểu toàn diện.
## Hiển thị tài liệu dự án MS sang HTML
Để hiển thị tài liệu MS Project sang định dạng HTML có kèm theo ghi chú, hãy làm theo các bước sau:
### Bước 2: Đặt thư mục đầu ra và định dạng tệp
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Bước 3: Khởi tạo đối tượng Viewer và đặt tùy chọn
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Bước 4: Kết xuất tài liệu sang HTML
```csharp
viewer.View(options);
```
## Hiển thị tài liệu dự án MS sang định dạng hình ảnh
Bạn cũng có thể kết xuất tài liệu MS Project sang các định dạng hình ảnh như JPG và PNG. Đây là cách thực hiện:
### Bước 5: Đặt thư mục đầu ra và định dạng tệp cho JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Bước 6: Khởi tạo đối tượng Viewer và đặt tùy chọn JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Bước 7: Kết xuất tài liệu sang JPG
```csharp
viewer.View(options);
```
Lặp lại các bước tương tự để hiển thị sang PNG và các định dạng hình ảnh khác.
## Hiển thị tài liệu dự án MS sang PDF
Để hiển thị tài liệu MS Project sang định dạng PDF, hãy tiến hành như sau:
### Bước 8: Đặt thư mục đầu ra và định dạng tệp cho PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Bước 9: Khởi tạo đối tượng Viewer và đặt tùy chọn PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Bước 10: Kết xuất tài liệu thành PDF
```csharp
viewer.View(options);
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách hiển thị tài liệu MS Project và điều chỉnh đơn vị thời gian bằng GroupDocs.Viewer cho .NET. Kết hợp kiến thức này vào các dự án của bạn để nâng cao khả năng xem tài liệu.
## Câu hỏi thường gặp
### Tôi có thể hiển thị tài liệu MS Project sang các định dạng khác ngoài HTML, hình ảnh và PDF không?
Có, GroupDocs.Viewer for .NET hỗ trợ hiển thị sang nhiều định dạng khác nhau như DOCX, XLSX, PPTX, v.v.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
 Có, bạn có thể dùng thử miễn phí từ[đây](https://releases.groupdocs.com/).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho GroupDocs.Viewer cho .NET?
 Thăm nom[liên kết này](https://purchase.groupdocs.com/temporary-license/) để có được giấy phép tạm thời.
### Tôi có thể tìm tài liệu về GroupDocs.Viewer cho .NET ở đâu?
 Tham khảo tài liệu[đây](https://tutorials.groupdocs.com/viewer/net/).
### Tôi có thể tìm kiếm hỗ trợ hoặc đặt câu hỏi liên quan đến GroupDocs.Viewer cho .NET ở đâu?
 Bạn có thể truy cập diễn đàn hỗ trợ[đây](https://forum.groupdocs.com/c/viewer/9).