---
title: Điều chỉnh kích thước và chất lượng hình ảnh (JPG)
linktitle: Điều chỉnh kích thước và chất lượng hình ảnh (JPG)
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách tối ưu hóa kích thước và chất lượng hình ảnh ở định dạng JPEG bằng Groupdocs.Viewer cho .NET. Nâng cao trải nghiệm xem tài liệu của bạn.
type: docs
weight: 11
url: /vi/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Giới thiệu
Groupdocs.Viewer for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tích hợp liền mạch chức năng xem tài liệu vào các ứng dụng .NET của họ. Một yêu cầu chung trong các ứng dụng xem tài liệu là khả năng điều chỉnh kích thước và chất lượng hình ảnh, đặc biệt khi xử lý hình ảnh JPEG (JPG). Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình điều chỉnh kích thước và chất lượng hình ảnh bằng Groupdocs.Viewer cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Hiểu biết cơ bản về ngôn ngữ lập trình C#.
2. Visual Studio được cài đặt trên hệ thống của bạn.
3.  Đã cài đặt Groupdocs.Viewer cho thư viện .NET. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).

## Nhập không gian tên
Trước tiên, bạn cần nhập các vùng tên cần thiết vào mã C# của mình. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để làm việc với Groupdocs.Viewer.
## Bước 1: Nhập không gian tên
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy chia mã ví dụ được cung cấp thành nhiều bước để hiểu rõ hơn.
## Bước 2: Đặt thư mục đầu ra và định dạng đường dẫn tệp trang
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Trong bước này, chúng tôi chỉ định thư mục đầu ra nơi hình ảnh được hiển thị sẽ được lưu và xác định định dạng cho đường dẫn tệp của mỗi hình ảnh trang.
## Bước 3: Khởi tạo Trình xem và Định cấu hình Tùy chọn Chế độ xem JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Ở đây, chúng ta khởi tạo đối tượng Viewer với đường dẫn đến tài liệu cần xem. Sau đó, chúng tôi tạo một phiên bản JpgViewOptions và đặt chiều rộng và chiều cao mong muốn cho hình ảnh JPEG.
## Bước 4: Kết xuất tài liệu nguồn
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cuối cùng, chúng tôi in một thông báo cho biết việc hiển thị thành công tài liệu nguồn và vị trí lưu hình ảnh đầu ra.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách điều chỉnh kích thước và chất lượng của hình ảnh JPEG bằng Groupdocs.Viewer cho .NET. Bằng cách làm theo các bước được nêu ở trên, bạn có thể dễ dàng kết hợp chức năng này vào các ứng dụng .NET của mình, cung cấp cho người dùng trải nghiệm xem hình ảnh được tối ưu hóa.
## Câu hỏi thường gặp
### Tôi có thể điều chỉnh chất lượng hình ảnh không?
Có, bạn có thể điều chỉnh chất lượng hình ảnh bằng cách đặt thuộc tính Chất lượng trong JpgViewOptions.
### Những định dạng tài liệu nào được Groupdocs.Viewer hỗ trợ cho .NET?
Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu bao gồm DOCX, PDF, PPTX, XLSX, v.v.
### Groupdocs.Viewer cho .NET có tương thích với .NET Core không?
Có, Groupdocs.Viewer cho .NET tương thích với .NET Core cùng với .NET Framework truyền thống.
### Tôi có thể tùy chỉnh định dạng đặt tên tệp đầu ra không?
Có, bạn có thể tùy chỉnh định dạng đặt tên tệp đầu ra bằng cách sửa đổi biến pageFilePathFormat trong mã.
### Groupdocs.Viewer cho .NET có hỗ trợ chú thích tài liệu không?
Có, Groupdocs.Viewer dành cho .NET cung cấp hỗ trợ toàn diện cho chú thích tài liệu bao gồm đánh dấu văn bản, gạch chân và nhận xét.