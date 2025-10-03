---
"description": "Tìm hiểu cách hiển thị kho lưu trữ thành các trang HTML bằng GroupDocs.Viewer cho .NET. Tích hợp dễ dàng các khả năng xem tài liệu vào các ứng dụng .NET của bạn."
"linktitle": "Hiển thị Lưu trữ thành Một hoặc Nhiều Trang HTML"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị Lưu trữ thành Một hoặc Nhiều Trang HTML"
"url": "/vi/net/rendering-archive-files/render-archives-html/"
"weight": 12
type: docs
---
# Hiển thị Lưu trữ thành Một hoặc Nhiều Trang HTML

## Giới thiệu
GroupDocs.Viewer for .NET là một thư viện kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển dễ dàng tích hợp khả năng xem tài liệu vào các ứng dụng .NET của họ. Cho dù bạn cần kết xuất kho lưu trữ thành một hoặc nhiều trang HTML, hướng dẫn này sẽ hướng dẫn bạn từng bước trong quy trình.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo bạn đáp ứng các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt thư viện trong dự án của mình. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển phù hợp cho việc phát triển .NET.
3. Thư mục tài liệu: Chuẩn bị một thư mục để lưu trữ tài liệu của bạn.
4. Hiểu biết cơ bản về C#: Làm quen với những kiến thức cơ bản về ngôn ngữ lập trình C#.

## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Thực hiện theo các bước sau để hiển thị kho lưu trữ thành một hoặc nhiều trang HTML bằng GroupDocs.Viewer cho .NET:
## Bước 1: Thiết lập thư mục đầu ra
Xác định thư mục mà bạn muốn lưu các trang HTML đã kết xuất:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp
Chỉ định định dạng đường dẫn tệp cho các trang HTML. Đối với kết xuất trang đơn:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Đối với kết xuất nhiều trang:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Bước 3: Hiển thị thành HTML trang đơn
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Bước 4: Hiển thị thành nhiều trang HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Đặt mục trên mỗi trang
    viewer.View(options);
}
```
## Bước 5: Kiểm tra đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Việc kết xuất các kho lưu trữ thành các trang HTML bằng GroupDocs.Viewer cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch các khả năng xem tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể xuất các định dạng tài liệu khác ngoài định dạng lưu trữ không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, DOCX, XLSX, PPTX, v.v.
### GroupDocs.Viewer có phù hợp cho cả ứng dụng trên máy tính để bàn và web không?
Hoàn toàn có thể, GroupDocs.Viewer có thể được sử dụng trên cả ứng dụng máy tính để bàn và web một cách liền mạch.
### GroupDocs.Viewer có cung cấp tùy chọn tùy chỉnh cho giao diện trình xem không?
Có, bạn có thể tùy chỉnh giao diện trình xem theo yêu cầu của mình.
### Tôi có thể hiển thị tài liệu không đồng bộ bằng GroupDocs.Viewer không?
Có, GroupDocs.Viewer cung cấp khả năng hiển thị không đồng bộ để cải thiện hiệu suất.
### GroupDocs.Viewer có hỗ trợ chú thích tài liệu không?
Có, GroupDocs.Viewer cho phép người dùng xem và quản lý chú thích tài liệu một cách hiệu quả.