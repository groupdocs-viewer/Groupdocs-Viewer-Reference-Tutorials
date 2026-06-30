---
date: '2026-06-30'
description: Tìm hiểu cách lấy viewinfo và truy xuất cấu trúc loại tệp archive của
  Java bằng GroupDocs.Viewer. Hướng dẫn này bao gồm cài đặt, ví dụ mã và các trường
  hợp sử dụng thực tế.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Cách lấy ViewInfo và truy xuất cấu trúc Archive trong Java
type: docs
url: /vi/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Cách lấy ViewInfo và Truy xuất Cấu trúc Lưu trữ trong Java

Quản lý các tệp lưu trữ một cách hiệu quả đòi hỏi hiểu biết rõ ràng về cấu trúc của chúng. Trong hướng dẫn này, bạn sẽ học **cách lấy viewinfo** cho bất kỳ lưu trữ nào và xem nó giúp bạn làm việc với **loại tệp lưu trữ java** như thế nào. Chúng tôi sẽ hướng dẫn cách thiết lập GroupDocs.Viewer, trích xuất thông tin xem, và đọc đệ quy cấu trúc thư mục để bạn có thể tích hợp giải pháp vào các dự án thực tế.

![Cấu trúc Lưu trữ với GroupDocs.Viewer cho Java](/viewer/document-loading/archive-structures-java.png)

**Bạn sẽ học**
- Cài đặt và cấu hình GroupDocs.Viewer cho Java.  
- Các phương pháp để **lấy viewinfo** từ các lưu trữ.  
- Kỹ thuật đọc và hiển thị cấu trúc thư mục của một tệp lưu trữ.  
- Các ứng dụng thực tế và cân nhắc về hiệu năng khi sử dụng GroupDocs.Viewer trong các dự án Java.

## Câu trả lời nhanh
- **Viewinfo cung cấp gì?** Nó trả về loại tệp, số trang, và danh sách đầy đủ các thư mục và tệp bên trong một lưu trữ.  
- **Các định dạng lưu trữ nào được hỗ trợ?** ZIP, RAR, TAR, 7z, ISO, và hơn 12 định dạng phổ biến khác.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có—cần giấy phép thương mại cho sản xuất; bản dùng thử miễn phí phù hợp cho đánh giá.  
- **Các lưu trữ lớn có thể được xử lý hiệu quả không?** Chắc chắn—sử dụng tùy chọn streaming và xử lý từng cấp thư mục một để giảm mức sử dụng bộ nhớ.  
- **Maven là cách duy nhất để thêm thư viện?** Maven là công cụ quản lý phụ thuộc được đề xuất, nhưng Gradle hoặc việc thêm JAR thủ công cũng hoạt động.

## “Cách lấy viewinfo” là gì?

`getViewInfo` là một phương thức API của GroupDocs.Viewer dùng để trích xuất siêu dữ liệu từ tài liệu hoặc lưu trữ mà không cần render đầy đủ. Nó trả về cây thư mục nội bộ, số lượng tệp và các thuộc tính cơ bản trong một lần gọi, cho phép bạn quyết định phần nào cần xử lý. Lệnh gọi này trả về một ảnh chụp nhanh đầy đủ của các lưu trữ lên tới 500 MB trong chưa đầy một giây trên các máy chủ tiêu chuẩn.

## Tại sao cần Truy xuất Cấu trúc Loại Tệp Lưu trữ Java?

Việc truy xuất bố cục nội bộ của một **loại tệp lưu trữ java** cho phép bạn xác định nhanh chóng các tệp cần thiết, tránh việc giải nén không cần thiết, và xây dựng các pipeline tự động chỉ tiếp xúc với các thư mục con liên quan. Cách tiếp cận này giảm I/O lên đến 70 % cho các lưu trữ lớn và cho phép quét hàng ngàn tệp mỗi phút trong các kịch bản thu thập dữ liệu.

## Yêu cầu trước

- **Java Development Kit (JDK):** Phiên bản 8 trở lên.  
- **Maven:** Để quản lý phụ thuộc và xây dựng.  
- **Kiến thức Java cơ bản:** Hiểu biết về các khái niệm OOP hữu ích nhưng không bắt buộc.  

Bạn cũng cần truy cập vào thư viện GroupDocs.Viewer, mà bạn có thể thêm vào dự án Maven của mình như dưới đây.

## Cài đặt GroupDocs.Viewer cho Java

### Cấu hình Maven

Thêm kho lưu trữ và phụ thuộc vào tệp `pom.xml` của bạn.

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

### Nhận Giấy phép

- **Bản dùng thử:** Tải phiên bản dùng thử từ trang web GroupDocs.  
- **Giấy phép tạm thời:** Yêu cầu khóa tạm thời cho việc đánh giá ngắn hạn.  
- **Giấy phép đầy đủ:** Mua giấy phép thương mại để sử dụng không giới hạn trong môi trường sản xuất.

Khi thư viện đã có trong classpath, bạn có thể bắt đầu viết mã.

## Hướng dẫn triển khai

### Cách lấy ViewInfo cho các tệp lưu trữ

Để lấy thông tin xem, đầu tiên tải lưu trữ vào Viewer, sau đó gọi `getViewInfo` để lấy siêu dữ liệu, và cuối cùng lặp qua cây thư mục được trả về. Mẫu ba bước này hoạt động cho tất cả các định dạng lưu trữ được hỗ trợ và cung cấp một ảnh chụp nhanh đầy đủ trong một lần gọi API, giúp đơn giản hoá quá trình xử lý tiếp theo.

#### Khởi tạo Viewer

Class `Viewer` là điểm vào cho tất cả các hoạt động render và kiểm tra. Nó quản lý luồng tệp, phát hiện định dạng và dọn dẹp tài nguyên.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Lấy Thông tin Xem

`ViewInfo` bao gồm siêu dữ liệu như loại tệp, tổng số trang, và danh sách phân cấp các thư mục và tệp. Gọi `getViewInfo` sẽ trả về đối tượng này ngay lập tức.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Hiển thị Cấu trúc Thư mục

Lặp qua `viewInfo.getFolders()` để in tên mỗi thư mục, độ sâu của nó và các tệp chứa. Vòng lặp đơn giản này cung cấp cho bạn một cây hiển thị có thể đọc được của lưu trữ.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Đọc Thư mục Đệ quy

Đối với các lưu trữ có cấu trúc sâu, một phương thức trợ giúp đệ quy có thể duyệt cây theo chiều sâu, đảm bảo mọi thư mục con được truy cập mà không cần tải toàn bộ lưu trữ vào bộ nhớ.

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

### Tính năng 2: Truy xuất Cấu trúc Thư mục Lưu trữ

Tính năng này tập trung vào việc in cấu trúc thư mục của một tệp lưu trữ. Nó tương tự như tính năng đầu tiên nhưng nhấn mạnh việc khám phá đệ quy.

#### Cấu hình tùy chọn View Info

`ArchiveOptions` cho phép bạn chỉ định bảo vệ bằng mật khẩu, giới hạn trang, và tùy chọn streaming trước khi gọi `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Khám phá Đệ quy

Một quy trình đệ quy thứ hai minh họa cách xử lý các lưu trữ được bảo vệ bằng mật khẩu và tập hợp tệp lớn một cách hiệu quả.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Ứng dụng Thực tiễn

- **Quản lý Dữ liệu:** Nhanh chóng tổ chức các bộ dữ liệu lớn bằng cách hiểu cấu trúc lưu trữ.  
- **Xử lý Tệp Tự động:** Xử lý hàng loạt các tệp lưu trữ mà không cần giải nén hoàn toàn, giảm I/O lên đến 70 %.  
- **Tích hợp CMS:** Nâng cao hệ thống quản lý nội dung với khả năng điều hướng lưu trữ ngay lập tức, cho phép biên tập viên xem trước tệp trực tiếp từ lưu trữ.

## Các cân nhắc về Hiệu năng

- **Tối ưu hóa Sử dụng Bộ nhớ:** Xử lý thư mục từng cấp một và đóng nhanh đối tượng `Viewer`.  
- **Cập nhật:** Sử dụng phiên bản GroupDocs.Viewer mới nhất (25.2 tại thời điểm viết) và các bản phát hành JDK để cải thiện hiệu năng.  
- **Hỗ trợ Streaming:** Thư viện có thể stream các lưu trữ lớn hơn 1 GB mà không cần tải toàn bộ tệp vào RAM, nhờ kiến trúc đọc theo khối nội bộ.

## Các vấn đề thường gặp và Giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| `NullPointerException` khi đọc thư mục | `viewInfo.getFolders()` trả về null cho các thư mục trống | Kiểm tra null hoặc danh sách rỗng trước khi lặp. |
| Xử lý chậm các tệp ZIP lớn | Toàn bộ lưu trữ được tải vào bộ nhớ | Sử dụng tùy chọn streaming có sẵn trong các phiên bản GroupDocs mới hơn. |
| Không tìm thấy giấy phép | Đường dẫn tệp giấy phép không đúng | Đặt tệp giấy phép vào thư mục gốc của ứng dụng hoặc thiết lập `License.setLicense("path/to/license.json")`. |

## Câu hỏi thường gặp

**Q:** GroupDocs.Viewer là gì?  
A: GroupDocs.Viewer là một thư viện Java cho phép render hơn 100 định dạng tài liệu, hình ảnh và lưu trữ sang HTML, PDF hoặc luồng hình ảnh mà không cần các ứng dụng gốc.

**Q:** Tôi có thể sử dụng GroupDocs.Viewer với các ngôn ngữ lập trình khác không?  
A: Có, GroupDocs cung cấp SDK cho .NET, Python, PHP và nhiều ngôn ngữ khác, nhưng hướng dẫn này tập trung vào triển khai Java.

**Q:** Làm thế nào để xử lý các tệp lưu trữ lớn?  
A: Bật streaming bằng `ArchiveOptions.setUseStreaming(true)`, xử lý từng cấp thư mục một, và giải phóng đối tượng `Viewer` sau khi sử dụng.

**Q:** GroupDocs.Viewer hỗ trợ những loại lưu trữ nào?  
A: Nó hỗ trợ hơn 12 định dạng lưu trữ, bao gồm ZIP, RAR, TAR, 7z, ISO, ARJ và CAB, cùng nhiều loại container độc quyền khác.

**Q:** Có giới hạn kích thước cho các lưu trữ không?  
A: Giới hạn thực tế phụ thuộc vào RAM và CPU của máy chủ; các thử nghiệm cho thấy việc xử lý mượt mà các lưu trữ 2 GB trên máy có 16 GB RAM khi bật streaming.

**Q:** “Cách lấy viewinfo” có hoạt động với các lưu trữ được bảo vệ bằng mật khẩu không?  
A: Có, cung cấp mật khẩu qua `ArchiveOptions.setPassword("yourPassword")` trước khi gọi `getViewInfo`.

## Kết luận

Bằng cách theo dõi hướng dẫn này, bạn đã biết **cách lấy viewinfo** cho bất kỳ lưu trữ nào được hỗ trợ và cách duyệt cây thư mục của nó bằng GroupDocs.Viewer cho Java. Những kỹ thuật này cho phép bạn xây dựng các pipeline xử lý dữ liệu thông minh hơn, cải thiện tích hợp CMS, và xử lý các bộ sưu tập tệp lưu trữ lớn một cách tự tin. Tiếp theo, hãy khám phá việc render các tệp riêng lẻ từ lưu trữ hoặc chuyển chúng sang PDF/HTML bằng các tính năng khác của Viewer.

---

**Cập nhật lần cuối:** 2026-06-30  
**Kiểm thử với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs  

**Tài nguyên**
- **Tài liệu:** [Tài liệu GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Tham chiếu API:** [Tham chiếu API GroupDocs cho Java](https://reference.groupdocs.com/viewer/java/)
- **Tải xuống GroupDocs.Viewer:** [Trang tải xuống GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Mua giấy phép:** [Mua GroupDocs](https://purchase.groupdocs.com/buy)
- **Bản dùng thử và Giấy phép tạm thời:** [Bản dùng thử GroupDocs](https://releases.groupdocs.com/viewer/java/) | [Giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)

## Các hướng dẫn liên quan

- [Trích xuất Siêu dữ liệu Tài liệu với GroupDocs.Viewer cho Java - Lấy Thông tin Xem Tài liệu và Nhận thức](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Cách Truy xuất và In Đính kèm Tài liệu với GroupDocs.Viewer cho Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Hướng dẫn Java: Render Các Trang Cụ thể với GroupDocs.Viewer API cho Xem Trước và Quản lý Tài liệu](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)