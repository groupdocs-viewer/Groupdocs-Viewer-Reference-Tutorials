---
title: Chỉ định loại tệp khi tải tài liệu
linktitle: Chỉ định loại tệp khi tải tài liệu
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách chỉ định loại tệp khi tải tài liệu bằng GroupDocs.Viewer cho .NET. Hiển thị chính xác các định dạng khác nhau trong ứng dụng .NET của bạn.
weight: 10
url: /vi/net/advanced-loading/specify-file-type/
---

# Chỉ định loại tệp khi tải tài liệu

## Giới thiệu
GroupDocs.Viewer cho .NET là API kết xuất tài liệu linh hoạt hỗ trợ nhiều định dạng tệp, bao gồm DOCX, PDF, PPTX, v.v. Bằng cách chỉ định loại tệp khi tải tài liệu, bạn có thể đảm bảo hiển thị chính xác và trải nghiệm xem mượt mà cho người dùng của mình.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về C# và .NET framework.
- Visual Studio được cài đặt trên hệ thống của bạn.
- GroupDocs.Viewer cho .NET được cài đặt trong dự án của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
##
## Nhập không gian tên
Trước tiên, bạn cần nhập các vùng tên cần thiết vào mã C# của mình. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để hiển thị tài liệu.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục đầu ra
Xác định thư mục nơi bạn muốn lưu các trang tài liệu được hiển thị.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Chỉ định định dạng đặt tên tệp HTML đầu ra cho mỗi trang của tài liệu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Chỉ định tùy chọn tải
 Tạo một thể hiện của`LoadOptions` class và đặt loại tệp mong muốn.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Bước 4: Tải tài liệu và kết xuất
 Sử dụng`Viewer` class để tải tài liệu và hiển thị nó sang định dạng HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 5: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công và chỉ định vị trí của tệp đầu ra.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng GroupDocs.Viewer cho .NET để chỉ định loại tệp khi tải tài liệu. Bằng cách làm theo các bước đơn giản này, bạn có thể đảm bảo hiển thị chính xác các định dạng tài liệu khác nhau trong ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các tài liệu không phải DOCX bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tệp, bao gồm PDF, PPTX, XLSX, v.v.
### GroupDocs.Viewer cho .NET có tương thích với .NET Core không?
Có, GroupDocs.Viewer cho .NET tương thích với cả .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh các tệp HTML đầu ra do GroupDocs.Viewer tạo ra không?
Có, bạn có thể tùy chỉnh đầu ra HTML bằng nhiều tùy chọn khác nhau do API cung cấp.
### GroupDocs.Viewer dành cho .NET có yêu cầu bất kỳ sự phụ thuộc bên ngoài nào không?
Không, GroupDocs.Viewer dành cho .NET là một thư viện độc lập và không yêu cầu bất kỳ sự phụ thuộc bên ngoài nào.
### Có phiên bản dùng thử cho GroupDocs.Viewer cho .NET không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.groupdocs.com/viewer/net/).