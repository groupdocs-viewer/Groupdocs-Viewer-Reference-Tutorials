---
title: Hủy kết xuất bằng mã thông báo hủy
linktitle: Hủy kết xuất bằng mã thông báo hủy
second_title: API GroupDocs.Viewer .NET
description: Tích hợp Groupdocs.Viewer cho .NET một cách liền mạch vào các dự án .NET của bạn để xem tài liệu hiệu quả.
weight: 11
url: /vi/net/rendering-options/cancel-render-cancellation-token/
---
## Giới thiệu
Groupdocs.Viewer for .NET là một công cụ mạnh mẽ được thiết kế để đơn giản hóa việc xem và xử lý tài liệu trong các ứng dụng .NET. Cho dù bạn đang xử lý các tệp PDF, tài liệu Microsoft Office hay các định dạng phổ biến khác, thư viện này đều cung cấp chức năng mạnh mẽ để tích hợp liền mạch khả năng xem tài liệu vào các dự án .NET của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào việc tích hợp Groupdocs.Viewer cho .NET, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Cài đặt: Tải xuống và cài đặt thư viện Groupdocs.Viewer cho .NET từ thư viện được cung cấp[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
   
2.  Giấy phép: Lấy giấy phép từ[Nhóm tài liệu](https://purchase.groupdocs.com/buy) để khai thác toàn bộ tiềm năng của thư viện. Ngoài ra, bạn có thể bắt đầu dùng thử miễn phí bằng cách sử dụng[giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/).
   
3. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển tương thích, bao gồm Visual Studio hoặc bất kỳ .NET IDE nào khác mà bạn chọn.

## Nhập không gian tên
Để sử dụng Groupdocs.Viewer cho .NET một cách hiệu quả, bạn cần nhập các vùng tên cần thiết vào dự án của mình. Thực hiện theo các bước sau:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước để hiểu và triển khai tốt hơn:
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Bước này đặt thư mục nơi các trang tài liệu được hiển thị sẽ được lưu trữ.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ở đây, chúng tôi xác định định dạng cho đường dẫn tệp của từng trang tài liệu.
## Bước 3: Khởi tạo CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource được sử dụng để tạo các phiên bản CancellationToken có thể được sử dụng để hủy các hoạt động không đồng bộ.
## Bước 4: Nhận CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Bước này lấy mã thông báo từ CancellationTokenSource, mã này sẽ được sử dụng để hủy thao tác hiển thị.
## Bước 5: Kết xuất trang tài liệu
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
Ở đây, chúng tôi bắt đầu hiển thị các trang tài liệu một cách không đồng bộ bằng cách sử dụng Task.Run(). Phiên bản Viewer được tạo bằng tệp tài liệu được chỉ định (SAMPLE_DOCX) và các tùy chọn hiển thị được định cấu hình. Quá trình kết xuất sau đó được bắt đầu bằng phương thức View của lớp Viewer.
## Bước 6: Đặt thời gian chờ kết xuất
```csharp
cancellationTokenSource.CancelAfter(10);
```
Bước này đặt thời gian chờ là 10 mili giây cho thao tác hiển thị. Nếu thao tác vượt quá thời gian chờ này, nó sẽ tự động bị hủy.
## Bước 7: Hiển thị thông báo thành công
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cuối cùng, một thông báo thành công được hiển thị cho biết tài liệu đã được hiển thị thành công.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày những kiến thức cơ bản về tích hợp Groupdocs.Viewer dành cho .NET vào các dự án của bạn. Bằng cách làm theo các bước được nêu ở trên, bạn có thể kết hợp liền mạch khả năng xem tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm và năng suất của người dùng.
## Câu hỏi thường gặp
### Groupdocs.Viewer for .NET có tương thích với tất cả các định dạng tài liệu không?
Groupdocs.Viewer for .NET hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, tài liệu Microsoft Office, hình ảnh, v.v.
### Tôi có thể tùy chỉnh giao diện của các trang tài liệu được hiển thị không?
Có, bạn có thể tùy chỉnh các khía cạnh khác nhau của quá trình hiển thị, bao gồm kích thước trang, chất lượng, hình mờ, v.v.
### Groupdocs.Viewer cho .NET có yêu cầu kết nối internet không?
Không, Groupdocs.Viewer dành cho .NET hoạt động cục bộ trong môi trường .NET của bạn và không yêu cầu kết nối Internet để xem tài liệu.
### Có hỗ trợ kỹ thuật cho Groupdocs.Viewer dành cho .NET không?
 Có, hỗ trợ kỹ thuật có sẵn thông qua[diễn đàn Groupdocs](https://forum.groupdocs.com/c/viewer/9), nơi bạn có thể đặt câu hỏi, báo cáo sự cố và tương tác với cộng đồng.
### Tôi có thể dùng thử Groupdocs.Viewer cho .NET trước khi mua không?
 Có, bạn có thể bắt đầu dùng thử miễn phí bằng cách sử dụng dịch vụ được cung cấp[phiên bản dùng thử](https://releases.groupdocs.com/).