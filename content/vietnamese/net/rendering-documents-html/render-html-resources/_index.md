---
title: Kết xuất bằng tài nguyên nhúng hoặc bên ngoài
linktitle: Kết xuất bằng tài nguyên nhúng hoặc bên ngoài
second_title: API GroupDocs.Viewer .NET
description: Nâng cao khả năng xem tài liệu .NET bằng GroupDocs.Viewer để hiển thị liền mạch. Hãy làm theo hướng dẫn của chúng tôi để tích hợp hiệu quả và mang lại trải nghiệm người dùng vượt trội.
weight: 12
url: /vi/net/rendering-documents-html/render-html-resources/
---
## Giới thiệu

Trong thế giới phát triển .NET, việc xem tài liệu hiệu quả là một khía cạnh quan trọng của nhiều ứng dụng. GroupDocs.Viewer dành cho .NET cung cấp giải pháp mạnh mẽ để hiển thị tài liệu có tài nguyên được nhúng hoặc bên ngoài. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng GroupDocs.Viewer để hiển thị tài liệu một cách liền mạch, chia nhỏ từng bước cho rõ ràng và dễ hiểu.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1. Hiểu biết cơ bản về phát triển .NET: Cần phải làm quen với ngôn ngữ lập trình C# và .NET framework.
2.  Cài đặt GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[đây](https://releases.groupdocs.com/viewer/net/).
3. Tệp tài liệu cần kết xuất: Chuẩn bị tệp tài liệu mẫu (ví dụ: DOCX, PDF) để kết xuất.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết cho dự án .NET của chúng ta:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Bây giờ, hãy chia nhỏ quy trình hiển thị tài liệu có tài nguyên được nhúng hoặc bên ngoài thành các bước có thể quản lý được:

## Bước 1: Xác định thư mục đầu ra

```csharp
string outputDirectory = "Your Document Directory";
```

Chỉ định thư mục nơi bạn muốn lưu các trang HTML được hiển thị.

## Bước 2: Xác định định dạng đường dẫn tệp trang

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Đặt định dạng cho đường dẫn tệp nơi mỗi trang được hiển thị sẽ được lưu.`{0}` là một trình giữ chỗ cho số trang.

## Bước 3: Khởi tạo phiên bản Viewer

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Mã khởi tạo trình xem ở đây
}
```

Tạo một phiên bản Viewer bằng cách chuyển đường dẫn của tệp tài liệu sẽ được hiển thị.

## Bước 4: Định cấu hình tùy chọn chế độ xem HTML

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Định cấu hình tùy chọn chế độ xem HTML, chỉ định định dạng cho tài nguyên được nhúng và định dạng đường dẫn tệp trang.

## Bước 5: Kết xuất tài liệu

```csharp
viewer.View(options);
```

 Gọi`View` trên phiên bản Viewer, chuyển các tùy chọn chế độ xem HTML đã định cấu hình.

## Bước 6: Hiển thị đường dẫn thư mục đầu ra

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

In thông báo cho biết kết xuất thành công cùng với đường dẫn của thư mục đầu ra.

## Phần kết luận

GroupDocs.Viewer dành cho .NET đơn giản hóa quy trình hiển thị tài liệu bằng tài nguyên được nhúng hoặc bên ngoài, nâng cao khả năng xem tài liệu trong các ứng dụng .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, nhà phát triển có thể tích hợp liền mạch chức năng kết xuất tài liệu vào dự án của họ, mang đến cho người dùng trải nghiệm xem tài liệu mượt mà và hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi: GroupDocs.Viewer dành cho .NET có tương thích với nhiều định dạng tài liệu khác nhau không?

Trả lời: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm DOCX, PDF, XLSX, v.v.

### Hỏi: Tôi có thể tùy chỉnh các tùy chọn hiển thị theo yêu cầu của mình không?

Đáp: Hoàn toàn có thể, GroupDocs.Viewer cung cấp các tùy chọn mở rộng để định cấu hình quy trình kết xuất nhằm đáp ứng các nhu cầu cụ thể.

### Câu hỏi: Có bản dùng thử miễn phí GroupDocs.Viewer dành cho .NET không?

 Đ: Có, bạn có thể tận dụng bản dùng thử miễn phí từ[đây](https://releases.groupdocs.com/).

### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ hoặc trợ giúp khi tích hợp GroupDocs.Viewer?

 Đáp: Bạn có thể tìm kiếm trợ giúp từ diễn đàn cộng đồng GroupDocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9).

### Hỏi: Giấy phép tạm thời có sẵn cho mục đích thử nghiệm không?

 Đáp: Có, giấy phép tạm thời có thể được lấy từ[đây](https://purchase.groupdocs.com/temporary-license/).