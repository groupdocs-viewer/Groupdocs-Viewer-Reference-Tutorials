---
title: Kết xuất số
linktitle: Kết xuất số
second_title: API GroupDocs.Viewer .NET
description: Khám phá sức mạnh của Groupdocs.Viewer dành cho .NET trong việc hiển thị các tệp Numbers một cách liền mạch. Chuyển đổi sang HTML, JPG, PNG và PDF một cách dễ dàng.
weight: 15
url: /vi/net/spreadsheet-rendering-options/rendering-numbers/
---

# Kết xuất số

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước này về cách hiển thị tệp Numbers bằng Groupdocs.Viewer cho .NET. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn quy trình chuyển đổi tài liệu Numbers sang nhiều định dạng khác nhau. Groupdocs.Viewer dành cho .NET là một công cụ mạnh mẽ cho phép bạn tích hợp liền mạch khả năng xem tài liệu vào các ứng dụng .NET của mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về phát triển C# và .NET.
-  Đã cài đặt Groupdocs.Viewer cho thư viện .NET. Bạn có thể tải nó xuống[đây](https://releases.groupdocs.com/viewer/net/).
- Đường dẫn thư mục tài liệu của bạn nơi các tập tin đầu ra sẽ được lưu.
## Nhập không gian tên
Trong dự án C# của bạn, hãy đảm bảo bạn nhập các vùng tên cần thiết để sử dụng thư viện Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục đầu ra
Trước khi bạn bắt đầu kết xuất, hãy xác định thư mục đầu ra nơi các tệp đã chuyển đổi sẽ được lưu. Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Kết xuất thành HTML nhiều trang
Sử dụng đoạn mã sau để chuyển đổi tệp Numbers thành HTML nhiều trang:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Bước 3: Kết xuất sang JPG
Chuyển file Numbers sang định dạng JPG với đoạn code sau:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Bước 4: Kết xuất sang PNG
Chuyển đổi tệp Số thành định dạng PNG bằng mã sau:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Bước 5: Kết xuất thành PDF
Cuối cùng, chuyển đổi tệp Numbers sang định dạng PDF bằng mã sau:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Chúc mừng! Bạn đã kết xuất thành công các tệp Numbers thành nhiều định dạng khác nhau bằng Groupdocs.Viewer cho .NET.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày các kiến thức cơ bản về hiển thị tệp Numbers bằng Groupdocs.Viewer cho .NET. Thư viện mạnh mẽ này cung cấp sự tích hợp liền mạch để xem và chuyển đổi tài liệu trong các ứng dụng .NET của bạn.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Groupdocs.Viewer cho .NET với các loại tài liệu khác không?
Có, Groupdocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm Word, Excel, PDF, v.v.
### Giấy phép tạm thời có sẵn cho mục đích thử nghiệm không?
 Có, bạn có thể có được giấy phép tạm thời[đây](https://purchase.groupdocs.com/temporary-license/) để thử nghiệm.
### Tôi có thể tìm hỗ trợ cho Groupdocs.Viewer cho .NET ở đâu?
 Tham quan[Diễn đàn Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ và thảo luận.
### Làm cách nào để mua phiên bản đầy đủ của Groupdocs.Viewer cho .NET?
 Bạn có thể mua phiên bản đầy đủ[đây](https://purchase.groupdocs.com/buy).
### Có phiên bản dùng thử miễn phí không?
 Có, bạn có thể khám phá phiên bản dùng thử miễn phí[đây](https://releases.groupdocs.com/).