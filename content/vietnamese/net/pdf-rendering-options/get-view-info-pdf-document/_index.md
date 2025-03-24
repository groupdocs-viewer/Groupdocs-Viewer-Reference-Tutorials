---
title: Nhận thông tin xem cho tài liệu PDF
linktitle: Nhận thông tin xem cho tài liệu PDF
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách trích xuất thông tin xem từ tài liệu PDF bằng GroupDocs.Viewer dành cho .NET trong hướng dẫn toàn diện này.
weight: 16
url: /vi/net/pdf-rendering-options/get-view-info-pdf-document/
---

# Nhận thông tin xem cho tài liệu PDF

## Giới thiệu
GroupDocs.Viewer cho .NET là một công cụ mạnh mẽ được thiết kế để hợp lý hóa việc xem tài liệu trong các ứng dụng .NET. Cho dù bạn đang xử lý tệp PDF, tài liệu Word, bảng tính Excel hay bản trình bày PowerPoint, thư viện này sẽ đơn giản hóa quá trình hiển thị và tương tác với các định dạng tệp khác nhau. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc khai thác các khả năng của GroupDocs.Viewer đặc biệt để trích xuất thông tin chế độ xem từ tài liệu PDF.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Cài đặt GroupDocs.Viewer cho .NET: Đảm bảo bạn đã tải xuống và cài đặt thư viện GroupDocs.Viewer. Bạn có thể lấy nó từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).   
2. Kiến thức cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# để hiểu và triển khai các ví dụ mã được cung cấp.
3. Truy cập vào Tài liệu PDF: Chuẩn bị sẵn tài liệu PDF mà bạn sẽ sử dụng để trích xuất thông tin xem.

## Nhập không gian tên
Trong dự án C# của bạn, hãy nhập các vùng tên cần thiết để sử dụng các chức năng của GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Bây giờ, hãy chia nhỏ quy trình truy xuất thông tin chế độ xem từ tài liệu PDF bằng GroupDocs.Viewer cho .NET.
## Bước 1: Khởi tạo đối tượng Viewer
Tạo đối tượng Viewer và cung cấp đường dẫn đến tài liệu PDF làm tham số.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Bước 2: Xác định ViewInfoOptions
Chỉ định các tùy chọn chế độ xem, chẳng hạn như chế độ xem HTML, để truy xuất thông tin chế độ xem.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Bước 3: Nhận thông tin xem
Gọi phương thức GetViewInfo để trích xuất thông tin xem từ tài liệu PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Bước 4: Xuất thông tin xem
Hiển thị thông tin chế độ xem được trích xuất, chẳng hạn như loại tài liệu, số trang và quyền in.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng GroupDocs.Viewer dành cho .NET để trích xuất thông tin chế độ xem từ tài liệu PDF. Bằng cách làm theo các bước được cung cấp, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của mình, nâng cao khả năng xem và quản lý tài liệu.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với các định dạng tệp khác ngoài PDF không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm Word, Excel, PowerPoint, v.v.
### Tôi có thể tùy chỉnh các tùy chọn xem theo yêu cầu của ứng dụng của mình không?
Hoàn toàn có thể, GroupDocs.Viewer cung cấp nhiều tùy chọn khác nhau để điều chỉnh trải nghiệm xem dựa trên nhu cầu cụ thể của bạn.
### GroupDocs.Viewer có phù hợp cho cả ứng dụng máy tính để bàn và web không?
Có, GroupDocs.Viewer rất linh hoạt và có thể được tích hợp liền mạch vào cả ứng dụng .NET trên máy tính để bàn và trên web.
### GroupDocs.Viewer có hỗ trợ và trợ giúp nếu tôi gặp bất kỳ vấn đề nào trong quá trình triển khai không?
Chắc chắn, bạn có thể tìm kiếm sự trợ giúp từ diễn đàn cộng đồng GroupDocs.Viewer hoặc truy cập các dịch vụ hỗ trợ chuyên nghiệp để giải quyết kịp thời mọi vấn đề.
### Tôi có thể dùng thử GroupDocs.Viewer trước khi mua hàng không?
 Có, bạn có thể khám phá các tính năng của GroupDocs.Viewer bằng cách truy cập phiên bản dùng thử miễn phí có sẵn trên[trang mạng](https://purchase.groupdocs.com/buy).