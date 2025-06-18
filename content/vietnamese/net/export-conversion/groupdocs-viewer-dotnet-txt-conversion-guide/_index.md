---
"date": "2025-04-25"
"description": "Tìm hiểu cách chuyển đổi tệp TXT sang nhiều định dạng như HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho .NET với hướng dẫn toàn diện này."
"title": "Chuyển đổi TXT sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer .NET&#58; Hướng dẫn đầy đủ"
"url": "/vi/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# Chuyển đổi TXT sang nhiều định dạng với GroupDocs.Viewer .NET

## Giới thiệu

Bạn đang muốn chuyển đổi tài liệu văn bản sang nhiều định dạng khác nhau như HTML, JPG, PNG hoặc PDF một cách dễ dàng? Quản lý việc chuyển đổi tài liệu có thể là một thách thức, đặc biệt là khi xử lý nhiều trang hoặc yêu cầu định dạng cụ thể. **GroupDocs.Viewer cho .NET** đơn giản hóa quá trình kết xuất các tệp TXT thành nhiều định dạng đầu ra khác nhau, đảm bảo dữ liệu của bạn có thể truy cập được và hấp dẫn về mặt trực quan.

![Chuyển đổi TXT sang HTML, JPG, PNG, PDF với GroupDocs.Viewer cho .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng GroupDocs.Viewer cho .NET để chuyển đổi tài liệu TXT thành HTML nhiều trang, HTML một trang, JPG, PNG và PDF. Đến cuối, bạn sẽ thành thạo:
- Chuyển đổi các tệp TXT bằng C# với GroupDocs.Viewer
- Triển khai các tùy chọn kết xuất khác nhau cho nhu cầu của bạn
- Tối ưu hóa hiệu suất trong quá trình chuyển đổi

Hãy cùng tìm hiểu để giải quyết những thách thức trong việc chuyển đổi tài liệu của bạn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị những thứ sau:
- **Môi trường phát triển**: Visual Studio 2019 trở lên.
- **Khung .NET**: Phiên bản 4.6.1 trở lên.
- **GroupDocs.Viewer cho Thư viện .NET**:
  - Thông qua Bảng điều khiển Trình quản lý gói NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Sử dụng .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Nên quen thuộc với lập trình C# và các thao tác tệp cơ bản trong .NET để dễ dàng theo dõi.

## Thiết lập GroupDocs.Viewer cho .NET

### Cài đặt

Để bắt đầu, hãy cài đặt **GroupDocs.Viewer** thư viện bằng trình quản lý gói ưa thích của bạn:

#### Bảng điều khiển quản lý gói NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NETCLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Cấp phép

Bạn có thể bắt đầu với một **dùng thử miễn phí** hoặc có được một **giấy phép tạm thời** để khám phá toàn bộ khả năng của GroupDocs.Viewer cho .NET mà không có giới hạn đánh giá:
- Dùng thử miễn phí: [Tải xuống tại đây](https://releases.groupdocs.com/viewer/net/)
- Giấy phép tạm thời: [Yêu cầu ở đây](https://purchase.groupdocs.com/temporary-license/)

Để sử dụng liên tục, hãy cân nhắc mua giấy phép trực tiếp từ [NhómDocs](https://purchase.groupdocs.com/buy).

### Khởi tạo cơ bản

Để thiết lập GroupDocs.Viewer trong dự án của bạn:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Khởi tạo đối tượng Viewer bằng đường dẫn tệp TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Mã kết xuất của bạn sẽ nằm ở đây.
}
```

## Hướng dẫn thực hiện

Bây giờ, chúng ta hãy đi sâu vào từng tính năng và xem cách bạn có thể triển khai chúng.

### Kết xuất tài liệu TXT thành HTML nhiều trang

#### Tổng quan
Tính năng này minh họa việc chuyển đổi tài liệu TXT sang định dạng HTML nhiều trang. Mỗi trang của tệp văn bản được hiển thị dưới dạng tệp HTML riêng lẻ có tài nguyên nhúng.

#### Bước 1: Thiết lập Viewer

Tạo một `Viewer` đối tượng cho tệp TXT nguồn của bạn:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Khởi tạo Viewer bằng một tệp văn bản mẫu.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Tiếp tục bước 2...
```

#### Bước 2: Cấu hình Tùy chọn chế độ xem HTML

Cài đặt `HtmlViewOptions` để hiển thị từng trang riêng biệt:

```csharp
// Thiết lập tùy chọn chế độ xem HTML để hiển thị nhiều trang.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Hiển thị tài liệu dưới dạng HTML nhiều trang.
viewer.View(options);
}
```

**Giải thích**: Các `ForEmbeddedResources()` Phương pháp này đảm bảo rằng các tài nguyên như hình ảnh và kiểu được nhúng trực tiếp vào tệp HTML, giúp chia sẻ dễ dàng.

### Kết xuất tài liệu TXT thành HTML trang đơn

#### Tổng quan
Chuyển đổi một tài liệu TXT thành một trang HTML duy nhất, lý tưởng cho các tài liệu cần được hiển thị dưới dạng một trang web liên tục.

#### Bước 1: Thiết lập Viewer

Khởi tạo `Viewer` sự vật:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Khởi tạo một phiên bản Viewer mới cho một tệp văn bản khác.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Tiếp tục bước 2...
```

#### Bước 2: Cấu hình tùy chọn HTML trang đơn

Cấu hình `HtmlViewOptions` khi bật chế độ trang đơn:

```csharp
// Thiết lập các tùy chọn để hiển thị thành một trang HTML duy nhất.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Hiển thị dưới dạng một trang HTML duy nhất.
viewer.View(options);
}
```

**Giải thích**: Các `RenderToSinglePage` Thuộc tính này đảm bảo toàn bộ nội dung được hiển thị trên một trang.

### Chuyển đổi tài liệu TXT sang JPG

#### Tổng quan
Tính năng này cho phép bạn chuyển đổi tài liệu văn bản thành hình ảnh JPEG, hữu ích cho mục đích trình bày trực quan hoặc lưu trữ.

#### Bước 1: Thiết lập Viewer

Chuẩn bị của bạn `Viewer` sự vật:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Khởi tạo trình xem bằng một tệp mẫu.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Tiếp tục bước 2...
```

#### Bước 2: Cấu hình Tùy chọn xem JPG

Cài đặt `JpgViewOptions` để hiển thị hình ảnh:

```csharp
// Thiết lập tùy chọn để hiển thị dưới dạng hình ảnh JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Hiển thị tài liệu dưới dạng tệp JPEG.
viewer.View(options);
}
```

**Giải thích**: Các `JpgViewOptions` lớp này chỉ định cách hiển thị và lưu từng trang trong tài liệu của bạn ở định dạng JPEG.

### Chuyển đổi tài liệu TXT sang PNG

#### Tổng quan
Chuyển đổi tài liệu văn bản sang định dạng PNG, cung cấp hình ảnh đầu ra chất lượng cao với hỗ trợ độ trong suốt.

#### Bước 1: Thiết lập Viewer

Khởi tạo `Viewer` sự vật:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Tạo một phiên bản trình xem cho tệp TXT của bạn.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Tiếp tục bước 2...
```

#### Bước 2: Cấu hình Tùy chọn xem PNG

Cài đặt `PngViewOptions`:

```csharp
// Thiết lập tùy chọn chế độ xem để hiển thị dưới dạng hình ảnh PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Hiển thị tài liệu ở định dạng PNG.
viewer.View(options);
}
```

**Giải thích**: Các `PngViewOptions` Lớp này cho phép mỗi trang được hiển thị trong suốt, phù hợp với đồ họa nhiều lớp.

### Chuyển đổi tài liệu TXT sang PDF

#### Tổng quan
Tính năng này hoàn hảo để chuyển đổi tài liệu văn bản sang định dạng PDF phổ biến.

#### Bước 1: Thiết lập Viewer

Chuẩn bị của bạn `Viewer` sự vật:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Khởi tạo một phiên bản trình xem cho tệp văn bản mẫu của bạn.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Tiếp tục bước 2...
```

#### Bước 2: Cấu hình Tùy chọn xem PDF

Cài đặt `PdfViewOptions`:

```csharp
// Thiết lập tùy chọn chế độ xem để hiển thị dưới dạng tài liệu PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Chuyển tài liệu thành tệp PDF.
viewer.View(options);
}
```

**Giải thích**: Các `PdfViewOptions` lớp này chỉ định cách chuyển đổi và lưu tệp TXT của bạn dưới dạng tài liệu PDF.

## Phần kết luận

Với GroupDocs.Viewer cho .NET, việc chuyển đổi tài liệu văn bản sang nhiều định dạng khác nhau rất đơn giản. Hướng dẫn này đề cập đến việc chuyển đổi các tệp TXT thành HTML nhiều trang, HTML một trang, JPG, PNG và PDF bằng C#. Cho dù bạn đang muốn nâng cao khả năng truy cập hoặc khả năng tương thích của tài liệu, các phương pháp này đều cung cấp các giải pháp mạnh mẽ.

Để được hỗ trợ thêm hoặc các tính năng nâng cao hơn, hãy tham khảo [tài liệu chính thức của GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/). Chúc bạn viết mã vui vẻ!