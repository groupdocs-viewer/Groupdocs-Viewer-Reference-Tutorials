---
"description": "Tìm hiểu cách hiển thị tệp CHM trong .NET bằng GroupDocs.Viewer. Chuyển đổi CHM sang định dạng HTML, JPG, PNG và PDF một cách dễ dàng."
"linktitle": "Hiển thị tệp CHM"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị tệp CHM"
"url": "/vi/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Hiển thị tệp CHM

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách hiển thị các tệp CHM (Trợ giúp HTML biên dịch) bằng GroupDocs.Viewer cho .NET. GroupDocs.Viewer cho .NET là API hiển thị tài liệu mạnh mẽ cho phép các nhà phát triển hiển thị hơn 170 loại tài liệu trong các ứng dụng .NET của họ mà không cần cài đặt bất kỳ phần mềm bên ngoài nào.

## Điều kiện tiên quyết

Trước khi bắt đầu dựng tệp CHM, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

### Cài đặt GroupDocs.Viewer cho .NET

Để bắt đầu, bạn cần cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tải xuống thư viện từ [Trang web GroupDocs](https://releases.groupdocs.com/viewer/net/) hoặc cài đặt thông qua NuGet Package Manager bằng cách chạy lệnh sau trong Package Manager Console:

```bash
Install-Package GroupDocs.Viewer
```

## Nhập không gian tên

Hãy đảm bảo nhập các không gian tên cần thiết vào dự án của bạn:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ chúng ta hãy chia nhỏ quá trình kết xuất thành nhiều bước:

## Bước 1: Xác định thư mục đầu ra

Xác định thư mục mà bạn muốn lưu các tập tin đã kết xuất:

```csharp
string outputDirectory = "Your Document Directory";
```

## Bước 2: Kết xuất thành HTML

Để chuyển đổi tệp CHM thành HTML, hãy sử dụng đoạn mã sau:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Đặt thành true để chuyển đổi toàn bộ nội dung CHM thành một trang duy nhất

    viewer.View(options); // Chuyển đổi tất cả các trang
}
```

## Bước 3: Kết xuất sang JPG

Để chuyển đổi tệp CHM thành hình ảnh JPG, hãy sử dụng đoạn mã sau:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Chỉ chuyển đổi trang 1, 2, 3
}
```

## Bước 4: Kết xuất thành PNG

Để chuyển đổi tệp CHM thành hình ảnh PNG, hãy sử dụng đoạn mã sau:

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

    viewer.View(options); // Chuyển đổi tất cả các trang
}
```

## Bước 6: Kiểm tra đầu ra

Khi quá trình kết xuất hoàn tất, hãy kiểm tra thư mục đầu ra đã chỉ định để tìm các tệp đã kết xuất:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận

Kết xuất tệp CHM bằng GroupDocs.Viewer cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể chuyển đổi hiệu quả các tài liệu CHM thành nhiều định dạng khác nhau như HTML, hình ảnh (JPG, PNG) và PDF trong các ứng dụng .NET của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: GroupDocs.Viewer có thể hiển thị các định dạng tài liệu khác ngoài CHM không?

A1: Có, GroupDocs.Viewer hỗ trợ hiển thị hơn 170 định dạng tài liệu bao gồm PDF, DOCX, XLSX, PPTX, v.v.

### Câu hỏi 2: GroupDocs.Viewer có tương thích với .NET Core không?

A2: Có, GroupDocs.Viewer hỗ trợ .NET Core ngoài .NET Framework truyền thống.

### Câu hỏi 3: Tôi có thể tùy chỉnh tùy chọn kết xuất cho các định dạng đầu ra khác nhau không?

A3: Có, GroupDocs.Viewer cung cấp nhiều tùy chọn khác nhau để tùy chỉnh quy trình kết xuất, chẳng hạn như chỉ định số trang, cài đặt chất lượng hình ảnh và cấu hình đường dẫn đầu ra.

### Câu hỏi 4: GroupDocs.Viewer có yêu cầu bất kỳ sự phụ thuộc bên ngoài nào để hiển thị tài liệu không?

A4: Không, GroupDocs.Viewer là một thư viện độc lập và không yêu cầu bất kỳ sự phụ thuộc bên ngoài hoặc cài đặt phần mềm của bên thứ ba nào.

### Câu hỏi 5: Có bản dùng thử miễn phí cho GroupDocs.Viewer không?

A5: Có, bạn có thể dùng thử miễn phí GroupDocs.Viewer bằng cách truy cập [trang web](https://releases.groupdocs.com/).