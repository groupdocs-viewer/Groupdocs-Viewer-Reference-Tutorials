---
title: Đặt giới hạn kích thước hình ảnh
linktitle: Đặt giới hạn kích thước hình ảnh
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách đặt giới hạn kích thước hình ảnh trong các ứng dụng .NET một cách dễ dàng bằng GroupDocs.Viewer dành cho .NET, nâng cao trải nghiệm xem tài liệu.
weight: 21
url: /vi/net/rendering-options/set-image-size-limits/
---

# Đặt giới hạn kích thước hình ảnh

## Giới thiệu
GroupDocs.Viewer dành cho .NET là một công cụ mạnh mẽ được thiết kế để tạo điều kiện thuận lợi cho việc xem tài liệu liền mạch trong các ứng dụng .NET. Với các tính năng mạnh mẽ và giao diện trực quan, các nhà phát triển có thể dễ dàng tích hợp khả năng xem tài liệu vào dự án của mình, nâng cao trải nghiệm và năng suất của người dùng. Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt giới hạn kích thước hình ảnh bằng GroupDocs.Viewer cho .NET, đảm bảo hiển thị tài liệu tối ưu trong khi vẫn duy trì hiệu suất và hiệu quả.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt thư viện GroupDocs.Viewer cho .NET cần thiết trong môi trường phát triển của mình. Bạn có thể tải nó xuống từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển .NET ưa thích của bạn, chẳng hạn như Visual Studio, với các cấu hình được yêu cầu.
3. Thư mục tài liệu: Có một thư mục được chỉ định để lưu trữ tài liệu của bạn và đảm bảo rằng đường dẫn thư mục có thể truy cập được trong ứng dụng của bạn.

## Nhập không gian tên
Trước khi tiếp tục triển khai, điều cần thiết là nhập các không gian tên cần thiết để truy cập các chức năng của GroupDocs.Viewer cho .NET một cách hiệu quả.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Xác định thư mục đầu ra và đường dẫn tệp
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế đến thư mục tài liệu của bạn.
## Bước 2: Khởi tạo đối tượng Viewer và chỉ định đường dẫn tài liệu
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX đại diện cho đường dẫn đến tài liệu mẫu.
    // Thay thế nó bằng đường dẫn đến tài liệu bạn muốn.
```
 Thay thế`TestFiles.SAMPLE_DOCX` với đường dẫn đến tài liệu của bạn. Đây có thể là DOCX, PDF hoặc bất kỳ định dạng tệp được hỗ trợ nào khác.
## Bước 3: Định cấu hình tùy chọn xem JPEG
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
 Điều chỉnh`MaxWidth` thuộc tính để đặt chiều rộng tối đa của hình ảnh được hiển thị theo yêu cầu của bạn. Điều này đảm bảo rằng hình ảnh không vượt quá chiều rộng được chỉ định, duy trì khả năng hiển thị tối ưu.
## Bước 4: Kết xuất tài liệu với các tùy chọn được chỉ định
```csharp
viewer.View(options);
```
Dòng mã này kích hoạt quá trình kết xuất, tạo ra hình ảnh đầu ra với giới hạn kích thước được xác định.
## Bước 5: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Sau khi kết xuất thành công, một thông báo cho biết hoàn thành thành công cùng với đường dẫn thư mục đầu ra sẽ được hiển thị.

## Phần kết luận
Tóm lại, việc nắm vững nghệ thuật thiết lập giới hạn kích thước hình ảnh bằng GroupDocs.Viewer cho .NET có thể nâng cao đáng kể trải nghiệm xem tài liệu trong các ứng dụng .NET của bạn. Bằng cách làm theo hướng dẫn từng bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tối ưu hóa hiển thị hình ảnh trong khi vẫn đảm bảo hiệu suất và hiệu quả.
## Câu hỏi thường gặp
### Tôi có thể đặt cả chiều rộng và chiều cao tối đa cho hình ảnh được hiển thị không?
Có, bạn có thể đặt cả chiều rộng và chiều cao tối đa bằng cách sử dụng các thuộc tính thích hợp trong tùy chọn chế độ xem.
### Những định dạng tài liệu nào được GroupDocs.Viewer hỗ trợ cho .NET?
GroupDocs.Viewer cho .NET hỗ trợ nhiều định dạng tài liệu, bao gồm DOCX, PDF, PPT, XLS, v.v.
### GroupDocs.Viewer cho .NET có tương thích với .NET Core không?
Có, GroupDocs.Viewer dành cho .NET cung cấp khả năng tương thích với .NET Core, cho phép tích hợp liền mạch vào các ứng dụng .NET hiện đại.
### Tôi có thể tùy chỉnh định dạng hình ảnh đầu ra khác ngoài JPEG không?
Có, GroupDocs.Viewer for .NET cung cấp hỗ trợ cho nhiều định dạng đầu ra khác nhau, bao gồm PNG, TIFF và PDF.
### Có phiên bản dùng thử để thử nghiệm trước khi mua không?
 Có, bạn có thể sử dụng phiên bản dùng thử miễn phí từ[trang mạng](https://releases.groupdocs.com/viewer/net/). để khám phá các tính năng và chức năng của GroupDocs.Viewer dành cho .NET trước khi mua hàng.