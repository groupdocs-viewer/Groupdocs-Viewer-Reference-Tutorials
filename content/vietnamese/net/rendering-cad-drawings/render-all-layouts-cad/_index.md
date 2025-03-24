---
title: Kết xuất tất cả bố cục trong bản vẽ CAD
linktitle: Kết xuất tất cả bố cục trong bản vẽ CAD
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách hiển thị tất cả bố cục trong bản vẽ CAD bằng GroupDocs.Viewer cho .NET. Hãy làm theo hướng dẫn toàn diện của chúng tôi để tích hợp liền mạch.
weight: 11
url: /vi/net/rendering-cad-drawings/render-all-layouts-cad/
---

# Kết xuất tất cả bố cục trong bản vẽ CAD

## Giới thiệu
Trong lĩnh vực quản lý và trực quan hóa tài liệu, GroupDocs.Viewer dành cho .NET được coi là một giải pháp linh hoạt, trao quyền cho các nhà phát triển dễ dàng hiển thị nhiều loại tài liệu khác nhau trong ứng dụng .NET của họ. Trong số vô số khả năng của nó là khả năng hiển thị các bản vẽ CAD một cách hiệu quả, bao gồm cả các bố cục phức tạp mà chúng đòi hỏi. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tận dụng GroupDocs.Viewer cho .NET để hiển thị tất cả các bố cục có trong bản vẽ CAD. 
## Điều kiện tiên quyết
Trước khi bắt tay vào hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Hiểu biết cơ bản về Phát triển .NET: Làm quen với các nguyên tắc cơ bản về phát triển .NET sẽ có ích trong việc hiểu các bước triển khai được nêu trong hướng dẫn này.
2.  Cài đặt GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt thư viện GroupDocs.Viewer cho .NET. Bạn có thể tải nó xuống từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
3. Tệp bản vẽ CAD: Lấy tệp bản vẽ CAD mà bạn định kết xuất. Chúng có thể bao gồm các tệp DWG có nhiều bố cục.
4. Môi trường phát triển: Thiết lập môi trường phát triển ưa thích của bạn với các công cụ và phần phụ thuộc cần thiết.

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
Xác định thư mục nơi bạn muốn lưu đầu ra được hiển thị.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Thiết lập định dạng cho đường dẫn tệp của các trang được hiển thị. Trong trường hợp này, các trang sẽ được lưu dưới dạng tệp HTML.
## Bước 3: Khởi tạo đối tượng người xem
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Tạo một phiên bản của lớp Viewer, chuyển đường dẫn đến tệp bản vẽ CAD làm tham số.
## Bước 4: Định cấu hình tùy chọn chế độ xem HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Định cấu hình các tùy chọn chế độ xem HTML, chỉ định rằng bố cục sẽ được hiển thị cho bản vẽ CAD.
## Bước 5: Kết xuất bản vẽ CAD
```csharp
viewer.View(options);
```
Gọi phương thức View của đối tượng Viewer, chuyển các tùy chọn đã định cấu hình để hiển thị bản vẽ CAD.
## Bước 6: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc hiển thị thành công và vị trí của thư mục đầu ra.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách sử dụng GroupDocs.Viewer cho .NET để hiển thị tất cả các bố cục có trong bản vẽ CAD. Bằng cách làm theo hướng dẫn từng bước và triển khai các đoạn mã được cung cấp, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của mình, từ đó nâng cao khả năng hiển thị tài liệu.
## Câu hỏi thường gặp
### GroupDocs.Viewer có tương thích với nhiều định dạng CAD khác nhau không?
Có, GroupDocs.Viewer hỗ trợ hiển thị bản vẽ CAD ở các định dạng như DWG và DXF.
### Tôi có thể tùy chỉnh kết quả hiển thị theo yêu cầu của ứng dụng không?
Hoàn toàn có thể, GroupDocs.Viewer cung cấp nhiều tùy chọn để tùy chỉnh kết quả hiển thị, bao gồm chất lượng hình ảnh, kích thước trang, v.v.
### GroupDocs.Viewer có yêu cầu bất kỳ giấy phép bổ sung nào để sử dụng cho mục đích thương mại không?
Có, để sử dụng cho mục đích thương mại, bạn có thể cần phải có giấy phép. Bạn có thể lấy giấy phép tạm thời cho mục đích thử nghiệm hoặc mua giấy phép thương mại từ trang web.
### Tôi có thể hiển thị bản vẽ CAD không đồng bộ với GroupDocs.Viewer không?
Có, GroupDocs.Viewer cung cấp khả năng hiển thị không đồng bộ, cho phép xử lý hiệu quả các bản vẽ CAD lớn mà không chặn luồng chính.
### GroupDocs.Viewer có cung cấp hỗ trợ khắc phục sự cố và hỗ trợ kỹ thuật không?
 Chắc chắn bạn có thể tìm kiếm sự hỗ trợ, trợ giúp từ diễn đàn cộng đồng GroupDocs.Viewer, có thể truy cập[đây](https://forum.groupdocs.com/c/viewer/9).