---
"description": "Khám phá sự kỳ diệu của GroupDocs.Viewer cho .NET – tích hợp liền mạch chức năng xem tài liệu vào ứng dụng của bạn. Hãy dùng thử miễn phí ngay!"
"linktitle": "Nhận tên bảng tính"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Nhận tên bảng tính"
"url": "/vi/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Nhận tên bảng tính

## Giới thiệu
Chào mừng đến với thế giới hấp dẫn của GroupDocs.Viewer dành cho .NET! Nếu bạn là nhà phát triển hoặc người đam mê muốn khám phá khả năng xem tài liệu mạnh mẽ trong các ứng dụng .NET của mình, bạn sẽ được thưởng thức. Trong hướng dẫn toàn diện này, chúng ta sẽ đi sâu vào những điều phức tạp của việc lấy tên bảng tính bằng GroupDocs.Viewer. Vì vậy, hãy thắt dây an toàn và bắt đầu cuộc hành trình thú vị này!
## Điều kiện tiên quyết
Trước khi đi sâu vào phép thuật mã hóa, hãy đảm bảo bạn đã thiết lập mọi thứ:
1. Cài đặt GroupDocs.Viewer cho .NET: Truy cập [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/) để lấy phiên bản mới nhất của GroupDocs.Viewer cho .NET. Làm theo hướng dẫn cài đặt để tích hợp liền mạch vào môi trường phát triển của bạn.
2. Chuẩn bị tài liệu: Đảm bảo bạn có tài liệu mục tiêu, chẳng hạn như tệp Excel có tên "file.xlsx", trong thư mục tài liệu được chỉ định.
## Nhập không gian tên
Bây giờ bạn đã có đủ các điều kiện tiên quyết, hãy bắt đầu bằng cách nhập các không gian tên cần thiết. Điều này đảm bảo ứng dụng của bạn nhận dạng và có thể sử dụng các chức năng do GroupDocs.Viewer cung cấp cho .NET.
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
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn đến thư mục chứa tài liệu mục tiêu của bạn.
## 2. Khởi tạo Viewer
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Ở bước này, chúng ta tạo một thể hiện của lớp Viewer, cung cấp đường dẫn đến tệp Excel của bạn.
## 3. Cấu hình tùy chọn thông tin chế độ xem
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Tại đây, chúng tôi cấu hình ViewInfoOptions để tạo chế độ xem HTML và thiết lập các tùy chọn bổ sung cho việc hiển thị bảng tính.
## 4. Truy xuất thông tin chế độ xem
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Sử dụng phiên bản Viewer để truy xuất thông tin chế độ xem dựa trên các tùy chọn đã cấu hình.
## 5. Hiển thị tên trang tính
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Lặp qua các trang đã lấy và in tên của từng bảng tính vào bảng điều khiển.
## Phần kết luận
Xin chúc mừng! Bạn đã điều hướng thành công qua quá trình lấy tên bảng tính bằng GroupDocs.Viewer cho .NET. Điều này mở ra vô số khả năng để nâng cao chức năng xem tài liệu trong ứng dụng của bạn.
## Câu hỏi thường gặp
### Tôi có thể sử dụng GroupDocs.Viewer cho .NET với các định dạng tài liệu khác không?
Chắc chắn rồi! GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Microsoft Office, v.v.
### Có bản dùng thử miễn phí không?
Có, bạn có thể khám phá GroupDocs.Viewer cho .NET với [dùng thử miễn phí](https://releases.groupdocs.com/).
### Tôi có thể tìm thêm sự hỗ trợ ở đâu?
Đi đến [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để cộng đồng hỗ trợ và thảo luận.
### Tôi có thể xin giấy phép tạm thời không?
Chắc chắn rồi! Ghé thăm [liên kết này](https://purchase.groupdocs.com/temporary-license/) để có được giấy phép tạm thời của bạn.
### Có nguồn tài liệu hướng dẫn chi tiết nào không?
Chắc chắn rồi! Hãy xem [tài liệu chính thức](https://tutorials.groupdocs.com/viewer/net/) để biết thông tin chi tiết và hướng dẫn.