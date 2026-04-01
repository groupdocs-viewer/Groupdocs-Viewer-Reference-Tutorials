---
date: '2026-04-01'
description: Tìm hiểu cách chia các bản vẽ CAD thành các ô bằng GroupDocs Viewer cho
  Java, nâng cao hiệu suất hiển thị và đơn giản hoá việc xử lý các tệp lớn.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Cách chia các bản vẽ CAD thành các ô bằng GroupDocs Viewer
type: docs
url: /vi/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Cách chia tách bản vẽ CAD thành các ô với GroupDocs Viewer

Nếu bạn đang tự hỏi **cách chia tách CAD** thành các phần nhỏ hơn, dễ quản lý hơn, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước cần thiết để chia tách các bản vẽ CAD lớn thành các ô bằng cách sử dụng **GroupDocs Viewer for Java**. Khi kết thúc, bạn sẽ có một giải pháp sẵn sàng sử dụng, cải thiện tốc độ hiển thị, giảm tiêu thụ bộ nhớ và giúp dễ dàng hiển thị bản vẽ trong các ứng dụng web hoặc di động.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Câu trả lời nhanh
- **Mục đích của việc “chia tách CAD” là gì?** Nó chia một bản vẽ khổng lồ thành các hình ảnh (ô) nhỏ hơn, tải nhanh hơn và tiêu thụ ít bộ nhớ hơn.  
- **Định dạng nào được sử dụng cho các ô?** Mặc định tạo file PNG, nhưng các định dạng khác cũng được hỗ trợ qua các tùy chọn Viewer.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép trả phí cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi kích thước ô không?** Có – điều chỉnh các phép tính `tileWidth` và `tileHeight` cho phù hợp.  
- **Cách tiếp cận này có an toàn với đa luồng không?** Việc render mỗi ô trong một thể hiện `Viewer` riêng bằng try‑with‑resources là an toàn cho thực thi đồng thời.

## “Cách chia tách CAD” là gì?
Việc chia tách CAD đề cập đến việc chia một bản vẽ CAD duy nhất, thường rất lớn, thành nhiều phần hình chữ nhật (ô). Mỗi ô được render độc lập, cho phép bạn chỉ tải các phần mà người dùng thực sự cần—hoàn hảo cho bản đồ web, cổng tài liệu và trình xem di động.

## Tại sao nên sử dụng GroupDocs Viewer cho Java?
GroupDocs Viewer cung cấp hỗ trợ ngay lập tức cho hơn 100 định dạng tệp, bao gồm DWG, DXF và DWF. API ô của nó cho phép bạn chỉ định tọa độ chính xác, vì vậy bạn có thể render đúng khu vực cần mà không phải xử lý toàn bộ tệp trước. Điều này tiết kiệm chu kỳ CPU, giảm băng thông và mang lại trải nghiệm người dùng mượt mà hơn.

## Yêu cầu trước
- **Thư viện**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Bất kỳ Java Development Kit hiện đại nào (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse, hoặc bất kỳ IDE tương thích Java nào khác.  
- **Công cụ xây dựng**: Maven (các công cụ xây dựng khác cũng hoạt động miễn là đã thêm phụ thuộc).  

## Cài đặt GroupDocs.Viewer cho Java
Thêm kho lưu trữ GroupDocs và phụ thuộc vào `pom.xml` của bạn:

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

### Nhận giấy phép
GroupDocs.Viewer cung cấp giấy phép dùng thử miễn phí để đánh giá:

- **Dùng thử miễn phí**: Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) để tải thư viện.  
- **Giấy phép tạm thời**: Đăng ký tại [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Giấy phép đầy đủ**: Mua giấy phép sản xuất trên [Purchase Page](https://purchase.groupdocs.com/buy).

### Khởi tạo cơ bản
Tạo một thể hiện `Viewer` đơn giản để xác minh thư viện tải đúng:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Hướng dẫn từng bước để chia tách bản vẽ CAD thành các ô

### Bước 1: Xác định thư mục đầu ra
Chúng tôi sẽ lưu mỗi ô dưới dạng một file PNG riêng. Sử dụng một phương thức tiện ích giúp logic đường dẫn sạch sẽ và tái sử dụng.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Bước 2: Cấu hình tùy chọn xem
Đặt định dạng render thành PNG và yêu cầu viewer không tải trước mọi trang (giúp tiết kiệm bộ nhớ).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Bước 3: Tính kích thước ô
Đầu tiên chúng ta lấy chiều rộng và chiều cao gốc của bản vẽ, sau đó chia nó thành bốn phần tư bằng nhau.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Bước 4: Render và lưu các ô
Thêm các ô đã tính vào tùy chọn render và để `Viewer` tạo các file PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Mẹo khắc phục sự cố
- **Đường xây dựng** – Đảm bảo các file JAR của GroupDocs nằm trong classpath.  
- **Quyền** – Thư mục đầu ra phải có quyền ghi cho tiến trình Java.  
- **Ngoại lệ** – Nếu bạn thấy `ViewerException`, kiểm tra lại xem file DWG có bị hỏng không và giấy phép đúng đã được áp dụng.

## Các trường hợp sử dụng phổ biến cho việc chia tách ô CAD
1. **Bản đồ web** – Chỉ tải phần hiển thị của bản thiết kế khi người dùng di chuyển/thu phóng.  
2. **Quản lý tài liệu** – Lưu mỗi ô riêng biệt để tạo preview nhanh hơn.  
3. **Xem trên di động** – Giảm băng thông bằng cách tải chỉ các ô cần cho màn hình hiện tại.

## Các yếu tố hiệu năng cần cân nhắc
- **Kích thước ô** – Ô lớn hơn nghĩa là ít file hơn nhưng render chậm hơn; tìm cân bằng dựa trên nhu cầu UI của bạn.  
- **Giám sát bộ nhớ** – Sử dụng công cụ profiling của Java (ví dụ, VisualVM) để theo dõi việc sử dụng heap khi xử lý các bản vẽ rất lớn.  
- **Dọn dẹp tài nguyên** – Mẫu try‑with‑resources được trình bày ở trên tự động giải phóng tài nguyên gốc.

## Câu hỏi thường gặp

**Q: Tôi có thể chia tách các loại tệp khác (PDF, hình ảnh) thành ô bằng cùng cách không?**  
A: Có. GroupDocs Viewer hỗ trợ nhiều định dạng; bạn chỉ cần sử dụng lớp tùy chọn tương ứng (ví dụ, `PdfViewOptions`).

**Q: Làm sao để thay đổi chất lượng hình ảnh đầu ra?**  
A: Điều chỉnh `viewOptions.setResolution(int dpi)` hoặc thiết lập các tùy chọn nén trên đối tượng `PngOptions`.

**Q: Ứng dụng của tôi bị hết bộ nhớ khi xử lý các file DWG rất lớn—tôi có thể làm gì?**  
A: Giảm kích thước ô, tăng heap JVM (`-Xmx`), hoặc render các ô tuần tự trong các thể hiện `Viewer` riêng biệt.

**Q: Có thể render các ô một cách bất đồng bộ không?**  
A: Chắc chắn. Đóng gói mỗi lời gọi render ô trong một `CompletableFuture` hoặc sử dụng executor service để thực hiện song song.

**Q: Tôi có cần giấy phép riêng cho mỗi ô không?**  
A: Không. Một giấy phép GroupDocs Viewer hợp lệ duy nhất bao phủ tất cả các thao tác render trong ứng dụng của bạn.

## Tài nguyên
- [Tài liệu](https://docs.groupdocs.com/viewer/java/)
- [Tham chiếu API](https://reference.groupdocs.com/viewer/java/)
- [Tải GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Mua giấy phép](https://purchase.groupdocs.com/buy)
- [Dùng thử miễn phí](https://releases.groupdocs.com/viewer/java/)
- [Giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-04-01  
**Được kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs