---
title: Hiển thị hình ảnh SVG và SVGZ
linktitle: Hiển thị hình ảnh SVG và SVGZ
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị hình ảnh SVG và SVGZ bằng GroupDocs.Viewer cho .NET. Chuyển đổi đồ họa vector thành HTML, JPG, PNG và PDF một cách dễ dàng.
type: docs
weight: 16
url: /vi/net/image-rendering/render-svg-svgz-images/
---
## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình hiển thị hình ảnh SVG và SVGZ bằng GroupDocs.Viewer cho .NET. GroupDocs.Viewer cho .NET là API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị các định dạng tài liệu khác nhau trong ứng dụng .NET của họ. SVG và SVGZ là các định dạng hình ảnh phổ biến được sử dụng cho đồ họa vector và với GroupDocs.Viewer dành cho .NET, bạn có thể dễ dàng hiển thị chúng thành các định dạng đầu ra khác nhau như HTML, JPG, PNG và PDF.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập các điều kiện tiên quyết sau:
1.  GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Đảm bảo bạn có môi trường phát triển hoạt động để phát triển .NET, chẳng hạn như Visual Studio.
3. Tệp SVGZ mẫu: Chuẩn bị sẵn tệp SVGZ mẫu để thử nghiệm.

## Nhập không gian tên
Trước khi đi sâu vào mã, hãy nhập các không gian tên cần thiết:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Bước 1: Kết xuất SVGZ sang HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Bước 2: Kết xuất SVGZ sang JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Bước 3: Kết xuất SVGZ thành PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Bước 4: Kết xuất SVGZ thành PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách hiển thị hình ảnh SVG và SVGZ bằng GroupDocs.Viewer cho .NET. Chỉ với một vài bước đơn giản, bạn có thể chuyển đổi hình ảnh SVGZ thành nhiều định dạng đầu ra khác nhau như HTML, JPG, PNG và PDF, giúp chúng có thể truy cập và xem được trong các môi trường khác nhau.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể hiển thị các định dạng hình ảnh khác không?
Có, GroupDocs.Viewer hỗ trợ hiển thị nhiều định dạng hình ảnh khác nhau bao gồm PNG, JPEG, BMP, TIFF, GIF, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer tương thích với cả .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh các tùy chọn kết xuất không?
Có, GroupDocs.Viewer cung cấp các tùy chọn hiển thị mở rộng cho phép bạn tùy chỉnh đầu ra theo yêu cầu của mình.
### GroupDocs.Viewer có yêu cầu bất kỳ sự phụ thuộc nào của bên thứ ba không?
Không, GroupDocs.Viewer là một API độc lập và không yêu cầu bất kỳ sự phụ thuộc nào của bên thứ ba để hiển thị tài liệu.
### Có phiên bản dùng thử để thử nghiệm không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của GroupDocs.Viewer từ[đây](https://releases.groupdocs.com/) để đánh giá các tính năng của nó trước khi mua hàng.