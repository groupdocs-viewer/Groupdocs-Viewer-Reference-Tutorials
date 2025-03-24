---
title: Kết xuất khoảng thời gian dự án cụ thể (MS Project)
linktitle: Kết xuất khoảng thời gian dự án cụ thể (MS Project)
second_title: API GroupDocs.Viewer .NET
description: Tích hợp GroupDocs.Viewer dành cho .NET vào các ứng dụng của bạn một cách liền mạch để xem tài liệu hiệu quả. Nâng cao năng suất với khả năng kết xuất linh hoạt.
weight: 12
url: /vi/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---
## Giới thiệu
Trong lĩnh vực phát triển phần mềm, việc xử lý và hiển thị hiệu quả các định dạng tài liệu khác nhau là điều tối quan trọng. Cho dù đó là để xem hay thao tác tài liệu, việc có các công cụ phù hợp có thể nâng cao đáng kể năng suất và hợp lý hóa các quy trình. GroupDocs.Viewer dành cho .NET nổi bật như một giải pháp linh hoạt, cung cấp cho các nhà phát triển khả năng tích hợp liền mạch khả năng xem tài liệu vào các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào tích hợp GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### 1. Làm quen với .NET Framework
Đảm bảo bạn có hiểu biết cơ bản về .NET framework, bao gồm ngôn ngữ lập trình C# và Visual Studio IDE.
### 2. Cài đặt GroupDocs.Viewer cho .NET
 Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/). Làm theo hướng dẫn cài đặt được cung cấp để thiết lập thư viện trong môi trường phát triển của bạn.
### 3. Giấy phép hợp lệ hoặc Giấy phép tạm thời
 Có được giấy phép hợp lệ từ[Tài liệu nhóm](https://purchase.groupdocs.com/buy) hoặc xin giấy phép tạm thời từ[đây](https://purchase.groupdocs.com/temporary-license/) để sử dụng đầy đủ chức năng của GroupDocs.Viewer cho .NET.
### 4. Tài liệu mẫu
Chuẩn bị sẵn một tài liệu mẫu, chẳng hạn như tệp MS Project, để kiểm tra chức năng kết xuất.

## Nhập không gian tên
Kết hợp các không gian tên cần thiết vào dự án của bạn để truy cập các chức năng do GroupDocs.Viewer cung cấp cho .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Hãy chia nhỏ ví dụ về hiển thị khoảng thời gian dự án cụ thể từ tệp MS Project thành nhiều bước:
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Chỉ định thư mục nơi các trang HTML được hiển thị sẽ được lưu.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Đặt định dạng cho đường dẫn tệp của từng trang HTML được hiển thị.
## Bước 3: Khởi tạo đối tượng người xem
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Tạo một phiên bản của lớp Viewer, chuyển đường dẫn đến tệp MS Project mẫu.
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Định cấu hình tùy chọn chế độ xem HTML để hiển thị, chỉ định định dạng cho tài nguyên được nhúng.
## Bước 5: Truy xuất thông tin xem quản lý dự án
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Truy xuất thông tin dạng xem quản lý dự án để xác định ngày bắt đầu và ngày kết thúc của dự án.
## Bước 6: Đặt ngày bắt đầu và ngày kết thúc
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Đặt ngày bắt đầu và ngày kết thúc cho khoảng thời gian dự án sẽ được hiển thị.
## Bước 7: Kết xuất tài liệu
```csharp
viewer.View(options);
```
Bắt đầu quá trình kết xuất với các tùy chọn được chỉ định.
## Bước 8: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc kết xuất thành công và hiển thị thư mục lưu kết quả đầu ra.

## Phần kết luận
Việc tích hợp GroupDocs.Viewer dành cho .NET vào các dự án của bạn sẽ giúp bạn xử lý hiệu quả các tác vụ xem tài liệu, nâng cao trải nghiệm và năng suất của người dùng. Bằng cách làm theo hướng dẫn từng bước được cung cấp, bạn có thể kết hợp liền mạch các chức năng kết xuất tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có tương thích với tất cả các định dạng tài liệu không?
GroupDocs.Viewer cho .NET hỗ trợ nhiều định dạng tài liệu, bao gồm Microsoft Office, PDF, CAD, v.v.
### Tôi có thể tùy chỉnh giao diện của tài liệu được hiển thị không?
Có, bạn có thể tùy chỉnh các khía cạnh khác nhau của quá trình hiển thị, chẳng hạn như bố cục trang, hình mờ và xoay trang.
### GroupDocs.Viewer cho .NET có phù hợp với các ứng dụng web không?
Hoàn toàn có thể, GroupDocs.Viewer dành cho .NET có thể được tích hợp liền mạch vào các ứng dụng web để cung cấp khả năng xem tài liệu.
### GroupDocs.Viewer cho .NET có cung cấp hỗ trợ cho nền tảng di động không?
Có, GroupDocs.Viewer for .NET hỗ trợ nền tảng di động, cho phép bạn tạo các ứng dụng có tính năng xem tài liệu phản hồi nhanh.
### Có diễn đàn cộng đồng nào để tôi có thể tìm kiếm sự trợ giúp với GroupDocs.Viewer cho .NET không?
 Có, bạn có thể ghé thăm[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để đặt câu hỏi, chia sẻ ý tưởng và tương tác với những người dùng và nhà phát triển khác.