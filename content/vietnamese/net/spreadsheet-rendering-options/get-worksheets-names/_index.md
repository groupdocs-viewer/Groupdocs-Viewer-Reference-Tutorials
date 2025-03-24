---
title: Nhận tên bảng tính
linktitle: Nhận tên bảng tính
second_title: API GroupDocs.Viewer .NET
description: Khám phá sự kỳ diệu của GroupDocs.Viewer dành cho .NET – tích hợp liền mạch việc xem tài liệu vào ứng dụng của bạn. Hãy thử dùng thử miễn phí ngay bây giờ!
weight: 11
url: /vi/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Giới thiệu
Chào mừng bạn đến với thế giới hấp dẫn của GroupDocs.Viewer dành cho .NET! Nếu bạn là nhà phát triển hoặc người đam mê khám phá các khả năng xem tài liệu mạnh mẽ trong các ứng dụng .NET của mình thì bạn sẽ rất thích thú. Trong hướng dẫn toàn diện này, chúng ta sẽ đi sâu vào sự phức tạp của việc truy xuất tên bảng tính bằng GroupDocs.Viewer. Vì vậy, hãy thắt dây an toàn và bắt tay vào cuộc hành trình thú vị này!
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào phép thuật mã hóa, hãy đảm bảo bạn đã thiết lập mọi thứ:
1.  Cài đặt GroupDocs.Viewer cho .NET: Đi tới[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/)để lấy phiên bản mới nhất của GroupDocs.Viewer cho .NET. Làm theo hướng dẫn cài đặt để tích hợp nó liền mạch vào môi trường phát triển của bạn.
2. Chuẩn bị sẵn tài liệu của bạn: Đảm bảo bạn có tài liệu đích, giả sử tệp Excel có tên "file.xlsx" trong thư mục tài liệu được chỉ định của bạn.
## Nhập không gian tên
Bây giờ bạn đã có sẵn các điều kiện tiên quyết, hãy bắt đầu mọi thứ bằng cách nhập các không gian tên cần thiết. Điều này đảm bảo ứng dụng của bạn nhận dạng và có thể sử dụng các chức năng do GroupDocs.Viewer cung cấp cho .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Thiết lập thư mục tài liệu
```csharp
string outputDirectory = "Your Document Directory";
```
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn đến thư mục chứa tài liệu đích của bạn.
## 2. Khởi tạo Viewer
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Trong bước này, chúng tôi tạo một phiên bản của lớp Viewer, cung cấp đường dẫn đến tệp Excel của bạn.
## 3. Định cấu hình tùy chọn xem thông tin
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Tại đây, chúng tôi định cấu hình ViewInfoOptions để tạo chế độ xem HTML và đặt các tùy chọn bổ sung để hiển thị bảng tính.
## 4. Truy xuất thông tin xem
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Sử dụng phiên bản Trình xem để truy xuất thông tin chế độ xem dựa trên các tùy chọn đã định cấu hình.
## 5. Hiển thị tên bảng tính
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Lặp lại các trang được truy xuất và in tên của từng trang tính ra bảng điều khiển.
## Phần kết luận
Chúc mừng! Bạn đã điều hướng thành công qua quá trình tìm nạp tên trang tính bằng GroupDocs.Viewer cho .NET. Điều này mở ra vô số khả năng để nâng cao chức năng xem tài liệu trong ứng dụng của bạn.
## Câu hỏi thường gặp
### Tôi có thể sử dụng GroupDocs.Viewer cho .NET với các định dạng tài liệu khác không?
Tuyệt đối! GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Microsoft Office, v.v.
### Có bản dùng thử miễn phí không?
 Có, bạn có thể khám phá GroupDocs.Viewer dành cho .NET bằng[dùng thử miễn phí](https://releases.groupdocs.com/).
### Tôi có thể tìm thêm hỗ trợ ở đâu?
 Đi đến[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để được cộng đồng hỗ trợ và thảo luận.
### Tôi có thể xin được giấy phép tạm thời không?
 Chắc chắn! Thăm nom[liên kết này](https://purchase.groupdocs.com/temporary-license/) để có được giấy phép tạm thời của bạn.
### Có sẵn nguồn tài liệu chi tiết không?
 Tuyệt đối! Kiểm tra[tài liệu chính thức](https://tutorials.groupdocs.com/viewer/net/) để biết thông tin và hướng dẫn chuyên sâu.