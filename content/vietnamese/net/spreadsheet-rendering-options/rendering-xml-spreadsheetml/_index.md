---
"description": "Khám phá khả năng hiển thị liền mạch các tệp XML SpreadSheetML ở nhiều định dạng khác nhau bằng GroupDocs.Viewer cho .NET. Tích hợp dễ dàng vào các ứng dụng của bạn."
"linktitle": "Hiển thị XML SpreadSheetML"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị XML SpreadSheetML"
"url": "/vi/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# Hiển thị XML SpreadSheetML

## Giới thiệu
Chào mừng đến với thế giới của GroupDocs.Viewer cho .NET! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách kết xuất các tệp XML SpreadSheetML một cách dễ dàng bằng GroupDocs.Viewer, một thư viện .NET mạnh mẽ. Cho dù bạn là một nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn từng bước này sẽ giúp bạn dễ dàng tích hợp kết xuất XML SpreadSheetML vào các ứng dụng của mình.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
- Môi trường phát triển hỗ trợ .NET.
- GroupDocs.Viewer cho thư viện .NET đã được cài đặt. Bạn có thể tải xuống [đây](https://releases.groupdocs.com/viewer/net/).
- Hiểu biết cơ bản về lập trình C#.
## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án C# của bạn. Điều này đảm bảo rằng bạn có quyền truy cập vào các chức năng do GroupDocs.Viewer cung cấp.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Bước 1: Thiết lập thư mục tài liệu của bạn
Xác định đường dẫn đến thư mục tài liệu nơi đầu ra sẽ được lưu.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Chỉ định đường dẫn tệp đầu ra
Thiết lập đường dẫn đầy đủ cho các tệp đầu ra HTML, JPG, PNG và PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Bước 3: Chỉ định Tùy chọn Tải
Chỉ định rõ ràng loại tệp là Excel 2003 XML SpreadSheetML để hiển thị chính xác.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Bước 4: Kết xuất thành HTML nhiều trang
Sử dụng các tùy chọn chế độ xem HTML để hiển thị tệp XML SpreadSheetML thành tài liệu HTML nhiều trang.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Bước 5: Kết xuất sang JPG
Kết xuất tệp XML SpreadSheetML thành hình ảnh JPG bằng các tùy chọn đã chỉ định.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Bước 6: Kết xuất thành PNG
Tương tự như vậy, chuyển đổi tệp thành hình ảnh PNG với các tùy chọn đã chỉ định.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Bước 7: Kết xuất thành PDF
Cuối cùng, chuyển tệp XML SpreadSheetML thành tài liệu PDF bằng các tùy chọn đã chỉ định.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách hiển thị tệp XML SpreadSheetML bằng GroupDocs.Viewer cho .NET. Nâng cao khả năng xem tài liệu của bạn bằng cách khám phá thêm nhiều tính năng và tùy chọn do thư viện đa năng này cung cấp.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với các định dạng tệp khác không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Word, Excel, v.v.
### Tôi có thể tùy chỉnh giao diện của tài liệu được kết xuất không?
Chắc chắn rồi! GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh khác nhau, cho phép bạn điều chỉnh đầu ra theo nhu cầu cụ thể của mình.
### Tôi có thể tìm thêm hỗ trợ và tài nguyên ở đâu?
Ghé thăm [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để hỗ trợ cộng đồng và khám phá [tài liệu](https://tutorials.groupdocs.com/viewer/net/) để biết thông tin chi tiết.
### Có bản dùng thử miễn phí không?
Có, bạn có thể truy cập bản dùng thử miễn phí [đây](https://releases.groupdocs.com/).
### Làm thế nào để tôi có thể xin được giấy phép tạm thời?
Bạn có thể nhận được giấy phép tạm thời [đây](https://purchase.groupdocs.com/temporary-license/).