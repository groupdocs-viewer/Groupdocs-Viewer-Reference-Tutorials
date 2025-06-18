---
"description": "Mở khóa dữ liệu ẩn trong bảng tính một cách dễ dàng bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để hiển thị các cột và hàng ẩn."
"linktitle": "Hiển thị các cột và hàng ẩn"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị các cột và hàng ẩn"
"url": "/vi/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
---

# Hiển thị các cột và hàng ẩn

## Giới thiệu
Trong lĩnh vực trực quan hóa tài liệu, GroupDocs.Viewer for .NET nổi bật là một công cụ mạnh mẽ giúp tạo điều kiện kết xuất liền mạch nhiều định dạng tài liệu khác nhau. Một khả năng hấp dẫn là khả năng hiển thị các cột và hàng ẩn trong bảng tính. Trong hướng dẫn này, chúng ta sẽ đi sâu vào các bước để mở khóa tính năng này và giải phóng tiềm năng của dữ liệu của bạn.
## Điều kiện tiên quyết
Trước khi bắt đầu hành trình này, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
- GroupDocs.Viewer cho .NET: Đảm bảo bạn đã cài đặt phiên bản mới nhất. Nếu chưa, bạn có thể tải xuống từ [trang web chính thức](https://releases.groupdocs.com/viewer/net/).
- Tệp tài liệu: Chuẩn bị một tài liệu mẫu ở định dạng bảng tính (ví dụ: SAMPLE.XLSX) để thử nghiệm với các cột và hàng ẩn.
- Môi trường phát triển: Thiết lập môi trường làm việc, tốt nhất là sử dụng Visual Studio hoặc bất kỳ IDE phù hợp nào khác để phát triển .NET.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy nhập các không gian tên cần thiết để tận dụng hiệu quả các chức năng của GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Thiết lập thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Xác định thư mục đầu ra nơi các trang HTML được hiển thị sẽ được lưu trữ. Điều chỉnh định dạng đường dẫn tệp cho phù hợp.
## Bước 2: Khởi tạo Viewer và Cấu hình Tùy chọn
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Tạo một phiên bản Viewer bằng cách cung cấp đường dẫn đến tài liệu bảng tính của bạn. Cấu hình tùy chọn chế độ xem HTML để nhúng tài nguyên và cho phép hiển thị các cột và hàng ẩn.
## Bước 3: Thực hiện quá trình kết xuất
```csharp
    viewer.View(options);
}
```
Gọi phương thức View trên đối tượng trình xem, truyền các tùy chọn đã cấu hình. Thao tác này sẽ khởi tạo quá trình kết xuất.
## Bước 4: Kiểm tra đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Xác minh việc kết xuất thành công tài liệu nguồn và định vị đầu ra trong thư mục đã chỉ định.
## Phần kết luận
Mở khóa các cột và hàng ẩn trong bảng tính của bạn trở nên dễ dàng với GroupDocs.Viewer cho .NET. Hướng dẫn này cung cấp cho bạn các bước cần thiết để hiển thị dữ liệu ẩn, cung cấp chế độ xem toàn diện hơn về tài liệu của bạn.
## Những câu hỏi thường gặp
### Tôi có thể hiển thị các cột và hàng ẩn trong các định dạng tài liệu khác ngoài bảng tính không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm Word, PDF và PowerPoint, ngoài bảng tính.
### Có giới hạn số lượng cột và hàng ẩn có thể hiển thị không?
GroupDocs.Viewer xử lý hiệu quả việc kết xuất cho nhiều cột và hàng ẩn. Tuy nhiên, các trường hợp cực đoan với lượng dữ liệu ẩn lớn có thể ảnh hưởng đến hiệu suất.
### Tôi có thể tùy chỉnh định dạng đầu ra của dữ liệu được kết xuất không?
Hoàn toàn đúng! GroupDocs.Viewer cung cấp các tùy chọn linh hoạt để tùy chỉnh đầu ra, cho phép bạn điều chỉnh dữ liệu được kết xuất theo nhu cầu cụ thể của mình.
### Có bất kỳ cân nhắc nào về cấp phép khi sử dụng GroupDocs.Viewer không?
Có, hãy đảm bảo bạn có giấy phép phù hợp cho mục đích sử dụng của mình. Khám phá các tùy chọn cấp phép tại [Mua GroupDocs](https://purchase.groupdocs.com/buy) hoặc có được một [giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/) để thử nghiệm.
### Tôi có thể tìm kiếm sự trợ giúp hoặc kết nối với cộng đồng GroupDocs để được hỗ trợ ở đâu?
Ghé thăm [Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để hỗ trợ, thảo luận và tương tác cộng đồng.