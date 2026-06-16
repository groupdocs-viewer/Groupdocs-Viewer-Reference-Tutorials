---
date: '2026-03-22'
description: Tìm hiểu cách tạo HTML từ PDF và tắt tính năng nhóm ký tự bằng GroupDocs
  Viewer cho Java để hiển thị văn bản một cách chính xác.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Tạo HTML từ PDF & Vô hiệu hoá nhóm – GroupDocs Java
type: docs
url: /vi/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Tạo HTML từ PDF và Vô hiệu hoá Nhóm ký tự với GroupDocs Viewer cho Java

Trong nhiều dự án, bạn cần **tạo HTML từ PDF** đồng thời giữ nguyên vị trí của từng glyph. Điều này đặc biệt quan trọng với các script phức tạp, ngôn ngữ cổ đại hoặc tài liệu pháp lý, nơi một ký tự sai vị trí có thể làm thay đổi ý nghĩa. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình đầy đủ để render PDF sang HTML bằng GroupDocs Viewer cho Java và chỉ cho bạn **cách vô hiệu hoá nhóm ký tự** để mỗi ký tự được xử lý như một phần tử độc lập.

![Kỹ thuật render chính xác với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Câu trả lời nhanh
- **“Vô hiệu hoá nhóm ký tự” làm gì?** Nó buộc trình render xem mỗi ký tự như một phần tử độc lập, bảo toàn bố cục chính xác.  
- **Tùy chọn API nào điều khiển điều này?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Tôi có cần giấy phép không?** Bản dùng thử hoạt động cho việc thử nghiệm, nhưng cần giấy phép đầy đủ cho môi trường sản xuất.  
- **Có thể tạo HTML từ PDF đồng thời không?** Có — sử dụng `HtmlViewOptions` để tạo đầu ra HTML trong khi vô hiệu hoá nhóm ký tự.  
- **Tính năng này có giới hạn chỉ với PDF không?** Chủ yếu dành cho PDF, nhưng viewer hỗ trợ nhiều định dạng khác.

## Giới thiệu

Khi làm việc với tài liệu PDF, độ chính xác trong việc render là rất quan trọng — đặc biệt khi xử lý các cấu trúc văn bản phức tạp như chữ tượng hình hoặc các ngôn ngữ yêu cầu biểu diễn ký tự chính xác. Tính năng “Character Grouping” thường gây ra vấn đề bằng cách nhóm các ký tự không đúng, dẫn đến việc hiểu sai nội dung tài liệu. Điều này có thể gây khó khăn đặc biệt cho người dùng cần sao chép chính xác bố cục văn bản của tài liệu.

### Yêu cầu trước

Trước khi bắt đầu triển khai mã, hãy đảm bảo bạn đáp ứng các yêu cầu sau:
- **Thư viện & Phụ thuộc**: Cần có GroupDocs.Viewer cho Java phiên bản 25.2 trở lên.  
- **Cài đặt môi trường**: Đảm bảo đã cài Java Development Kit (JDK) và IDE của bạn được cấu hình để làm việc với dự án Maven.  
- **Kiến thức nền**: Hiểu cơ bản về lập trình Java, đặc biệt là xử lý đường dẫn tệp và sử dụng các thư viện bên ngoài.

## Cách tạo HTML từ PDF với GroupDocs Viewer

Việc tạo HTML từ PDF là một quy trình hai bước: cấu hình viewer, sau đó render tài liệu. Điều quan trọng là tắt tính năng nhóm ký tự trước khi render để đầu ra HTML phản ánh chính xác bố cục PDF ký tự‑theo‑ký tự.

### Cài đặt GroupDocs.Viewer cho Java

#### Cài đặt qua Maven

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

#### Mua giấy phép

Để sử dụng đầy đủ GroupDocs.Viewer, hãy cân nhắc mua giấy phép:
- **Bản dùng thử miễn phí**: Bắt đầu với bản dùng thử để kiểm tra các tính năng.  
- **Giấy phép tạm thời**: Yêu cầu giấy phép tạm thời nếu bạn cần thời gian thêm.  
- **Mua bản quyền**: Đối với các dự án dài hạn, nên mua giấy phép.

#### Khởi tạo và cấu hình cơ bản

Dưới đây là một đoạn mã sẵn sàng chạy, thể hiện quy trình hoàn chỉnh — từ việc thiết lập thư mục đầu ra đến việc render PDF thành HTML trong khi vô hiệu hoá nhóm ký tự:

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

### Hướng dẫn triển khai

#### Tính năng: Vô hiệu hoá Nhóm ký tự

Sau đây chúng tôi sẽ phân tích từng dòng trong ví dụ để bạn hiểu **tại sao** chúng ta làm như vậy và **cách** chúng góp phần tạo HTML từ PDF mà không bị gộp ký tự không mong muốn.

##### Bước 1: Xác định thư mục đầu ra  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Tại sao?** Điều này đảm bảo các tệp HTML đã render được lưu trong một thư mục riêng, giúp bạn dễ dàng tìm và quản lý chúng sau này.

##### Bước 2: Cấu hình định dạng đường dẫn tệp  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Tại sao?** Sử dụng placeholder (`{0}`) cho phép viewer tạo một tệp HTML riêng cho mỗi trang PDF, giữ cho đầu ra được tổ chức gọn gàng.

##### Bước 3: Khởi tạo HTML View Options  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Tại sao?** Các tài nguyên nhúng (hình ảnh, phông chữ, CSS) được gói trực tiếp vào mỗi trang HTML, rất phù hợp cho các viewer dựa trên web hoặc nền tảng e‑learning.

##### Bước 4: Vô hiệu hoá Nhóm ký tự  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Tại sao?** Đây là dòng quan trọng nói với engine render **không** hợp nhất các ký tự liền kề, đảm bảo HTML sinh ra phản ánh chính xác vị trí glyph từ PDF nguồn.

##### Bước 5: Render tài liệu  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Tại sao?** Đặt `Viewer` trong khối try‑with‑resources đảm bảo tất cả tài nguyên gốc được giải phóng tự động, ngăn ngừa rò rỉ bộ nhớ trong các ứng dụng chạy lâu.

### Tạo HTML Java từ PDF mà không nhóm ký tự

Lớp `HtmlViewOptions` cho phép bạn **tạo html từ pdf** trong khi giữ mỗi ký tự riêng biệt. Điều này rất hữu ích khi bạn cần nhúng các trang đã render vào cổng thông tin web hoặc nền tảng e‑learning, nơi vị trí glyph chính xác là yếu tố quan trọng.

### Các vấn đề thường gặp và giải pháp

- **FileNotFoundException** – Kiểm tra lại đường dẫn bạn truyền vào `new Viewer(...)`. Sử dụng đường dẫn tuyệt đối hoặc `Path.of(...)` để rõ ràng hơn.  
- **Quyền ghi** – Đảm bảo thư mục đầu ra có quyền ghi cho tiến trình Java; trên Linux bạn có thể cần điều chỉnh quyền thư mục (`chmod 775`).  
- **Phiên bản không khớp** – Tùy chọn `setDisableCharsGrouping` chỉ có từ phiên bản 25.2 trở lên. Xác nhận `pom.xml` của bạn đã chỉ định đúng phiên bản.

### Ứng dụng thực tiễn

1. **Bảo tồn ngôn ngữ** – Lý tưởng cho việc render tài liệu bằng tiếng Trung, Nhật, Ả Rập hoặc các script cổ, nơi khoảng cách ký tự mang ý nghĩa.  
2. **Tài liệu pháp lý & tài chính** – Đảm bảo sao chép chính xác văn bản cho các giấy tờ có yêu cầu tuân thủ nghiêm ngặt.  
3. **Tài nguyên giáo dục** – Hoàn hảo cho sách giáo khoa có biểu đồ phức tạp, chú thích, hoặc nội dung đa ngôn ngữ.

### Cân nhắc về hiệu năng

- **Tối ưu sử dụng tài nguyên** – PDF lớn có thể tiêu tốn nhiều bộ nhớ. Xem xét xử lý theo lô và giải phóng các instance `Viewer` kịp thời.  
- **Quản lý bộ nhớ Java** – Điều chỉnh heap JVM (`-Xmx2g` hoặc cao hơn) nếu dự kiến xử lý PDF hàng trăm trang.  
- **Render song song** – Đối với chuyển đổi hàng loạt, tạo các luồng riêng biệt mỗi luồng có một instance `Viewer` để tận dụng đa lõi CPU.

## Câu hỏi thường gặp

**Hỏi:** *Tại sao tôi lại cần vô hiệu hoá nhóm ký tự?*  
**Đáp:** Vô hiệu hoá nhóm ký tự ngăn trình render hợp nhất các ký tự thuộc các glyph riêng biệt, điều này rất quan trọng đối với các script mà khoảng cách và thứ tự ký tự truyền tải ý nghĩa.

**Hỏi:** *Cài đặt `setDisableCharsGrouping` chỉ áp dụng cho đầu ra HTML phải không?*  
**Đáp:** Không, nó ảnh hưởng tới engine render PDF nền tảng, vì vậy bất kỳ định dạng đầu ra nào (HTML, PNG, JPEG, v.v.) đều sẽ phản ánh thay đổi này.

**Hỏi:** *Tôi có thể kết hợp cài đặt này với phông chữ tùy chỉnh không?*  
**Đáp:** Có — tải phông chữ tùy chỉnh trước khi khởi tạo `Viewer`, và quy tắc nhóm ký tự vẫn sẽ được áp dụng.

**Hỏi:** *Vô hiệu hoá nhóm ký tự có ảnh hưởng tới hiệu năng không?*  
**Đáp:** Có chút ảnh hưởng vì engine xử lý từng ký tự riêng lẻ, nhưng tác động là tối thiểu đối với hầu hết các tài liệu.

**Hỏi:** *Có cách bật/tắt nhóm ký tự theo từng trang không?*  
**Đáp:** Hiện tại tùy chọn này là toàn cục cho mỗi instance `PdfOptions`; nếu cần hành vi hỗn hợp, bạn phải tạo các instance `Viewer` riêng cho các trang khác nhau.

## Tài nguyên

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-03-22  
**Kiểm thử với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs