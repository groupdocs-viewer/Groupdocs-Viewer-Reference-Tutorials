---
"description": "Dễ dàng tích hợp chế độ xem tài liệu được bảo vệ bằng mật khẩu vào các ứng dụng .NET bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để có trải nghiệm liền mạch."
"linktitle": "Tải các tài liệu được bảo vệ bằng mật khẩu"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Tải các tài liệu được bảo vệ bằng mật khẩu"
"url": "/vi/net/advanced-loading/load-password-protected-document/"
"weight": 12
type: docs
---
# Tải các tài liệu được bảo vệ bằng mật khẩu

## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc quản lý và xem nhiều định dạng tài liệu khác nhau một cách liền mạch là điều cần thiết đối với nhiều doanh nghiệp và cá nhân. May mắn thay, GroupDocs.Viewer cho .NET cung cấp giải pháp toàn diện cho các nhà phát triển .NET để dễ dàng tích hợp khả năng xem tài liệu vào ứng dụng của họ. Trong hướng dẫn này, chúng ta sẽ đi sâu vào một trong những chức năng thiết yếu của GroupDocs.Viewer: tải các tài liệu được bảo vệ bằng mật khẩu. Chúng tôi sẽ chia nhỏ quy trình từng bước, đảm bảo rằng các nhà phát triển có thể dễ dàng theo dõi và triển khai tính năng này vào các dự án của họ.

![Tải các tài liệu được bảo vệ bằng mật khẩu trong GroupDocs.Viewer cho .NET](/viewer/advanced-loading/load-password-protected-documents-img.png)

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo rằng bạn đã thiết lập các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
Hãy đảm bảo bạn đã cài đặt GroupDocs.Viewer cho .NET trong môi trường phát triển của mình. Bạn có thể tải xuống từ [trang web](https://releases.groupdocs.com/viewer/net/).
### 2. Nhận một tài liệu được bảo vệ bằng mật khẩu
Để thử nghiệm, hãy chuẩn bị sẵn một tài liệu được bảo vệ bằng mật khẩu. Điều này sẽ cho phép chúng tôi trình diễn quy trình tải hiệu quả.

## Nhập không gian tên
Trước khi thực hiện hướng dẫn, hãy nhập các không gian tên cần thiết vào dự án của chúng ta:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Đầu tiên, hãy chỉ định thư mục mà bạn muốn lưu kết quả đã kết xuất:
```csharp
string outputDirectory = "Your Document Directory";
```
Thay thế `"Your Document Directory"` với đường dẫn đến thư mục bạn mong muốn.
## Bước 2: Xác định định dạng đường dẫn tệp trang
Tiếp theo, hãy xác định định dạng cho đường dẫn tệp của mỗi trang được hiển thị:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Định dạng này sẽ tạo ra các đường dẫn tệp như `"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, và vân vân.
## Bước 3: Cấu hình Tùy chọn Tải
Cấu hình các tùy chọn tải cho tài liệu được bảo vệ bằng mật khẩu, bao gồm cả mật khẩu:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
Thay thế `"12345"` bằng mật khẩu thực tế của tài liệu của bạn.
## Bước 4: Khởi tạo Viewer
Khởi tạo GroupDocs.Viewer với các tùy chọn tài liệu và tải:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Mã cho các tùy chọn xem sẽ được thêm vào ở bước tiếp theo.
}
```
Thay thế `"Path_to_your_document"` với đường dẫn đến tài liệu được bảo vệ bằng mật khẩu của bạn.
## Bước 5: Cấu hình Tùy chọn chế độ xem HTML
Cấu hình tùy chọn chế độ xem HTML để hiển thị tài liệu có tài nguyên nhúng:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Bước 6: Kết xuất tài liệu
Hiển thị tài liệu bằng trình xem được cấu hình và các tùy chọn xem:
```csharp
viewer.View(options);
```
## Bước 7: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách tải các tài liệu được bảo vệ bằng mật khẩu bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước, các nhà phát triển có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của họ, cho phép người dùng xem các tài liệu được bảo vệ một cách dễ dàng.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể xử lý các định dạng tài liệu khác ngoài các tài liệu được bảo vệ bằng mật khẩu không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, DOCX, XLSX, PPTX, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer tương thích với cả môi trường .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh các tùy chọn hiển thị cho tài liệu không?
Hoàn toàn đúng! GroupDocs.Viewer cung cấp nhiều tùy chọn hiển thị khác nhau, cho phép các nhà phát triển tùy chỉnh trải nghiệm xem theo yêu cầu của họ.
### GroupDocs.Viewer có hỗ trợ chú thích tài liệu không?
Có, GroupDocs.Viewer hỗ trợ chú thích tài liệu, cho phép người dùng thêm bình luận, đánh dấu và các chú thích khác vào tài liệu.
### Có phiên bản dùng thử nào cho GroupDocs.Viewer không?
Có, bạn có thể nhận bản dùng thử miễn phí của GroupDocs.Viewer từ [trang web](https://releases.groupdocs.com/).