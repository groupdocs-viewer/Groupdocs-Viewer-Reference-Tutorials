---
"description": "Tìm hiểu cách hiển thị tất cả các bố cục trong bản vẽ CAD bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn toàn diện của chúng tôi để tích hợp liền mạch."
"linktitle": "Kết xuất tất cả các bố cục trong bản vẽ CAD"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất tất cả các bố cục trong bản vẽ CAD"
"url": "/vi/net/rendering-cad-drawings/render-all-layouts-cad/"
"weight": 11
type: docs
---
# Kết xuất tất cả các bố cục trong bản vẽ CAD

## Giới thiệu
Trong lĩnh vực quản lý và trực quan hóa tài liệu, GroupDocs.Viewer for .NET nổi bật như một giải pháp đa năng, giúp các nhà phát triển dễ dàng kết xuất nhiều loại tài liệu khác nhau trong các ứng dụng .NET của họ. Trong số vô vàn khả năng của nó là khả năng kết xuất hiệu quả các bản vẽ CAD, bao gồm cả các bố cục phức tạp mà chúng đòi hỏi. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tận dụng GroupDocs.Viewer for .NET để kết xuất tất cả các bố cục có trong bản vẽ CAD. 
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. Hiểu biết cơ bản về phát triển .NET: Việc quen thuộc với các nguyên tắc cơ bản về phát triển .NET sẽ có lợi trong việc hiểu các bước triển khai được nêu trong hướng dẫn này.
2. Cài đặt GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt thư viện GroupDocs.Viewer cho .NET. Bạn có thể tải xuống từ [trang web](https://releases.groupdocs.com/viewer/net/).
3. Tệp bản vẽ CAD: Lấy các tệp bản vẽ CAD mà bạn định kết xuất. Chúng có thể bao gồm các tệp DWG với nhiều bố cục.
4. Môi trường phát triển: Thiết lập môi trường phát triển ưa thích của bạn với các công cụ và phụ thuộc cần thiết.

## Nhập không gian tên
Trước tiên, hãy đảm bảo rằng bạn nhập các không gian tên cần thiết vào dự án .NET của mình. Các không gian tên này cung cấp quyền truy cập vào các chức năng cần thiết để hiển thị bản vẽ CAD bằng GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 2: Nhập không gian tên System.IO
```csharp
using System.IO;
```
## Bước 1: Chỉ định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Xác định thư mục mà bạn muốn lưu kết quả đã kết xuất.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Thiết lập định dạng cho đường dẫn tệp của các trang được hiển thị. Trong trường hợp này, các trang sẽ được lưu dưới dạng tệp HTML.
## Bước 3: Khởi tạo đối tượng Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Tạo một thể hiện của lớp Viewer, truyền đường dẫn đến tệp bản vẽ CAD dưới dạng tham số.
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Cấu hình các tùy chọn chế độ xem HTML, chỉ định rằng bố cục sẽ được hiển thị cho bản vẽ CAD.
## Bước 5: Kết xuất bản vẽ CAD
```csharp
viewer.View(options);
```
Gọi phương thức View của đối tượng Viewer, truyền các tùy chọn đã cấu hình để hiển thị bản vẽ CAD.
## Bước 6: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc kết xuất thành công và vị trí của thư mục đầu ra.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng GroupDocs.Viewer cho .NET để hiển thị tất cả các bố cục có trong bản vẽ CAD. Bằng cách làm theo hướng dẫn từng bước và triển khai các đoạn mã được cung cấp, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của mình, do đó nâng cao khả năng trực quan hóa tài liệu.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với nhiều định dạng CAD khác nhau không?
Có, GroupDocs.Viewer hỗ trợ hiển thị bản vẽ CAD ở các định dạng như DWG và DXF.
### Tôi có thể tùy chỉnh kết quả hiển thị theo yêu cầu của ứng dụng không?
Đúng vậy, GroupDocs.Viewer cung cấp nhiều tùy chọn để tùy chỉnh đầu ra kết xuất, bao gồm chất lượng hình ảnh, kích thước trang, v.v.
### GroupDocs.Viewer có yêu cầu bất kỳ giấy phép bổ sung nào để sử dụng cho mục đích thương mại không?
Có, đối với mục đích thương mại, bạn có thể cần phải có giấy phép. Bạn có thể xin giấy phép tạm thời cho mục đích thử nghiệm hoặc mua giấy phép thương mại từ trang web.
### Tôi có thể kết xuất bản vẽ CAD không đồng bộ với GroupDocs.Viewer không?
Có, GroupDocs.Viewer cung cấp khả năng kết xuất không đồng bộ, cho phép xử lý hiệu quả các bản vẽ CAD lớn mà không làm tắc luồng chính.
### GroupDocs.Viewer có cung cấp hỗ trợ khắc phục sự cố và hỗ trợ kỹ thuật không?
Chắc chắn, bạn có thể tìm kiếm sự hỗ trợ và trợ giúp từ diễn đàn cộng đồng GroupDocs.Viewer, có thể truy cập [đây](https://forum.groupdocs.com/c/viewer/9).