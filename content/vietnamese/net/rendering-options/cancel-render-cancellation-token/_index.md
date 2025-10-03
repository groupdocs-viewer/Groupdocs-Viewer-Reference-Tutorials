---
"description": "Tích hợp Groupdocs.Viewer cho .NET một cách liền mạch vào các dự án .NET của bạn để xem tài liệu hiệu quả."
"linktitle": "Hủy kết xuất bằng mã thông báo hủy"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Hủy kết xuất bằng mã thông báo hủy"
"url": "/vi/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Hủy kết xuất bằng mã thông báo hủy

## Giới thiệu
Groupdocs.Viewer for .NET là một công cụ mạnh mẽ được thiết kế để đơn giản hóa việc xem và xử lý tài liệu trong các ứng dụng .NET. Cho dù bạn đang xử lý PDF, tài liệu Microsoft Office hay các định dạng phổ biến khác, thư viện này cung cấp chức năng mạnh mẽ để tích hợp liền mạch khả năng xem tài liệu vào các dự án .NET của bạn.
## Điều kiện tiên quyết
Trước khi bắt đầu tích hợp Groupdocs.Viewer cho .NET, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:
1. Cài đặt: Tải xuống và cài đặt Groupdocs.Viewer cho thư viện .NET từ thư viện được cung cấp [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
   
2. Giấy phép: Xin giấy phép từ [Nhóm tài liệu](https://purchase.groupdocs.com/buy) để mở khóa toàn bộ tiềm năng của thư viện. Ngoài ra, bạn có thể bắt đầu dùng thử miễn phí bằng cách sử dụng [giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/).
   
3. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển tương thích, bao gồm Visual Studio hoặc bất kỳ .NET IDE nào khác mà bạn chọn.

## Nhập không gian tên
Để sử dụng Groupdocs.Viewer cho .NET một cách hiệu quả, bạn cần nhập các không gian tên cần thiết vào dự án của mình. Thực hiện theo các bước sau:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Bây giờ, chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hiểu và triển khai tốt hơn:
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Bước này thiết lập thư mục nơi các trang tài liệu được kết xuất sẽ được lưu trữ.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tại đây, chúng tôi xác định định dạng cho đường dẫn tệp của từng trang tài liệu.
## Bước 3: Khởi tạo CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource được sử dụng để tạo các phiên bản CancellationToken có thể được sử dụng để hủy các hoạt động không đồng bộ.
## Bước 4: Nhận CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Bước này sẽ lấy mã thông báo từ CancellationTokenSource, mã thông báo này sẽ được sử dụng để hủy thao tác kết xuất.
## Bước 5: Kết xuất các trang tài liệu
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Ở đây, chúng tôi khởi tạo việc hiển thị các trang tài liệu không đồng bộ bằng cách sử dụng Task.Run(). Phiên bản Viewer được tạo bằng tệp tài liệu được chỉ định (SAMPLE_DOCX) và các tùy chọn hiển thị được cấu hình. Sau đó, quá trình hiển thị được bắt đầu bằng cách sử dụng phương thức View của lớp Viewer.
## Bước 6: Thiết lập thời gian chờ kết xuất
```csharp
cancellationTokenSource.CancelAfter(10);
```
Bước này đặt thời gian chờ là 10 mili giây cho hoạt động kết xuất. Nếu hoạt động vượt quá thời gian chờ này, nó sẽ tự động bị hủy.
## Bước 7: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cuối cùng, một thông báo thành công sẽ hiển thị cho biết tài liệu đã được hiển thị thành công.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã đề cập đến những điều cơ bản về tích hợp Groupdocs.Viewer cho .NET vào các dự án của bạn. Bằng cách làm theo các bước được nêu ở trên, bạn có thể kết hợp liền mạch các khả năng xem tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm người dùng và năng suất.
## Câu hỏi thường gặp
### Groupdocs.Viewer cho .NET có tương thích với mọi định dạng tài liệu không?
Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v.
### Tôi có thể tùy chỉnh giao diện của các trang tài liệu được hiển thị không?
Có, bạn có thể tùy chỉnh nhiều khía cạnh khác nhau của quy trình kết xuất, bao gồm kích thước trang, chất lượng, hình mờ và nhiều hơn nữa.
### Groupdocs.Viewer cho .NET có yêu cầu kết nối internet không?
Không, Groupdocs.Viewer cho .NET hoạt động cục bộ trong môi trường .NET của bạn và không yêu cầu kết nối internet để xem tài liệu.
### Có hỗ trợ kỹ thuật nào cho Groupdocs.Viewer dành cho .NET không?
Có, hỗ trợ kỹ thuật có sẵn thông qua [Diễn đàn Groupdocs](https://forum.groupdocs.com/c/viewer/9), nơi bạn có thể đặt câu hỏi, báo cáo sự cố và tương tác với cộng đồng.
### Tôi có thể dùng thử Groupdocs.Viewer cho .NET trước khi mua không?
Có, bạn có thể bắt đầu dùng thử miễn phí bằng cách sử dụng [phiên bản dùng thử](https://releases.groupdocs.com/).