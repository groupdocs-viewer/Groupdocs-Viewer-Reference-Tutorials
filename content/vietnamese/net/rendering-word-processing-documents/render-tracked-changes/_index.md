---
"description": "Khám phá cách hiển thị các thay đổi được theo dõi trong tài liệu một cách dễ dàng bằng GroupDocs.Viewer cho .NET. Nâng cao hiệu quả quản lý tài liệu của bạn."
"linktitle": "Hiển thị những thay đổi được theo dõi"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị những thay đổi được theo dõi"
"url": "/vi/net/rendering-word-processing-documents/render-tracked-changes/"
"weight": 10
type: docs
---
# Hiển thị những thay đổi được theo dõi

## Giới thiệu
Trong kỷ nguyên số ngày nay, việc quản lý và xem tài liệu hiệu quả là rất quan trọng đối với cả doanh nghiệp và cá nhân. Với sự ra đời của các công nghệ tiên tiến, các giải pháp như GroupDocs.Viewer cho .NET đã cách mạng hóa cách chúng ta tương tác với nhiều định dạng tài liệu khác nhau, bao gồm tài liệu Word, PDF, v.v. Trong hướng dẫn toàn diện này, chúng ta sẽ đi sâu vào cách tận dụng GroupDocs.Viewer cho .NET để hiển thị các thay đổi được theo dõi trong tài liệu của bạn một cách liền mạch.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho Cài đặt .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [trang web](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework trên hệ thống của mình.
3. Thư mục tài liệu: Chuẩn bị một thư mục nơi bạn sẽ lưu trữ tài liệu.

## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án của bạn. Các không gian tên này rất cần thiết để sử dụng hiệu quả các chức năng của GroupDocs.Viewer.
## Các bước thực hiện:
1. Mở IDE của bạn: Khởi chạy Môi trường phát triển tích hợp (IDE) mà bạn thích, chẳng hạn như Visual Studio.
2. Tạo hoặc mở dự án của bạn: Bắt đầu một dự án mới hoặc mở một dự án hiện có mà bạn định sử dụng GroupDocs.Viewer.
3. Nhập không gian tên: Trong tệp dự án hoặc tệp mã của bạn, hãy thêm các không gian tên sau:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Bây giờ, chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hướng dẫn bạn cách hiển thị những thay đổi được theo dõi bằng GroupDocs.Viewer cho .NET.
## Bước 1: Thiết lập thư mục đầu ra
Đầu tiên, hãy xác định thư mục mà bạn muốn lưu kết quả đã kết xuất.
```csharp
string outputDirectory = "Your Document Directory";
```
Thay thế `"Your Document Directory"` với đường dẫn đến thư mục bạn mong muốn.
## Bước 2: Xác định định dạng đường dẫn tệp trang
Chỉ định định dạng cho đường dẫn tệp trang. Định dạng này sẽ xác định cách các trang được hiển thị được đặt tên và lưu trữ.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Đây, `"page_{0}.html"` chỉ ra rằng các trang sẽ được đặt tên là `page_1.html`, `page_2.html`, và vân vân.
## Bước 3: Khởi tạo đối tượng Viewer
Khởi tạo một `Viewer` đối tượng bằng cách truyền đường dẫn của tài liệu làm đối số.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // Mã tiếp tục ở bước tiếp theo...
}
```
Đảm bảo thay thế `TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` với đường dẫn đến tài liệu của bạn.
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
Cấu hình tùy chọn chế độ xem HTML để tùy chỉnh cài đặt hiển thị, chẳng hạn như hiển thị những thay đổi được theo dõi.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
Bước này cho phép hiển thị những thay đổi được theo dõi trong HTML đầu ra.
## Bước 5: Kết xuất tài liệu
Hiển thị tài liệu bằng các tùy chọn đã cấu hình.
```csharp
viewer.View(options);
```
Lệnh này khởi tạo quá trình kết xuất dựa trên các thiết lập được cung cấp.
## Bước 6: Hiển thị thư mục đầu ra
Thông báo cho người dùng về vị trí lưu trữ kết quả đã hiển thị.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo này thông báo cho người dùng về việc kết xuất thành công và nơi tìm tệp đầu ra.

## Phần kết luận
Tóm lại, GroupDocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để hiển thị các thay đổi được theo dõi trong tài liệu một cách dễ dàng. Bằng cách làm theo hướng dẫn từng bước được nêu trong bài viết này, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của mình, nâng cao hiệu quả quản lý tài liệu.
## Câu hỏi thường gặp
### Tôi có thể hiển thị những thay đổi được theo dõi ở nhiều định dạng tài liệu khác nhau bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer hỗ trợ hiển thị các thay đổi được theo dõi ở nhiều định dạng, bao gồm DOCX, PDF, v.v.
### GroupDocs.Viewer cho .NET có tương thích với tất cả các phiên bản .NET Framework không?
Có, GroupDocs.Viewer cho .NET tương thích với nhiều phiên bản khác nhau của .NET Framework, đảm bảo khả năng tương thích rộng rãi.
### GroupDocs.Viewer có cung cấp bản dùng thử miễn phí nào cho mục đích thử nghiệm không?
Có, bạn có thể dùng thử miễn phí GroupDocs.Viewer để khám phá các tính năng trước khi quyết định mua.
### Tôi có thể tùy chỉnh cài đặt kết xuất để đáp ứng các yêu cầu cụ thể không?
Đúng vậy, GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh, cho phép bạn điều chỉnh quy trình kết xuất theo nhu cầu của mình.
### Tôi có thể tìm kiếm sự trợ giúp ở đâu nếu gặp bất kỳ sự cố hoặc có thắc mắc nào về GroupDocs.Viewer?
Để được hỗ trợ và trợ giúp cộng đồng, bạn có thể truy cập diễn đàn GroupDocs.Viewer tại [liên kết này](https://forum.groupdocs.com/c/viewer/9).