---
title: Kết xuất các đường lưới
linktitle: Kết xuất các đường lưới
second_title: API GroupDocs.Viewer .NET
description: Nâng cao khả năng trực quan hóa tài liệu với GroupDocs.Viewer dành cho .NET. Hiển thị các đường lưới một cách dễ dàng. Hãy thử dùng thử miễn phí ngay bây giờ! #GroupDocs #Viewer
weight: 12
url: /vi/net/spreadsheet-rendering-options/render-grid-lines/
---

# Kết xuất các đường lưới

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước này về cách sử dụng GroupDocs.Viewer dành cho .NET để hiển thị các đường lưới trong tài liệu của bạn. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới làm quen với .NET framework, hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình với các giải thích chi tiết và ví dụ dễ làm theo.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
-  GroupDocs.Viewer for .NET: Tải xuống và cài đặt thư viện từ[Trang web chính thức](https://releases.groupdocs.com/viewer/net/).
- Thư mục tài liệu của bạn: Đảm bảo bạn có một thư mục được chỉ định cho tài liệu của mình và thay thế "Thư mục tài liệu của bạn" trong đoạn mã được cung cấp bằng đường dẫn thực tế.
Bây giờ bạn đã thiết lập mọi thứ, hãy bắt đầu.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục tài liệu
Bắt đầu bằng cách chỉ định đường dẫn đến thư mục tài liệu của bạn:
```csharp
string outputDirectory = "Your Document Directory";
```
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế nơi tài liệu của bạn được lưu trữ.
## Bước 2: Xác định đường dẫn tệp và định dạng đầu ra HTML
Tạo một biến để lưu trữ định dạng đường dẫn tệp cho mỗi trang và định dạng HTML đầu ra:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Dòng này xây dựng đường dẫn tệp cho mỗi trang theo định dạng đã chỉ định.
## Bước 3: Khởi tạo GroupDocs.Viewer
Khởi tạo lớp Viewer bằng tài liệu bạn muốn xem:
```csharp
using (Viewer viewer = new Viewer(outputDirectory + "SAMPLE.XLSX"))
{
    // Các bước tiếp theo sẽ được thực hiện trong khối sử dụng này.
}
```
Đảm bảo thay thế "SAMPLE.XLSX" bằng tên tài liệu thực tế của bạn.
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
Thiết lập các tùy chọn chế độ xem HTML, đặc biệt cho phép hiển thị các đường lưới:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions.RenderGridLines = true;
```
Đoạn mã này định cấu hình các tùy chọn chế độ xem HTML để nhúng tài nguyên và hiển thị các đường lưới cho tài liệu bảng tính.
## Bước 5: Kết xuất các đường lưới
 Gọi`View` phương pháp hiển thị tài liệu với các tùy chọn được chỉ định cho trang 1, 2 và 3:
```csharp
viewer.View(options, 1, 2, 3);
```
Điều chỉnh số trang theo yêu cầu của bạn.
Đó là nó! Bạn đã hiển thị thành công các đường lưới bằng GroupDocs.Viewer cho .NET.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá quy trình hiển thị các đường lưới trong tài liệu bằng GroupDocs.Viewer cho .NET. Thực hiện theo các bước đã nêu sẽ giúp bạn nâng cao khả năng trình bày trực quan các tài liệu bảng tính của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có được sử dụng miễn phí không?
 GroupDocs.Viewer for .NET cung cấp cả phiên bản dùng thử miễn phí và trả phí. Khám phá cái[dùng thử miễn phí](https://releases.groupdocs.com/) hoặc ghé thăm[trang mua hàng](https://purchase.groupdocs.com/buy) để biết chi tiết cấp phép.
### Làm cách nào tôi có thể nhận được hỗ trợ cho GroupDocs.Viewer cho .NET?
 Tham quan[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để tìm kiếm sự hỗ trợ, chia sẻ kinh nghiệm và kết nối với cộng đồng.
### Giấy phép tạm thời có sẵn cho GroupDocs.Viewer cho .NET không?
 Có, bạn có thể nhận được một[giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/) cho GroupDocs.Viewer dành cho .NET.
### Tôi có thể tìm tài liệu chi tiết về GroupDocs.Viewer cho .NET không?
 Tuyệt đối! Tham khảo đến[tài liệu chính thức](https://tutorials.groupdocs.com/viewer/net/) để biết thông tin chuyên sâu về cách sử dụng GroupDocs.Viewer cho .NET.
### Tôi có thể tải xuống phiên bản mới nhất của GroupDocs.Viewer cho .NET ở đâu?
 Tải xuống thư viện từ[trang phát hành chính thức](https://releases.groupdocs.com/viewer/net/).