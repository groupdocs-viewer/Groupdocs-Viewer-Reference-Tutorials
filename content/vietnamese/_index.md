---
additionalTitle: GroupDocs API References
date: 2025-12-15
description: Tìm hiểu cách thêm watermark vào tài liệu bằng GroupDocs.Viewer và render
  các tệp PDF .NET. Thành thạo việc xem hơn 170 định dạng trong .NET và Java.
is_root: true
linktitle: GroupDocs.Viewer Tutorials
title: Thêm Đánh Dấu Nước cho Tài liệu với Hướng Dẫn GroupDocs.Viewer
type: docs
url: /vi/
weight: 11
---

# Hướng dẫn GroupDocs.Viewer

Chào mừng bạn đến với trung tâm hướng dẫn GroupDocs.Viewer. Tại đây bạn sẽ tìm thấy bộ sưu tập đầy đủ các hướng dẫn và tài liệu giúp bạn **add watermark document** và làm chủ các API xem tài liệu mạnh mẽ của chúng tôi cho .NET và Java. Dù bạn đang xây dựng ứng dụng web, ứng dụng desktop hay giải pháp di động, GroupDocs.Viewer cho phép bạn dễ dàng render và hiển thị đa dạng các định dạng tài liệu, bao gồm PDF, Microsoft Office (Word, Excel, PowerPoint), CAD, hình ảnh và hơn thế nữa.

## Câu trả lời nhanh
- **What does “add watermark document” mean?** Nó đề cập đến việc nhúng một lớp văn bản hoặc hình ảnh bán trong suốt lên mỗi trang của tài liệu đã được render.  
- **Which formats support watermarks?** Tất cả các định dạng được GroupDocs.Viewer render, bao gồm PDF, DOCX, XLSX, CAD và các tin nhắn email.  
- **Do I need a license?** Cần có giấy phép GroupDocs.Viewer hợp lệ để sử dụng trong môi trường production; bạn có thể dùng bản dùng thử miễn phí.  
- **Can I combine watermarks with other features?** Có—watermarks có thể được áp dụng cùng với caching, custom rendering và các cài đặt bảo mật.  
- **Is it compatible with .NET Core?** Chắc chắn—GroupDocs.Viewer hoạt động với .NET Framework, .NET Core và .NET 5/6+.

## Hướng dẫn GroupDocs.Viewer cho .NET

{{% alert color="primary" %}}
Tăng cường khả năng xem tài liệu chất lượng cao cho các ứng dụng .NET của bạn. Các hướng dẫn GroupDocs.Viewer cho .NET của chúng tôi cung cấp mọi thông tin cần thiết để tích hợp một trình xem tài liệu mạnh mẽ. Học cách render hơn 170 định dạng tài liệu sang HTML, JPEG, PNG và PDF. Khám phá các chủ đề nâng cao như render bố cục cụ thể trong bản vẽ CAD, xử lý tệp đính kèm tài liệu và tối ưu hiệu năng. Bắt đầu xây dựng các trải nghiệm xem tài liệu chuyên nghiệp và vững chắc trong C#, ASP.NET và các framework .NET khác.
{{% /alert %}}

Đây là các liên kết tới một số tài nguyên .NET hữu ích:
 
- [Tải tài liệu](./net/loading-documents/)
- [Tùy chọn tải nâng cao](./net/advanced-loading/)
- [Sử dụng nâng cao (Caching)](./net/advanced-usage-caching/)
- [Tùy chọn render](./net/rendering-options/)
- [Render tệp lưu trữ](./net/rendering-archive-files/)
- [Render bản vẽ CAD](./net/rendering-cad-drawings/)
- [Bắt đầu](./net/getting-started/)
- [Render tin nhắn email](./net/rendering-email-messages/)
- [Render hình ảnh](./net/image-rendering/)
- [Render tài liệu sang PDF](./net/rendering-documents-pdf/)
- [Render tài liệu sang hình ảnh](./net/rendering-documents-images/)
- [Render tài liệu sang HTML](./net/rendering-documents-html/)
- [Xử lý tệp đính kèm tài liệu](./net/processing-document-attachments/)
- [Render tệp văn bản](./net/rendering-text-files/)
- [Render tài liệu Visio](./net/rendering-visio-documents/)
- [Render tài liệu web](./net/rendering-web-documents/)
- [Render tài liệu xử lý văn bản](./net/rendering-word-processing-documents/)
- [Tùy chọn render bảng tính](./net/spreadsheet-rendering-options/)
- [Tùy chọn render PDF](./net/pdf-rendering-options/)
- [Render tệp dữ liệu Outlook (PST, OST)](./net/rendering-outlook-data-files/)
- [Render tài liệu Microsoft Project](./net/rendering-ms-project-documents/)
- [Tải tài liệu](./net/document-loading/)
- [Cơ bản về render](./net/rendering-basics/)
- [Render nâng cao](./net/advanced-rendering/)
- [Tối ưu hiệu năng](./net/performance-optimization/)
- [Bảo mật & Quyền](./net/security-permissions/)
- [Watermarks & Annotations](./net/watermarks-annotations/)
- [Hỗ trợ định dạng tệp](./net/file-formats-support/)
- [Render tài liệu trên đám mây & từ xa](./net/cloud-remote-document-rendering/)
- [Caching & Quản lý tài nguyên](./net/caching-resource-management/)
- [Metadata & Thuộc tính](./net/metadata-properties/)
- [Xuất & Chuyển đổi](./net/export-conversion/)
- [Render tùy chỉnh](./net/custom-rendering/)

## Cách thêm Watermark Document với GroupDocs.Viewer

Thêm watermark thường cần thiết cho việc xây dựng thương hiệu, bảo mật thông tin hoặc tuân thủ quy định. Với GroupDocs.Viewer bạn có thể áp dụng watermark khi render tài liệu sang HTML, PDF hoặc các định dạng hình ảnh. Quy trình rất đơn giản:

1. **Create a `WatermarkOptions` object** và thiết lập văn bản, màu, độ trong suốt và góc quay.  
2. **Pass the options** tới phương thức render phù hợp (ví dụ: `RenderToPdf`, `RenderToHtml` hoặc `RenderToImage`).  
3. **Render the document**—kết quả sẽ chứa watermark trên mọi trang.

Cách tiếp cận này hoạt động trên tất cả các loại tệp được hỗ trợ, bao gồm các kịch bản **render pdf .net**, bản vẽ CAD và tin nhắn email.

## Hướng dẫn GroupDocs.Viewer cho Java

{{% alert color="primary" %}}
Tích hợp một trình xem tài liệu đa năng và hiệu quả vào các ứng dụng Java của bạn với GroupDocs.Viewer cho Java. Các hướng dẫn của chúng tôi sẽ dẫn bạn qua từng bước, từ thiết lập môi trường đến triển khai các tính năng render nâng cao. Học cách hiển thị nhiều định dạng tệp, bao gồm các tài liệu phức tạp như tệp CAD đa bố cục và các tệp lưu trữ được bảo vệ bằng mật khẩu. Thực hành các ví dụ để render tài liệu sang HTML5, hình ảnh và PDF, giúp bạn dễ dàng triển khai xem tài liệu đa nền tảng.
{{% /alert %}}

Đây là các liên kết tới một số tài nguyên Java hữu ích:

- [Bắt đầu](./java/getting-started/)
- [Tải tài liệu](./java/document-loading/)
- [Cơ bản về render](./java/rendering-basics/)
- [Render nâng cao](./java/advanced-rendering/)
- [Tối ưu hiệu năng](./java/performance-optimization/)
- [Bảo mật & Quyền](./java/security-permissions/)
- [Watermarks & Annotations](./java/watermarks-annotations/)
- [Hỗ trợ định dạng tệp](./java/file-formats-support/)
- [Render tài liệu trên đám mây & từ xa](./java/cloud-remote-document-rendering/)
- [Caching & Quản lý tài nguyên](./java/caching-resource-management/)
- [Metadata & Thuộc tính](./java/metadata-properties/)
- [Xuất & Chuyển đổi](./java/export-conversion/)
- [Render tùy chỉnh](./java/custom-rendering/)

## Câu hỏi thường gặp

**Q: Can I add a watermark to documents rendered as images?**  
A: Có—sử dụng `WatermarkOptions` cùng với `RenderToImage` để nhúng watermark lên mỗi trang hình ảnh được tạo.

**Q: Does adding a watermark affect rendering performance?**  
A: Ảnh hưởng là tối thiểu; GroupDocs.Viewer tối ưu quá trình overlay, đặc biệt khi kết hợp với caching.

**Q: Are watermarks supported when rendering email messages?**  
A: Chắc chắn—watermarks có thể được áp dụng cho đầu ra HTML hoặc PDF của các tin nhắn email đã render.

**Q: How do I customize watermark appearance?**  
A: Bạn có thể đặt phông chữ, kích thước, màu, độ trong suốt, góc quay và thậm chí sử dụng hình ảnh làm watermark.

**Q: Is it possible to apply different watermarks to different pages?**  
A: API tiêu chuẩn áp dụng watermark đồng nhất, nhưng bạn có thể triển khai logic render tùy chỉnh để thay đổi watermark theo từng trang.

---

**Last Updated:** 2025-12-15  
**Tested With:** GroupDocs.Viewer 23.11 for .NET & Java  
**Author:** GroupDocs