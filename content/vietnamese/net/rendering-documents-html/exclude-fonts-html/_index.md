---
title: Loại trừ phông chữ khỏi HTML được hiển thị
linktitle: Loại trừ phông chữ khỏi HTML được hiển thị
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách loại trừ phông chữ khỏi HTML được hiển thị bằng GroupDocs.Viewer cho .NET. Hãy làm theo hướng dẫn từng bước này để hiển thị tài liệu liền mạch.
weight: 10
url: /vi/net/rendering-documents-html/exclude-fonts-html/
---
## Giới thiệu
GroupDocs.Viewer for .NET là thư viện kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị hơn 50 định dạng tài liệu trong ứng dụng .NET của họ mà không cần phụ thuộc bên ngoài. Trong hướng dẫn này, chúng tôi sẽ tập trung vào một tính năng cụ thể của GroupDocs.Viewer: loại trừ phông chữ khỏi đầu ra HTML được hiển thị. 
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Hiểu biết cơ bản về phát triển C# và .NET.
2.  Đã cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio hoặc bất kỳ IDE nào khác để phát triển C#.

## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo bao gồm các không gian tên cần thiết:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Thiết lập thư mục nơi bạn muốn lưu các tệp HTML được hiển thị.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Chỉ định định dạng cho đường dẫn tệp của các trang riêng lẻ của tài liệu được hiển thị.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
Khởi tạo đối tượng Viewer bằng tài liệu bạn muốn hiển thị.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Mã của bạn ở đây
}
```
## Bước 4: Đặt tùy chọn chế độ xem HTML
Xác định các tùy chọn để hiển thị HTML, bao gồm định dạng của tài nguyên được nhúng và phông chữ cần loại trừ.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Bước 5: Kết xuất tài liệu
Chuyển các tùy chọn chế độ xem HTML cho đối tượng Viewer để hiển thị tài liệu.
```csharp
viewer.View(options);
```
## Bước 6: Xuất ra vị trí tài liệu được hiển thị
Thông báo cho người dùng về vị trí lưu tệp HTML được hiển thị.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng GroupDocs.Viewer dành cho .NET để loại trừ phông chữ khỏi đầu ra HTML được hiển thị. Bằng cách làm theo các bước được nêu ở trên, bạn có thể tùy chỉnh quy trình kết xuất để đáp ứng các yêu cầu cụ thể của mình, đảm bảo hiển thị tài liệu tối ưu trong ứng dụng của bạn.
## Câu hỏi thường gặp
### Tôi có thể loại trừ nhiều phông chữ khỏi HTML được hiển thị không?
 Có, bạn có thể thêm nhiều tên phông chữ vào`FontsToExclude` danh sách trong các tùy chọn chế độ xem HTML.
### GroupDocs.Viewer có tương thích với tất cả các khung .NET không?
Có, GroupDocs.Viewer hỗ trợ .NET Framework 4.6.1 trở lên.
### Tôi có thể kết xuất tài liệu từ các vị trí lưu trữ từ xa không?
Có, GroupDocs.Viewer hỗ trợ hiển thị tài liệu từ bộ nhớ cục bộ cũng như các vị trí và luồng lưu trữ từ xa.
### GroupDocs.Viewer có hỗ trợ thiết kế đáp ứng cho đầu ra HTML không?
Có, bạn có thể bật hiển thị đáp ứng bằng cách điều chỉnh tùy chọn chế độ xem HTML cho phù hợp.
### GroupDocs.Viewer có hỗ trợ kỹ thuật không?
 Có, bạn có thể tìm kiếm sự trợ giúp và tham gia thảo luận về[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).