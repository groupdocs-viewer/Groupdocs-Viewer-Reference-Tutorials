---
date: '2025-12-21'
description: Tìm hiểu cách tắt tính năng nhóm trong PDF bằng GroupDocs.Viewer cho
  Java, sử dụng java html từ các tùy chọn render PDF để đảm bảo biểu diễn văn bản
  chính xác.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Cách vô hiệu hóa việc nhóm trong PDF bằng GroupDocs.Viewer cho Java
type: docs
url: /vi/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Cách Vô Hiệu Hóa Nhóm Ký Tự trong PDF bằng GroupDocs.Viewer cho Java

Khi bạn cần **cách vô hiệu hoá nhóm** trong quá trình render PDF, đặc biệt với các script phức tạp hoặc ngôn ngữ cổ đại, việc đặt ký tự một cách chính xác trở nên thiết yếu. Tính năng *Character Grouping* mặc định có thể hợp nhất các ký tự sai cách, gây hiểu sai nội dung. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn từng bước cách vô hiệu hoá nhóm bằng GroupDocs.Viewer cho Java, để mỗi glyph luôn ở đúng vị trí của nó.

![Kỹ Thuật Render Chính Xác với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Câu Trả Lời Nhanh
- **Tính năng “vô hiệu hoá nhóm” làm gì?** Nó buộc trình render xử lý mỗi ký tự như một phần tử độc lập, giữ nguyên bố cục chính xác.  
- **Tùy chọn API nào kiểm soát tính năng này?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Tôi có cần giấy phép không?** Bản dùng thử hoạt động cho việc kiểm tra, nhưng cần giấy phép đầy đủ cho môi trường sản xuất.  
- **Tôi có thể tạo HTML Java từ PDF đồng thời không?** Có — sử dụng `HtmlViewOptions` để tạo đầu ra HTML trong khi vô hiệu hoá nhóm.  
- **Tính năng này có giới hạn chỉ với PDF không?** Chủ yếu dành cho PDF, nhưng viewer hỗ trợ nhiều định dạng khác.

## Giới Thiệu

Khi làm việc với tài liệu PDF, độ chính xác trong việc render là rất quan trọng — đặc biệt khi xử lý các cấu trúc văn bản phức tạp như chữ tượng hình hoặc các ngôn ngữ yêu cầu biểu diễn ký tự chính xác. Tính năng "Character Grouping" thường gây ra vấn đề bằng cách nhóm các ký tự không đúng, dẫn đến việc hiểu sai nội dung tài liệu. Điều này có thể đặc biệt gây phiền toái cho người dùng cần sao chép chính xác bố cục văn bản của tài liệu.

### Yêu Cầu Trước

Trước khi bắt đầu triển khai mã, hãy đảm bảo bạn đáp ứng các yêu cầu sau:
- **Thư viện & Phụ Thuộc**: Bạn cần GroupDocs.Viewer cho Java phiên bản 25.2 trở lên.  
- **Cài Đặt Môi Trường**: Đảm bảo đã cài Java Development Kit (JDK) và IDE của bạn được cấu hình để làm việc với các dự án Maven.  
- **Kiến Thức Cần Có**: Hiểu biết cơ bản về lập trình Java, đặc biệt là xử lý đường dẫn tệp và sử dụng các thư viện bên ngoài.

## Cách Vô Hiệu Hóa Nhóm trong Render PDF

### Cài Đặt GroupDocs.Viewer cho Java

#### Cài Đặt qua Maven

Đầu tiên, tích hợp thư viện cần thiết vào dự án của bạn. Thêm cấu hình sau vào file `pom.xml` của bạn:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

#### Mua Giấy Phép

- **Bản Dùng Thử Miễn Phí**: Bắt đầu với bản dùng thử để kiểm tra các tính năng.  
- **Giấy Phép Tạm Thời**: Yêu cầu giấy phép tạm thời nếu bạn cần thêm thời gian.  
- **Mua Giấy Phép**: Đối với các dự án dài hạn, nên mua giấy phép.

#### Khởi Tạo và Cấu Hình Cơ Bản

Bắt đầu bằng việc thiết lập môi trường dự án của bạn:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Hướng Dẫn Triển Khai

#### Tính Năng: Vô Hiệu Hóa Nhóm Ký Tự

##### Bước 1: Xác Định Thư Mục Đầu Ra

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Tại sao?** Điều này đảm bảo đầu ra của bạn được tổ chức và dễ truy cập.

##### Bước 2: Cấu Hình Định Dạng Đường Dẫn Tệp

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Tại sao?** Nó giúp tổ chức có hệ thống các trang của tài liệu PDF.

##### Bước 3: Khởi Tạo HTML View Options

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Tại sao?** Các tài nguyên nhúng đảm bảo mọi tài sản cần thiết được bao gồm trong file HTML của mỗi trang.

##### Bước 4: Vô Hiệu Hóa Nhóm Ký Tự

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Tại sao?** Điều này đảm bảo các ký tự được render riêng lẻ, giữ nguyên bố cục và ý nghĩa dự định.

##### Bước 5: Render Tài Liệu

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Tại sao?** Điều này đảm bảo mọi tài nguyên được đóng đúng cách, ngăn ngừa rò rỉ bộ nhớ.

### Tạo HTML Java từ PDF mà Không Nhóm

Lớp `HtmlViewOptions` cho phép bạn tạo **java html from pdf** trong khi giữ mỗi ký tự riêng biệt. Điều này đặc biệt hữu ích khi bạn cần nhúng các trang đã render vào một cổng thông tin web hoặc nền tảng e‑learning, nơi vị trí chính xác của glyph rất quan trọng.

### Mẹo Khắc Phục Sự Cố

- Đảm bảo đường dẫn tài liệu của bạn đúng để tránh `FileNotFoundException`.  
- Kiểm tra thư mục đầu ra có quyền ghi không.  
- Kiểm tra lại rằng bạn đang sử dụng phiên bản tương thích của GroupDocs.Viewer cho Java.

## Ứng Dụng Thực Tế

1. **Bảo Tồn Ngôn Ngữ**: Lý tưởng để render tài liệu bằng các ngôn ngữ như tiếng Trung, Nhật, hoặc các ký tự cổ đại nơi độ chính xác ký tự quan trọng.  
2. **Tài Liệu Pháp Lý và Tài Chính**: Đảm bảo độ chính xác trong các tài liệu yêu cầu biểu diễn văn bản chính xác để tuân thủ.  
3. **Tài Nguyên Giáo Dục**: Hoàn hảo cho sách giáo khoa và bài báo học thuật có chứa các sơ đồ hoặc chú thích phức tạp.

## Các Yếu Tố Về Hiệu Suất

- **Tối Ưu Hóa Sử Dụng Tài Nguyên**: Đảm bảo máy chủ của bạn có đủ tài nguyên để xử lý các tệp PDF lớn.  
- **Quản Lý Bộ Nhớ Java**: Sử dụng cấu trúc dữ liệu hiệu quả và các thực hành thu gom rác để quản lý bộ nhớ hiệu quả.  
- **Xử Lý Hàng Loạt**: Khi render nhiều tài liệu, xử lý chúng theo lô để cải thiện thông lượng.

## Kết Luận

Bạn đã nắm vững **cách vô hiệu hoá nhóm** trong quá trình render PDF với GroupDocs.Viewer cho Java. Khả năng này rất quan trọng đối với các ứng dụng yêu cầu biểu diễn văn bản chính xác. Để khám phá thêm, hãy thử tích hợp tính năng này với các hệ thống quản lý tài liệu khác hoặc thử nghiệm các tùy chọn render bổ sung.

Các bước tiếp theo bao gồm khám phá các tính năng nâng cao hơn của GroupDocs.Viewer và tối ưu hiệu suất cho các triển khai quy mô lớn.

## Câu Hỏi Thường Gặp

**Q:** *Tại sao tôi lại cần vô hiệu hoá nhóm ký tự?*  
**A:** Vô hiệu hoá nhóm ngăn trình render hợp nhất các ký tự thuộc các glyph riêng biệt, điều này rất cần thiết cho các script mà khoảng cách và thứ tự ký tự truyền tải ý nghĩa.

**Q:** *Cài đặt `setDisableCharsGrouping` chỉ áp dụng cho đầu ra HTML phải không?*  
**A:** Không, nó ảnh hưởng đến engine render PDF nền tảng, vì vậy bất kỳ định dạng đầu ra nào (HTML, PNG, v.v.) cũng sẽ phản ánh thay đổi này.

**Q:** *Tôi có thể kết hợp cài đặt này với phông chữ tùy chỉnh không?*  
**A:** Có — chỉ cần tải phông chữ tùy chỉnh của bạn trước khi khởi tạo `Viewer`, và quy tắc nhóm vẫn sẽ được áp dụng.

**Q:** *Vô hiệu hoá nhóm có ảnh hưởng đến hiệu suất không?*  
**A:** Hơi ảnh hưởng, vì engine phải xử lý từng ký tự một cách riêng lẻ, nhưng tác động này là tối thiểu đối với hầu hết các tài liệu.

**Q:** *Có cách nào bật/tắt nhóm theo từng trang không?*  
**A:** Hiện tại tùy chọn này là toàn cục cho mỗi instance của `PdfOptions`; bạn sẽ cần tạo các instance `Viewer` riêng cho các trang khác nhau nếu muốn thay đổi.

## Tài Nguyên

- [Tài liệu GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Tham chiếu API](https://reference.groupdocs.com/viewer/java/)
- [Tải xuống GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Mua Giấy Phép](https://purchase.groupdocs.com/buy)
- [Phiên bản Dùng Thử Miễn Phí](https://releases.groupdocs.com/viewer/java/)
- [Đăng ký Giấy Phép Tạm Thời](https://purchase.groupdocs.com/temporary-license/)
- [Diễn đàn Hỗ trợ GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2025-12-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs