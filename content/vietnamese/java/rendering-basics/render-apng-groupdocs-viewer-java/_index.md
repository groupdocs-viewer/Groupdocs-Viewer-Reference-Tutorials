---
date: '2026-06-20'
description: Hướng dẫn GroupDocs Viewer Java cho thấy cách hiển thị các tệp APNG sang
  HTML, JPG, PNG và PDF. Bao gồm cài đặt, đoạn mã mẫu và các trường hợp sử dụng thực
  tế.
keywords:
- groupdocs viewer java tutorial
- render animated png
- how to convert apng to jpg
schemas:
- author: GroupDocs
  dateModified: '2026-06-20'
  description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  headline: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  type: TechArticle
- description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  name: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  steps:
  - name: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
    text: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
  - name: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
    text: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
  - name: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
    text: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
  - name: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
    text: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
  - name: '**Configure Paths** – specify the output folder for the generated JPG files.'
    text: '**Configure Paths** – specify the output folder for the generated JPG files.'
  - name: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
    text: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
  - name: '**Set Output Paths** – choose a folder for the PNG sequence.'
    text: '**Set Output Paths** – choose a folder for the PNG sequence.'
  - name: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
    text: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
  type: HowTo
- questions:
  - answer: Yes, it supports GIF, WebP, and even animated SVG, providing the same
      HTML, image, and PDF output options.
    question: Can GroupDocs Viewer render other animated formats like GIF or WebP?
  - answer: There’s no hard limit, but performance may degrade after ~500 frames;
      consider down‑sampling for very large animations.
    question: Is there a limit to the number of frames an APNG can have?
  - answer: APNG does not support encryption, but if the file is inside a ZIP archive,
      supply the password via `Viewer`’s `load` method.
    question: How do I handle password‑protected APNG files?
  - answer: Absolutely—use `JpgViewOptions.setResolution(300)` and `setQuality(90)`
      before calling `view`.
    question: Can I customize the DPI or quality of the generated JPGs?
  - answer: Yes, GroupDocs Viewer is pure Java and runs on any OS with a compatible
      JRE, making it ideal for Docker deployments.
    question: Does the library work on Linux containers?
  type: FAQPage
title: 'Hướng dẫn GroupDocs Viewer Java: Hiển thị PNG động'
type: docs
url: /vi/java/rendering-basics/render-apng-groupdocs-viewer-java/
weight: 1
---

# Hướng dẫn GroupDocs Viewer Java: Kết xuất PNG hoạt hình

Trong **hướng dẫn GroupDocs Viewer Java** này, bạn sẽ khám phá cách chuyển đổi các tệp Animated PNG (APNG) sang các định dạng HTML, JPG, PNG và PDF bằng thư viện mạnh mẽ GroupDocs.Viewer. Dù bạn đang xây dựng một cổng web, công cụ báo cáo, hay quy trình xuất bản kỹ thuật số, việc kết xuất APNG một cách chính xác là cần thiết để bảo toàn chất lượng hoạt hình trên các nền tảng.

![Render Animated PNGs with GroupDocs.Viewer for Java](/viewer/rendering-basics/render-animated-pngs-java.png)  
[Render Animated PNGs with GroupDocs.Viewer for Java](/viewer/rendering-basics/render-animated-pngs-java.png)

## Câu trả lời nhanh
- **GroupDocs.Viewer làm gì?** Nó kết xuất hơn 70 loại tệp—bao gồm APNG—ra HTML, hình ảnh và PDF mà không cần phần mềm bên ngoài.  
- **Cần bao nhiêu dòng mã để chuyển đổi APNG sang JPG?** Chỉ cần hai dòng: tạo một thể hiện `Viewer` và gọi `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.  
- **Tôi có cần giấy phép cho việc phát triển không?** Giấy phép dùng thử hoạt động cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể kết xuất APNG lớn (hơn 100 khung) một cách hiệu quả không?** Có—sử dụng try‑with‑resources và truyền luồng đầu ra để giữ mức sử dụng bộ nhớ thấp.  
- **Maven là cách duy nhất để thêm thư viện không?** Maven được khuyến nghị, nhưng bạn cũng có thể dùng Gradle hoặc thêm các JAR một cách thủ công.

## GroupDocs Viewer là gì?
**GroupDocs Viewer** là một thành phần Java chuyển đổi hơn 70 định dạng tài liệu và hình ảnh thành các biểu diễn thân thiện với web như HTML, JPG, PNG và PDF. Nó xử lý bố cục phức tạp, giữ lại đồ họa vector và hỗ trợ các định dạng hoạt hình như APNG mà không cần phụ thuộc bên ngoài.

## Tại sao nên kết xuất PNG hoạt hình với GroupDocs Viewer?
GroupDocs Viewer cung cấp cách chuyển đổi APNG đáng tin cậy, hiệu suất cao đồng thời bảo toàn thời gian hoạt hình và độ trong suốt. Nó loại bỏ nhu cầu sử dụng công cụ của bên thứ ba, hoạt động trên mọi nền tảng và dễ dàng tích hợp vào các ứng dụng Java.

- **Hỗ trợ đa dạng định dạng:** hơn 70 định dạng đầu vào, bao gồm APNG, PDF, DOCX và SVG.  
- **Tối ưu hiệu suất:** Xử lý tài liệu hàng trăm trang hoặc hoạt hình 200 khung sử dụng dưới 150 MB RAM trên máy chủ tiêu chuẩn.  
- **Không cần cài đặt:** Không cần thư viện gốc hay codec đặc thù hệ điều hành, giúp triển khai trên container trở nên đơn giản.  
- **Đầu ra nhất quán:** Đảm bảo kết xuất pixel‑perfect, giữ nguyên độ trong suốt và thời gian hoạt hình.

## Yêu cầu trước
- **Java Development Kit (JDK) 8+** – đảm bảo tương thích với các tính năng ngôn ngữ hiện đại.  
- **Maven** – đơn giản hoá quản lý phụ thuộc; Gradle cũng hoạt động.  
- **Một tệp APNG** – đặt nó trong thư mục `resources` của dự án (ví dụ, `src/main/resources/sample.apng`).  

## Cài đặt GroupDocs Viewer cho Java

### Cấu hình Maven
Thêm phụ thuộc sau vào file `pom.xml` của bạn để lấy phiên bản ổn định mới nhất:

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

### Cách lấy giấy phép
Để đánh giá GroupDocs Viewer, bạn có thể:
- **Tải bản dùng thử** từ [trang web GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Yêu cầu giấy phép tạm thời** để thử nghiệm đầy đủ tính năng.  
- **Mua giấy phép sản xuất** để sử dụng thương mại không giới hạn.  
- Để biết hướng dẫn chi tiết, xem [tài liệu chính thức](https://docs.groupdocs.com/viewer/java/).

### Khởi tạo cơ bản
Lớp `Viewer` là điểm vào cho tất cả các thao tác kết xuất. Nó tải tệp nguồn và cung cấp các phương thức để xuất ra các định dạng khác nhau.

`Viewer` đại diện cho một tài liệu hoặc hình ảnh và điều phối việc kết xuất sang định dạng đầu ra đã chọn.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.*;
```

## Cách kết xuất PNG hoạt hình sang HTML?
Tải tệp APNG, cấu hình các tùy chọn HTML, và gọi `view`. Quá trình này đơn giản và thường chỉ cần vài dòng mã, rất phù hợp cho việc tích hợp nhanh trong dịch vụ web hoặc công việc batch.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.html");
   ```

### Định nghĩa – Thể hiện Viewer
`Viewer` là lớp cốt lõi của GroupDocs.Viewer, đại diện cho một tài liệu hoặc hình ảnh và điều phối việc kết xuất sang định dạng đầu ra đã chọn.

### Kết xuất HTML từng bước
1. **Thiết lập đường dẫn** – xác định nơi tệp HTML và các tài nguyên của nó sẽ được lưu.  
2. **Khởi tạo Viewer** – tạo đối tượng `Viewer` với đường dẫn APNG.  
3. **Cấu hình tùy chọn** – sử dụng `HtmlViewOptions.forEmbeddedResources` để nhúng CSS, JS và hình ảnh trực tiếp vào tệp HTML, loại bỏ phụ thuộc bên ngoài.  
4. **Kết xuất** – gọi `viewer.view(documentPath, htmlOptions)`.

## Cách chuyển đổi APNG sang JPG?
GroupDocs Viewer có thể trích xuất mỗi khung của hoạt hình thành một hình ảnh JPG riêng biệt, rất phù hợp cho ảnh thu nhỏ hoặc bản xem trước tĩnh. Quá trình chuyển đổi giữ nguyên thứ tự khung gốc và cho phép bạn kiểm soát chất lượng và độ phân giải của hình ảnh.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.jpg");
   ```

### Định nghĩa – JpgViewOptions
`JpgViewOptions` xác định cách mỗi khung của APNG nguồn được kết xuất thành một tệp JPEG riêng, cho phép bạn đặt chất lượng, DPI và quy tắc đặt tên.

### Chuyển đổi JPG từng bước
1. **Cấu hình đường dẫn** – chỉ định thư mục đầu ra cho các tệp JPG được tạo.  
2. **Kết xuất sang JPG** – gọi `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.  
3. **Kết quả** – mỗi khung sẽ thành `output_1.jpg`, `output_2.jpg`, … giữ nguyên chuỗi hoạt hình gốc.

## Cách chuyển đổi APNG sang PNG?
Khi cần chất lượng không mất dữ liệu, PNG là định dạng mục tiêu lý tưởng. GroupDocs Viewer trích xuất mỗi khung mà không gây ra hiện tượng nén, giữ nguyên độ trong suốt và đảm bảo độ chính xác pixel‑perfect.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.png");
   ```

### Định nghĩa – PngViewOptions
`PngViewOptions` chỉ cho viewer ghi mỗi khung hoạt hình thành một tệp PNG riêng, giữ độ trong suốt và dữ liệu pixel chính xác.

### Trích xuất PNG từng bước
1. **Đặt đường dẫn đầu ra** – chọn thư mục cho chuỗi PNG.  
2. **Thực hiện kết xuất** – gọi `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.  
3. **Kết quả** – bạn nhận được một loạt các tệp PNG có thể được ghép lại hoặc sử dụng riêng lẻ.

## Cách chuyển đổi APNG sang PDF?
Biên dịch một chuỗi hoạt hình thành một PDF duy nhất hữu ích cho tài liệu có thể in hoặc lưu trữ. Mỗi khung trở thành một trang riêng, giữ nguyên thứ tự hoạt hình trong một định dạng tĩnh, có thể chia sẻ.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.pdf");
   ```

### Định nghĩa – PdfViewOptions
`PdfViewOptions` tổng hợp tất cả các khung của APNG thành một PDF đa trang, mỗi khung chiếm một trang riêng.

### Tạo PDF từng bước
1. **Xác định đường dẫn** – đặt đường dẫn tệp PDF đích.  
2. **Kết xuất sang PDF** – thực thi `viewer.view(documentPath, PdfViewOptions.forEmbeddedResources(outputPath))`.  
3. **Kết quả** – một PDF trong đó mỗi trang phản ánh một khung của hoạt hình gốc.

## Ứng dụng thực tiễn
- **Phát triển web:** Nhúng APNG vào blog hoặc trang sản phẩm mà không cần dựa vào GIF, đảm bảo hoạt hình mượt hơn và kích thước tệp nhỏ hơn.  
- **Xuất bản kỹ thuật số:** Chuyển đổi biểu đồ hoạt hình thành tài liệu PDF cho hội nghị, bảo toàn câu chuyện hình ảnh.  
- **Tài sản marketing:** Tạo ảnh chụp JPG hoặc PNG độ phân giải cao cho banner, quảng cáo và bài đăng mạng xã hội.  
- **Trực quan hoá dữ liệu:** Chuyển đồ thị thời gian thành các hình ảnh khung‑khung cho bảng điều khiển phân tích.

## Các cân nhắc về hiệu suất
- **Tối ưu kích thước hình ảnh:** Thay đổi kích thước hoặc nén APNG nguồn trước khi kết xuất để giảm tải CPU.  
- **Quản lý tài nguyên:** Đặt `Viewer` trong khối try‑with‑resources để tự động đóng luồng và giải phóng bộ đệm gốc.  
- **Xử lý batch:** Khi xử lý hàng chục APNG, xử lý chúng theo lô 10–20 để tránh tăng đột biến bộ nhớ.

## Các vấn đề thường gặp và giải pháp
- **Thiếu khung:** Đảm bảo APNG tuân thủ đặc tả APNG; một số công cụ cũ tạo tệp không chuẩn.  
- **Thời gian không đúng:** Sử dụng `AnimatedPngOptions` (nếu có) để điều chỉnh độ trễ khung sau khi kết xuất.  
- **Lỗi hết bộ nhớ:** Bật `viewer.setCacheSize(50)` để giới hạn bộ nhớ đệm trong RAM cho các hoạt hình lớn.

## Câu hỏi thường gặp

**Q: GroupDocs Viewer có thể kết xuất các định dạng hoạt hình khác như GIF hoặc WebP không?**  
A: Có, nó hỗ trợ GIF, WebP và thậm chí SVG hoạt hình, cung cấp các tùy chọn đầu ra HTML, hình ảnh và PDF tương tự.

**Q: Có giới hạn số khung của một APNG không?**  
A: Không có giới hạn cứng, nhưng hiệu suất có thể giảm sau khoảng ~500 khung; cân nhắc giảm mẫu cho các hoạt hình rất lớn.

**Q: Làm sao xử lý tệp APNG được bảo vệ bằng mật khẩu?**  
A: APNG không hỗ trợ mã hoá, nhưng nếu tệp nằm trong archive ZIP, cung cấp mật khẩu qua phương thức `load` của `Viewer`.

**Q: Tôi có thể tùy chỉnh DPI hoặc chất lượng của JPG được tạo không?**  
A: Chắc chắn—sử dụng `JpgViewOptions.setResolution(300)` và `setQuality(90)` trước khi gọi `view`.

**Q: Thư viện có hoạt động trên container Linux không?**  
A: Có, GroupDocs Viewer thuần Java và chạy trên bất kỳ OS nào có JRE tương thích, rất phù hợp cho triển khai Docker.

---

**Cập nhật lần cuối:** 2026-06-20  
**Kiểm tra với:** GroupDocs.Viewer 23.9 for Java  
**Tác giả:** GroupDocs

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
       // Render the APNG into HTML with embedded resources.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
       // Each frame becomes a separate JPG image.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PngViewOptions options = new PngViewOptions(pageFilePathFormat);
       // Converts each frame to a separate PNG.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
       // Convert the APNG into a single PDF.
       viewer.view(options);
   }
   ```

## Hướng dẫn liên quan

- [Hướng dẫn Kết xuất Tài liệu Java - Chuyển đổi Tệp sang HTML, PDF & Hình ảnh](/viewer/java/rendering-basics/)
- [Cách kết xuất pdf sang html và tối ưu chất lượng hình ảnh trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Cách chuyển đổi tệp DOCX sang PNG bằng GroupDocs.Viewer cho Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)