---
title: Kết xuất tài liệu sang JPGPNG
linktitle: Kết xuất tài liệu sang JPGPNG
second_title: API GroupDocs.Viewer .NET
description: Khám phá cách kết xuất liền mạch các tài liệu sang JPG/PNG trong .NET bằng GroupDocs.Viewer để nâng cao trải nghiệm và năng suất của người dùng.
weight: 10
url: /vi/net/rendering-documents-images/render-jpg-png/
---

# Kết xuất tài liệu sang JPGPNG

## Giới thiệu

Trong thế giới phát triển .NET, việc xử lý tài liệu một cách hiệu quả là điều cần thiết cho nhiều ứng dụng khác nhau. Cho dù bạn đang xây dựng hệ thống quản lý tài liệu, nền tảng thương mại điện tử hay ứng dụng giàu nội dung thì khả năng xem tài liệu một cách liền mạch là rất quan trọng. Đây là lúc GroupDocs.Viewer dành cho .NET phát huy tác dụng, cung cấp giải pháp toàn diện để hiển thị tài liệu sang nhiều định dạng khác nhau như JPG và PNG.

## Điều kiện tiên quyết

Trước khi đi sâu vào sử dụng GroupDocs.Viewer cho .NET, bạn cần đảm bảo một số điều kiện tiên quyết:

1. Môi trường phát triển .NET: Đảm bảo rằng bạn đã thiết lập môi trường phát triển .NET đang hoạt động trên máy của mình. Điều này bao gồm việc cài đặt .NET SDK.

2. Giấy phép GroupDocs.Viewer: Nhận giấy phép hợp lệ cho GroupDocs.Viewer. Bạn có thể mua giấy phép hoặc sử dụng giấy phép tạm thời cho mục đích đánh giá.

3.  Cài đặt: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ gói được cung cấp[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).

4. Tệp tài liệu: Chuẩn bị sẵn các tệp tài liệu mà bạn muốn hiển thị. GroupDocs.Viewer hỗ trợ nhiều định dạng khác nhau bao gồm DOCX, PDF, PPT, v.v.

## Nhập không gian tên

Để bắt đầu hiển thị tài liệu bằng GroupDocs.Viewer cho .NET, bạn cần nhập các vùng tên cần thiết vào dự án của mình. Điều này cho phép bạn truy cập các chức năng được cung cấp bởi thư viện.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Hiển thị tài liệu sang định dạng JPG hoặc PNG là một quá trình đơn giản với GroupDocs.Viewer dành cho .NET. Dưới đây là hướng dẫn từng bước để giúp bạn đạt được điều này:

## Bước 1: Xác định thư mục đầu ra

Đầu tiên, xác định thư mục nơi bạn muốn lưu các trang được hiển thị. Thư mục này phải tồn tại và ứng dụng có thể truy cập được.

```csharp
string outputDirectory = "Your Document Directory";
```

## Bước 2: Xác định định dạng đường dẫn tệp trang

 Chỉ định định dạng cho đường dẫn tệp của từng trang được hiển thị. GroupDocs.Viewer sẽ thay thế`{0}` với số trang trong khi lưu tập tin.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Bước 3: Khởi tạo đối tượng người xem

 Tạo một thể hiện của`Viewer` class bằng cách cung cấp đường dẫn đến tệp tài liệu bạn muốn kết xuất.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Mã để hiển thị ở đây
}
```

## Bước 4: Xác định tùy chọn kết xuất

Chỉ định các tùy chọn kết xuất theo yêu cầu của bạn. Để hiển thị JPG/PNG, bạn sẽ sử dụng`JpgViewOptions` hoặc`PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Bước 5: Kết xuất tài liệu

 Gọi`View` phương pháp của`Viewer` đối tượng và chuyển các tùy chọn kết xuất được tạo trước đó.

```csharp
viewer.View(options);
```

## Bước 6: Kết quả đầu ra

Sau khi quá trình hiển thị hoàn tất, bạn có thể thông báo cho người dùng về quá trình hiển thị thành công và cung cấp thư mục lưu các trang được hiển thị.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận

Tóm lại, GroupDocs.Viewer cho .NET cung cấp một giải pháp mạnh mẽ để hiển thị tài liệu sang nhiều định dạng khác nhau, bao gồm JPG và PNG. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch chức năng kết xuất tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm và năng suất của người dùng.

## Câu hỏi thường gặp

### Câu hỏi: Tôi có thể hiển thị các tài liệu không phải DOCX bằng GroupDocs.Viewer cho .NET không?

Trả lời: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, PPT, XLS, v.v.

### Câu hỏi: Có bản dùng thử miễn phí GroupDocs.Viewer dành cho .NET không?

 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.groupdocs.com/).

### Hỏi: Làm cách nào tôi có thể xin được giấy phép tạm thời cho mục đích đánh giá?

Đáp: Bạn có thể yêu cầu giấy phép tạm thời từ[đây](https://purchase.groupdocs.com/temporary-license/).

### Câu hỏi: Tôi có thể tìm tài liệu về GroupDocs.Viewer dành cho .NET ở đâu?

 A: Tài liệu chi tiết có sẵn[đây](https://tutorials.groupdocs.com/viewer/net/).

### Câu hỏi: Tôi có thể nhận hỗ trợ hoặc đặt câu hỏi liên quan đến GroupDocs.Viewer cho .NET ở đâu?

 A: Bạn có thể truy cập diễn đàn hỗ trợ[đây](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ.