---
title: Hiển thị các thư mục cụ thể và lọc tin nhắn (Outlook)
linktitle: Hiển thị các thư mục cụ thể và lọc tin nhắn (Outlook)
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị các thư mục cụ thể và lọc thư trong Outlook bằng GroupDocs.Viewer dành cho .NET. Đơn giản hóa việc quản lý tài liệu trong các ứng dụng .NET.
type: docs
weight: 11
url: /vi/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---
## Giới thiệu
Trong thế giới phát triển .NET, việc quản lý và hiển thị tài liệu một cách hiệu quả là rất quan trọng. GroupDocs.Viewer dành cho .NET đơn giản hóa tác vụ này bằng cách cung cấp các chức năng mạnh mẽ để hiển thị liền mạch các định dạng tài liệu khác nhau. Trong hướng dẫn này, chúng tôi sẽ đi sâu vào cách hiển thị các thư mục cụ thể và lọc thư trong Outlook bằng GroupDocs.Viewer cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
1.  GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Bạn cần cài đặt .NET framework trên máy của mình.
3. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có ích khi làm theo hướng dẫn.

## Nhập không gian tên
Đầu tiên, hãy nhập các không gian tên cần thiết vào mã C# của chúng ta:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
 Thay thế`"Your Document Directory"` với đường dẫn thư mục nơi bạn muốn lưu tài liệu được hiển thị.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Dòng này xác định định dạng cho đường dẫn tệp của mỗi trang được hiển thị. Trong ví dụ này, nó sẽ tạo các tệp HTML có tên`page_1.html`, `page_2.html`, và như thế.
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 Ở đây, chúng ta khởi tạo một`Viewer` đối tượng có đường dẫn đến thư mục Outlook mẫu.
## Bước 4: Xác định tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 Chúng tôi tạo một thể hiện của`HtmlViewOptions` và chỉ định định dạng cho tài nguyên được nhúng. Ngoài ra, chúng tôi đặt thư mục Outlook được hiển thị dưới dạng`"Входящие"` (Mới đến).
## Bước 5: Kết xuất tài liệu
```csharp
viewer.View(options);
```
Dòng này kích hoạt quá trình kết xuất với các tùy chọn được chỉ định.
## Bước 6: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Sau khi kết xuất, thông báo này được hiển thị cho biết quá trình kết xuất đã hoàn tất thành công và hướng người dùng đến thư mục đầu ra.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách hiển thị các thư mục cụ thể và lọc thư trong Outlook bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo các bước được nêu ở trên, bạn có thể quản lý và hiển thị tài liệu một cách hiệu quả trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các tài liệu không phải là thư Outlook bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer cho .NET hỗ trợ nhiều định dạng tài liệu bao gồm PDF, DOCX, XLSX, v.v.
### GroupDocs.Viewer cho .NET có tương thích với .NET Core không?
Có, GroupDocs.Viewer cho .NET tương thích với cả .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh định dạng đầu ra kết xuất không?
Hoàn toàn có thể, GroupDocs.Viewer for .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh kết quả hiển thị bao gồm các định dạng HTML, hình ảnh và PDF.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[trang mạng](https://releases.groupdocs.com/).
### Tôi có thể tìm trợ giúp hoặc hỗ trợ cho GroupDocs.Viewer dành cho .NET ở đâu?
 Bạn có thể ghé thăm[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) cho bất kỳ sự trợ giúp hoặc thắc mắc.