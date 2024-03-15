---
title: Kết xuất với văn bản được phủ để hiển thị
linktitle: Kết xuất với văn bản được phủ để hiển thị
second_title: API GroupDocs.Viewer .NET
description: Kết xuất tài liệu một cách liền mạch trong các ứng dụng .NET bằng GroupDocs.Viewer, hỗ trợ nhiều định dạng khác nhau để nâng cao trải nghiệm người dùng.
type: docs
weight: 13
url: /vi/net/rendering-documents-images/render-with-text-overlay/
---
## Giới thiệu
Trong lĩnh vực phát triển .NET, việc quản lý và hiển thị liền mạch các định dạng tài liệu khác nhau là rất quan trọng đối với nhiều ứng dụng. GroupDocs.Viewer dành cho .NET nổi lên như một giải pháp mạnh mẽ để dễ dàng hiển thị tài liệu trong các ứng dụng .NET của bạn. Cho dù đó là tệp PDF, tài liệu Word, bảng tính Excel hay bản trình bày PowerPoint, GroupDocs.Viewer đều đơn giản hóa quy trình, cung cấp một loạt tính năng để nâng cao khả năng xem tài liệu.
## Điều kiện tiên quyết
Trước khi đi sâu vào việc tích hợp GroupDocs.Viewer cho .NET vào các dự án của bạn, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
### Thiết lập môi trường .NET
1. Cài đặt Visual Studio: Nếu bạn chưa cài đặt, hãy tải xuống và cài đặt Visual Studio từ trang web của Microsoft.
   
2. Tạo dự án .NET: Mở Visual Studio và tạo dự án .NET mới hoặc mở dự án hiện có mà bạn muốn tích hợp GroupDocs.Viewer.
3. .NET Framework: Đảm bảo rằng dự án của bạn hướng tới phiên bản .NET Framework tương thích.
### Cài đặt GroupDocs.Viewer
1.  Tải xuống GroupDocs.Viewer: Truy cập[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/) để có phiên bản mới nhất của GroupDocs.Viewer cho .NET.
2. Thêm GroupDocs.Viewer vào dự án của bạn: Giải nén các tệp đã tải xuống và thêm các tập hợp GroupDocs.Viewer cần thiết vào tài liệu tham khảo dự án của bạn.

## Nhập không gian tên
Để sử dụng các chức năng GroupDocs.Viewer trong ứng dụng .NET của bạn, hãy nhập các vùng tên được yêu cầu:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn mà bạn muốn lưu trữ các trang tài liệu được hiển thị.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
 Dòng này chỉ định định dạng để đặt tên cho các trang được hiển thị. Trong ví dụ này, nó sử dụng một trình giữ chỗ`{0}` để thể hiện số trang.
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Khối mã
}
```
 Tạo một`Viewer`đối tượng bằng cách chuyển đường dẫn của tài liệu cần xem. Trong trường hợp này,`TestFiles.SAMPLE_DOCX` đại diện cho đường dẫn của tài liệu mẫu.
## Bước 4: Đặt tùy chọn kết xuất
```csharp
PngViewOptions options = new PngViewOptions(pageFilePathFormat);
options.ExtractText = true;
```
 Định cấu hình tùy chọn kết xuất dựa trên yêu cầu của bạn. Đây,`PngViewOptions` được sử dụng để hiển thị các trang dưới dạng hình ảnh PNG và`ExtractText` được đặt thành`true` để trích xuất văn bản từ tài liệu.
## Bước 5: Kết xuất tài liệu
```csharp
viewer.View(options);
```
 Gọi`View` phương pháp của`Viewer` đối tượng, chuyển các tùy chọn kết xuất để bắt đầu quá trình kết xuất.
## Bước 6: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Sau khi kết xuất, hiển thị thông báo thành công cho biết quá trình hoàn tất và vị trí lưu trữ các trang được kết xuất.

## Phần kết luận
Việc kết hợp GroupDocs.Viewer dành cho .NET vào các dự án của bạn sẽ mở ra vô số khả năng hiển thị tài liệu hiệu quả. Với API trực quan và các tính năng mạnh mẽ, việc xử lý các định dạng tài liệu khác nhau trở nên liền mạch, nâng cao trải nghiệm người dùng.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với tất cả các định dạng tài liệu không?
GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v.
### Tôi có thể tùy chỉnh các tùy chọn hiển thị theo yêu cầu của ứng dụng của mình không?
Có, GroupDocs.Viewer cung cấp các tùy chọn tùy chỉnh mở rộng để điều chỉnh quy trình kết xuất theo nhu cầu cụ thể của bạn.
### GroupDocs.Viewer có cung cấp hỗ trợ đa nền tảng không?
GroupDocs.Viewer được thiết kế chủ yếu cho các ứng dụng .NET nhưng cũng cung cấp hỗ trợ cho các ứng dụng Java thông qua GroupDocs.Viewer cho Java.
### GroupDocs.Viewer có phù hợp để xử lý tài liệu quy mô lớn không?
Có, GroupDocs.Viewer được tối ưu hóa để xử lý khối lượng lớn tài liệu một cách hiệu quả, khiến nó trở nên lý tưởng cho các ứng dụng cấp doanh nghiệp.
### Tôi có thể tìm trợ giúp ở đâu nếu gặp sự cố trong quá trình tích hợp hoặc sử dụng?
 Bạn có thể tìm kiếm sự hỗ trợ từ diễn đàn cộng đồng GroupDocs[đây](https://forum.groupdocs.com/c/viewer/9).