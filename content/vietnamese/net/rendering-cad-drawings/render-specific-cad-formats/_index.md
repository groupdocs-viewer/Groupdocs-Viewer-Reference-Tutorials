---
title: Kết xuất các định dạng CAD cụ thể (CF2)
linktitle: Kết xuất các định dạng CAD cụ thể (CF2)
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị các định dạng CAD cụ thể như CF2 sang HTML, JPG, PNG và PDF bằng Groupdocs.Viewer cho .NET.
weight: 12
url: /vi/net/rendering-cad-drawings/render-specific-cad-formats/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách hiển thị các định dạng CAD cụ thể bằng Groupdocs.Viewer cho .NET. Groupdocs.Viewer là API trình xem tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị hơn 170 loại tài liệu trong ứng dụng của họ mà không yêu cầu bất kỳ cài đặt phần mềm bên ngoài nào. Cụ thể, chúng tôi sẽ tập trung vào việc hiển thị các định dạng CAD như CF2 sang các định dạng đầu ra khác nhau như HTML, JPG, PNG và PDF.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Visual Studio được cài đặt trên hệ thống của bạn.
-  Groupdocs.Viewer cho .NET SDK. Bạn có thể tải nó xuống từ[đây](https://releases.groupdocs.com/viewer/net/).
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết để hiển thị các định dạng CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Bây giờ, hãy chia từng ví dụ thành nhiều bước:
## Kết xuất CF2 sang HTML
### Bước 1: Xác định thư mục đầu ra nơi HTML được hiển thị sẽ được lưu.
```csharp
string outputDirectory = "Your Document Directory";
```
### Bước 2: Xác định định dạng đường dẫn tệp cho đầu ra HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Bước 3: Khởi tạo đối tượng Viewer và chỉ định tệp CF2 đầu vào.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Đặt tùy chọn hiển thị bổ sung nếu cần
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Kết xuất CF2 sang JPG
### Bước 1: Xác định định dạng đường dẫn tệp cho đầu ra JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Bước 2: Khởi tạo đối tượng Viewer và chỉ định tệp CF2 đầu vào.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Đặt tùy chọn hiển thị bổ sung nếu cần
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Kết xuất CF2 thành PNG

### Bước 1: Xác định định dạng đường dẫn tệp cho đầu ra PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Bước 2: Khởi tạo đối tượng Viewer và chỉ định tệp CF2 đầu vào.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Đặt tùy chọn hiển thị bổ sung nếu cần
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Kết xuất CF2 sang PDF
### Bước 1: Xác định định dạng đường dẫn tệp cho đầu ra PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Bước 2: Khởi tạo đối tượng Viewer và chỉ định tệp CF2 đầu vào.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Đặt tùy chọn hiển thị bổ sung nếu cần
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách hiển thị các định dạng CAD cụ thể như CF2 bằng Groupdocs.Viewer cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể dễ dàng tích hợp khả năng kết xuất tài liệu vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Groupdocs.Viewer có thể hiển thị các định dạng CAD khác ngoài CF2 không?
Có, Groupdocs.Viewer hỗ trợ nhiều định dạng CAD, bao gồm DWG, DXF, DGN, v.v.
### Groupdocs.Viewer có phù hợp để hiển thị tài liệu trong ứng dụng web không?
Hoàn toàn có thể, Groupdocs.Viewer có thể được tích hợp liền mạch vào các ứng dụng web để hiển thị tài liệu trực tiếp trong trình duyệt.
### Groupdocs.Viewer có yêu cầu bất kỳ sự phụ thuộc bên ngoài nào để hiển thị không?
Không, Groupdocs.Viewer là một API độc lập và không yêu cầu bất kỳ sự phụ thuộc bên ngoài hoặc cài đặt phần mềm nào.
### Tôi có thể tùy chỉnh các tùy chọn kết xuất theo yêu cầu của mình không?
Có, Groupdocs.Viewer cung cấp nhiều tùy chọn hiển thị khác nhau có thể được tùy chỉnh để đáp ứng nhu cầu cụ thể của bạn.
### Có phiên bản dùng thử cho Groupdocs.Viewer không?
 Có, bạn có thể tải phiên bản dùng thử miễn phí của Groupdocs.Viewer từ[đây](https://releases.groupdocs.com/).