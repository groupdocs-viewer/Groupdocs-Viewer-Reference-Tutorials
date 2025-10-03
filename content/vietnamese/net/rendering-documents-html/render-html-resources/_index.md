---
"description": "Cải thiện khả năng xem tài liệu .NET với GroupDocs.Viewer để hiển thị liền mạch. Làm theo hướng dẫn của chúng tôi để tích hợp hiệu quả và trải nghiệm người dùng vượt trội."
"linktitle": "Kết xuất với tài nguyên nhúng hoặc bên ngoài"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất với tài nguyên nhúng hoặc bên ngoài"
"url": "/vi/net/rendering-documents-html/render-html-resources/"
"weight": 12
type: docs
---
# Kết xuất với tài nguyên nhúng hoặc bên ngoài

## Giới thiệu

Trong thế giới phát triển .NET, việc xem tài liệu hiệu quả là một khía cạnh quan trọng của nhiều ứng dụng. GroupDocs.Viewer cho .NET cung cấp giải pháp mạnh mẽ để kết xuất tài liệu với các tài nguyên nhúng hoặc bên ngoài. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng GroupDocs.Viewer để kết xuất tài liệu một cách liền mạch, chia nhỏ từng bước để rõ ràng và dễ hiểu.

## Điều kiện tiên quyết

Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

1. Hiểu biết cơ bản về phát triển .NET: Cần phải quen thuộc với ngôn ngữ lập trình C# và .NET framework.
2. Cài đặt GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [đây](https://releases.groupdocs.com/viewer/net/).
3. Tệp tài liệu để kết xuất: Chuẩn bị một tệp tài liệu mẫu (ví dụ: DOCX, PDF) để kết xuất.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết cho dự án .NET của chúng ta:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Bây giờ, chúng ta hãy chia nhỏ quy trình kết xuất tài liệu bằng tài nguyên nhúng hoặc bên ngoài thành các bước dễ quản lý:

## Bước 1: Xác định thư mục đầu ra

```csharp
string outputDirectory = "Your Document Directory";
```

Chỉ định thư mục mà bạn muốn lưu các trang HTML đã hiển thị.

## Bước 2: Xác định định dạng đường dẫn tệp trang

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Đặt định dạng cho đường dẫn tệp nơi mỗi trang được kết xuất sẽ được lưu. `{0}` là chỗ giữ chỗ cho số trang.

## Bước 3: Khởi tạo Viewer Instance

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Mã khởi tạo trình xem ở đây
}
```

Tạo một phiên bản Viewer bằng cách truyền đường dẫn đến tệp tài liệu cần hiển thị.

## Bước 4: Cấu hình Tùy chọn chế độ xem HTML

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Cấu hình tùy chọn chế độ xem HTML, chỉ định định dạng cho tài nguyên nhúng và định dạng đường dẫn tệp trang.

## Bước 5: Kết xuất tài liệu

```csharp
viewer.View(options);
```

Gọi `View` phương thức trên phiên bản Viewer, truyền các tùy chọn chế độ xem HTML đã cấu hình.

## Bước 6: Hiển thị đường dẫn thư mục đầu ra

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

In ra thông báo cho biết quá trình kết xuất thành công cùng với đường dẫn đến thư mục đầu ra.

## Phần kết luận

GroupDocs.Viewer for .NET đơn giản hóa quá trình kết xuất tài liệu với các tài nguyên nhúng hoặc bên ngoài, tăng cường khả năng xem tài liệu trong các ứng dụng .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, các nhà phát triển có thể tích hợp liền mạch chức năng kết xuất tài liệu vào các dự án của họ, cung cấp cho người dùng trải nghiệm xem tài liệu mượt mà và hiệu quả.

## Câu hỏi thường gặp

### H: GroupDocs.Viewer for .NET có tương thích với nhiều định dạng tài liệu khác nhau không?

A: Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm DOCX, PDF, XLSX, v.v.

### H: Tôi có thể tùy chỉnh các tùy chọn kết xuất theo yêu cầu của mình không?

A: Chắc chắn rồi, GroupDocs.Viewer cung cấp nhiều tùy chọn để cấu hình quy trình kết xuất nhằm đáp ứng các nhu cầu cụ thể.

### H: Có bản dùng thử miễn phí của GroupDocs.Viewer dành cho .NET không?

A: Có, bạn có thể tận dụng bản dùng thử miễn phí từ [đây](https://releases.groupdocs.com/).

### H: Tôi có thể nhận được hỗ trợ hoặc trợ giúp khi tích hợp GroupDocs.Viewer như thế nào?

A: Bạn có thể tìm kiếm sự trợ giúp từ diễn đàn cộng đồng GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9).

### H: Có giấy phép tạm thời cho mục đích thử nghiệm không?

A: Có, giấy phép tạm thời có thể được xin từ [đây](https://purchase.groupdocs.com/temporary-license/).