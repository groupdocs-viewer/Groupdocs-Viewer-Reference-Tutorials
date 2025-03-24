---
title: Hiển thị các cột và hàng ẩn
linktitle: Hiển thị các cột và hàng ẩn
second_title: API GroupDocs.Viewer .NET
description: Dễ dàng mở khóa dữ liệu ẩn trong bảng tính bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để hiển thị các cột và hàng bị ẩn.
weight: 13
url: /vi/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## Giới thiệu
Trong lĩnh vực trực quan hóa tài liệu, GroupDocs.Viewer dành cho .NET nổi bật như một công cụ mạnh mẽ tạo điều kiện hiển thị liền mạch các định dạng tài liệu khác nhau. Một khả năng hấp dẫn là khả năng hiển thị các cột và hàng ẩn trong bảng tính. Trong hướng dẫn này, chúng tôi sẽ đi sâu vào các bước để mở khóa tính năng này và giải phóng tiềm năng dữ liệu của bạn.
## Điều kiện tiên quyết
Trước khi bắt đầu cuộc hành trình này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- GroupDocs.Viewer dành cho .NET: Đảm bảo bạn đã cài đặt phiên bản mới nhất. Nếu không, bạn có thể tải xuống từ[Trang web chính thức](https://releases.groupdocs.com/viewer/net/).
- Tệp Tài liệu: Chuẩn bị một tài liệu mẫu ở định dạng bảng tính (ví dụ: SAMPLE.XLSX) để thử nghiệm các cột và hàng ẩn.
- Môi trường phát triển: Thiết lập môi trường làm việc, tốt nhất là sử dụng Visual Studio hoặc bất kỳ IDE phù hợp nào khác để phát triển .NET.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy nhập các vùng tên cần thiết để tận dụng hiệu quả các chức năng của GroupDocs.Viewer:
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
Xác định thư mục đầu ra nơi các trang HTML được hiển thị sẽ được lưu trữ. Điều chỉnh định dạng đường dẫn file cho phù hợp.
## Bước 2: Khởi tạo tùy chọn Viewer và Cấu hình
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Tạo phiên bản Trình xem bằng cách cung cấp đường dẫn đến tài liệu bảng tính của bạn. Định cấu hình tùy chọn chế độ xem HTML để nhúng tài nguyên và cho phép hiển thị các cột và hàng ẩn.
## Bước 3: Thực hiện quá trình kết xuất
```csharp
    viewer.View(options);
}
```
Gọi phương thức View trên đối tượng trình xem, chuyển các tùy chọn đã định cấu hình. Điều này bắt đầu quá trình kết xuất.
## Bước 4: Kiểm tra đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Xác minh việc hiển thị thành công tài liệu nguồn và định vị đầu ra trong thư mục được chỉ định.
## Phần kết luận
Việc mở khóa các cột và hàng ẩn trong bảng tính của bạn trở nên dễ dàng với GroupDocs.Viewer dành cho .NET. Hướng dẫn này đã trang bị cho bạn các bước cần thiết để tiết lộ dữ liệu bị ẩn, cung cấp cái nhìn toàn diện hơn về tài liệu của bạn.
## Các câu hỏi thường gặp
### Tôi có thể hiển thị các cột và hàng ẩn ở các định dạng tài liệu khác ngoài bảng tính không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm Word, PDF và PowerPoint, ngoài bảng tính.
### Có giới hạn về số lượng cột và hàng ẩn có thể được hiển thị không?
GroupDocs.Viewer xử lý hiệu quả việc hiển thị cho nhiều cột và hàng ẩn. Tuy nhiên, các trường hợp cực đoan với lượng dữ liệu ẩn lớn có thể ảnh hưởng đến hiệu suất.
### Tôi có thể tùy chỉnh định dạng đầu ra của dữ liệu được hiển thị không?
Tuyệt đối! GroupDocs.Viewer cung cấp các tùy chọn linh hoạt để tùy chỉnh đầu ra, cho phép bạn điều chỉnh dữ liệu được hiển thị theo nhu cầu cụ thể của mình.
### Có bất kỳ cân nhắc cấp phép nào khi sử dụng GroupDocs.Viewer không?
 Có, hãy đảm bảo bạn có giấy phép phù hợp cho việc sử dụng của mình. Khám phá các tùy chọn cấp phép tại[Mua tài liệu nhóm](https://purchase.groupdocs.com/buy) hoặc có được một[giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/) để thử nghiệm.
### Tôi có thể tìm kiếm sự trợ giúp hoặc kết nối với cộng đồng GroupDocs để được hỗ trợ ở đâu?
 Tham quan[Diễn đàn GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ, thảo luận và tương tác cộng đồng.