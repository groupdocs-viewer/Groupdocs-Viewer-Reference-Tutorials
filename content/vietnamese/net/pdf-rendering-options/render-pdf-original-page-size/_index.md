---
title: Kết xuất PDF với kích thước trang gốc
linktitle: Kết xuất PDF với kích thước trang gốc
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị tệp PDF với kích thước trang gốc bằng GroupDocs.Viewer dành cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi và tích hợp liền mạch chức năng này.
type: docs
weight: 17
url: /vi/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Giới thiệu
Trong lĩnh vực phát triển .NET, GroupDocs.Viewer nổi bật như một công cụ mạnh mẽ để hiển thị các định dạng tài liệu khác nhau, bao gồm cả tệp PDF. Một yêu cầu phổ biến trong việc xử lý tài liệu là hiển thị các tệp PDF trong khi vẫn giữ nguyên kích thước trang gốc của chúng. Để đạt được nhiệm vụ này một cách liền mạch đòi hỏi sự hiểu biết toàn diện về GroupDocs.Viewer cho .NET và các chức năng của nó.
## Điều kiện tiên quyết
Trước khi đi sâu vào hiển thị các tệp PDF có kích thước trang gốc bằng GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
 Bắt đầu bằng cách tải xuống thư viện GroupDocs.Viewer từ trang web. Bạn có thể lấy thư viện từ nguồn được cung cấp[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/). Làm theo hướng dẫn cài đặt được cung cấp trong tài liệu để tích hợp nó vào dự án .NET của bạn một cách hiệu quả.
### 2. Thiết lập môi trường phát triển
Đảm bảo bạn đã thiết lập môi trường phát triển để phát triển .NET. Điều này bao gồm việc cài đặt IDE tương thích, chẳng hạn như Visual Studio và hiểu biết cơ bản về lập trình C#.
### 3. Lấy tài liệu PDF
Bạn sẽ cần một tài liệu PDF mẫu để hiển thị bằng GroupDocs.Viewer. Bạn có thể sử dụng bất kỳ tài liệu PDF nào cho mục đích thử nghiệm. Nếu không có, bạn có thể tải xuống bản PDF mẫu từ nhiều nguồn trực tuyến khác nhau.

## Nhập không gian tên
Trước khi tiếp tục hiển thị tệp PDF, điều cần thiết là nhập các vùng tên cần thiết vào dự án C# của bạn. Bước này cho phép bạn truy cập các lớp và phương thức cần thiết từ thư viện GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ bạn đã có sẵn các điều kiện tiên quyết và các không gian tên cần thiết đã được nhập, hãy chia nhỏ quy trình hiển thị tệp PDF với kích thước trang gốc bằng GroupDocs.Viewer cho .NET thành các bước đơn giản:
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
 Đảm bảo bạn chỉ định thư mục nơi bạn muốn lưu các trang được hiển thị. Thay thế`"Your Document Directory"` với đường dẫn của thư mục bạn muốn.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Thiết lập định dạng để đặt tên cho các tệp trang được hiển thị. Trong ví dụ này, các trang sẽ được lưu dưới dạng hình ảnh PNG với tên tệp ở định dạng`"page_1.png"`, `"page_2.png"`, và như thế.
## Bước 3: Kết xuất PDF với kích thước trang gốc
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Khởi tạo một`Viewer` object bằng đường dẫn đến tệp PDF của bạn. Sau đó, tạo`PngViewOptions` với định dạng đường dẫn tệp trang được chỉ định. Bộ`RenderOriginalPageSize` tài sản để`true` để duy trì kích thước trang gốc trong khi hiển thị.
## Bước 4: Hiển thị vị trí tài liệu được hiển thị
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
In thông báo cho biết hiển thị thành công và cung cấp thư mục lưu các trang được hiển thị.

## Phần kết luận
Hiển thị các tệp PDF có kích thước trang gốc bằng GroupDocs.Viewer dành cho .NET là một quá trình đơn giản khi bạn làm theo các bước được nêu trong hướng dẫn này. Bằng cách nhập các không gian tên cần thiết và làm theo hướng dẫn từng bước, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### GroupDocs.Viewer có thể hiển thị các định dạng tài liệu khác ngoài PDF không?
Có, GroupDocs.Viewer hỗ trợ hiển thị nhiều định dạng tài liệu khác nhau, bao gồm Word, Excel, PowerPoint, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer tương thích với cả môi trường .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh định dạng đầu ra của các trang được hiển thị không?
Có, bạn có thể tùy chỉnh định dạng đầu ra bằng cách điều chỉnh các tùy chọn do GroupDocs.Viewer cung cấp, chẳng hạn như đặt các định dạng hình ảnh khác nhau hoặc chỉ định các tùy chọn hiển thị tùy chỉnh.
### GroupDocs.Viewer có cung cấp hỗ trợ hiển thị tài liệu dựa trên đám mây không?
Có, GroupDocs.Viewer cung cấp API để hiển thị tài liệu dựa trên đám mây, cho phép bạn hiển thị tài liệu trực tiếp từ các nhà cung cấp lưu trữ đám mây.
### Có bản dùng thử miễn phí cho GroupDocs.Viewer không?
 Có, bạn có thể khám phá GroupDocs.Viewer với bản dùng thử miễn phí bằng cách truy cập vào trang được cung cấp[liên kết](https://releases.groupdocs.com/).