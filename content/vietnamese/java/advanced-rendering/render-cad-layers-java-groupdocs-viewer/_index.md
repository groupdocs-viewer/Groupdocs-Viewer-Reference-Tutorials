---
date: '2026-01-08'
description: Tìm hiểu cách hiển thị các lớp CAD trong Java bằng GroupDocs.Viewer.
  Hướng dẫn này bao gồm cài đặt, cấu hình và các ứng dụng thực tiễn để nâng cao việc
  trực quan hoá thiết kế.
keywords:
- Render CAD Layers in Java
- GroupDocs.Viewer for Java
- CAD Layer Rendering
title: Kết xuất các lớp CAD trong Java với GroupDocs.Viewer – Hướng dẫn toàn diện
type: docs
url: /vi/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/
weight: 1
---

# Kết xuất các lớp CAD Java với GroupDocs.Viewer

Nếu bạn cần **kết xuất các lớp CAD Java** để có cái nhìn rõ ràng hơn về các bản vẽ phức tạp, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua mọi thứ bạn cần—từ cài đặt GroupDocs.Viewer để chọn chính xác các lớp mà bạn muốn hiển thị. Khi hoàn tất, bạn sẽ có thể tích hợp các công việc kết xuất lớp vào các ứng dụng Java của mình một cách tự động.

![Kết xuất các lớp CAD cụ thể bằng GroupDocs.Viewer cho Java](/viewer/advanced-rendering/render-special-cad-layers-java.png)

**Bạn sẽ học được gì**
- Cách thiết lập GroupDocs.Viewer trong dự án Java
- Các bước chính xác để hiển thị các lớp CAD cụ thể Java
- Cho phép kiểm tra cấu hình tùy chọn Kiểm soát chi tiết
- Các kịch bản thực tế nơi công việc render lớp mang lại giá trị

## Trả lời nhanh
- **Thư viện nào xử lý công việc kết xuất CAD trong Java?** GroupDocs.Viewer for Java.
- **Tôi có thể chọn các lẻ riêng lẻ để hiển thị không?** Có—sử dụng `viewOptions.getCadOptions().setLayers(...)`.
- **Có cần giấy phép cho môi trường production không?** Cần một giấy phép GroupDocs.Viewer hợp lệ để sử dụng trong production.
- **Phiên bản Java nào được hỗ trợ?** JDK8 hoặc cao hơn.
- **Maven có phải là cách duy nhất để thêm sự phụ thuộc không?** Maven được khuyến nghị, nhưng bạn cũng có thể sử dụng Gradle hoặc thêm JAR thủ công.

## Điều kiện tiên quyết
### Thư viện và thư viện phụ thuộc bắt buộc
Đảm bảo bạn đã cài đặt sẵn Bộ công cụ phát triển Java (JDK) và Maven để quản lý phần phụ thuộc.

### Yêu cầu thiết lập môi trường
- JDK8+
- IntelliJ IDEA, Eclipse, hoặc IDE Java khác
- Terminal hoặc dấu nhắc lệnh để chạy Maven lệnh

### Kiến thức tiên quyết
Kiến thức cơ bản về Java và Maven sẽ hữu ích nhưng bạn sẽ nhận được tất cả các chi tiết liên quan đến CAD ngay tại đây.

## Thiết lập GroupDocs.Viewer cho Java
### Cài đặt qua Maven
Thêm kho GroupDocs và dependency Viewer vào file `pom.xml` của bạn:

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

### Xin giấy phép
GroupDocs.Viewer cung cấp bản dùng thử miễn phí, giấy phép tạm thời để đánh giá và giấy phép mua đầy đủ cho môi trường production.

### Khởi tạo và thiết lập cơ bản
Dưới đây là một ví dụ về việc tối thiểu mở tệp DWG và hiển thị ra HTML:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize viewer with the path to your CAD file
try (Viewer viewer = new Viewer("path/to/your/file.dwg")) {
    // Configure view options for rendering
    HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources();
    viewer.view(viewOptions);
}
```

## Cách kết xuất các lớp CAD Java
Dưới đây là hướng dẫn từng bước cho phép bạn chọn chính xác các lớp sẽ xuất hiện trong kết quả.

### Bước 1: Xác định đường dẫn đầu ra

```java
import java.nio.file.Path;

// Define your output directory path
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY").resolve("RenderLayers");

// Set the format for rendered pages
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

### Bước 2: Cấu hình các tùy chọn hiển thị HTML
Yêu cầu viewer sử dụng mẫu tên file tùy chỉnh mà bạn vừa tạo:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 3: Chỉ định các lớp cần hiển thị
Thêm tên các lớp bạn muốn hiển thị. `CacheableFactory` tạo các đối tượng `Layer` mà viewer hiểu:

```java
import java.util.ArrayList;
import java.util.List;
import com.groupdocs.viewer.results.Layer;
import com.groupdocs.viewer.caching.extra.CacheableFactory;

List<Layer> layers = new ArrayList<>();
layers.add(CacheableFactory.getInstance().newLayer("QUADRANT"));
viewOptions.getCadOptions().setLayers(layers);
```

### Bước 4: Hiển thị tài liệu
Cuối cùng, mở file CAD và render chỉ các lớp đã chọn:

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    viewer.view(viewOptions);
}
```

## Mẹo khắc phục sự cố
- **Không tìm thấy tệp** – Kiểm tra lại đường dẫn tuyệt đối hoặc đối số mà bạn đã truyền cho `Viewer`.
- **Vấn đề về tên lớp** – Tên lớp phân biệt chữ hoa/thường; Hãy xác nhận chúng trong phần mềm CAD của bạn.
- **Lỗi bộ nhớ** – Đối với các bản vẽ rất lớn, cân nhắc bật bộ nhớ đệm hoặc tăng kích thước heap của JVM.

## Ứng dụng thực tế
Kết xuất các lớp CAD cụ thể Java hữu ích trong nhiều bản kịch bản:

1. **Engineering Reviews** – Tập trung vào một hệ thống con duy nhất mà không bị rối mắt.
2. **Trình bày kiến ​​trúc** – Làm bật các cấu trúc nổi hoặc cơ khí thành phần thành phần cho khách hàng.
3. **Đảm bảo chất lượng** – Cô lập các tính năng quan trọng để kiểm tra dày thủ.
4. **Tích hợp BIM** – Cung cấp các chế độ xem theo lớp vào công cụ BIM để cung cấp tài liệu phong phú hơn.

## Cân nhắc về hiệu suất
###Tối Ưu Hóa Hiệu Năng
- Sử dụng bộ đệm của GroupDocs để tránh xử lý lại cùng một tệp nhiều lần.
- Lớp có giới hạn được hiển thị đồng thời nếu bạn gặp hiện tượng chậm lại.

### Nguyên tắc sử dụng tài nguyên
- Giám sát công việc sử dụng đống cho các bản vẽ phức tạp; điều chỉnh `-Xmx` khi cần thiết.
- JVM luôn cập nhật để tận dụng các tiến trình mới nhất của bộ sưu tập rác.

## Phần kết luận
Bạn đã có một phương pháp hoàn chỉnh, sẵn sàng để sản xuất để **kết xuất các lớp CAD Java** với GroupDocs.Viewer. Khả năng này giúp đơn giản hóa việc đánh giá, trình bày và phân tích quy trình làm việc cho các đội ngũ kỹ thuật và kiến ​​trúc.

**Các bước tiếp theo**
Khám phá các tính năng bổ sung của Trình xem—như hiển thị ra PDF hoặc PNG, xử lý bố cục DWG hoặc áp dụng tùy chỉnh kiểu—để nâng cao hơn nữa tài liệu đường dẫn của bạn.

## Câu hỏi thường gặp
**Q: GroupDocs.Viewer là gì?**
A: Đó là một thư viện Java cho phép xem, chuyển đổi và hiển thị hơn 100 tài liệu định dạng, bao gồm tất cả các tệp CAD.

**Q: Tôi có thể hiển thị lớp từ các loại tệp khác ngoài DWG không?**
A: Có, DXF, DGN hỗ trợ Viewer và các định dạng CAD khác, mặc dù lớp API chọn chỉ áp dụng cho CAD tài liệu.

**Q: Tôi nên xử lý lỗi như thế nào khi kết xuất?**
A: Bao bọc các lời gọi Viewer trong khối try‑catch và ghi nhật ký chi tiết `ViewerException` để dự đoán vấn đề.

**Q: GroupDocs.Viewer có mô phù hợp cho phát triển khai quy lớn, doanh nghiệp không?**
A: Hoàn toàn. Nó được thiết kế cho môi trường có lưu lượng cao và cung cấp bộ nhớ đệm phía máy chủ, đa luồng, cùng các tùy chọn giấy phép cho doanh nghiệp.

**Q: Tôi có thể tìm thêm các ví dụ tích hợp ở đâu?**
A: Tài liệu chính thức và API tham chiếu chứa rất nhiều mẫu cho web, máy tính để bàn và đám mây.

## Tài liệu tham khảo
- [Tài liệu](https://docs.groupdocs.com/viewer/java/)
- [Tham khảo API](https://reference.groupdocs.com/viewer/java/)
- [Tải xuống](https://releases.groupdocs.com/viewer/java/)
- [Mua](https://purchase.groupdocs.com/buy)

- [Dùng thử miễn phí](https://releases.groupdocs.com/viewer/java/)
- [Giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 08/01/2026
**Đã kiểm thử với:** GroupDocs.Viewer 25.2 cho Java
**Tác giả:** GroupDocs