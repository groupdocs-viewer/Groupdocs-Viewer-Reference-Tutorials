---
title: Kết xuất hình ảnh WMZ và WMF
linktitle: Kết xuất hình ảnh WMZ và WMF
second_title: API GroupDocs.Viewer .NET
description: Dễ dàng hiển thị hình ảnh WMZ và WMF trong các ứng dụng .NET bằng GroupDocs.Viewer cho .NET. Nâng cao khả năng xử lý tài liệu một cách dễ dàng.
weight: 18
url: /vi/net/image-rendering/render-wmz-wmf-images/
---
## Giới thiệu

Trong lĩnh vực phát triển phần mềm, việc xử lý và hiển thị hiệu quả các định dạng tài liệu khác nhau là điều tối quan trọng. GroupDocs.Viewer cho .NET là một công cụ mạnh mẽ tạo điều kiện thuận lợi cho việc hiển thị nhiều định dạng tài liệu, đảm bảo tích hợp liền mạch và nâng cao trải nghiệm người dùng trong các ứng dụng .NET. Trong số các khả năng của nó là hiển thị hình ảnh WMZ và WMF, một tác vụ thường gặp trong các tình huống xử lý tài liệu.

## Điều kiện tiên quyết

Trước khi đi sâu vào quá trình kết xuất hình ảnh WMZ và WMF bằng GroupDocs.Viewer cho .NET, có một số điều kiện tiên quyết cần đáp ứng:

1.  Cài đặt GroupDocs.Viewer cho .NET: Bắt đầu bằng cách tải xuống và cài đặt GroupDocs.Viewer cho .NET từ gói được cung cấp[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/). Thực hiện theo các hướng dẫn cài đặt để đảm bảo thiết lập đúng.

2.  Mua giấy phép: Để sử dụng GroupDocs.Viewer cho .NET, bạn cần phải có giấy phép. Bạn có thể chọn giấy phép tạm thời từ[trang giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/) hoặc mua giấy phép đầy đủ từ[trang mua hàng](https://purchase.groupdocs.com/buy).

3. Làm quen với Môi trường .NET: Hiểu biết cơ bản về .NET framework và ngôn ngữ lập trình C# là điều cần thiết để triển khai quá trình kết xuất một cách hiệu quả.

4.  Tích hợp vào Dự án của bạn: Đảm bảo rằng GroupDocs.Viewer dành cho .NET được tích hợp đúng cách vào dự án .NET của bạn. Tham khảo tài liệu để biết hướng dẫn chi tiết về tích hợp:[Tài liệu](https://tutorials.groupdocs.com/viewer/net/).

## Nhập không gian tên

Trước khi tiếp tục quá trình kết xuất, điều quan trọng là phải nhập các vùng tên cần thiết vào mã C# của bạn. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để hiển thị hình ảnh WMZ và WMF.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Bây giờ chúng ta đã đề cập đến các điều kiện tiên quyết và nhập các không gian tên bắt buộc, hãy chia quá trình kết xuất thành nhiều bước.

## Bước 1: Kết xuất hình ảnh WMZ sang HTML

Để hiển thị hình ảnh WMZ sang định dạng HTML, hãy làm theo các bước sau:

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.html");

// ĐẾN HTML
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

    viewer.View(options);
}
```

## Bước 2: Kết xuất hình ảnh WMZ sang JPG

Để hiển thị hình ảnh WMZ sang định dạng JPG, hãy tiến hành như sau:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.jpg");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Bước 3: Kết xuất hình ảnh WMZ thành PNG

Để hiển thị hình ảnh WMZ sang định dạng PNG, hãy làm theo các hướng dẫn sau:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.png");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Bước 4: Kết xuất hình ảnh WMZ thành PDF

Để hiển thị hình ảnh WMZ sang định dạng PDF, hãy tiến hành như sau:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.pdf");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Phần kết luận

Tóm lại, GroupDocs.Viewer for .NET cung cấp một giải pháp toàn diện để hiển thị hình ảnh WMZ và WMF một cách dễ dàng trong các ứng dụng .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch chức năng kết xuất vào dự án của mình, nâng cao khả năng xử lý tài liệu.

## Câu hỏi thường gặp

### Câu hỏi 1: GroupDocs.Viewer dành cho .NET có tương thích với tất cả các khung .NET không?

Câu trả lời 1: GroupDocs.Viewer dành cho .NET tương thích với nhiều khung .NET, bao gồm .NET Core và .NET Framework.

### Câu hỏi 2: Tôi có thể tùy chỉnh các tùy chọn hiển thị cho hình ảnh WMZ và WMF không?

Câu trả lời 2: Có, GroupDocs.Viewer dành cho .NET cung cấp các tùy chọn tùy chỉnh mở rộng để hiển thị hình ảnh, cho phép bạn điều chỉnh đầu ra theo yêu cầu của mình.

### Câu hỏi 3: GroupDocs.Viewer dành cho .NET có hỗ trợ kỹ thuật không?

 Câu trả lời 3: Có, bạn có thể truy cập hỗ trợ kỹ thuật cho GroupDocs.Viewer dành cho .NET thông qua trang web chuyên dụng[diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9).

### Câu hỏi 4: GroupDocs.Viewer dành cho .NET có hỗ trợ xem tài liệu trên thiết bị di động không?

Câu trả lời 4: Có, GroupDocs.Viewer dành cho .NET cung cấp khả năng xem tài liệu phản hồi nhanh, đảm bảo hiệu suất tối ưu trên nhiều thiết bị khác nhau, bao gồm cả điện thoại di động và máy tính bảng.

### Câu hỏi 5: Tôi có thể dùng thử GroupDocs.Viewer cho .NET trước khi mua không?

 Câu trả lời 5: Có, bạn có thể khám phá các tính năng của GroupDocs.Viewer dành cho .NET bằng cách truy cập vào bản dùng thử miễn phí có sẵn[đây](https://releases.groupdocs.com/).