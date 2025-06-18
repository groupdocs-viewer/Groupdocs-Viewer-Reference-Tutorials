---
"description": "Tìm hiểu cách hiển thị bố cục đơn trong bản vẽ CAD bằng GroupDocs.Viewer cho .NET. Các bước dễ dàng để tích hợp liền mạch vào các ứng dụng .NET của bạn."
"linktitle": "Kết xuất Bố cục Đơn trong Bản vẽ CAD"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Kết xuất Bố cục Đơn trong Bản vẽ CAD"
"url": "/vi/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# Kết xuất Bố cục Đơn trong Bản vẽ CAD

## Giới thiệu
Trong lĩnh vực phát triển .NET, xử lý và xem bản vẽ CAD là một yêu cầu chung. GroupDocs.Viewer for .NET đơn giản hóa nhiệm vụ này bằng cách cung cấp giải pháp toàn diện để hiển thị bản vẽ CAD trong các ứng dụng .NET. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc hiển thị một bố cục duy nhất trong bản vẽ CAD bằng GroupDocs.Viewer for .NET.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C# và .NET framework.
- Visual Studio được cài đặt trên hệ thống của bạn.
- GroupDocs.Viewer cho thư viện .NET đã tải xuống và tutorialsd trong dự án của bạn. Bạn có thể tải xuống từ [đây](https://releases.groupdocs.com/viewer/net/).
- Quen thuộc với định dạng tệp CAD và cấu trúc của chúng.

## Nhập không gian tên
Đầu tiên, hãy nhập các không gian tên cần thiết vào mã C# của bạn để truy cập các chức năng của GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Bước 1: Xác định thư mục đầu ra
Chỉ định thư mục mà bạn muốn lưu kết quả đã kết xuất.
```csharp
string outputDirectory = "Your Document Directory";
```
## Bước 2: Xác định định dạng đường dẫn tệp trang
Xác định định dạng cho đường dẫn tệp của mỗi trang được hiển thị.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Bước 3: Khởi tạo đối tượng Viewer
Tạo một phiên bản của lớp Viewer được cung cấp bởi GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Bước 4: Cấu hình Tùy chọn chế độ xem HTML
Cấu hình các tùy chọn để hiển thị đầu ra HTML với các tài nguyên được nhúng.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Bước 5: Chỉ định Tên Bố cục CAD
Chỉ định tên của bố cục CAD mà bạn muốn kết xuất.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Bước 6: Kết xuất bản vẽ CAD
Gọi phương thức View của đối tượng Viewer với các tùy chọn được chỉ định.
```csharp
viewer.View(options);
```
## Bước 7: Hiển thị thông báo thành công
Thông báo cho người dùng về việc hiển thị thành công tài liệu nguồn.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Phần kết luận
Việc kết xuất bản vẽ CAD, đặc biệt là khi xử lý các bố cục, có thể là một nhiệm vụ khó khăn. Tuy nhiên, với GroupDocs.Viewer cho .NET, quá trình này trở nên liền mạch và hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng kết xuất một bố cục duy nhất trong các bản vẽ CAD trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể hiển thị nhiều bố cục cùng lúc bằng GroupDocs.Viewer cho .NET không?
Có, GroupDocs.Viewer cho .NET hỗ trợ kết xuất nhiều bố cục từ bản vẽ CAD.
### GroupDocs.Viewer có tương thích với các định dạng tệp CAD khác nhau không?
Hoàn toàn có thể, GroupDocs.Viewer hỗ trợ nhiều định dạng tệp CAD, bao gồm DWG, DXF, DGN, v.v.
### Tôi có thể tùy chỉnh các tùy chọn kết xuất cho bản vẽ CAD không?
Có, GroupDocs.Viewer cung cấp nhiều tùy chọn để tùy chỉnh cài đặt hiển thị theo yêu cầu của bạn.
### Có bản dùng thử miễn phí nào cho GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể khám phá các tính năng của GroupDocs.Viewer với bản dùng thử miễn phí [đây](https://releases.groupdocs.com/).
### Tôi có thể nhận hỗ trợ cho GroupDocs.Viewer dành cho .NET ở đâu?
Đối với bất kỳ thắc mắc hoặc hỗ trợ nào, bạn có thể truy cập diễn đàn GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9).