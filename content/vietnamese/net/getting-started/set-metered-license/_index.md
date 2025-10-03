---
"description": "Nâng cao ứng dụng .NET của bạn với GroupDocs.Viewer để xem tài liệu liền mạch. Dễ dàng tích hợp chức năng kết xuất tài liệu vào dự án của bạn."
"linktitle": "Thiết lập giấy phép đo lường"
"second_title": "API GroupDocs.Viewer .NET"
"title": "Thiết lập giấy phép đo lường"
"url": "/vi/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# Thiết lập giấy phép đo lường

## Giới thiệu
Trong thế giới phát triển .NET, việc tích hợp các khả năng xem tài liệu mạnh mẽ vào ứng dụng của bạn là điều cần thiết để nâng cao trải nghiệm và chức năng của người dùng. GroupDocs.Viewer cho .NET cung cấp giải pháp mạnh mẽ để tích hợp liền mạch các chức năng xem tài liệu vào các dự án .NET của bạn. Cho dù bạn đang làm việc với PDF, tài liệu Microsoft Office hay nhiều định dạng hình ảnh khác nhau, GroupDocs.Viewer đều đơn giản hóa quy trình kết xuất và hiển thị các tài liệu này trong ứng dụng của bạn.

![Thiết lập Giấy phép theo định mức với GroupDocs.Viewer cho .NET](/viewer/getting-started/set-metered-license.png)

## Điều kiện tiên quyết
Trước khi bắt đầu triển khai GroupDocs.Viewer cho .NET, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
Để bắt đầu, bạn cần tải xuống và cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tìm thấy liên kết tải xuống [đây](https://releases.groupdocs.com/viewer/net/). Thực hiện theo hướng dẫn cài đặt được cung cấp để thiết lập thư viện trong môi trường phát triển của bạn.
### 2. Xin giấy phép đo lường
Để sử dụng GroupDocs.Viewer cho .NET, bạn cần phải có giấy phép theo định mức. Giấy phép này cho phép bạn kiểm soát và giám sát việc sử dụng API của mình dựa trên hạn ngạch được xác định trước. Thực hiện theo các bước dưới đây để thiết lập giấy phép theo định mức của bạn:

## Nhập không gian tên
Trước tiên, hãy đảm bảo bạn nhập các không gian tên cần thiết để truy cập chức năng do GroupDocs.Viewer cung cấp cho .NET:
```csharp
using System;
```

Bây giờ, chúng ta hãy chia nhỏ mã ví dụ được cung cấp thành nhiều bước:
## Bước 1: Khai báo khóa công khai và khóa riêng tư
Khai báo các biến để lưu trữ khóa công khai và khóa riêng tư của bạn:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Đảm bảo thay thế `"YOUR_PUBLIC_KEY"` Và `"YOUR_PRIVATE_KEY"` bằng chìa khóa thực tế của bạn.
## Bước 2: Thiết lập Giấy phép theo lưu lượng
Kiểm tra xem khóa công khai có được cung cấp không. Nếu không, hãy nhắc người dùng thiết lập khóa:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Bước 3: Khởi tạo Đối tượng được đo lường và Thiết lập Giấy phép
Khởi tạo đối tượng Metered và thiết lập giấy phép metered bằng khóa công khai và khóa riêng tư của bạn:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Bước 4: Tin nhắn xác nhận
Hiển thị thông báo xác nhận cho biết giấy phép đã được thiết lập thành công:
```csharp
Console.WriteLine("License set successfully.");
```

## Phần kết luận
Tóm lại, GroupDocs.Viewer for .NET cung cấp giải pháp toàn diện để kết hợp chức năng xem tài liệu vào ứng dụng .NET của bạn. Bằng cách làm theo các bước được nêu, bạn có thể dễ dàng thiết lập giấy phép có giới hạn và bắt đầu tận dụng các khả năng của GroupDocs.Viewer trong các dự án của mình.
## Câu hỏi thường gặp
### H: Tôi có thể tìm tài liệu về GroupDocs.Viewer cho .NET ở đâu?
Bạn có thể tìm thấy tài liệu [đây](https://tutorials.groupdocs.com/viewer/net/).
### H: Có bản dùng thử miễn phí của GroupDocs.Viewer dành cho .NET không?
Có, bạn có thể truy cập bản dùng thử miễn phí [đây](https://releases.groupdocs.com/).
### H: Tôi có thể xin giấy phép tạm thời cho mục đích thử nghiệm như thế nào?
Có thể xin được giấy phép tạm thời [đây](https://purchase.groupdocs.com/temporary-license/).
### H: Tôi có thể tìm kiếm sự hỗ trợ hoặc đặt câu hỏi liên quan đến GroupDocs.Viewer cho .NET ở đâu?
Bạn có thể tìm kiếm sự hỗ trợ và đặt câu hỏi trên diễn đàn GroupDocs.Viewer [đây](https://forum.groupdocs.com/c/viewer/9).
### H: Tôi có thể mua giấy phép GroupDocs.Viewer cho .NET ở đâu?
Bạn có thể mua giấy phép [đây](https://purchase.groupdocs.com/buy).