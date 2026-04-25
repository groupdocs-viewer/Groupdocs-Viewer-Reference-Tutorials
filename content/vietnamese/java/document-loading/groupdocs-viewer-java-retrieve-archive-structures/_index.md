---
date: '2026-02-05'
description: Tìm hiểu cách lấy viewinfo và truy xuất cấu trúc các tệp kiểu Java archive
  bằng GroupDocs.Viewer. Hướng dẫn này bao gồm cài đặt, ví dụ mã và các trường hợp
  sử dụng thực tế.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Cách lấy ViewInfo và truy xuất cấu trúc lưu trữ trong Java
type: docs
url: /vi/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Cách lấy ViewInfo và truy xuất cấu trúc lưu trữ trong Java

Quản lý các tệp lưu trữ một cách hiệu quả đòi hỏi phải hiểu rõ cấu trúc của chúng. Trong hướng dẫn này, bạn sẽ học **cách lấy viewinfo** cho bất kỳ lưu trữ nào và xem nó giúp bạn làm việc với **loại tệp lưu trữ java** như thế nào. Chúng tôi sẽ hướng dẫn cách thiết lập GroupDocs.Viewer, trích xuất thông tin xem, và đọc đệ quy các cây thư mục để bạn có thể tích hợp giải pháp vào các dự án thực tế.

![Cấu trúc lưu trữ với GroupDocs.Viewer cho Java](/viewer/document-loading/archive-structures-java.png)

**Bạn sẽ học**
- Cài đặt và cấu hình GroupDocs.Viewer cho Java.  
- Các phương pháp để **lấy viewinfo** từ các lưu trữ.  
- Kỹ thuật đọc và hiển thị cấu trúc thư mục của tệp lưu trữ.  
- Các ứng dụng thực tế và cân nhắc về hiệu năng khi sử dụng GroupDocs.Viewer trong các dự án Java.

## Câu trả lời nhanh
- **viewinfo** cung cấp gì? Nó trả về loại tệp, số trang và danh sách thư mục trong lưu trữ.  
- **Các loại lưu trữ nào được hỗ trợ?** ZIP, RAR, TAR và các định dạng phổ biến khác.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể xử lý các lưu trữ lớn không?** Có – sử dụng streaming và quản lý bộ nhớ hợp lý như được mô tả sau.  
- **Có cần Maven không?** Maven là cách được khuyến nghị để quản lý phụ thuộc GroupDocs.Viewer.

## “Cách lấy viewinfo” là gì?
`getViewInfo` là một phương thức trong API GroupDocs.Viewer giúp trích xuất siêu dữ liệu về tài liệu hoặc lưu trữ mà không cần render toàn bộ nội dung. Đối với các lưu trữ, nó hiển thị cây thư mục bên trong, cho phép bạn quyết định phần nào cần render hoặc xử lý tiếp.

## Tại sao cần truy xuất cấu trúc loại tệp lưu trữ Java?
Hiểu rõ bố cục bên trong của **loại tệp lưu trữ java** (ví dụ: ZIP, RAR) giúp bạn:
- Nhanh chóng xác định các tệp cần thiết mà không phải giải nén toàn bộ.  
- Xây dựng các pipeline tự động chỉ xử lý các thư mục con liên quan.  
- Tích hợp điều hướng lưu trữ vào hệ thống quản lý nội dung hoặc quy trình nhập dữ liệu.

## Các yêu cầu trước

- **Java Development Kit (JDK):** Phiên bản 8 hoặc mới hơn.  
- **Maven:** Để quản lý phụ thuộc và xây dựng.  
- **Kiến thức Java cơ bản:** Hiểu biết về các khái niệm OOP hữu ích nhưng không bắt buộc.

Bạn cũng cần truy cập vào thư viện GroupDocs.Viewer, có thể thêm vào dự án Maven như dưới đây.

## Cài đặt GroupDocs.Viewer cho Java

### Cấu hình Maven

Thêm kho lưu trữ và phụ thuộc vào `pom.xml` của bạn.

**Kho lưu trữ:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Phụ thuộc:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Cách lấy giấy phép

- **Bản dùng thử:** Tải phiên bản dùng thử từ trang web GroupDocs.  
- **Giấy phép tạm thời:** Yêu cầu khóa tạm thời cho việc đánh giá ngắn hạn.  
- **Giấy phép đầy đủ:** Mua giấy phép thương mại để sử dụng không giới hạn trong sản xuất.

Khi thư viện đã có trong classpath, bạn có thể bắt đầu viết mã.

## Hướng dẫn triển khai

### Cách lấy ViewInfo cho các tệp lưu trữ

Phần này trình bày các bước chính xác để gọi `getViewInfo` và đọc cây thư mục.

#### Khởi tạo Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Lấy thông tin xem

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Hiển thị cấu trúc thư mục

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Đọc thư mục đệ quy

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Tính năng 2: Truy xuất cấu trúc thư mục lưu trữ

Tính năng này tập trung vào việc in cấu trúc thư mục của một tệp lưu trữ. Nó tương tự như tính năng đầu tiên nhưng nhấn mạnh vào việc khám phá đệ quy.

#### Cấu hình tùy chọn View Info

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Khám phá đệ quy

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Ứng dụng thực tế

1. **Quản lý dữ liệu:** Nhanh chóng tổ chức các bộ dữ liệu lớn bằng cách hiểu cấu trúc lưu trữ.  
2. **Xử lý tệp tự động:** Xử lý hàng loạt các tệp lưu trữ mà không cần giải nén toàn bộ.  
3. **Tích hợp CMS:** Nâng cao hệ thống quản lý nội dung với khả năng điều hướng lưu trữ ngay trong quá trình.

## Cân nhắc về hiệu năng

- **Tối ưu sử dụng bộ nhớ:** Xử lý thư mục từng cấp một và đóng instance `Viewer` ngay khi xong.  
- **Cập nhật thường xuyên:** Sử dụng phiên bản GroupDocs.Viewer mới nhất và các bản phát hành JDK để cải thiện hiệu năng.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| `NullPointerException` khi đọc thư mục | `viewInfo.getFolders()` trả về null cho các thư mục trống | Kiểm tra null hoặc danh sách rỗng trước khi lặp. |
| Xử lý chậm các tệp ZIP lớn | Toàn bộ lưu trữ được tải vào bộ nhớ | Sử dụng các tùy chọn streaming có trong các phiên bản GroupDocs mới hơn. |
| License not found | Đường dẫn tệp giấy phép không đúng | Đặt tệp giấy phép vào thư mục gốc của ứng dụng hoặc thiết lập `License.setLicense("path/to/license.json")`. |

## Câu hỏi thường gặp

**Q: GroupDocs.Viewer là gì?**  
A: Đây là một thư viện Java mạnh mẽ để hiển thị tài liệu, bao gồm cả các lưu trữ, thành các định dạng như HTML, hình ảnh và PDF.

**Q: Tôi có thể sử dụng GroupDocs.Viewer với các ngôn ngữ lập trình khác không?**  
A: Có, GroupDocs cung cấp SDK cho nhiều nền tảng, nhưng hướng dẫn này tập trung vào triển khai Java.

**Q: Làm sao để xử lý các tệp lưu trữ lớn?**  
A: Sử dụng các thực hành quản lý bộ nhớ hiệu quả, và cân nhắc chia nhỏ các lưu trữ nếu cần.

**Q: GroupDocs.Viewer hỗ trợ những loại lưu trữ nào?**  
A: Nó hỗ trợ nhiều định dạng bao gồm ZIP, RAR, TAR và các định dạng khác.

**Q: Có giới hạn nào về kích thước lưu trữ tôi có thể xử lý không?**  
A: Giới hạn phụ thuộc vào tài nguyên hệ thống của bạn. Hãy thử nghiệm trong môi trường mục tiêu để xác định giới hạn thực tế.

**Q: “cách lấy viewinfo” có hoạt động với các lưu trữ được bảo vệ bằng mật khẩu không?**  
A: Có, bạn có thể cung cấp mật khẩu bằng cách gọi `ArchiveOptions.setPassword("yourPassword")` trước khi gọi `getViewInfo`.

## Kết luận

Bằng cách làm theo hướng dẫn này, bạn đã biết **cách lấy viewinfo** cho bất kỳ lưu trữ nào được hỗ trợ và cách duyệt cây thư mục của nó bằng GroupDocs.Viewer cho Java. Những kỹ thuật này giúp bạn xây dựng các pipeline xử lý dữ liệu thông minh hơn, cải thiện tích hợp CMS và xử lý các bộ sưu tập tệp lưu trữ lớn một cách tự tin. Tiếp theo, hãy khám phá việc render các tệp riêng lẻ từ lưu trữ hoặc chuyển đổi chúng sang PDF/HTML bằng các tính năng khác của Viewer.

---

**Last Updated:** 2026-02-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Tài nguyên**
- **Tài liệu:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Tham chiếu API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Tải GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Mua giấy phép:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Bản dùng thử và Giấy phép tạm thời:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)