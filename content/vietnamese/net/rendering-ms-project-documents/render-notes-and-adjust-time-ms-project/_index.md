---
"description": "Làm chủ việc kết xuất tài liệu MS Project với GroupDocs.Viewer cho .NET. Kết xuất ghi chú, điều chỉnh đơn vị thời gian và khám phá nhiều định dạng đầu ra dễ dàng."
"linktitle": "Render Notes và điều chỉnh đơn vị thời gian (MS Project)"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Render Notes và điều chỉnh đơn vị thời gian (MS Project)"
"url": "/vi/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Render Notes và điều chỉnh đơn vị thời gian (MS Project)

## Giới thiệu
GroupDocs.Viewer for .NET là một API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển xem và thao tác nhiều định dạng tài liệu khác nhau trong các ứng dụng .NET của họ. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc kết xuất ghi chú và điều chỉnh đơn vị thời gian cụ thể cho các tài liệu MS Project.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Đảm bảo bạn đã tải xuống và cài đặt thư viện GroupDocs.Viewer cho .NET. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển ưa thích của bạn với hỗ trợ .NET.
3. Tài liệu MS Project: Chuẩn bị một mẫu tài liệu MS Project để thử nghiệm.
## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết để bắt đầu kết xuất tài liệu MS Project:
## Bước 1: Nhập không gian tên
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Bây giờ chúng ta đã nhập các không gian tên cần thiết, hãy chia nhỏ từng ví dụ thành nhiều bước để hiểu rõ hơn.
## Kết xuất tài liệu MS Project sang HTML
Để hiển thị tài liệu MS Project sang định dạng HTML có kèm ghi chú, hãy làm theo các bước sau:
### Bước 2: Thiết lập thư mục đầu ra và định dạng tệp
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Bước 3: Khởi tạo đối tượng Viewer và thiết lập tùy chọn
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Bước 4: Kết xuất tài liệu thành HTML
```csharp
viewer.View(options);
```
## Kết xuất tài liệu MS Project sang định dạng hình ảnh
Bạn cũng có thể kết xuất tài liệu MS Project sang các định dạng hình ảnh như JPG và PNG. Sau đây là cách thực hiện:
### Bước 5: Thiết lập thư mục đầu ra và định dạng tệp cho JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Bước 6: Khởi tạo đối tượng Viewer và thiết lập tùy chọn JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Bước 7: Kết xuất tài liệu thành JPG
```csharp
viewer.View(options);
```
Lặp lại các bước tương tự để hiển thị sang PNG và các định dạng hình ảnh khác.
## Kết xuất tài liệu MS Project sang PDF
Để chuyển đổi tài liệu MS Project sang định dạng PDF, hãy thực hiện như sau:
### Bước 8: Thiết lập thư mục đầu ra và định dạng tệp cho PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Bước 9: Khởi tạo đối tượng Viewer và thiết lập tùy chọn PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Bước 10: Chuyển đổi tài liệu thành PDF
```csharp
viewer.View(options);
```

## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách kết xuất tài liệu MS Project và điều chỉnh đơn vị thời gian bằng GroupDocs.Viewer cho .NET. Kết hợp kiến thức này vào các dự án của bạn để nâng cao khả năng xem tài liệu.
## Câu hỏi thường gặp
### Tôi có thể chuyển đổi tài liệu MS Project sang các định dạng khác ngoài HTML, hình ảnh và PDF không?
Có, GroupDocs.Viewer for .NET hỗ trợ hiển thị sang nhiều định dạng khác nhau như DOCX, XLSX, PPTX, v.v.
### Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể nhận được bản dùng thử miễn phí từ [đây](https://releases.groupdocs.com/).
### Làm thế nào tôi có thể nhận được giấy phép tạm thời cho GroupDocs.Viewer dành cho .NET?
Thăm nom [liên kết này](https://purchase.groupdocs.com/temporary-license/) để xin giấy phép tạm thời.
### Tôi có thể tìm tài liệu về GroupDocs.Viewer cho .NET ở đâu?
Tham khảo tài liệu [đây](https://tutorials.groupdocs.com/viewer/net/).
### Tôi có thể tìm kiếm sự hỗ trợ hoặc đặt câu hỏi liên quan đến GroupDocs.Viewer cho .NET ở đâu?
Bạn có thể ghé thăm diễn đàn hỗ trợ [đây](https://forum.groupdocs.com/c/viewer/9).