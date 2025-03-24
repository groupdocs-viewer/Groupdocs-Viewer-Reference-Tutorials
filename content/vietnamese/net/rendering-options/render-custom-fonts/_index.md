---
title: Kết xuất với phông chữ tùy chỉnh
linktitle: Kết xuất với phông chữ tùy chỉnh
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị tài liệu bằng phông chữ tùy chỉnh bằng GroupDocs.Viewer cho .NET. Tăng cường trình bày trực quan một cách dễ dàng.
weight: 18
url: /vi/net/rendering-options/render-custom-fonts/
---
## Giới thiệu
Trong lĩnh vực phát triển .NET, GroupDocs.Viewer cung cấp một giải pháp mạnh mẽ để hiển thị các tài liệu ở nhiều định dạng khác nhau. Trong số nhiều khả năng của nó, GroupDocs.Viewer cho phép hiển thị tài liệu với phông chữ tùy chỉnh, thêm một lớp cá nhân hóa và tính linh hoạt cho ứng dụng của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào kết xuất tài liệu với phông chữ tùy chỉnh bằng GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
Để sử dụng GroupDocs.Viewer cho .NET, bạn cần cài đặt nó trong môi trường phát triển của mình. Bạn có thể tải xuống gói cần thiết từ liên kết được cung cấp:
[Tải xuống GroupDocs.Viewer cho .NET](https://releases.groupdocs.com/viewer/net/)
### 2. Lấy phông chữ
Chuẩn bị phông chữ tùy chỉnh mà bạn muốn sử dụng để hiển thị tài liệu. Đảm bảo các phông chữ này có thể truy cập được trong môi trường ứng dụng của bạn.
### 3. Thiết lập môi trường phát triển
Cài đặt môi trường phát triển .NET đang hoạt động trên hệ thống của bạn. Đảm bảo bạn đã cài đặt các công cụ và khung cần thiết.
### 4. Hiểu biết cơ bản về C# và .NET
Làm quen với ngôn ngữ lập trình C# và kiến thức cơ bản về .NET framework để làm theo hướng dẫn một cách hiệu quả.

## Nhập không gian tên
Để hiển thị tài liệu có phông chữ tùy chỉnh bằng GroupDocs.Viewer cho .NET, bạn cần nhập các vùng tên cần thiết vào dự án của mình.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;
```

## Bước 1: Thiết lập nguồn phông chữ
Đầu tiên, xác định nguồn phông chữ sẽ được sử dụng để hiển thị tài liệu. Bước này đảm bảo rằng GroupDocs.Viewer có thể truy cập các phông chữ tùy chỉnh.
```csharp
FontSettings.SetFontSources(
    new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));
```
## Bước 2: Xác định thư mục đầu ra
Chỉ định thư mục nơi bạn muốn lưu tài liệu được hiển thị.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 3: Xác định định dạng đường dẫn tệp trang
Đặt định dạng để đặt tên cho tệp HTML đầu ra chứa các trang tài liệu được hiển thị.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 4: Kết xuất tài liệu với phông chữ tùy chỉnh
 Sử dụng API GroupDocs.Viewer để hiển thị tài liệu với phông chữ tùy chỉnh. Thay thế`TestFiles.MISSING_FONT_ODG` với đường dẫn đến tài liệu của bạn.
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 5: Hiển thị thư mục đầu ra
Thông báo cho người dùng về vị trí lưu các trang tài liệu được hiển thị.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách hiển thị tài liệu với phông chữ tùy chỉnh bằng GroupDocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước và tận dụng ví dụ được cung cấp, bạn có thể nâng cao khả năng trình bày tài liệu trực quan trong ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể kết xuất tài liệu với phông chữ tùy chỉnh bằng GroupDocs.Viewer cho .NET trong các ứng dụng web không?
Có, GroupDocs.Viewer dành cho .NET có thể được tích hợp vào cả ứng dụng máy tính để bàn và web để hiển thị tài liệu với phông chữ tùy chỉnh.
### Câu hỏi: GroupDocs.Viewer dành cho .NET có tương thích với nhiều định dạng tài liệu khác nhau không?
Tuyệt đối! GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, tệp Microsoft Office, hình ảnh, v.v.
### Câu hỏi: Có bất kỳ hạn chế nào về loại phông chữ tùy chỉnh có thể được sử dụng không?
Miễn là các phông chữ tùy chỉnh có thể truy cập được trong môi trường ứng dụng, GroupDocs.Viewer dành cho .NET có thể hiển thị các tài liệu có các phông chữ đó mà không có bất kỳ hạn chế nào.
### Câu hỏi: Tôi có thể tùy chỉnh định dạng đầu ra của tài liệu được kết xuất không?
Có, GroupDocs.Viewer for .NET cung cấp các tùy chọn để tùy chỉnh định dạng đầu ra, bao gồm HTML, định dạng hình ảnh và PDF.
### Câu hỏi: GroupDocs.Viewer dành cho .NET có cung cấp hỗ trợ và tài liệu cho nhà phát triển không?
Chắc chắn! GroupDocs cung cấp tài liệu, diễn đàn hỗ trợ và tài nguyên toàn diện để hỗ trợ các nhà phát triển sử dụng GroupDocs.Viewer một cách hiệu quả.