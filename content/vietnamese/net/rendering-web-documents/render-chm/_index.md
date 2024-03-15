---
title: Kết xuất tệp CHM
linktitle: Kết xuất tệp CHM
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị tệp CHM trong .NET bằng GroupDocs.Viewer. Chuyển đổi CHM sang các định dạng HTML, JPG, PNG và PDF một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/rendering-web-documents/render-chm/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách hiển thị các tệp CHM (Trợ giúp HTML được biên dịch) bằng GroupDocs.Viewer cho .NET. GroupDocs.Viewer cho .NET là API kết xuất tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị hơn 170 loại tài liệu trong ứng dụng .NET của họ mà không yêu cầu bất kỳ cài đặt phần mềm bên ngoài nào.

## Điều kiện tiên quyết

Trước khi chúng tôi đi sâu vào hiển thị tệp CHM, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

### Cài đặt GroupDocs.Viewer cho .NET

 Để bắt đầu, bạn cần cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải xuống thư viện từ[Trang web GroupDocs](https://releases.groupdocs.com/viewer/net/) hoặc cài đặt nó thông qua Trình quản lý gói NuGet bằng cách chạy lệnh sau trong Bảng điều khiển quản lý gói:

```bash
Install-Package GroupDocs.Viewer
```

## Nhập không gian tên

Đảm bảo nhập các không gian tên cần thiết vào dự án của bạn:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ hãy chia quá trình kết xuất thành nhiều bước:

## Bước 1: Xác định thư mục đầu ra

Xác định thư mục nơi bạn muốn lưu các tệp được kết xuất:

```csharp
string outputDirectory = "Your Document Directory";
```

## Bước 2: Kết xuất sang HTML

Để hiển thị tệp CHM thành HTML, hãy sử dụng đoạn mã sau:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Đặt thành true để chuyển đổi tất cả nội dung CHM thành một trang

    viewer.View(options); //Chuyển đổi tất cả các trang
}
```

## Bước 3: Kết xuất sang JPG

Để hiển thị tệp CHM thành hình ảnh JPG, hãy sử dụng đoạn mã sau:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Chỉ chuyển đổi trang 1, 2, 3
}
```

## Bước 4: Kết xuất sang PNG

Để hiển thị tệp CHM thành hình ảnh PNG, hãy sử dụng đoạn mã sau:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Chỉ chuyển đổi trang 1, 2, 3
}
```

## Bước 5: Kết xuất thành PDF

Để hiển thị tệp CHM thành tài liệu PDF, hãy sử dụng đoạn mã sau:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Chuyển đổi tất cả các trang
}
```

## Bước 6: Kiểm tra đầu ra

Khi quá trình kết xuất hoàn tất, hãy kiểm tra thư mục đầu ra được chỉ định để tìm các tệp được kết xuất:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận

Hiển thị tệp CHM bằng GroupDocs.Viewer cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể chuyển đổi tài liệu CHM thành nhiều định dạng khác nhau một cách hiệu quả như HTML, hình ảnh (JPG, PNG) và PDF trong các ứng dụng .NET của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: GroupDocs.Viewer có thể hiển thị các định dạng tài liệu khác ngoài CHM không?

Câu trả lời 1: Có, GroupDocs.Viewer hỗ trợ hiển thị hơn 170 định dạng tài liệu bao gồm PDF, DOCX, XLSX, PPTX, v.v.

### Câu hỏi 2: GroupDocs.Viewer có tương thích với .NET Core không?

Câu trả lời 2: Có, GroupDocs.Viewer hỗ trợ .NET Core ngoài .NET Framework truyền thống.

### Câu hỏi 3: Tôi có thể tùy chỉnh các tùy chọn hiển thị cho các định dạng đầu ra khác nhau không?

Câu trả lời 3: Có, GroupDocs.Viewer cung cấp nhiều tùy chọn khác nhau để tùy chỉnh quy trình kết xuất, chẳng hạn như chỉ định số trang, đặt chất lượng hình ảnh và định cấu hình đường dẫn đầu ra.

### Câu hỏi 4: GroupDocs.Viewer có yêu cầu bất kỳ phần phụ thuộc bên ngoài nào để hiển thị tài liệu không?

Câu trả lời 4: Không, GroupDocs.Viewer là một thư viện độc lập và không yêu cầu bất kỳ sự phụ thuộc bên ngoài nào hoặc cài đặt phần mềm của bên thứ ba.

### Câu hỏi 5: Có bản dùng thử miễn phí cho GroupDocs.Viewer không?

 Câu trả lời 5: Có, bạn có thể tận dụng bản dùng thử miễn phí của GroupDocs.Viewer bằng cách truy cập vào[trang mạng](https://releases.groupdocs.com/).