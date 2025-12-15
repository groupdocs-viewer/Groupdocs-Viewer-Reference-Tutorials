---
additionalTitle: GroupDocs API References
date: 2025-12-15
description: Tìm hiểu cách thêm watermark vào tài liệu với GroupDocs.Viewer và khám
  phá cách chuyển đổi Word sang PDF, hiển thị tài liệu dưới dạng HTML, và hiển thị
  bảng tính dưới dạng HTML.
is_root: true
linktitle: GroupDocs.Viewer Tutorials
title: Thêm Đánh Dấu Nước vào Tài liệu – Hướng Dẫn GroupDocs.Viewer
type: docs
url: /vi/
weight: 11
---

# Thêm Watermark vào Tài liệu với GroupDocs.Viewer

Chào mừng đến với trung tâm hướng dẫn GroupDocs.Viewer. Tại đây bạn sẽ tìm thấy bộ sưu tập đầy đủ các hướng dẫn và tài liệu giúp bạn làm chủ các API xem tài liệu mạnh mẽ của chúng tôi cho .NET và Java. Dù bạn đang xây dựng ứng dụng web, ứng dụng desktop hay giải pháp di động, GroupDocs.Viewer cho phép bạn dễ dàng render và hiển thị đa dạng các định dạng tài liệu, bao gồm PDF, Microsoft Office (Word, Excel, PowerPoint), CAD, hình ảnh và nhiều hơn nữa. **Bạn cũng có thể dễ dàng thêm watermark vào tài liệu** để bảo vệ nội dung và củng cố thương hiệu.

## Cách thêm watermark vào tài liệu bằng GroupDocs.Viewer

Thêm watermark là một yêu cầu phổ biến đối với các doanh nghiệp cần bảo vệ thông tin sở hữu hoặc gắn thương hiệu vào mỗi trang xuất. Với GroupDocs.Viewer, bạn có thể áp dụng watermark dạng văn bản hoặc hình ảnh trong quá trình render mà không làm thay đổi tệp gốc. Cách tiếp cận này hoạt động với PDF, tệp Word, bảng tính và thậm chí cả bản vẽ CAD, cung cấp cho bạn lớp bảo vệ nhất quán trên tất cả các định dạng được hỗ trợ.

Dưới đây chúng tôi sẽ hướng dẫn qua các phần chính của thư viện hướng dẫn của chúng tôi. Mỗi phần chứa các hướng dẫn từng bước, đoạn mã mẫu và các mẹo thực hành tốt nhất, giúp bạn nhanh chóng bắt đầu render, chuyển đổi và watermark tài liệu trong ứng dụng của mình.

## Hướng dẫn GroupDocs.Viewer cho .NET

{{% alert color="primary" %}}
Trao quyền cho các ứng dụng .NET của bạn với khả năng xem tài liệu độ chính xác cao. Các hướng dẫn GroupDocs.Viewer cho .NET của chúng tôi cung cấp mọi thông tin bạn cần để tích hợp một trình xem tài liệu mạnh mẽ. Tìm hiểu cách render hơn 170 định dạng tài liệu sang HTML, JPEG, PNG và PDF. Khám phá các chủ đề nâng cao như render bố cục cụ thể trong bản vẽ CAD, xử lý tệp đính kèm tài liệu và tối ưu hiệu năng. Bắt đầu xây dựng trải nghiệm xem tài liệu chuyên nghiệp và vững chắc trong C#, ASP.NET và các framework .NET khác.
{{% /alert %}}

Đây là một số liên kết tới tài nguyên .NET hữu ích:

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
- [Cơ bản render](./net/rendering-basics/)
- [Render nâng cao](./net/advanced-rendering/)
- [Tối ưu hiệu năng](./net/performance-optimization/)
- [Bảo mật & Quyền](./net/security-permissions/)
- [Watermark & Ghi chú](./net/watermarks-annotations/)
- [Hỗ trợ định dạng tệp](./net/file-formats-support/)
- [Render tài liệu trên Cloud & Remote](./net/cloud-remote-document-rendering/)
- [Caching & Quản lý tài nguyên](./net/caching-resource-management/)
- [Metadata & Thuộc tính](./net/metadata-properties/)
- [Xuất & Chuyển đổi](./net/export-conversion/)
- [Render tùy chỉnh](./net/custom-rendering/)

## Hướng dẫn GroupDocs.Viewer cho Java

{{% alert color="primary" %}}
Tích hợp một trình xem tài liệu đa năng và hiệu quả vào các ứng dụng Java của bạn với GroupDocs.Viewer cho Java. Các hướng dẫn của chúng tôi sẽ dẫn bạn qua từng bước, từ thiết lập môi trường đến triển khai các tính năng render nâng cao. Học cách hiển thị nhiều định dạng tệp, bao gồm các tài liệu phức tạp như tệp CAD đa bố cục và các kho lưu trữ được bảo vệ bằng mật khẩu. Theo dõi các ví dụ của chúng tôi để render tài liệu sang HTML5, hình ảnh và PDF, cho phép xem tài liệu đa nền tảng một cách dễ dàng.
{{% /alert %}}

Đây là một số liên kết tới tài nguyên Java hữu ích:

- [Bắt đầu](./java/getting-started/)
- [Tải tài liệu](./java/document-loading/)
- [Cơ bản render](./java/rendering-basics/)
- [Render nâng cao](./java/advanced-rendering/)
- [Tối ưu hiệu năng](./java/performance-optimization/)
- [Bảo mật & Quyền](./java/security-permissions/)
- [Watermark & Ghi chú](./java/watermarks-annotations/)
- [Hỗ trợ định dạng tệp](./java/file-formats-support/)
- [Render tài liệu trên Cloud & Remote](./java/cloud-remote-document-rendering/)
- [Caching & Quản lý tài nguyên](./java/caching-resource-management/)
- [Metadata & Thuộc tính](./java/metadata-properties/)
- [Xuất & Chuyển đổi](./java/export-conversion/)
- [Render tùy chỉnh](./java/custom-rendering/)

---

**Cập nhật lần cuối:**2025-12-15  
**Tác giả:** GroupDocs