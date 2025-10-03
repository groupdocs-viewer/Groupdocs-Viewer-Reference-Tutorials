---
"description": "Khám phá cách chuyển đổi tài liệu sang JPG/PNG trong .NET một cách liền mạch bằng GroupDocs.Viewer để nâng cao trải nghiệm và năng suất của người dùng."
"linktitle": "Kết xuất tài liệu sang JPGPNG"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất tài liệu sang JPGPNG"
"url": "/vi/net/rendering-documents-images/render-jpg-png/"
"weight": 10
type: docs
---
# Kết xuất tài liệu sang JPGPNG

## Giới thiệu

Trong thế giới phát triển .NET, việc xử lý tài liệu hiệu quả là điều cần thiết cho nhiều ứng dụng khác nhau. Cho dù bạn đang xây dựng hệ thống quản lý tài liệu, nền tảng thương mại điện tử hay ứng dụng giàu nội dung, khả năng xem tài liệu liền mạch là rất quan trọng. Đây chính là lúc GroupDocs.Viewer for .NET phát huy tác dụng, cung cấp giải pháp toàn diện để hiển thị tài liệu sang nhiều định dạng khác nhau như JPG và PNG.

## Điều kiện tiên quyết

Trước khi bắt đầu sử dụng GroupDocs.Viewer cho .NET, bạn cần đảm bảo một số điều kiện tiên quyết sau:

1. Môi trường phát triển .NET: Đảm bảo rằng bạn có môi trường phát triển .NET đang hoạt động được thiết lập trên máy của mình. Điều này bao gồm việc cài đặt .NET SDK.

2. Giấy phép GroupDocs.Viewer: Nhận giấy phép hợp lệ cho GroupDocs.Viewer. Bạn có thể mua giấy phép hoặc sử dụng giấy phép tạm thời cho mục đích đánh giá.

3. Cài đặt: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).

4. Tệp tài liệu: Chuẩn bị các tệp tài liệu mà bạn muốn hiển thị. GroupDocs.Viewer hỗ trợ nhiều định dạng khác nhau bao gồm DOCX, PDF, PPT, v.v.

## Nhập không gian tên

Để bắt đầu kết xuất tài liệu bằng GroupDocs.Viewer cho .NET, bạn cần nhập các không gian tên cần thiết vào dự án của mình. Điều này cho phép bạn truy cập các chức năng do thư viện cung cấp.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Kết xuất tài liệu sang định dạng JPG hoặc PNG là một quá trình đơn giản với GroupDocs.Viewer cho .NET. Dưới đây là hướng dẫn từng bước để giúp bạn thực hiện điều này:

## Bước 1: Xác định thư mục đầu ra

Đầu tiên, hãy xác định thư mục mà bạn muốn lưu các trang đã kết xuất. Thư mục này phải tồn tại và có thể truy cập được bằng ứng dụng.

```csharp
string outputDirectory = "Your Document Directory";
```

## Bước 2: Xác định định dạng đường dẫn tệp trang

Chỉ định định dạng cho đường dẫn tệp của mỗi trang được hiển thị. GroupDocs.Viewer sẽ thay thế `{0}` cùng với số trang khi lưu tập tin.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Bước 3: Khởi tạo đối tượng Viewer

Tạo một phiên bản của `Viewer` lớp bằng cách cung cấp đường dẫn đến tệp tài liệu mà bạn muốn hiển thị.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Mã để hiển thị ở đây
}
```

## Bước 4: Xác định tùy chọn kết xuất

Chỉ định các tùy chọn kết xuất theo yêu cầu của bạn. Đối với kết xuất JPG/PNG, bạn sẽ sử dụng `JpgViewOptions` hoặc `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Bước 5: Kết xuất tài liệu

Gọi `View` phương pháp của `Viewer` đối tượng và truyền các tùy chọn kết xuất đã tạo trước đó.

```csharp
viewer.View(options);
```

## Bước 6: Xuất kết quả

Khi quá trình kết xuất hoàn tất, bạn có thể thông báo cho người dùng về việc kết xuất thành công và cung cấp thư mục lưu các trang đã kết xuất.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận

Tóm lại, GroupDocs.Viewer for .NET cung cấp giải pháp mạnh mẽ để kết xuất tài liệu sang nhiều định dạng khác nhau, bao gồm JPG và PNG. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch chức năng kết xuất tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm người dùng và năng suất.

## Câu hỏi thường gặp

### H: Tôi có thể hiển thị các tài liệu khác ngoài DOCX bằng GroupDocs.Viewer cho .NET không?

A: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu bao gồm PDF, PPT, XLS, v.v.

### H: Có bản dùng thử miễn phí của GroupDocs.Viewer dành cho .NET không?

A: Có, bạn có thể tải xuống bản dùng thử miễn phí từ [đây](https://releases.groupdocs.com/).

### H: Tôi có thể xin giấy phép tạm thời để đánh giá như thế nào?

A: Bạn có thể yêu cầu cấp giấy phép tạm thời từ [đây](https://purchase.groupdocs.com/temporary-license/).

### H: Tôi có thể tìm tài liệu về GroupDocs.Viewer cho .NET ở đâu?

A: Tài liệu chi tiết có sẵn [đây](https://tutorials.groupdocs.com/viewer/net/).

### H: Tôi có thể nhận hỗ trợ hoặc đặt câu hỏi liên quan đến GroupDocs.Viewer cho .NET ở đâu?

A: Bạn có thể truy cập diễn đàn hỗ trợ [đây](https://forum.groupdocs.com/c/viewer/9) để được hỗ trợ.