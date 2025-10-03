---
"description": "Tìm hiểu cách chỉ định loại tệp khi tải tài liệu bằng GroupDocs.Viewer cho .NET. Hiển thị chính xác nhiều định dạng khác nhau trong ứng dụng .NET của bạn."
"linktitle": "Chỉ định loại tệp khi tải tài liệu"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Chỉ định loại tệp khi tải tài liệu"
"url": "/vi/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Chỉ định loại tệp khi tải tài liệu

## Giới thiệu
GroupDocs.Viewer for .NET là API kết xuất tài liệu đa năng hỗ trợ nhiều định dạng tệp, bao gồm DOCX, PDF, PPTX, v.v. Bằng cách chỉ định loại tệp khi tải tài liệu, bạn có thể đảm bảo kết xuất chính xác và trải nghiệm xem mượt mà cho người dùng của mình.

![Chỉ định loại tệp khi tải tài liệu trong GroupDocs.Viewer cho .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
- Kiến thức cơ bản về C# và .NET framework.
- Visual Studio được cài đặt trên hệ thống của bạn.
- GroupDocs.Viewer cho .NET được cài đặt trong dự án của bạn. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
##
## Nhập không gian tên
Đầu tiên, bạn cần nhập các không gian tên cần thiết vào mã C# của mình. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để hiển thị tài liệu.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục đầu ra
Xác định thư mục mà bạn muốn lưu các trang tài liệu đã kết xuất.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Chỉ định định dạng để đặt tên cho tệp HTML đầu ra cho mỗi trang của tài liệu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Chỉ định Tùy chọn Tải
Tạo một phiên bản của `LoadOptions` lớp và thiết lập loại tệp mong muốn.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Bước 4: Tải tài liệu và kết xuất
Sử dụng `Viewer` lớp để tải tài liệu và hiển thị nó thành định dạng HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 5: Hiển thị thông báo thành công
Thông báo cho người dùng rằng tài liệu đã được hiển thị thành công và chỉ định vị trí của các tệp đầu ra.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng GroupDocs.Viewer cho .NET để chỉ định loại tệp khi tải tài liệu. Bằng cách làm theo các bước đơn giản này, bạn có thể đảm bảo hiển thị chính xác các định dạng tài liệu khác nhau trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các tài liệu khác ngoài DOCX bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tệp, bao gồm PDF, PPTX, XLSX, v.v.
### GroupDocs.Viewer cho .NET có tương thích với .NET Core không?
Có, GroupDocs.Viewer cho .NET tương thích với cả .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh các tệp HTML đầu ra được tạo bởi GroupDocs.Viewer không?
Có, bạn có thể tùy chỉnh đầu ra HTML bằng nhiều tùy chọn khác nhau do API cung cấp.
### GroupDocs.Viewer cho .NET có yêu cầu bất kỳ sự phụ thuộc bên ngoài nào không?
Không, GroupDocs.Viewer cho .NET là một thư viện độc lập và không yêu cầu bất kỳ sự phụ thuộc bên ngoài nào.
### Có phiên bản dùng thử của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [đây](https://releases.groupdocs.com/viewer/net/).