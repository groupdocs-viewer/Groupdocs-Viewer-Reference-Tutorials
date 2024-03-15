---
title: Đặt giấy phép đo lường
linktitle: Đặt giấy phép đo lường
second_title: API GroupDocs.Viewer .NET
description: Nâng cao các ứng dụng .NET của bạn với GroupDocs.Viewer để xem tài liệu liền mạch. Dễ dàng tích hợp các chức năng kết xuất tài liệu vào dự án của bạn.
type: docs
weight: 12
url: /vi/net/getting-started/set-metered-license/
---
## Giới thiệu
Trong thế giới phát triển .NET, việc kết hợp khả năng xem tài liệu mạnh mẽ vào ứng dụng của bạn là điều cần thiết để nâng cao trải nghiệm và chức năng của người dùng. GroupDocs.Viewer dành cho .NET cung cấp giải pháp mạnh mẽ để tích hợp liền mạch các chức năng xem tài liệu vào các dự án .NET của bạn. Cho dù bạn đang làm việc với tệp PDF, tài liệu Microsoft Office hay các định dạng hình ảnh khác nhau, GroupDocs.Viewer sẽ đơn giản hóa quá trình kết xuất và hiển thị các tài liệu này trong ứng dụng của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào triển khai GroupDocs.Viewer cho .NET, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt GroupDocs.Viewer cho .NET
 Để bắt đầu, bạn cần tải xuống và cài đặt GroupDocs.Viewer cho .NET. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.groupdocs.com/viewer/net/). Làm theo hướng dẫn cài đặt được cung cấp để thiết lập thư viện trong môi trường phát triển của bạn.
### 2. Lấy giấy phép đo
Để sử dụng GroupDocs.Viewer cho .NET, bạn cần có giấy phép đồng hồ đo. Giấy phép này cho phép bạn kiểm soát và giám sát việc sử dụng API của mình dựa trên hạn ngạch được xác định trước. Thực hiện theo các bước bên dưới để thiết lập giấy phép đo của bạn:

## Nhập không gian tên
Trước tiên, hãy đảm bảo bạn nhập các vùng tên cần thiết để truy cập chức năng do GroupDocs.Viewer cung cấp cho .NET:
```csharp
using System;
```

Bây giờ, hãy chia mã ví dụ được cung cấp thành nhiều bước:
## Bước 1: Khai báo khóa công khai và khóa riêng
Khai báo các biến để lưu trữ khóa chung và khóa riêng của bạn:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Đảm bảo thay thế`"YOUR_PUBLIC_KEY"` Và`"YOUR_PRIVATE_KEY"` với các phím thực tế của bạn.
## Bước 2: Đặt giấy phép đo
Kiểm tra xem khóa công khai có được cung cấp hay không. Nếu không, hãy nhắc người dùng đặt khóa:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://buy.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Bước 3: Khởi tạo đối tượng đo và đặt giấy phép
Khởi tạo đối tượng Metered và đặt giấy phép đo bằng cách sử dụng khóa chung và khóa riêng của bạn:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Bước 4: Tin nhắn xác nhận
Hiển thị thông báo xác nhận cho biết giấy phép đã được đặt thành công:
```csharp
Console.WriteLine("License set successfully.");
```

## Phần kết luận
Tóm lại, GroupDocs.Viewer dành cho .NET cung cấp giải pháp toàn diện để kết hợp các chức năng xem tài liệu vào các ứng dụng .NET của bạn. Bằng cách làm theo các bước đã nêu, bạn có thể dễ dàng thiết lập giấy phép được đo lường và bắt đầu tận dụng các khả năng của GroupDocs.Viewer trong các dự án của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tìm tài liệu về GroupDocs.Viewer dành cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu[đây](https://reference.groupdocs.com/viewer/net/).
### Câu hỏi: Có bản dùng thử miễn phí GroupDocs.Viewer dành cho .NET không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.groupdocs.com/).
### Hỏi: Làm cách nào tôi có thể xin được giấy phép tạm thời cho mục đích thử nghiệm?
 Giấy phép tạm thời có thể được lấy[đây](https://purchase.groupdocs.com/temporary-license/).
### Câu hỏi: Tôi có thể tìm kiếm hỗ trợ hoặc đặt câu hỏi liên quan đến GroupDocs.Viewer cho .NET ở đâu?
 Bạn có thể tìm kiếm sự hỗ trợ và đặt câu hỏi trên diễn đàn GroupDocs.Viewer[đây](https://forum.groupdocs.com/c/viewer/9).
### Câu hỏi: Tôi có thể mua giấy phép GroupDocs.Viewer cho .NET ở đâu?
 Bạn có thể mua giấy phép[đây](https://purchase.groupdocs.com/buy).