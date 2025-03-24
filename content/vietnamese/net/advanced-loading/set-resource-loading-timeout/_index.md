---
title: Đặt thời gian chờ tải tài nguyên (Nâng cao)
linktitle: Đặt thời gian chờ tải tài nguyên (Nâng cao)
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách định cấu hình thời gian chờ tải tài nguyên trong GroupDocs.Viewer cho .NET một cách hiệu quả. Kết xuất tài liệu chính với độ chính xác và ổn định.
weight: 13
url: /vi/net/advanced-loading/set-resource-loading-timeout/
---
## Giới thiệu
Trong lĩnh vực phát triển .NET, GroupDocs.Viewer cung cấp bộ công cụ mạnh mẽ để hiển thị tài liệu và hình ảnh với độ chính xác và hiệu quả. Việc tận dụng các khả năng của nó đòi hỏi phải hiểu được những điểm phức tạp của nó, bao gồm cả việc đặt thời gian chờ tải tài nguyên. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình định cấu hình thời gian chờ tải tài nguyên trong GroupDocs.Viewer cho .NET.
## Điều kiện tiên quyết
Trước khi bắt tay vào hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Kiến thức cơ bản về phát triển .NET: Cần phải làm quen với lập trình C# và các nguyên tắc cơ bản về .NET framework.
2.  Cài đặt GroupDocs.Viewer cho .NET: Tải xuống và cài đặt thư viện GroupDocs.Viewer cho .NET từ[trang tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Môi trường phát triển tích hợp (IDE): Cài đặt IDE như Visual Studio trên hệ thống của bạn.

## Nhập không gian tên
Trước khi đi sâu vào quá trình mã hóa, hãy nhập các không gian tên cần thiết:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Đầu tiên, xác định thư mục nơi tài liệu được hiển thị sẽ được lưu:
```csharp
string outputDirectory = "Your Document Directory";
```
 Thay thế`"Your Document Directory"`với đường dẫn mà bạn muốn lưu tài liệu được kết xuất.
## Bước 2: Xác định định dạng đường dẫn tệp trang
Xác định định dạng cho đường dẫn tệp của từng trang riêng lẻ:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Định dạng này sẽ tạo ra tên tệp như`page_1.html`, `page_2.html`, v.v., trong thư mục đầu ra được chỉ định.
## Bước 3: Định cấu hình tùy chọn tải
Định cấu hình các tùy chọn tải, bao gồm cả thời gian chờ tải tài nguyên:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Trong ví dụ này, thời gian chờ là 5 giây được đặt để tải tài nguyên.
## Bước 4: Khởi tạo đối tượng Viewer
 Khởi tạo`Viewer` đối tượng có tài liệu được hiển thị và các tùy chọn tải được xác định:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Thay thế`TestFiles.WITH_EXTERNAL_IMAGE_DOC` với đường dẫn đến tài liệu bạn muốn kết xuất.
## Bước 5: Định cấu hình tùy chọn chế độ xem HTML
Định cấu hình tùy chọn chế độ xem HTML cho tài nguyên được nhúng:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Cấu hình này đảm bảo rằng các tài nguyên được nhúng như hình ảnh được đưa vào HTML được hiển thị.
## Bước 6: Kết xuất tài liệu
Kết xuất tài liệu bằng các tùy chọn được định cấu hình:
```csharp
viewer.View(options);
```
Bước này bắt đầu quá trình kết xuất.
## Bước 7: Hiển thị thư mục đầu ra
Hiển thị thông báo hiển thị thành công và vị trí của thư mục đầu ra:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Nắm vững thời gian chờ tải tài nguyên trong GroupDocs.Viewer dành cho .NET là rất quan trọng để đảm bảo quá trình kết xuất tài liệu diễn ra suôn sẻ. Bằng cách làm theo hướng dẫn này, bạn đã hiểu rõ hơn về cách định cấu hình thời gian chờ một cách hiệu quả, nâng cao trình độ phát triển .NET của bạn.
## Câu hỏi thường gặp
### Tầm quan trọng của việc thiết lập thời gian chờ tải tài nguyên là gì?
Đặt thời gian chờ tải tài nguyên đảm bảo rằng quá trình kết xuất không bị treo vô thời hạn, nâng cao tính ổn định của ứng dụng.
### Thời gian chờ tải tài nguyên có thể được tùy chỉnh dựa trên loại tài liệu không?
Có, thời gian chờ tải tài nguyên có thể được điều chỉnh dựa trên độ phức tạp và kích thước của tài liệu được hiển thị.
### Có bất kỳ ý nghĩa hiệu suất nào của việc đặt thời gian chờ ngắn hơn không?
Thời gian chờ ngắn hơn có thể dẫn đến việc hiển thị không đầy đủ các tài liệu phức tạp nếu không thể tải tài nguyên trong khoảng thời gian được chỉ định.
### GroupDocs.Viewer có phù hợp để hiển thị các định dạng tài liệu khác nhau không?
Có, GroupDocs.Viewer hỗ trợ hiển thị nhiều định dạng tài liệu bao gồm PDF, DOCX, XLSX, v.v.
### Có thể tắt thời gian chờ tải tài nguyên không?
Mặc dù không được khuyến nghị nhưng thời gian chờ tải tài nguyên có thể được đặt thành giá trị cao hoặc bị vô hiệu hóa hoàn toàn tùy thuộc vào yêu cầu cụ thể.