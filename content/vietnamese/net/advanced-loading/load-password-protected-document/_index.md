---
title: Tải tài liệu được bảo vệ bằng mật khẩu
linktitle: Tải tài liệu được bảo vệ bằng mật khẩu
second_title: API GroupDocs.Viewer .NET
description: Dễ dàng tích hợp tính năng xem tài liệu được bảo vệ bằng mật khẩu vào các ứng dụng .NET bằng GroupDocs.Viewer cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có được sự liền mạch.
type: docs
weight: 12
url: /vi/net/advanced-loading/load-password-protected-document/
---
## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc quản lý và xem các định dạng tài liệu khác nhau một cách liền mạch là điều cần thiết đối với nhiều doanh nghiệp cũng như cá nhân. May mắn thay, GroupDocs.Viewer dành cho .NET cung cấp giải pháp toàn diện cho các nhà phát triển .NET để dễ dàng tích hợp khả năng xem tài liệu vào ứng dụng của họ. Trong hướng dẫn này, chúng ta sẽ đi sâu vào một trong những chức năng thiết yếu của GroupDocs.Viewer: tải tài liệu được bảo vệ bằng mật khẩu. Chúng tôi sẽ chia nhỏ quy trình này theo từng bước để đảm bảo rằng các nhà phát triển có thể dễ dàng theo dõi và triển khai tính năng này vào dự án của họ.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn đã thiết lập các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
 Đảm bảo bạn đã cài đặt GroupDocs.Viewer cho .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
### 2. Lấy tài liệu được bảo vệ bằng mật khẩu
Vì mục đích thử nghiệm, hãy chuẩn bị sẵn tài liệu được bảo vệ bằng mật khẩu. Điều này sẽ cho phép chúng tôi chứng minh quá trình tải một cách hiệu quả.

## Nhập không gian tên
Trước khi tiếp tục hướng dẫn, hãy nhập các không gian tên cần thiết vào dự án của chúng ta:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Đầu tiên, chỉ định thư mục nơi bạn muốn lưu đầu ra được hiển thị:
```csharp
string outputDirectory = "Your Document Directory";
```
 Thay thế`"Your Document Directory"` với đường dẫn của thư mục bạn muốn.
## Bước 2: Xác định định dạng đường dẫn tệp trang
Tiếp theo, xác định định dạng cho đường dẫn tệp của từng trang được hiển thị:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Định dạng này sẽ tạo ra các đường dẫn tệp như`"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, và như thế.
## Bước 3: Định cấu hình tùy chọn tải
Định cấu hình các tùy chọn tải cho tài liệu được bảo vệ bằng mật khẩu, bao gồm cả mật khẩu:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
 Thay thế`"12345"` bằng mật khẩu thực tế của tài liệu của bạn.
## Bước 4: Khởi tạo Viewer
Khởi tạo GroupDocs.Viewer với các tùy chọn tải và tài liệu:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Mã cho các tùy chọn xem sẽ được thêm vào trong bước tiếp theo.
}
```
 Thay thế`"Path_to_your_document"` với đường dẫn đến tài liệu được bảo vệ bằng mật khẩu của bạn.
## Bước 5: Định cấu hình tùy chọn chế độ xem HTML
Định cấu hình tùy chọn chế độ xem HTML để hiển thị tài liệu bằng các tài nguyên được nhúng:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Bước 6: Kết xuất tài liệu
Kết xuất tài liệu bằng cách sử dụng tùy chọn xem và xem đã định cấu hình:
```csharp
viewer.View(options);
```
## Bước 7: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách tải tài liệu được bảo vệ bằng mật khẩu bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước, các nhà phát triển có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của họ, cho phép người dùng xem các tài liệu được bảo vệ một cách dễ dàng.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể xử lý các định dạng tài liệu khác ngoài tài liệu được bảo vệ bằng mật khẩu không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, DOCX, XLSX, PPTX, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer cung cấp khả năng tương thích với cả môi trường .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh các tùy chọn hiển thị cho tài liệu không?
Tuyệt đối! GroupDocs.Viewer cung cấp nhiều tùy chọn hiển thị khác nhau, cho phép các nhà phát triển tùy chỉnh trải nghiệm xem theo yêu cầu của họ.
### GroupDocs.Viewer có hỗ trợ chú thích tài liệu không?
Có, GroupDocs.Viewer hỗ trợ chú thích tài liệu, cho phép người dùng thêm nhận xét, đánh dấu và các chú thích khác vào tài liệu.
### Có phiên bản dùng thử cho GroupDocs.Viewer không?
 Có, bạn có thể nhận bản dùng thử miễn phí GroupDocs.Viewer từ[trang mạng](https://releases.groupdocs.com/).