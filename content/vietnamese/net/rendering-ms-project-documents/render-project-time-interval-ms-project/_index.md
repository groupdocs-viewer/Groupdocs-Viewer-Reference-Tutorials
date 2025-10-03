---
"description": "Tích hợp GroupDocs.Viewer for .NET liền mạch vào các ứng dụng của bạn để xem tài liệu hiệu quả. Nâng cao năng suất với khả năng kết xuất đa dạng."
"linktitle": "Kết xuất khoảng thời gian cụ thể của dự án (MS Project)"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất khoảng thời gian cụ thể của dự án (MS Project)"
"url": "/vi/net/rendering-ms-project-documents/render-project-time-interval-ms-project/"
"weight": 12
type: docs
---
# Kết xuất khoảng thời gian cụ thể của dự án (MS Project)

## Giới thiệu
Trong lĩnh vực phát triển phần mềm, việc xử lý và hiển thị hiệu quả các định dạng tài liệu khác nhau là tối quan trọng. Cho dù là để xem hay thao tác tài liệu, việc có đúng công cụ có thể nâng cao đáng kể năng suất và hợp lý hóa quy trình. GroupDocs.Viewer for .NET nổi bật là một giải pháp đa năng, cung cấp cho các nhà phát triển khả năng tích hợp liền mạch các chức năng xem tài liệu vào các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi bắt đầu tích hợp GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
### 1. Làm quen với .NET Framework
Đảm bảo bạn có hiểu biết cơ bản về .NET framework, bao gồm ngôn ngữ lập trình C# và Visual Studio IDE.
### 2. Cài đặt GroupDocs.Viewer cho .NET
Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/). Thực hiện theo hướng dẫn cài đặt được cung cấp để thiết lập thư viện trong môi trường phát triển của bạn.
### 3. Giấy phép hợp lệ hoặc giấy phép tạm thời
Có được giấy phép hợp lệ từ [NhómDocs](https://purchase.groupdocs.com/buy) hoặc xin giấy phép tạm thời từ [đây](https://purchase.groupdocs.com/temporary-license/) để sử dụng đầy đủ chức năng của GroupDocs.Viewer cho .NET.
### 4. Tài liệu mẫu
Chuẩn bị một tài liệu mẫu, chẳng hạn như tệp MS Project, để thử nghiệm chức năng kết xuất.

## Nhập không gian tên
Kết hợp các không gian tên cần thiết vào dự án của bạn để truy cập các chức năng do GroupDocs.Viewer cung cấp cho .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Chúng ta hãy chia nhỏ ví dụ về việc kết xuất khoảng thời gian cụ thể của một dự án từ tệp MS Project thành nhiều bước:
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Chỉ định thư mục nơi các trang HTML được hiển thị sẽ được lưu.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Đặt định dạng cho đường dẫn tệp của mỗi trang HTML được hiển thị.
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Tạo một thể hiện của lớp Viewer, truyền đường dẫn đến tệp MS Project mẫu.
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Cấu hình tùy chọn chế độ xem HTML để hiển thị, chỉ định định dạng cho các tài nguyên được nhúng.
## Bước 5: Truy xuất thông tin chế độ xem quản lý dự án
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Truy xuất thông tin dạng xem quản lý dự án để xác định ngày bắt đầu và ngày kết thúc của dự án.
## Bước 6: Đặt ngày bắt đầu và ngày kết thúc
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Đặt ngày bắt đầu và ngày kết thúc cho khoảng thời gian dự án được kết xuất.
## Bước 7: Kết xuất tài liệu
```csharp
viewer.View(options);
```
Bắt đầu quá trình kết xuất với các tùy chọn đã chỉ định.
## Bước 8: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc kết xuất thành công và hiển thị thư mục lưu kết quả đầu ra.

## Phần kết luận
Tích hợp GroupDocs.Viewer cho .NET vào các dự án của bạn giúp bạn xử lý hiệu quả các tác vụ xem tài liệu, nâng cao trải nghiệm người dùng và năng suất. Bằng cách làm theo hướng dẫn từng bước được cung cấp, bạn có thể kết hợp liền mạch các chức năng kết xuất tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer for .NET có tương thích với mọi định dạng tài liệu không?
GroupDocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm Microsoft Office, PDF, CAD, v.v.
### Tôi có thể tùy chỉnh giao diện của tài liệu đã kết xuất không?
Có, bạn có thể tùy chỉnh nhiều khía cạnh khác nhau của quy trình kết xuất, chẳng hạn như bố cục trang, thêm hình mờ và xoay trang.
### GroupDocs.Viewer cho .NET có phù hợp với ứng dụng web không?
Hoàn toàn có thể, GroupDocs.Viewer cho .NET có thể được tích hợp liền mạch vào các ứng dụng web để cung cấp khả năng xem tài liệu.
### GroupDocs.Viewer for .NET có hỗ trợ nền tảng di động không?
Có, GroupDocs.Viewer for .NET hỗ trợ nền tảng di động, cho phép bạn tạo ứng dụng có tính năng xem tài liệu phản hồi.
### Có diễn đàn cộng đồng nào mà tôi có thể tìm kiếm sự trợ giúp về GroupDocs.Viewer cho .NET không?
Vâng, bạn có thể ghé thăm [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để đặt câu hỏi, chia sẻ ý tưởng và tương tác với những người dùng và nhà phát triển khác.