---
title: Hiển thị kho lưu trữ thành một hoặc nhiều trang HTML
linktitle: Hiển thị kho lưu trữ thành một hoặc nhiều trang HTML
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị các bản lưu trữ thành các trang HTML bằng GroupDocs.Viewer dành cho .NET. Dễ dàng tích hợp khả năng xem tài liệu vào các ứng dụng .NET của bạn.
type: docs
weight: 12
url: /vi/net/rendering-archive-files/render-archives-html/
---
## Giới thiệu
GroupDocs.Viewer dành cho .NET là thư viện kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển tích hợp dễ dàng khả năng xem tài liệu vào các ứng dụng .NET của họ. Cho dù bạn cần hiển thị các kho lưu trữ thành một hay nhiều trang HTML, hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình từng bước.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  GroupDocs.Viewer dành cho .NET: Đảm bảo bạn đã cài đặt thư viện trong dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Có môi trường phát triển làm việc được thiết lập để phát triển .NET.
3. Thư mục tài liệu: Chuẩn bị một thư mục nơi tài liệu của bạn được lưu trữ.
4. Hiểu biết cơ bản về C#: Làm quen với những điều cơ bản về ngôn ngữ lập trình C#.

## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Hãy làm theo các bước sau để hiển thị các bản lưu trữ thành một hoặc nhiều trang HTML bằng GroupDocs.Viewer dành cho .NET:
## Bước 1: Đặt thư mục đầu ra
Xác định thư mục nơi bạn muốn lưu các trang HTML được hiển thị:
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp
Chỉ định định dạng đường dẫn tệp cho các trang HTML. Để hiển thị một trang:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Để hiển thị nhiều trang:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Bước 3: Kết xuất thành HTML một trang
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Bước 4: Kết xuất thành nhiều trang HTML
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
Hiển thị các kho lưu trữ sang các trang HTML bằng GroupDocs.Viewer dành cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch khả năng xem tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các định dạng tài liệu khác ngoài kho lưu trữ không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, DOCX, XLSX, PPTX, v.v.
### GroupDocs.Viewer có phù hợp cho cả ứng dụng máy tính để bàn và web không?
Hoàn toàn có thể, GroupDocs.Viewer có thể được sử dụng liền mạch trong cả ứng dụng máy tính để bàn và web.
### GroupDocs.Viewer có cung cấp các tùy chọn tùy chỉnh cho giao diện trình xem không?
Có, bạn có thể tùy chỉnh giao diện xem theo yêu cầu của mình.
### Tôi có thể hiển thị tài liệu không đồng bộ với GroupDocs.Viewer không?
Có, GroupDocs.Viewer cung cấp khả năng hiển thị không đồng bộ để cải thiện hiệu suất.
### GroupDocs.Viewer có hỗ trợ chú thích tài liệu không?
Có, GroupDocs.Viewer cho phép người dùng xem và quản lý các chú thích tài liệu một cách hiệu quả.