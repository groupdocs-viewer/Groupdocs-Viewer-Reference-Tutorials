---
title: Kết xuất hình ảnh CMX
linktitle: Kết xuất hình ảnh CMX
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách dễ dàng hiển thị hình ảnh CMX thành nhiều định dạng khác nhau bằng GroupDocs.Viewer cho .NET. Tăng cường quản lý tài liệu của bạn.
type: docs
weight: 13
url: /vi/net/image-rendering/render-cmx-images/
---
## Giới thiệu
Trong lĩnh vực quản lý và thao tác tài liệu, việc hiển thị hình ảnh từ nhiều định dạng khác nhau là một nhiệm vụ then chốt. GroupDocs.Viewer dành cho .NET đơn giản hóa quy trình này bằng cách cung cấp các chức năng toàn diện để hiển thị hình ảnh CMX thành các định dạng khác nhau như HTML, JPG, PNG và PDF. Hướng dẫn này sẽ hướng dẫn bạn quy trình từng bước hiển thị hình ảnh CMX bằng GroupDocs.Viewer cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  GroupDocs.Viewer for .NET Library: Tải xuống và cài đặt thư viện GroupDocs.Viewer for .NET từ[đây](https://releases.groupdocs.com/viewer/net/).
2. Môi trường phát triển: Có môi trường phát triển làm việc được thiết lập với .NET framework.
3. Tệp hình ảnh CMX: Lấy tệp hình ảnh CMX mà bạn muốn hiển thị.

## Nhập không gian tên
Trước khi tiếp tục, hãy đảm bảo nhập các vùng tên cần thiết để truy cập các chức năng GroupDocs.Viewer trong ứng dụng .NET của bạn:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Hiển thị sang HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Đặt thư mục nơi bạn muốn lưu trữ các tệp HTML được hiển thị.
- Xác định định dạng đường dẫn tệp: Xác định định dạng cho tệp HTML đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một phiên bản của lớp Viewer bằng tệp hình ảnh CMX.
- Tùy chọn hiển thị HTML: Định cấu hình các tùy chọn hiển thị HTML, chẳng hạn như nhúng tài nguyên.
- Kết xuất CMX sang HTML: Gọi phương thức View của đối tượng trình xem để hiển thị hình ảnh CMX thành HTML.
## Hiển thị sang JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Đặt thư mục để lưu trữ các tệp JPG được hiển thị.
- Specify File Path Format: Xác định định dạng cho file JPG đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một phiên bản của lớp Viewer bằng tệp hình ảnh CMX.
- Tùy chọn hiển thị JPG: Định cấu hình tùy chọn hiển thị JPG.
- Kết xuất CMX sang JPG: Gọi phương thức View của đối tượng trình xem để hiển thị hình ảnh CMX thành JPG.
## Hiển thị sang PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Đặt thư mục để lưu trữ các tệp PNG được hiển thị.
- Specify File Path Format: Xác định định dạng cho file PNG đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một phiên bản của lớp Viewer bằng tệp hình ảnh CMX.
- Tùy chọn hiển thị PNG: Định cấu hình tùy chọn hiển thị PNG.
- Kết xuất CMX thành PNG: Gọi phương thức View của đối tượng trình xem để hiển thị hình ảnh CMX thành PNG.
## Hiển thị sang PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Xác định thư mục đầu ra: Đặt thư mục để lưu trữ tệp PDF được hiển thị.
- Specify File Path Format: Xác định định dạng cho file PDF đầu ra.
- Khởi tạo đối tượng Viewer: Tạo một phiên bản của lớp Viewer bằng tệp hình ảnh CMX.
- Tùy chọn hiển thị PDF: Định cấu hình tùy chọn hiển thị PDF.
- Hiển thị CMX thành PDF: Gọi phương thức Xem của đối tượng trình xem để hiển thị hình ảnh CMX thành PDF.

## Phần kết luận
Tóm lại, GroupDocs.Viewer cho .NET cung cấp một giải pháp mạnh mẽ để hiển thị hình ảnh CMX thành nhiều định dạng khác nhau một cách liền mạch. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tích hợp khả năng kết xuất hình ảnh CMX vào các ứng dụng .NET của mình, nâng cao hiệu quả quản lý tài liệu.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các trang cụ thể của hình ảnh CMX không?
Có, bạn có thể hiển thị các trang cụ thể bằng cách chỉ định số trang trong tùy chọn hiển thị.
### GroupDocs.Viewer cho .NET có tương thích với tất cả các khung .NET không?
Có, GroupDocs.Viewer cho .NET tương thích với nhiều khung .NET, bao gồm .NET Core và .NET Framework.
### GroupDocs.Viewer có hỗ trợ hiển thị hình ảnh CMX được mã hóa không?
Có, GroupDocs.Viewer hỗ trợ hiển thị hình ảnh CMX được mã hóa bằng khóa giải mã thích hợp.
### Tôi có thể tùy chỉnh các tùy chọn hiển thị cho các định dạng đầu ra khác nhau không?
Hoàn toàn có thể, GroupDocs.Viewer cung cấp các tùy chọn mở rộng để tùy chỉnh các tham số hiển thị dựa trên yêu cầu của bạn.
### Có diễn đàn cộng đồng nào hỗ trợ GroupDocs.Viewer không?
 Có, bạn có thể tìm kiếm sự trợ giúp và tương tác với cộng đồng GroupDocs.Viewer trên diễn đàn hỗ trợ[đây](https://forum.groupdocs.com/c/viewer/9).