---
title: Kết xuất hình ảnh EMZ và EMF
linktitle: Kết xuất hình ảnh EMZ và EMF
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị hình ảnh EMZ và EMF sang các định dạng khác nhau bằng GroupDocs.Viewer cho .NET. Hướng dẫn dễ làm theo dành cho nhà phát triển.
type: docs
weight: 14
url: /vi/net/image-rendering/render-emz-emf-images/
---
## Giới thiệu

GroupDocs.Viewer cho .NET là API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị nhiều loại tài liệu khác nhau, bao gồm hình ảnh EMZ (Siêu tệp Windows nâng cao) và EMF (Siêu tệp nâng cao) trong các ứng dụng .NET của họ. Trong hướng dẫn này, chúng ta sẽ khám phá cách hiển thị hình ảnh EMZ và EMF sang các định dạng khác nhau như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1.  GroupDocs.Viewer cho .NET: Bạn có thể tải xuống thư viện từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Đảm bảo bạn có môi trường phát triển tương thích được thiết lập để phát triển .NET.
3. Hình ảnh EMZ/EMF mẫu: Có sẵn hình ảnh EMZ và EMF mẫu để hiển thị.

## Nhập không gian tên

Trước khi đi sâu vào mã, hãy nhập các không gian tên cần thiết:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Bây giờ, hãy chia mỗi ví dụ thành nhiều bước theo định dạng hướng dẫn từng bước:

## Hiển thị hình ảnh EMZ/EMF sang HTML

### Bước 1: Đặt thư mục đầu ra:
```csharp
string outputDirectory = "Your Document Directory";
```
 Thay thế`"Your Document Directory"`với đường dẫn mà bạn muốn lưu tệp HTML được hiển thị.

### Bước 2: Xác định định dạng đường dẫn tệp trang:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Điều này sẽ chỉ định định dạng đường dẫn tệp cho tệp HTML được hiển thị.

### Bước 3: Kết xuất sang HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Mã này khởi tạo`Viewer` đối tượng bằng hình ảnh EMZ mẫu và hiển thị nó sang định dạng HTML bằng các tùy chọn được chỉ định.

## Hiển thị hình ảnh EMZ/EMF sang JPG, PNG và PDF

Lặp lại các bước sau để hiển thị sang định dạng JPG, PNG và PDF:

### Bước 1: Xác định định dạng đường dẫn tệp trang:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Điều chỉnh tên tệp và phần mở rộng theo định dạng đầu ra mong muốn (`jpg`, `png` , hoặc`pdf`).

### Bước 2: Kết xuất sang định dạng tương ứng:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Điều chỉnh các tùy chọn theo định dạng đầu ra (Jpg, PNG, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Thay thế`JpgViewOptions` với`PngViewOptions` hoặc`PdfViewOptions` dựa trên định dạng đầu ra mong muốn.

## Phần kết luận

Tóm lại, GroupDocs.Viewer cho .NET cung cấp một giải pháp liền mạch để hiển thị hình ảnh EMZ và EMF sang các định dạng khác nhau trong các ứng dụng .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, nhà phát triển có thể dễ dàng tích hợp khả năng kết xuất tài liệu vào ứng dụng của họ.

## Câu hỏi thường gặp

### Câu hỏi: GroupDocs.Viewer có thể hiển thị các định dạng tài liệu khác ngoài hình ảnh EMZ và EMF không?
Trả lời: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, DOCX, PPTX, XLSX, v.v.

### Câu hỏi: Có bản dùng thử miễn phí GroupDocs.Viewer dành cho .NET không?
 Đ: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.groupdocs.com/).

### Câu hỏi: GroupDocs.Viewer có cung cấp hỗ trợ cho nhà phát triển không?
 Đáp: Có, GroupDocs cung cấp hỗ trợ thông qua[diễn đàn](https://forum.groupdocs.com/c/viewer/9) nơi các nhà phát triển có thể đặt câu hỏi và tìm kiếm sự trợ giúp.

### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho GroupDocs.Viewer cho .NET không?
 Đáp: Có, giấy phép tạm thời có sẵn để mua[đây](https://purchase.groupdocs.com/temporary-license/).

### Câu hỏi: Tôi có thể tìm tài liệu chi tiết về GroupDocs.Viewer dành cho .NET ở đâu?
 Đáp: Bạn có thể tham khảo tài liệu[đây](https://reference.groupdocs.com/viewer/net/)để được hướng dẫn toàn diện về cách sử dụng API.