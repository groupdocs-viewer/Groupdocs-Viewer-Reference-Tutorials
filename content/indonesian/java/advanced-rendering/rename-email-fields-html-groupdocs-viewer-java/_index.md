---
date: '2026-03-24'
description: Pelajari cara mengonversi email ke HTML dan mengganti nama bidang email
  menggunakan GroupDocs Viewer untuk Java. Panduan ini menunjukkan cara merender email
  sebagai HTML dengan header khusus.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Konversi Email ke HTML & Ubah Nama Field – GroupDocs Viewer Java
type: docs
url: /id/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Convert Email to HTML & Rename Fields – GroupDocs Viewer Java

Jika Anda perlu **mengonversi email ke HTML** sambil memberikan header email tampilan khusus, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas langkah‑langkah tepat untuk mengganti nama bidang email, **mengonversi email ke HTML**, dan menyesuaikan header email menggunakan GroupDocs.Viewer untuk Java. Pada akhir tutorial Anda akan memiliki representasi HTML yang bersih dengan nama header yang Anda inginkan, sehingga output lebih mudah dibaca dan diintegrasikan ke dalam aplikasi Anda.

![Rename Email Fields When Converting Emails to HTML with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### What You'll Learn
- Cara menggunakan GroupDocs.Viewer untuk Java untuk **mengonversi email ke HTML**.  
- Teknik untuk **mengganti nama bidang email** seperti “From,” “To,” “Sent,” dan “Subject.”  
- Praktik terbaik untuk menyiapkan Maven dan lisensi.  
- Skenario dunia nyata di mana **menyesuaikan header email** menambah nilai.

## Quick Answers
- **What does “convert email to HTML” mean?** Itu berarti merender file email (MSG/EML) sebagai dokumen HTML yang siap ditampilkan di web.  
- **Which library handles the conversion?** GroupDocs.Viewer untuk Java (v25.2+).  
- **Do I need a license?** Versi percobaan dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Can I change any header name?** Ya, setiap header email standar dapat dipetakan ulang melalui `fieldTextMap`.  
- **Is the output HTML or embedded resources?** Anda dapat memilih sumber daya tersemat untuk satu file mandiri.

## What is “convert email to HTML” in the Context of GroupDocs.Viewer?
Mengonversi email ke HTML berarti mengambil file email mentah dan menghasilkan halaman HTML yang menampilkan isi pesan beserta metadata‑nya. Ketika Anda juga **mengganti nama bidang email**, label default (misalnya “From”) diganti dengan teks khusus (misalnya “Sender”), yang membantu menyesuaikan istilah perusahaan atau meningkatkan konsistensi UI.

## Why Convert Email to HTML and Rename Email Fields?
- **Consistent branding:** Menyelaraskan output dengan bahasa organisasi Anda.  
- **Improved searchability:** Header khusus dapat diindeks lebih efektif dalam sistem arsip.  
- **Better UI integration:** Menyesuaikan potongan HTML agar cocok secara mulus dengan portal web atau dasbor dukungan.

## Prerequisites

### Required Libraries, Versions, and Dependencies
- **GroupDocs.Viewer for Java** – versi 25.2 atau lebih baru.  
- **Java Development Kit (JDK)** – versi 8+.

### Environment Setup Requirements
- **Maven** untuk manajemen dependensi.  
- IDE seperti IntelliJ IDEA, Eclipse, atau VS Code.

### Knowledge Prerequisites
Pemahaman dasar tentang Java dan Maven akan membantu Anda mengikuti tutorial ini dengan cepat.

## Setting Up GroupDocs.Viewer for Java

### Maven Configuration
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

### License Acquisition Steps
- **Free Trial:** Unduh versi percobaan gratis dari [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** Dapatkan lisensi sementara untuk menjelajahi semua fitur tanpa batasan di [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** Untuk penggunaan berkelanjutan, pertimbangkan membeli lisensi melalui [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Basic Initialization and Setup
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Sesuaikan jalur file untuk mengarah ke file `.msg` Anda.

## How to Convert Email to HTML and Rename Fields – Step‑by‑Step

### 1. Set Up the Output Directory Path
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Ganti `"YOUR_OUTPUT_DIRECTORY"` dengan folder tempat Anda ingin menyimpan file HTML.*

### 2. Define Page File Path Format
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` akan digantikan oleh nomor halaman saat rendering.*

### 3. Create a Mapping of Email Fields to New Names
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Di sini kami mengubah label default menjadi label khusus.*

### 4. Configure HTML View Options
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` menggabungkan CSS/JS di dalam HTML, sementara `setFieldTextMap` menerapkan nama header khusus.*

### 5. Render the Email to HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ganti `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` dengan jalur aktual ke file MSG Anda.*

#### Troubleshooting Tips
- Pastikan direktori output dapat ditulisi.  
- Pastikan file MSG input ada dan jalurnya benar.  
- Gunakan versi GroupDocs.Viewer yang sama (25.2) seperti yang dideklarasikan di Maven.

## Practical Applications
1. **Custom Email Reports:** Menyelaraskan header email dengan istilah perusahaan untuk laporan yang lebih jelas.  
2. **Email Archiving Systems:** Meningkatkan kemampuan pencarian dengan menggunakan nama header yang terstandarisasi.  
3. **Customer Support Platforms:** Menampilkan tiket dengan label header yang dipersonalisasi untuk pengalaman agen yang lebih baik.

## Performance Considerations
- Buang objek `Viewer` dengan try‑with‑resources untuk membebaskan memori secara cepat.  
- Profilkan batch besar dan pertimbangkan memproses email secara paralel jika diperlukan.

## Conclusion
Anda kini tahu **cara mengonversi email ke HTML** sambil **mengganti nama bidang email** dan **menyesuaikan header email** dengan GroupDocs.Viewer untuk Java. Teknik ini memberi Anda kontrol penuh atas penyajian metadata email dalam output HTML.

### Next Steps
- Bereksperimen dengan pemetaan bidang tambahan (mis., CC, BCC).  
- Jelajahi format rendering lain seperti **PDF** atau **PNG**.  
- Kunjungi [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) untuk wawasan API yang lebih mendalam.

## Frequently Asked Questions

**Q: Does this approach work with other email formats like EML?**  
A: Ya, GroupDocs.Viewer mendukung file MSG dan EML; logika pemetaan bidang yang sama dapat diterapkan.

**Q: Can I output the HTML without embedded resources?**  
A: Anda dapat menggunakan `HtmlViewOptions.forExternalResources(...)` jika lebih suka file CSS/JS terpisah.

**Q: What version of GroupDocs.Viewer was tested?**  
A: Kode ini diuji dengan GroupDocs.Viewer **25.2**.

**Q: Is it possible to change the font or style of the custom headers?**  
A: Styling dapat diterapkan melalui CSS setelah rendering, atau Anda dapat menyuntikkan CSS khusus menggunakan `HtmlViewOptions.getResourcesPath()`.

**Q: How do I programmatically retrieve the generated HTML file path?**  
A: Jalur file mengikuti pola yang didefinisikan dalam `pageFilePathFormat`; Anda dapat membangunnya menggunakan `String.format` dengan nomor halaman.

## Resources
- **Documentation:** Panduan lengkap tersedia di [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Informasi API detail dapat ditemukan di [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Akses versi terbaru melalui [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Last Updated:** 2026-03-24  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs