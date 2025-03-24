---
title: Thêm hình mờ vào tài liệu
linktitle: Thêm hình mờ vào tài liệu
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách thêm hình mờ vào tài liệu một cách liền mạch bằng GroupDocs.Viewer dành cho .NET. Tăng cường bảo mật tài liệu và xây dựng thương hiệu bằng hướng dẫn dễ thực hiện này.
weight: 10
url: /vi/net/rendering-options/add-watermark/
---

# Thêm hình mờ vào tài liệu

## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc quản lý và xem các định dạng tài liệu khác nhau một cách liền mạch là điều cần thiết đối với nhiều doanh nghiệp cũng như cá nhân. May mắn thay, với các công cụ như GroupDocs.Viewer dành cho .NET, việc xử lý tài liệu trở nên dễ dàng. Thư viện .NET mạnh mẽ này cho phép các nhà phát triển tích hợp dễ dàng chức năng xem tài liệu vào ứng dụng của họ, cho phép người dùng xem tài liệu mà không cần phần mềm gốc đã tạo ra chúng.
## Điều kiện tiên quyết
Trước khi bắt đầu sử dụng GroupDocs.Viewer dành cho .NET để thêm hình mờ vào tài liệu, hãy đảm bảo bạn có những điều sau:
1. Thiết lập môi trường: Đã thiết lập môi trường phát triển với cài đặt .NET Framework hoặc .NET Core.
2.  GroupDocs.Viewer for .NET: Tải xuống và cài đặt thư viện GroupDocs.Viewer for .NET từ[trang tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Tệp tài liệu: Chuẩn bị các tệp tài liệu bạn muốn làm việc, chẳng hạn như DOCX, PDF hoặc các tệp khác.
4. Kiến thức cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# để triển khai các ví dụ mã.

## Nhập không gian tên
Trước khi bắt đầu thêm hình mờ vào tài liệu bằng GroupDocs.Viewer dành cho .NET, hãy đảm bảo nhập các vùng tên được yêu cầu trong mã C# của bạn. Bước này cho phép bạn truy cập liền mạch các lớp và phương thức do thư viện cung cấp.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, hãy xem quy trình thêm hình mờ vào tài liệu bằng GroupDocs.Viewer cho .NET. Hãy làm theo các bước sau để tích hợp liền mạch chức năng tạo hình mờ vào ứng dụng của bạn.
## Bước 1: Đặt thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Chỉ định thư mục nơi bạn muốn lưu các tệp đầu ra sau khi áp dụng hình mờ.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Đặt định dạng cho đường dẫn tệp của các trang được hiển thị. Trong ví dụ này, các tệp HTML có số trang sẽ được tạo.
## Bước 3: Khởi tạo đối tượng người xem
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Mã tiếp tục ở bước tiếp theo...
}
```
Tạo một thể hiện của lớp Viewer, chuyển đường dẫn đến tệp tài liệu làm tham số. Trong ví dụ này, chúng tôi đang sử dụng tệp DOCX mẫu.
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Định cấu hình các tùy chọn chế độ xem HTML, bao gồm văn bản hình mờ mà bạn muốn thêm vào tài liệu.
## Bước 5: Xem tài liệu có hình mờ
```csharp
viewer.View(options);
```
Gọi phương thức View của đối tượng Viewer, chuyển các tùy chọn đã cấu hình. Điều này sẽ hiển thị tài liệu có hình mờ được chỉ định.
## Bước 6: Hiển thị đường dẫn thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc hiển thị thành công tài liệu và cho biết thư mục lưu các tệp đầu ra.

## Phần kết luận
GroupDocs.Viewer dành cho .NET cung cấp một cách thuận tiện để thêm hình mờ vào tài liệu theo chương trình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch chức năng hình mờ vào các ứng dụng .NET của mình, tăng cường bảo mật tài liệu và xây dựng thương hiệu.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh hình thức của hình mờ không?
Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của hình mờ, chẳng hạn như văn bản, phông chữ, màu sắc, kích thước và vị trí.
### GroupDocs.Viewer có hỗ trợ xem tài liệu từ các nguồn từ xa không?
Có, GroupDocs.Viewer hỗ trợ xem tài liệu từ bộ nhớ cục bộ cũng như các URL từ xa.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.groupdocs.com/).
### Tôi có thể thêm hình mờ vào nhiều trang của tài liệu không?
Hoàn toàn có thể, GroupDocs.Viewer cho phép thêm hình mờ vào từng trang riêng lẻ hoặc tất cả các trang của tài liệu.
### Làm cách nào tôi có thể nhận được hỗ trợ hoặc trợ giúp nếu tôi gặp bất kỳ vấn đề nào?
 Bạn có thể tìm kiếm sự trợ giúp và hỗ trợ từ các diễn đàn cộng đồng GroupDocs[đây](https://forum.groupdocs.com/c/viewer/9).