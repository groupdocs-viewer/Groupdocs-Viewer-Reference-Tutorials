---
"description": "Tìm hiểu cách loại trừ phông chữ khỏi HTML được hiển thị bằng GroupDocs.Viewer cho .NET. Thực hiện theo hướng dẫn từng bước này để hiển thị tài liệu liền mạch."
"linktitle": "Loại trừ phông chữ khỏi HTML được hiển thị"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Loại trừ phông chữ khỏi HTML được hiển thị"
"url": "/vi/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# Loại trừ phông chữ khỏi HTML được hiển thị

## Giới thiệu
GroupDocs.Viewer for .NET là một thư viện kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị hơn 50 định dạng tài liệu trong các ứng dụng .NET của họ mà không cần phụ thuộc bên ngoài. Trong hướng dẫn này, chúng tôi sẽ tập trung vào một tính năng cụ thể của GroupDocs.Viewer: loại trừ phông chữ khỏi đầu ra HTML được kết xuất. 
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Hiểu biết cơ bản về phát triển C# và .NET.
2. GroupDocs.Viewer cho .NET đã được cài đặt. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio hoặc bất kỳ IDE nào khác để phát triển C#.

## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo bao gồm các không gian tên cần thiết:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Thiết lập thư mục mà bạn muốn lưu các tệp HTML đã kết xuất.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Chỉ định định dạng cho đường dẫn tệp của từng trang trong tài liệu được hiển thị.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
Khởi tạo đối tượng Viewer với tài liệu bạn muốn hiển thị.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Mã của bạn ở đây
}
```
## Bước 4: Thiết lập Tùy chọn chế độ xem HTML
Xác định các tùy chọn để hiển thị HTML, bao gồm định dạng của tài nguyên nhúng và phông chữ cần loại trừ.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Bước 5: Kết xuất tài liệu
Truyền các tùy chọn chế độ xem HTML cho đối tượng Viewer để hiển thị tài liệu.
```csharp
viewer.View(options);
```
## Bước 6: Xuất Vị trí Tài liệu được Kết xuất
Thông báo cho người dùng về vị trí lưu các tệp HTML đã hiển thị.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng GroupDocs.Viewer cho .NET để loại trừ phông chữ khỏi đầu ra HTML được hiển thị. Bằng cách làm theo các bước được nêu ở trên, bạn có thể tùy chỉnh quy trình hiển thị để đáp ứng các yêu cầu cụ thể của mình, đảm bảo hiển thị tối ưu các tài liệu trong ứng dụng của bạn.
## Câu hỏi thường gặp
### Tôi có thể loại trừ nhiều phông chữ khỏi HTML được hiển thị không?
Có, bạn có thể thêm nhiều tên phông chữ vào `FontsToExclude` liệt kê trong các tùy chọn chế độ xem HTML.
### GroupDocs.Viewer có tương thích với tất cả các nền tảng .NET không?
Có, GroupDocs.Viewer hỗ trợ .NET Framework 4.6.1 trở lên.
### Tôi có thể xuất tài liệu từ các vị trí lưu trữ từ xa không?
Có, GroupDocs.Viewer hỗ trợ hiển thị tài liệu từ bộ nhớ cục bộ cũng như các vị trí lưu trữ và luồng từ xa.
### GroupDocs.Viewer có hỗ trợ thiết kế đáp ứng cho đầu ra HTML không?
Có, bạn có thể bật tính năng hiển thị phản hồi bằng cách điều chỉnh tùy chọn chế độ xem HTML cho phù hợp.
### Có hỗ trợ kỹ thuật cho GroupDocs.Viewer không?
Có, bạn có thể tìm kiếm sự hỗ trợ và tham gia thảo luận về [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).