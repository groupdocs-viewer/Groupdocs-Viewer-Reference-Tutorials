---
"description": "Tìm hiểu cách kết xuất hình ảnh AI dễ dàng trong các ứng dụng .NET bằng GroupDocs.Viewer cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch."
"linktitle": "Kết xuất hình ảnh AI"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất hình ảnh AI"
"url": "/vi/net/image-rendering/render-ai-images/"
"weight": 10
---

# Kết xuất hình ảnh AI

## Giới thiệu
GroupDocs.Viewer for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển dễ dàng kết xuất nhiều định dạng tài liệu khác nhau trong các ứng dụng .NET của họ. Cho dù bạn cần hiển thị hình ảnh AI, PDF hay các loại tài liệu khác, GroupDocs.Viewer đều đơn giản hóa quy trình, cung cấp nhiều định dạng đầu ra để tích hợp liền mạch vào các dự án của bạn. Hướng dẫn này sẽ hướng dẫn bạn từng bước kết xuất hình ảnh AI bằng GroupDocs.Viewer for .NET.

![Kết xuất hình ảnh AI với GroupDocs.Viewer cho .NET](/viewer/image-rendering/render-ai-images.png)

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
1. Visual Studio: Cài đặt Visual Studio IDE trên hệ thống của bạn.
2. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [trang web](https://releases.groupdocs.com/viewer/net/).
3. Kiến thức cơ bản về C#: Cần phải quen thuộc với ngôn ngữ lập trình C# để hiểu các ví dụ mã.

## Nhập không gian tên
Trong dự án C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các chức năng của GroupDocs.Viewer cho .NET.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Kết xuất hình ảnh AI bằng GroupDocs.Viewer cho .NET bao gồm một số bước, mỗi bước phục vụ cho một định dạng đầu ra cụ thể. Dưới đây, chúng tôi sẽ chia nhỏ quy trình thành các bước riêng lẻ để rõ ràng hơn.
## Bước 1: Chỉ định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Kết xuất sang HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 3: Kết xuất sang JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 4: Kết xuất thành PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Bước 5: Kết xuất thành PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Phần kết luận
GroupDocs.Viewer for .NET cung cấp giải pháp liền mạch để kết xuất hình ảnh AI và nhiều định dạng tài liệu khác nhau trong các ứng dụng .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, các nhà phát triển có thể dễ dàng tích hợp khả năng kết xuất tài liệu vào các dự án của họ.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh giao diện đầu ra khi kết xuất hình ảnh AI không?
Có, GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện đầu ra, bao gồm kích thước trang, chất lượng hình ảnh, v.v.
### Có phiên bản dùng thử nào để thử nghiệm không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ GroupDocs [trang web](https://releases.groupdocs.com/viewer/net/) để đánh giá các tính năng của thư viện trước khi mua.
### GroupDocs.Viewer có hỗ trợ hiển thị hình ảnh AI được mã hóa không?
Có, GroupDocs.Viewer cho .NET hỗ trợ kết xuất hình ảnh AI được mã hóa với khóa giải mã phù hợp được cung cấp.
### Tôi có thể hiển thị hình ảnh AI trực tiếp từ URL không?
Có, GroupDocs.Viewer cho .NET cho phép hiển thị hình ảnh AI từ URL bằng cách chỉ định đường dẫn URL thay vì đường dẫn tệp cục bộ.
### Có hỗ trợ kỹ thuật cho GroupDocs.Viewer dành cho .NET không?
Có, hỗ trợ kỹ thuật có sẵn thông qua GroupDocs [diễn đàn](https://forum.groupdocs.com/c/viewer/9), nơi bạn có thể đặt câu hỏi, báo cáo vấn đề và tìm kiếm sự trợ giúp từ cộng đồng.