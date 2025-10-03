---
"description": "Tích hợp GroupDocs.Viewer for .NET một cách liền mạch vào các ứng dụng của bạn để có khả năng xem tài liệu mạnh mẽ. Nâng cao trải nghiệm người dùng với các tùy chọn có thể tùy chỉnh."
"linktitle": "Đặt Định dạng Ngày giờ và Độ lệch múi giờ (Email)"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Đặt Định dạng Ngày giờ và Độ lệch múi giờ (Email)"
"url": "/vi/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# Đặt Định dạng Ngày giờ và Độ lệch múi giờ (Email)


## Giới thiệu
GroupDocs.Viewer for .NET là một công cụ mạnh mẽ cho phép các nhà phát triển tích hợp liền mạch các khả năng xem tài liệu vào các ứng dụng .NET của họ. Với GroupDocs.Viewer, bạn có thể hiển thị nhiều định dạng tài liệu bao gồm PDF, tài liệu Microsoft Office, hình ảnh và nhiều định dạng khác trực tiếp trong ứng dụng của mình mà không cần bất kỳ plugin hoặc trình xem bên ngoài nào. Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập GroupDocs.Viewer for .NET, khám phá các tính năng của nó và trình bày cách sử dụng nó hiệu quả để nâng cao khả năng xem tài liệu của ứng dụng.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo rằng bạn đã thiết lập các điều kiện tiên quyết sau:
1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. GroupDocs.Viewer for .NET hoàn toàn tương thích với Visual Studio, cho phép tích hợp liền mạch vào các dự án .NET của bạn.
2. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/). Thực hiện theo hướng dẫn cài đặt được cung cấp để thiết lập thư viện trong môi trường phát triển của bạn.
3. .NET Framework: Đảm bảo rằng bạn đã cài đặt phiên bản .NET Framework phù hợp. GroupDocs.Viewer cho .NET hỗ trợ nhiều phiên bản .NET Framework, bao gồm .NET Core và .NET Standard.

## Nhập không gian tên
Để sử dụng GroupDocs.Viewer cho .NET hiệu quả, bạn cần nhập các không gian tên cần thiết vào dự án của mình. Thực hiện theo các bước sau để nhập các không gian tên cần thiết:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hiểu từng thành phần và chức năng của nó.
## Bước 1: Thiết lập thư mục đầu ra và đường dẫn tệp
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Ở bước này, chúng tôi xác định thư mục đầu ra nơi tài liệu được kết xuất sẽ được lưu và chỉ định đường dẫn tệp cho tệp HTML đầu ra.
## Bước 2: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Ở đây, chúng ta tạo một phiên bản mới của `Viewer` lớp, truyền đường dẫn đến tài liệu cần xem (trong trường hợp này là tệp EML mẫu) làm tham số.
## Bước 3: Xác định tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Ở bước này, chúng ta sẽ cấu hình các tùy chọn chế độ xem HTML để hiển thị tài liệu, chỉ định đường dẫn tệp đầu ra cho tài liệu HTML được hiển thị.
## Bước 4: Thiết lập Định dạng Ngày giờ và Độ lệch múi giờ
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Tại đây, chúng tôi tùy chỉnh định dạng ngày và giờ cho tin nhắn email và đặt độ lệch múi giờ theo múi giờ mong muốn.
## Bước 5: Kết xuất tài liệu
```csharp
viewer.View(options);
```
Cuối cùng, chúng tôi gọi `View` phương pháp của `Viewer` đối tượng, truyền các tùy chọn chế độ xem HTML đã cấu hình để hiển thị tài liệu sang định dạng HTML.
## Bước 6: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Bước này chỉ hiển thị thông báo cho biết tài liệu đã được hiển thị thành công và cung cấp đường dẫn đến thư mục đầu ra nơi lưu trữ tài liệu HTML đã hiển thị.

## Phần kết luận
GroupDocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để tích hợp khả năng xem tài liệu vào các ứng dụng .NET của bạn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng thiết lập GroupDocs.Viewer, nhập các không gian tên cần thiết và sử dụng các tính năng của nó để hiển thị tài liệu với các tùy chọn có thể tùy chỉnh. Cho dù bạn đang làm việc với PDF, tài liệu Microsoft Office hay các định dạng khác, GroupDocs.Viewer đều đơn giản hóa quy trình xem tài liệu, nâng cao trải nghiệm người dùng của các ứng dụng của bạn.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer cho .NET hỗ trợ .NET Core, cho phép ứng dụng của bạn tương thích đa nền tảng.
### Tôi có thể tùy chỉnh giao diện của tài liệu được kết xuất không?
Chắc chắn rồi! GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh bao gồm mức thu phóng, xoay trang và nhiều tùy chọn khác để tùy chỉnh trải nghiệm xem theo hướng dẫn của bạn.
### Có phiên bản dùng thử nào để thử nghiệm không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của GroupDocs.Viewer cho .NET từ [liên kết trang web](https://releases.groupdocs.com/viewer/net/) để đánh giá các tính năng của sản phẩm trước khi mua hàng.
### GroupDocs.Viewer có hỗ trợ hiển thị tài liệu được bảo vệ bằng mật khẩu không?
Có, GroupDocs.Viewer có hỗ trợ tích hợp để hiển thị các tài liệu được bảo vệ bằng mật khẩu, đảm bảo xem tài liệu an toàn trong ứng dụng của bạn.
### Tôi có thể tìm thêm hỗ trợ hoặc trợ giúp về GroupDocs.Viewer ở đâu?
Đối với bất kỳ thắc mắc hoặc hỗ trợ kỹ thuật nào, bạn có thể truy cập GroupDocs.Viewer [diễn đàn](https://forum.groupdocs.com/c/viewer/9) hoặc liên hệ với nhóm hỗ trợ của họ để được trợ giúp và hướng dẫn kịp thời.