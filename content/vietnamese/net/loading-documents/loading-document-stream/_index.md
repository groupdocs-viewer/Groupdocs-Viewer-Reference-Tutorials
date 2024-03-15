---
title: Tải tài liệu từ luồng
linktitle: Tải tài liệu từ luồng
second_title: API GroupDocs.Viewer .NET
description: Tìm hiểu cách tải tài liệu từ luồng một cách liền mạch bằng GroupDocs.Viewer dành cho .NET. Nâng cao ứng dụng .NET của bạn với khả năng xem tài liệu mạnh mẽ.
type: docs
weight: 12
url: /vi/net/loading-documents/loading-document-stream/
---
## Giới thiệu
Trong lĩnh vực phát triển .NET, việc quản lý và xem tài liệu một cách hiệu quả là điều tối quan trọng. Với sự ra đời của các công cụ và thư viện tiên tiến, những công việc từng có vẻ khó khăn nay đã được đơn giản hóa. Trong số các công cụ này, GroupDocs.Viewer dành cho .NET nổi bật như một giải pháp linh hoạt để xử lý liền mạch các định dạng tài liệu khác nhau. Trong hướng dẫn toàn diện này, chúng tôi đi sâu vào những điểm phức tạp của việc sử dụng GroupDocs.Viewer dành cho .NET để tải tài liệu từ một luồng. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn này sẽ trang bị cho bạn kiến thức để khai thác sức mạnh của GroupDocs.Viewer một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Hiểu biết cơ bản về C# và .NET Framework: Làm quen với ngôn ngữ lập trình C# và .NET framework sẽ giúp hiểu các khái niệm được thảo luận.
   
2.  Cài đặt GroupDocs.Viewer cho .NET: Tải xuống và cài đặt GroupDocs.Viewer cho .NET từ[trang mạng](https://releases.groupdocs.com/viewer/net/).
3. IDE: Đã cài đặt Môi trường phát triển tích hợp (IDE) như Visual Studio để mã hóa và thử nghiệm.
4. Luồng tài liệu: Chuẩn bị luồng tài liệu để tải. Đây có thể là luồng tệp hoặc bất kỳ nguồn luồng tương thích nào khác.

## Nhập không gian tên
Trước khi triển khai mã để tải tài liệu từ một luồng, hãy đảm bảo nhập các vùng tên cần thiết:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Bước 1: Xác định thư mục đầu ra
```csharp
string outputDirectory = "Your Document Directory";
```
Đặt đường dẫn thư mục nơi tài liệu được hiển thị sẽ được lưu.
## Bước 2: Xác định định dạng đường dẫn tệp trang
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Xác định định dạng cho đường dẫn file của mỗi trang. Ở đây, "{0}" sẽ được thay thế bằng số trang.
## Bước 3: Nhận luồng tài liệu
```csharp
Stream stream = GetFileStream();
```
Lấy luồng tài liệu từ nguồn bạn mong muốn. Đây có thể là luồng tệp, luồng bộ nhớ hoặc bất kỳ luồng tương thích nào khác.
## Bước 4: Tải tài liệu bằng Viewer
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Khởi tạo một phiên bản mới của lớp Viewer bằng luồng tài liệu. Sau đó, định cấu hình các tùy chọn chế độ xem HTML và hiển thị tài liệu.
## Bước 5: Hiển thị thư mục đầu ra
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Thông báo cho người dùng về việc hiển thị thành công tài liệu và cung cấp vị trí lưu đầu ra.

## Phần kết luận
Tóm lại, GroupDocs.Viewer cho .NET cung cấp một giải pháp mạnh mẽ để tải và xem tài liệu từ các luồng một cách dễ dàng. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch khả năng xem tài liệu vào các ứng dụng .NET của mình, nâng cao trải nghiệm và năng suất của người dùng.
## Câu hỏi thường gặp
### GroupDocs.Viewer cho .NET có thể xử lý các định dạng tài liệu khác nhau không?
Có, GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, DOCX, XLSX, PPTX, v.v.
### GroupDocs.Viewer cho .NET có phù hợp cho cả ứng dụng web và máy tính để bàn không?
Tuyệt đối! GroupDocs.Viewer có thể được tích hợp liền mạch vào cả ứng dụng web và máy tính để bàn được phát triển bằng .NET.
### GroupDocs.Viewer có cung cấp các tùy chọn tùy chỉnh để hiển thị tài liệu không?
Có, bạn có thể tùy chỉnh các khía cạnh khác nhau của việc hiển thị tài liệu, chẳng hạn như hình mờ, xoay trang và mức thu phóng, theo yêu cầu của bạn.
### Tôi có thể sử dụng GroupDocs.Viewer cho .NET trong các dự án thương mại không?
Có, GroupDocs.Viewer cung cấp các tùy chọn cấp phép phù hợp cho các dự án thương mại. Bạn có thể mua giấy phép từ chính thức[trang mạng](https://purchase.groupdocs.com/temporary-license/).
### Có hỗ trợ kỹ thuật cho GroupDocs.Viewer dành cho .NET không?
 Có, bạn có thể tìm kiếm sự hỗ trợ và hướng dẫn kỹ thuật từ diễn đàn hỗ trợ chuyên dụng do[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).