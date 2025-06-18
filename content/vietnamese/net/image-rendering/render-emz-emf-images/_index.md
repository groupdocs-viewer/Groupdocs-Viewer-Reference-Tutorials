---
"description": "Tìm hiểu cách hiển thị hình ảnh EMZ và EMF sang nhiều định dạng khác nhau bằng GroupDocs.Viewer cho .NET. Hướng dẫn dễ làm theo dành cho nhà phát triển."
"linktitle": "Kết xuất hình ảnh EMZ và EMF"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất hình ảnh EMZ và EMF"
"url": "/vi/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# Kết xuất hình ảnh EMZ và EMF

## Giới thiệu

GroupDocs.Viewer for .NET là API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị nhiều loại tài liệu khác nhau, bao gồm hình ảnh EMZ (Enhanced Windows Metafile) và EMF (Enhanced Metafile), trong các ứng dụng .NET của họ. Trong hướng dẫn này, chúng ta sẽ khám phá cách kết xuất hình ảnh EMZ và EMF sang các định dạng khác nhau như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer for .NET.

![Kết xuất hình ảnh EMZ và EMF với GroupDocs.Viewer cho .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng đủ các điều kiện tiên quyết sau:

1. GroupDocs.Viewer cho .NET: Bạn có thể tải xuống thư viện từ [đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển tương thích cho phát triển .NET.
3. Mẫu hình ảnh EMZ/EMF: Có sẵn các hình ảnh EMZ và EMF mẫu để kết xuất.

## Nhập không gian tên

Trước khi đi sâu vào mã, hãy nhập các không gian tên cần thiết:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Bây giờ, chúng ta hãy chia nhỏ từng ví dụ thành nhiều bước theo định dạng hướng dẫn từng bước:

## Kết xuất hình ảnh EMZ/EMF sang HTML

### Bước 1: Thiết lập thư mục đầu ra:
```csharp
string outputDirectory = "Your Document Directory";
```
Thay thế `"Your Document Directory"` bằng đường dẫn mà bạn muốn lưu tệp HTML đã hiển thị.

### Bước 2: Xác định định dạng đường dẫn tệp trang:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Thao tác này sẽ chỉ định định dạng đường dẫn tệp cho tệp HTML được hiển thị.

### Bước 3: Kết xuất thành HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Mã này khởi tạo `Viewer` đối tượng có hình ảnh EMZ mẫu và hiển thị nó ở định dạng HTML bằng các tùy chọn được chỉ định.

## Kết xuất hình ảnh EMZ/EMF sang JPG, PNG và PDF

Lặp lại các bước sau để hiển thị sang định dạng JPG, PNG và PDF:

### Bước 1: Xác định định dạng đường dẫn tệp trang:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Điều chỉnh tên tệp và phần mở rộng theo định dạng đầu ra mong muốn (`jpg`, `png`, hoặc `pdf`).

### Bước 2: Hiển thị theo định dạng tương ứng:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Điều chỉnh tùy chọn theo định dạng đầu ra (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Thay thế `JpgViewOptions` với `PngViewOptions` hoặc `PdfViewOptions` dựa trên định dạng đầu ra mong muốn.

## Phần kết luận

Tóm lại, GroupDocs.Viewer for .NET cung cấp giải pháp liền mạch để kết xuất hình ảnh EMZ và EMF sang nhiều định dạng khác nhau trong các ứng dụng .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, các nhà phát triển có thể dễ dàng tích hợp khả năng kết xuất tài liệu vào ứng dụng của họ.

## Câu hỏi thường gặp

### H: GroupDocs.Viewer có thể hiển thị các định dạng tài liệu khác ngoài hình ảnh EMZ và EMF không?
A: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, DOCX, PPTX, XLSX, v.v.

### H: Có bản dùng thử miễn phí của GroupDocs.Viewer dành cho .NET không?
A: Có, bạn có thể truy cập bản dùng thử miễn phí [đây](https://releases.groupdocs.com/).

### H: GroupDocs.Viewer có hỗ trợ cho nhà phát triển không?
A: Có, GroupDocs cung cấp hỗ trợ thông qua [diễn đàn](https://forum.groupdocs.com/c/viewer/9) nơi các nhà phát triển có thể đặt câu hỏi và tìm kiếm sự hỗ trợ.

### H: Tôi có thể mua giấy phép tạm thời cho GroupDocs.Viewer dành cho .NET không?
A: Có, giấy phép tạm thời có thể mua được [đây](https://purchase.groupdocs.com/temporary-license/).

### H: Tôi có thể tìm tài liệu chi tiết về GroupDocs.Viewer cho .NET ở đâu?
A: Bạn có thể tham khảo tài liệu [đây](https://tutorials.groupdocs.com/viewer/net/) để có hướng dẫn toàn diện về cách sử dụng API.