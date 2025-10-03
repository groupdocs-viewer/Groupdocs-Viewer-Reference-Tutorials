---
"description": "Tìm hiểu cách dễ dàng kết xuất hình ảnh CMX thành nhiều định dạng khác nhau bằng GroupDocs.Viewer cho .NET. Nâng cao khả năng quản lý tài liệu của bạn."
"linktitle": "Kết xuất hình ảnh CMX"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất hình ảnh CMX"
"url": "/vi/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Kết xuất hình ảnh CMX

## Giới thiệu
Trong lĩnh vực quản lý và thao tác tài liệu, việc kết xuất hình ảnh từ nhiều định dạng khác nhau là một nhiệm vụ then chốt. GroupDocs.Viewer for .NET đơn giản hóa quy trình này bằng cách cung cấp các chức năng toàn diện để kết xuất hình ảnh CMX thành nhiều định dạng khác nhau như HTML, JPG, PNG và PDF. Hướng dẫn này sẽ hướng dẫn bạn từng bước trong quy trình kết xuất hình ảnh CMX bằng GroupDocs.Viewer for .NET.

![Kết xuất hình ảnh CMX với GroupDocs.Viewer cho .NET](/viewer/image-rendering/render-cmx-images.png)

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
1. GroupDocs.Viewer cho Thư viện .NET: Tải xuống và cài đặt GroupDocs.Viewer cho thư viện .NET từ [đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển đang hoạt động bằng .NET framework.
3. Tệp hình ảnh CMX: Lấy tệp hình ảnh CMX mà bạn muốn kết xuất.

## Nhập không gian tên
Trước khi tiếp tục, hãy đảm bảo nhập các không gian tên cần thiết để truy cập các chức năng của GroupDocs.Viewer trong ứng dụng .NET của bạn:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Kết xuất sang HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Thiết lập thư mục mà bạn muốn lưu trữ các tệp HTML được hiển thị.
- Chỉ định định dạng đường dẫn tệp: Xác định định dạng cho tệp HTML đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một thể hiện của lớp Viewer với tệp hình ảnh CMX.
- Tùy chọn hiển thị HTML: Cấu hình các tùy chọn hiển thị HTML, chẳng hạn như nhúng tài nguyên.
- Hiển thị CMX thành HTML: Gọi phương thức View của đối tượng trình xem để hiển thị hình ảnh CMX thành HTML.
## Kết xuất sang JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Thiết lập thư mục lưu trữ các tệp JPG đã kết xuất.
- Chỉ định định dạng đường dẫn tệp: Xác định định dạng cho tệp JPG đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một thể hiện của lớp Viewer với tệp hình ảnh CMX.
- Tùy chọn kết xuất JPG: Cấu hình tùy chọn kết xuất JPG.
- Kết xuất CMX thành JPG: Gọi phương thức View của đối tượng trình xem để kết xuất hình ảnh CMX thành JPG.
## Kết xuất sang PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Thiết lập thư mục lưu trữ các tệp PNG đã kết xuất.
- Chỉ định định dạng đường dẫn tệp: Xác định định dạng cho tệp PNG đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một thể hiện của lớp Viewer với tệp hình ảnh CMX.
- Tùy chọn kết xuất PNG: Cấu hình tùy chọn kết xuất PNG.
- Kết xuất CMX thành PNG: Gọi phương thức View của đối tượng trình xem để kết xuất hình ảnh CMX thành PNG.
## Kết xuất sang PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Thiết lập thư mục lưu trữ tệp PDF đã kết xuất.
- Chỉ định định dạng đường dẫn tệp: Xác định định dạng cho tệp PDF đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một thể hiện của lớp Viewer với tệp hình ảnh CMX.
- Tùy chọn kết xuất PDF: Cấu hình tùy chọn kết xuất PDF.
- Kết xuất CMX thành PDF: Gọi phương thức View của đối tượng trình xem để kết xuất hình ảnh CMX thành PDF.

## Phần kết luận
Tóm lại, GroupDocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để kết xuất hình ảnh CMX thành nhiều định dạng khác nhau một cách liền mạch. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tích hợp khả năng kết xuất hình ảnh CMX vào các ứng dụng .NET của mình, nâng cao hiệu quả quản lý tài liệu.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các trang cụ thể của hình ảnh CMX không?
Có, bạn có thể hiển thị các trang cụ thể bằng cách chỉ định số trang trong tùy chọn hiển thị.
### GroupDocs.Viewer cho .NET có tương thích với tất cả các nền tảng .NET không?
Có, GroupDocs.Viewer cho .NET tương thích với nhiều nền tảng .NET, bao gồm .NET Core và .NET Framework.
### GroupDocs.Viewer có hỗ trợ hiển thị hình ảnh CMX được mã hóa không?
Có, GroupDocs.Viewer hỗ trợ kết xuất hình ảnh CMX được mã hóa với khóa giải mã phù hợp.
### Tôi có thể tùy chỉnh tùy chọn kết xuất cho các định dạng đầu ra khác nhau không?
Đúng vậy, GroupDocs.Viewer cung cấp nhiều tùy chọn để tùy chỉnh các thông số kết xuất dựa trên yêu cầu của bạn.
### Có diễn đàn cộng đồng nào hỗ trợ GroupDocs.Viewer không?
Có, bạn có thể tìm kiếm sự hỗ trợ và tham gia cộng đồng GroupDocs.Viewer trên diễn đàn hỗ trợ [đây](https://forum.groupdocs.com/c/viewer/9).