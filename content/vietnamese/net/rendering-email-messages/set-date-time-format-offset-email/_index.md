---
title: Đặt định dạng ngày giờ và chênh lệch múi giờ (Email)
linktitle: Đặt định dạng ngày giờ và chênh lệch múi giờ (Email)
second_title: API GroupDocs.Viewer .NET
description: Tích hợp GroupDocs.Viewer dành cho .NET vào các ứng dụng của bạn một cách liền mạch để có khả năng xem tài liệu mạnh mẽ. Nâng cao trải nghiệm người dùng với các tùy chọn tùy chỉnh.
weight: 11
url: /vi/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Giới thiệu
GroupDocs.Viewer dành cho .NET là một công cụ mạnh mẽ cho phép các nhà phát triển tích hợp liền mạch khả năng xem tài liệu vào các ứng dụng .NET của họ. Với GroupDocs.Viewer, bạn có thể hiển thị nhiều định dạng tài liệu bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v. trực tiếp trong ứng dụng của mình mà không cần bất kỳ plugin hoặc trình xem bên ngoài nào. Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn qua quá trình thiết lập GroupDocs.Viewer cho .NET, khám phá các tính năng của nó và trình bày cách sử dụng nó một cách hiệu quả để nâng cao khả năng xem tài liệu của ứng dụng của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo rằng bạn đã thiết lập các điều kiện tiên quyết sau:
1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. GroupDocs.Viewer dành cho .NET hoàn toàn tương thích với Visual Studio, cho phép tích hợp liền mạch vào các dự án .NET của bạn.
2.  GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/). Làm theo hướng dẫn cài đặt được cung cấp để thiết lập thư viện trong môi trường phát triển của bạn.
3. .NET Framework: Đảm bảo rằng bạn đã cài đặt phiên bản .NET Framework thích hợp. GroupDocs.Viewer for .NET hỗ trợ nhiều phiên bản khác nhau của .NET Framework, bao gồm .NET Core và .NET Standard.

## Nhập không gian tên
Để sử dụng GroupDocs.Viewer cho .NET một cách hiệu quả, bạn cần nhập các vùng tên cần thiết vào dự án của mình. Hãy làm theo các bước sau để nhập các không gian tên được yêu cầu:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Hãy chia ví dụ được cung cấp thành nhiều bước để hiểu từng thành phần và chức năng của nó.
## Bước 1: Đặt thư mục đầu ra và đường dẫn tệp
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Trong bước này, chúng tôi xác định thư mục đầu ra nơi tài liệu được hiển thị sẽ được lưu và chỉ định đường dẫn tệp cho tệp HTML đầu ra.
## Bước 2: Khởi tạo đối tượng người xem
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Ở đây, chúng ta tạo một phiên bản mới của`Viewer` class, chuyển đường dẫn của tài liệu cần xem (trong trường hợp này là tệp EML mẫu) làm tham số.
## Bước 3: Xác định tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Trong bước này, chúng tôi định cấu hình các tùy chọn chế độ xem HTML để hiển thị tài liệu, chỉ định đường dẫn tệp đầu ra cho tài liệu HTML được hiển thị.
## Bước 4: Đặt định dạng ngày giờ và độ lệch múi giờ
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Tại đây, chúng ta tùy chỉnh định dạng ngày giờ cho email và đặt offset múi giờ theo múi giờ mong muốn.
## Bước 5: Kết xuất tài liệu
```csharp
viewer.View(options);
```
 Cuối cùng, chúng tôi gọi`View` phương pháp của`Viewer` đối tượng, chuyển các tùy chọn chế độ xem HTML đã định cấu hình để hiển thị tài liệu sang định dạng HTML.
## Bước 6: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bước này chỉ hiển thị một thông báo cho biết việc hiển thị tài liệu thành công và cung cấp đường dẫn đến thư mục đầu ra nơi chứa tài liệu HTML được hiển thị.

## Phần kết luận
GroupDocs.Viewer dành cho .NET cung cấp giải pháp mạnh mẽ để tích hợp khả năng xem tài liệu vào các ứng dụng .NET của bạn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng thiết lập GroupDocs.Viewer, nhập các không gian tên cần thiết và sử dụng các tính năng của nó để hiển thị tài liệu với các tùy chọn có thể tùy chỉnh. Cho dù bạn đang làm việc với tệp PDF, tài liệu Microsoft Office hay các định dạng khác, GroupDocs.Viewer sẽ đơn giản hóa quá trình xem tài liệu, nâng cao trải nghiệm người dùng đối với các ứng dụng của bạn.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer for .NET hỗ trợ .NET Core, cho phép ứng dụng của bạn tương thích đa nền tảng.
### Tôi có thể tùy chỉnh giao diện của tài liệu được hiển thị không?
Tuyệt đối! GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh khác nhau bao gồm mức thu phóng, xoay trang, v.v. để điều chỉnh trải nghiệm xem theo sở thích của bạn.
### Có phiên bản dùng thử nào dành cho mục đích thử nghiệm không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của GroupDocs.Viewer dành cho .NET từ[Địa chỉ website](https://releases.groupdocs.com/viewer/net/) để đánh giá các tính năng của nó trước khi mua hàng.
### GroupDocs.Viewer có hỗ trợ hiển thị tài liệu được bảo vệ bằng mật khẩu không?
Có, GroupDocs.Viewer có hỗ trợ tích hợp để hiển thị tài liệu được bảo vệ bằng mật khẩu, đảm bảo xem tài liệu an toàn trong ứng dụng của bạn.
### Tôi có thể tìm sự hỗ trợ hoặc hỗ trợ bổ sung với GroupDocs.Viewer ở đâu?
 Đối với bất kỳ truy vấn hoặc hỗ trợ kỹ thuật nào, bạn có thể truy cập GroupDocs.Viewer[diễn đàn](https://forum.groupdocs.com/c/viewer/9) hoặc liên hệ với nhóm hỗ trợ của họ để được trợ giúp và hướng dẫn nhanh chóng.