---
"description": "Nâng cao ứng dụng .NET của bạn với GroupDocs.Viewer để xem tài liệu liền mạch. Làm theo hướng dẫn từng bước của chúng tôi và tích hợp các khả năng xem tài liệu mạnh mẽ một cách dễ dàng."
"linktitle": "Thiết lập giấy phép từ Stream"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Thiết lập giấy phép từ Stream"
"url": "/vi/net/getting-started/set-license-from-stream/"
"weight": 11
---

# Thiết lập giấy phép từ Stream

## Giới thiệu
Bạn có muốn trao quyền cho các ứng dụng .NET của mình với khả năng xem tài liệu nâng cao không? GroupDocs.Viewer for .NET cung cấp giải pháp toàn diện để tích hợp liền mạch các chức năng xem tài liệu vào các dự án của bạn. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tận dụng GroupDocs.Viewer for .NET để làm phong phú thêm các ứng dụng của bạn với khả năng xem tài liệu mạnh mẽ. 

![Thiết lập Giấy phép từ Stream với GroupDocs.Viewer cho .NET](/viewer/getting-started/set-license-from-stream.png)

## Điều kiện tiên quyết
Trước khi đi sâu vào quá trình tích hợp, hãy đảm bảo rằng bạn đã đáp ứng các điều kiện tiên quyết sau:
1. Kiến thức cơ bản về phát triển .NET: Cần phải quen thuộc với C# và .NET framework để thực hiện theo hướng dẫn này.
   
2. Gói GroupDocs.Viewer cho .NET: Đảm bảo bạn đã tải xuống và cài đặt gói GroupDocs.Viewer cho .NET. Bạn có thể lấy nó từ [liên kết tải xuống](https://releases.groupdocs.com/viewer/net/).
3. Truy cập vào Tài liệu GroupDocs: Giữ nguyên [tài liệu](https://tutorials.groupdocs.com/viewer/net/) hữu ích cho các hướng dẫn trong quá trình tích hợp.

## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết vào ứng dụng .NET của bạn. Thực hiện theo các bước sau:
### Bước 1: Mở dự án .NET của bạn.
Đảm bảo rằng bạn đã mở dự án .NET của mình trong môi trường phát triển mà bạn thích.
### Bước 2: Thêm không gian tên GroupDocs.Viewer.
Trong tệp mã của bạn, hãy thêm không gian tên sau để truy cập các chức năng của GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Thiết lập giấy phép từ Stream
Bước tiếp theo bao gồm thiết lập giấy phép từ một luồng. Thực hiện theo các bước chi tiết sau:
### Bước 1: Xác định thư mục đầu ra.
Thiết lập thư mục nơi tài liệu của bạn sẽ được lưu trữ bằng cách xác định thư mục đầu ra:
```csharp
string outputDirectory = "Your Document Directory";
```
### Bước 2: Kiểm tra sự tồn tại của tệp giấy phép.
Kiểm tra xem tệp giấy phép có tồn tại trong thư mục dự án của bạn không:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Bước 3: Thiết lập Giấy phép.
Nếu tệp giấy phép tồn tại, hãy thiết lập giấy phép bằng luồng được cung cấp:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Bước 4: Xử lý tình trạng thiếu giấy phép.
Nếu không tìm thấy tệp giấy phép, hãy cung cấp hướng dẫn để xin giấy phép:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách tích hợp GroupDocs.Viewer cho .NET vào các ứng dụng của mình. Với công cụ mạnh mẽ này, giờ đây bạn có thể dễ dàng xem nhiều định dạng tài liệu khác nhau trong các dự án .NET của mình, nâng cao trải nghiệm người dùng và năng suất.
## Câu hỏi thường gặp
### Tôi có cần giấy phép để sử dụng GroupDocs.Viewer cho .NET không?
Có, bạn cần giấy phép để sử dụng GroupDocs.Viewer cho .NET. Bạn có thể lấy giấy phép tạm thời hoặc vĩnh viễn từ trang web GroupDocs.
### Tôi có thể tích hợp GroupDocs.Viewer vào ứng dụng ASP.NET của mình không?
Hoàn toàn đúng! GroupDocs.Viewer cho .NET tích hợp liền mạch vào cả ứng dụng máy tính để bàn và web, bao gồm cả ASP.NET.
### GroupDocs.Viewer hỗ trợ những định dạng tài liệu nào?
GroupDocs.Viewer hỗ trợ nhiều định dạng tài liệu, bao gồm PDF, Microsoft Office (Word, Excel, PowerPoint), hình ảnh, v.v.
### GroupDocs.Viewer có tương thích với .NET Core không?
Có, GroupDocs.Viewer cho .NET tương thích với cả .NET Framework và .NET Core.
### Tôi có thể tùy chỉnh giao diện trình xem theo chủ đề của ứng dụng không?
Có, GroupDocs.Viewer cung cấp nhiều tùy chọn tùy chỉnh, cho phép bạn tùy chỉnh giao diện trình xem sao cho phù hợp với chủ đề ứng dụng của bạn một cách liền mạch.