---
"date": "2025-04-25"
"description": "Tìm hiểu cách trích xuất thông tin lưu trữ hiệu quả bằng GroupDocs.Viewer cho .NET. Hướng dẫn này bao gồm thiết lập, ví dụ mã và ứng dụng thực tế."
"title": "Cách lấy thông tin lưu trữ bằng GroupDocs.Viewer cho .NET&#58; Hướng dẫn toàn diện"
"url": "/vi/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
---

# Cách lấy thông tin lưu trữ bằng GroupDocs.Viewer cho .NET: Hướng dẫn toàn diện

## Giới thiệu

Bạn có muốn trích xuất thông tin chi tiết một cách hiệu quả từ các tệp lưu trữ như ZIP không? Hiểu cấu trúc có thể rất quan trọng đối với việc quản lý tài liệu. Hướng dẫn này sẽ chỉ cho bạn cách sử dụng **GroupDocs.Viewer cho .NET** để truy xuất và hiển thị thông tin chi tiết toàn diện về một tệp lưu trữ.

![Truy xuất thông tin lưu trữ với GroupDocs.Viewer cho .NET](/viewer/metadata-properties/retrieve-archive-information.png)

Trong hướng dẫn này, chúng tôi sẽ đề cập đến:
- Thiết lập GroupDocs.Viewer trong ứng dụng .NET của bạn
- Lấy thông tin chế độ xem từ các tệp lưu trữ
- Hiển thị cấu trúc thư mục trong kho lưu trữ

Đến cuối hướng dẫn này, bạn sẽ hiểu rõ cách triển khai các chức năng này. Hãy bắt đầu với những gì bạn cần trước khi đi sâu vào mã.

### Điều kiện tiên quyết

Hãy đảm bảo bạn đã chuẩn bị những thứ sau:

- **Thư viện và Phiên bản**: Cài đặt GroupDocs.Viewer cho .NET (phiên bản 25.3.0).
- **Thiết lập môi trường**: Sử dụng môi trường phát triển .NET phù hợp như Visual Studio.
- **Điều kiện tiên quyết về kiến thức**: Hiểu biết cơ bản về C# và xử lý tệp trong các ứng dụng .NET.

## Thiết lập GroupDocs.Viewer cho .NET

Để sử dụng GroupDocs.Viewer cho .NET, hãy cài đặt nó thông qua NuGet Package Manager:

### Hướng dẫn cài đặt

**Bảng điều khiển quản lý gói NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NETCLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Xin giấy phép

GroupDocs.Viewer cung cấp một số tùy chọn cấp phép:
- **Dùng thử miễn phí**Khám phá các chức năng cơ bản.
- **Giấy phép tạm thời**: Truy cập đầy đủ tính năng trong quá trình đánh giá.
- **Mua**:Để sử dụng lâu dài, hãy cân nhắc việc mua giấy phép.

Sau khi cài đặt và thiết lập giấy phép, hãy khởi tạo GroupDocs.Viewer trong ứng dụng của bạn. Sau đây là ví dụ thiết lập:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // Sử dụng chức năng Viewer ở đây.
}
```

## Hướng dẫn thực hiện

Chúng tôi sẽ chia nhỏ quá trình triển khai thành các tính năng chính để có phương pháp tiếp cận có cấu trúc.

### Lấy thông tin chế độ xem cho các tệp lưu trữ

Hiểu được cấu trúc lưu trữ của bạn là rất quan trọng. Sau đây là cách thực hiện:

#### Khởi tạo đối tượng Viewer

Tạo một phiên bản của `Viewer` lớp với đường dẫn tệp lưu trữ của bạn:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // Mã xử lý của bạn sẽ nằm ở đây.
}
```

#### Lấy thông tin xem

Truy xuất thông tin chế độ xem, được định dạng dưới dạng hình ảnh JPG:

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### Hiển thị thông tin thư mục gốc

Để có cái nhìn tổng quan, hãy in thông tin chi tiết về thư mục gốc:

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### Đọc và in tên thư mục con theo cách đệ quy

Để khám phá các thư mục con trong kho lưu trữ của bạn, hãy sử dụng phương pháp đệ quy này:

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### Ứng dụng thực tế

GroupDocs.Viewer cho .NET có thể được sử dụng trong nhiều trường hợp khác nhau:
- **Hệ thống quản lý tài liệu**: Tự động trích xuất và hiển thị cấu trúc lưu trữ.
- **Nền tảng phân phối nội dung**: Cung cấp bản xem trước nội dung đã lưu trữ cho người dùng.
- **Công cụ phân tích dữ liệu**: Phân tích hệ thống phân cấp thư mục trong kho lưu trữ để có thông tin chi tiết về doanh nghiệp.

Việc tích hợp với các nền tảng khác như ASP.NET hoặc WPF rất đơn giản, cho phép kết hợp liền mạch vào các hệ thống hiện có.

## Cân nhắc về hiệu suất

Để có hiệu suất tối ưu:
- **Tối ưu hóa việc sử dụng tài nguyên**: Quản lý bộ nhớ và xử lý các tập tin lớn một cách hiệu quả.
- **Thực hành quản lý bộ nhớ tốt nhất**: Xử lý `Viewer` các đối tượng một cách hợp lý để giải phóng tài nguyên kịp thời.

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách sử dụng GroupDocs.Viewer cho .NET để lấy thông tin chi tiết từ các tệp lưu trữ. Việc triển khai các tính năng này có thể cải thiện đáng kể khả năng quản lý tài liệu của bạn.

### Các bước tiếp theo

Hãy cân nhắc khám phá các tính năng nâng cao hơn do GroupDocs.Viewer cung cấp hoặc tích hợp nó với các thành phần khác của ứng dụng. Thử nghiệm với các loại tệp khác nhau và cấu trúc thư mục phức tạp để hiểu sâu hơn.

## Phần Câu hỏi thường gặp

1. **Mục đích của việc này là gì? `ViewInfoOptions`?**
   - Nó cấu hình cách bạn muốn xem tài liệu, chẳng hạn như hiển thị các định dạng cụ thể như JPG.

2. **Làm thế nào để xử lý kho lưu trữ lớn một cách hiệu quả?**
   - Sử dụng các kỹ thuật quản lý bộ nhớ và phân bổ tài nguyên hợp lý.

3. **GroupDocs.Viewer có thể xử lý các tệp được bảo vệ bằng mật khẩu không?**
   - Có, với giấy phép và cấu hình phù hợp, phần mềm này có thể xử lý được các tài liệu được mã hóa.

4. **Có giới hạn về kích thước tệp lưu trữ có thể xử lý không?**
   - Giới hạn phụ thuộc vào dung lượng bộ nhớ của hệ thống; các tệp lớn hơn cần nhiều tài nguyên hơn.

5. **Làm thế nào để tích hợp GroupDocs.Viewer với các ứng dụng ASP.NET?**
   - Sử dụng lớp Viewer trong các dịch vụ hoặc hành động điều khiển của bạn, tương tự như cách bạn làm trong ứng dụng bảng điều khiển.

## Tài nguyên

- [Tài liệu](https://docs.groupdocs.com/viewer/net/)
- [Tài liệu tham khảo API](https://reference.groupdocs.com/viewer/net/)
- [Tải xuống GroupDocs.Viewer cho .NET](https://releases.groupdocs.com/viewer/net/)
- [Mua giấy phép](https://purchase.groupdocs.com/buy)
- [Phiên bản dùng thử miễn phí](https://releases.groupdocs.com/viewer/net/)
- [Đơn xin cấp giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9)