---
title: Đặt giấy phép từ luồng
linktitle: Đặt giấy phép từ luồng
second_title: API GroupDocs.Viewer .NET
description: Nâng cao các ứng dụng .NET của bạn với GroupDocs.Viewer để xem tài liệu liền mạch. Hãy làm theo hướng dẫn từng bước của chúng tôi và tích hợp khả năng xem tài liệu mạnh mẽ một cách dễ dàng.
weight: 11
url: /vi/net/getting-started/set-license-from-stream/
---

# Đặt giấy phép từ luồng

## Giới thiệu
Bạn đang tìm cách trang bị cho các ứng dụng .NET của mình khả năng xem tài liệu nâng cao? GroupDocs.Viewer dành cho .NET cung cấp giải pháp toàn diện để tích hợp liền mạch các chức năng xem tài liệu vào dự án của bạn. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tận dụng GroupDocs.Viewer dành cho .NET để làm phong phú thêm ứng dụng của bạn bằng khả năng xem tài liệu mạnh mẽ. 
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào quá trình tích hợp, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
1. Kiến thức cơ bản về phát triển .NET: Cần phải làm quen với C# và .NET framework theo hướng dẫn này.
   
2.  Gói GroupDocs.Viewer cho .NET: Đảm bảo bạn đã tải xuống và cài đặt gói GroupDocs.Viewer cho .NET. Bạn có thể lấy nó từ[Liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
3.  Truy cập vào Tài liệu GroupDocs: Giữ nguyên[tài liệu](https://tutorials.groupdocs.com/viewer/net/) thuận tiện cho việc tham khảo trong quá trình hội nhập.

## Nhập không gian tên
Để bắt đầu, hãy nhập các vùng tên cần thiết vào ứng dụng .NET của bạn. Thực hiện theo các bước sau:
### Bước 1: Mở dự án .NET của bạn.
Đảm bảo rằng bạn đã mở dự án .NET trong môi trường phát triển ưa thích của mình.
### Bước 2: Thêm không gian tên GroupDocs.Viewer.
Trong tệp mã của bạn, hãy thêm không gian tên sau để truy cập các chức năng của GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Đặt giấy phép từ luồng
Bước tiếp theo liên quan đến việc thiết lập giấy phép từ một luồng. Thực hiện theo các bước chi tiết sau:
### Bước 1: Xác định thư mục đầu ra.
Đặt thư mục nơi tài liệu của bạn sẽ được lưu trữ bằng cách xác định thư mục đầu ra:
```csharp
string outputDirectory = "Your Document Directory";
```
### Bước 2: Kiểm tra sự tồn tại của tệp giấy phép.
Kiểm tra xem tệp giấy phép có tồn tại trong thư mục dự án của bạn không:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Bước 3: Đặt giấy phép.
Nếu tệp giấy phép tồn tại, hãy đặt giấy phép bằng luồng được cung cấp:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Bước 4: Xử lý việc thiếu giấy phép.
Nếu không tìm thấy tệp giấy phép, hãy cung cấp hướng dẫn để lấy giấy phép:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://mua.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://mua.groupdocs.com/temporary-license.");
}
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách tích hợp GroupDocs.Viewer dành cho .NET vào các ứng dụng của mình. Với công cụ mạnh mẽ này, giờ đây bạn có thể dễ dàng xem các định dạng tài liệu khác nhau trong các dự án .NET của mình, nâng cao trải nghiệm và năng suất của người dùng.
## Câu hỏi thường gặp
### Tôi có cần giấy phép để sử dụng GroupDocs.Viewer cho .NET không?
Có, bạn cần có giấy phép để sử dụng GroupDocs.Viewer cho .NET. Bạn có thể lấy giấy phép tạm thời hoặc vĩnh viễn từ trang web GroupDocs.
### Tôi có thể tích hợp GroupDocs.Viewer vào ứng dụng ASP.NET của mình không?
Tuyệt đối! GroupDocs.Viewer dành cho .NET tích hợp liền mạch vào cả ứng dụng web và máy tính để bàn, bao gồm cả ASP.NET.
### Những định dạng tài liệu nào được GroupDocs.Viewer hỗ trợ?
GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Microsoft Office (Word, Excel, PowerPoint), hình ảnh, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer cho .NET tương thích với cả .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh giao diện trình xem theo chủ đề ứng dụng của mình không?
Có, GroupDocs.Viewer cung cấp các tùy chọn tùy chỉnh mở rộng, cho phép bạn điều chỉnh giao diện trình xem để phù hợp liền mạch với chủ đề ứng dụng của bạn.