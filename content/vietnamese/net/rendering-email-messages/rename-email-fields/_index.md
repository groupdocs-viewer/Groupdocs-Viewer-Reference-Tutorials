---
title: Đổi tên các trường email trong khi hiển thị
linktitle: Đổi tên các trường email trong khi hiển thị
second_title: API GroupDocs.Viewer .NET
description: Nâng cao trải nghiệm xem tài liệu với GroupDocs.Viewer dành cho .NET. Hiển thị và tùy chỉnh email một cách liền mạch.
weight: 12
url: /vi/net/rendering-email-messages/rename-email-fields/
---
## Giới thiệu

Trong thời đại kỹ thuật số ngày nay, việc quản lý và xem tài liệu một cách hiệu quả là điều tối quan trọng đối với các doanh nghiệp cũng như cá nhân. Cho dù đó là hợp đồng, báo cáo hay email, khả năng điều hướng qua các tài liệu này một cách liền mạch có thể nâng cao năng suất đáng kể. Đây là lúc GroupDocs.Viewer dành cho .NET phát huy tác dụng. Thư viện mạnh mẽ này cho phép các nhà phát triển tích hợp khả năng xem tài liệu trực tiếp vào các ứng dụng .NET của họ, cung cấp nhiều tính năng để hiển thị các định dạng tài liệu khác nhau.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn đổi tên các trường email trong khi kết xuất bằng GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1.  GroupDocs.Viewer for .NET Library: Tải xuống và cài đặt thư viện GroupDocs.Viewer for .NET từ[đây](https://releases.groupdocs.com/viewer/net/).

2. Môi trường phát triển: Đảm bảo bạn có môi trường phát triển phù hợp được thiết lập để phát triển .NET, chẳng hạn như Visual Studio.

3. Hiểu biết cơ bản về C#: Làm quen với những điều cơ bản về ngôn ngữ lập trình C# vì hướng dẫn sẽ liên quan đến các đoạn mã C#.

4. Thư mục tài liệu: Chuẩn bị một thư mục lưu trữ các tài liệu được hiển thị.

## Nhập không gian tên

Để sử dụng các chức năng GroupDocs.Viewer trong ứng dụng .NET của bạn, bạn cần nhập các vùng tên cần thiết.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy chia nhỏ quy trình đổi tên các trường email trong khi kết xuất bằng GroupDocs.Viewer cho .NET thành nhiều bước:

## Bước 1: Xác định thư mục đầu ra

Đầu tiên, chỉ định thư mục nơi các trang HTML được hiển thị sẽ được lưu.

```csharp
string outputDirectory = "Your Document Directory";
```

## Bước 2: Xác định định dạng đường dẫn tệp trang

Xác định định dạng cho đường dẫn tệp của các trang HTML được hiển thị. Mỗi trang sẽ được lưu dưới dạng một tệp HTML riêng biệt.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Bước 3: Khởi tạo đối tượng Viewer

Tạo một phiên bản của lớp Viewer và chuyển đường dẫn của tài liệu được xem dưới dạng tham số.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Bước 4: Định cấu hình tùy chọn chế độ xem HTML

Định cấu hình các tùy chọn cho chế độ xem HTML, bao gồm chỉ định định dạng tệp đầu ra và thiết lập ánh xạ trường email.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Bước 5: Kết xuất tài liệu

Gọi phương thức View của đối tượng Viewer, chuyển các tùy chọn dạng xem HTML đã được định cấu hình.

```csharp
viewer.View(options);
```

## Bước 6: Hiển thị thông báo thành công

Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận

Tóm lại, GroupDocs.Viewer cho .NET cung cấp một giải pháp liền mạch để hiển thị tài liệu trong các ứng dụng .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng đổi tên các trường email trong khi hiển thị, nâng cao khả năng đọc và khả năng sử dụng của tài liệu email. Với API trực quan và các tính năng toàn diện, GroupDocs.Viewer trao quyền cho các nhà phát triển hợp lý hóa quy trình xem tài liệu một cách hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi: Tôi có thể hiển thị các tài liệu không phải email bằng GroupDocs.Viewer cho .NET không?

Trả lời: Có, GroupDocs.Viewer hỗ trợ hiển thị nhiều định dạng tài liệu khác nhau bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v.

### Câu hỏi: GroupDocs.Viewer có tương thích với .NET Core không?

Trả lời: Có, GroupDocs.Viewer hỗ trợ .NET Core cùng với .NET Framework truyền thống.

### Câu hỏi: Tôi có thể tùy chỉnh giao diện của tài liệu được hiển thị không?

Trả lời: Hoàn toàn có thể, GroupDocs.Viewer cung cấp các tùy chọn tùy chỉnh mở rộng để kiểm soát hình thức và hoạt động của tài liệu được hiển thị.

### Câu hỏi: GroupDocs.Viewer có hỗ trợ truyền phát tài liệu không?

Trả lời: Có, GroupDocs.Viewer cho phép truyền tài liệu trực tiếp đến trình duyệt của khách hàng mà không cần lưu trữ chúng trên máy chủ.

### Câu hỏi: GroupDocs.Viewer có phù hợp với các ứng dụng cấp doanh nghiệp không?

Trả lời: Chắc chắn, GroupDocs.Viewer được thiết kế để đáp ứng nhu cầu của các ứng dụng cấp doanh nghiệp với khả năng mở rộng, độ tin cậy và bộ tính năng mạnh mẽ.
