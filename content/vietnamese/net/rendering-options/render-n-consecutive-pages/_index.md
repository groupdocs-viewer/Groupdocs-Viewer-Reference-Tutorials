---
"description": "Tìm hiểu cách tích hợp GroupDocs.Viewer cho .NET vào ứng dụng của bạn để dễ dàng hiển thị tài liệu có N trang liên tiếp."
"linktitle": "Hiển thị N trang liên tiếp"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hiển thị N trang liên tiếp"
"url": "/vi/net/rendering-options/render-n-consecutive-pages/"
"weight": 16
---

# Hiển thị N trang liên tiếp

## Giới thiệu
Trong lĩnh vực phát triển .NET, việc tích hợp khả năng xem tài liệu vào ứng dụng của bạn có thể cải thiện đáng kể trải nghiệm và chức năng của người dùng. Một công cụ như vậy giúp tạo điều kiện cho việc hiển thị tài liệu liền mạch là GroupDocs.Viewer cho .NET. Thư viện mạnh mẽ này giúp các nhà phát triển dễ dàng hiển thị nhiều định dạng tài liệu khác nhau trong ứng dụng của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào việc triển khai GroupDocs.Viewer cho .NET, hãy đảm bảo rằng bạn đã đáp ứng các điều kiện tiên quyết sau:
1. Môi trường phát triển .NET: Đảm bảo rằng bạn đã thiết lập môi trường phát triển .NET đang hoạt động trên máy của mình.
  
2. GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Tệp tài liệu: Chuẩn bị các tệp tài liệu mà bạn định hiển thị bằng GroupDocs.Viewer cho .NET.
#
## Nhập không gian tên
Để bắt đầu tích hợp GroupDocs.Viewer cho .NET vào dự án của bạn, bạn cần nhập các không gian tên cần thiết. Bước này rất quan trọng để truy cập chức năng của thư viện trong cơ sở mã của bạn.
## Bước 1: Nhập không gian tên GroupDocs.Viewer
```csharp
using System;
using System.IO;
using System.Linq;
using GroupDocs.Viewer.Options;
```
## Bước 2: Nhập không gian tên System.IO
```csharp
using System.IO;
```

Bây giờ bạn đã thiết lập các điều kiện tiên quyết và nhập các không gian tên cần thiết, hãy cùng tìm hiểu cách hiển thị số trang liên tiếp được chỉ định từ một tài liệu bằng GroupDocs.Viewer cho .NET.
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Chỉ định thư mục mà bạn muốn lưu các trang đã kết xuất.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Thiết lập định dạng cho đường dẫn tệp của các trang được hiển thị. Trong ví dụ này, các trang sẽ được lưu dưới dạng tệp HTML có tên như "page_1.html", "page_2.html", v.v.
## Bước 3: Xác định Phạm vi Trang
```csharp
int[] range = Enumerable.Range(1, 3).ToArray();
```
Chỉ định phạm vi các trang liên tiếp mà bạn muốn hiển thị. Trong trường hợp này, chúng tôi đang hiển thị các trang từ 1 đến 3.
## Bước 4: Kết xuất các trang tài liệu
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options, range);
}
```
Tạo một phiên bản của `Viewer` lớp, truyền đường dẫn đến tệp tài liệu dưới dạng tham số. Sau đó, cấu hình tùy chọn chế độ xem HTML và gọi `View` phương pháp, chỉ định phạm vi trang cần hiển thị.
## Bước 5: Hiển thị đầu ra đã kết xuất
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cuối cùng, hiển thị thông báo thành công cho biết tài liệu đã được hiển thị thành công và thông báo cho người dùng về thư mục đầu ra nơi các trang đã hiển thị được lưu.

## Phần kết luận
Việc tích hợp GroupDocs.Viewer cho .NET vào các ứng dụng .NET của bạn sẽ mở ra một thế giới khả năng cho việc kết xuất tài liệu liền mạch. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng kết xuất N trang liên tiếp từ nhiều định dạng tài liệu khác nhau, nâng cao chức năng và trải nghiệm người dùng của ứng dụng.
## Câu hỏi thường gặp
### Tôi có thể hiển thị các trang từ các tài liệu khác ngoài tệp DOCX không?
Có, GroupDocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, PPT, XLS, v.v.
### GroupDocs.Viewer cho .NET có phù hợp với ứng dụng web không?
Hoàn toàn đúng! GroupDocs.Viewer cho .NET có thể được tích hợp liền mạch vào cả ứng dụng máy tính để bàn và web.
### GroupDocs.Viewer cho .NET có yêu cầu giấy phép sử dụng cho mục đích thương mại không?
Có, bạn có thể lấy giấy phép thương mại từ liên kết mua hàng được cung cấp để sử dụng GroupDocs.Viewer cho .NET trong các dự án thương mại.
### Tôi có thể tùy chỉnh giao diện của các trang được hiển thị không?
Có, GroupDocs.Viewer cho .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh giao diện và hành vi của tài liệu được hiển thị.
### Có diễn đàn cộng đồng nào để tìm kiếm sự hỗ trợ và chia sẻ kinh nghiệm không?
Có, bạn có thể truy cập diễn đàn GroupDocs.Viewer thông qua liên kết hỗ trợ được cung cấp để tương tác với cộng đồng và nhận trợ giúp từ các chuyên gia.