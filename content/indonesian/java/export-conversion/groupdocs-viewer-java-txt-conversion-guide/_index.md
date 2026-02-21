---
date: '2026-02-21'
description: Pelajari cara menggunakan GroupDocs Viewer Maven untuk mengonversi file
  txt ke html, jpg, png, dan pdf dalam Java. Termasuk langkah-langkah untuk txt ke
  pdf Java dan html multi halaman Java.
keywords:
- GroupDocs.Viewer for Java
- convert TXT to HTML
- render TXT as JPG/PNG
title: 'groupdocs viewer maven: Konversi TXT ke HTML, JPG, PNG, PDF'
type: docs
url: /id/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/
weight: 1
---

**Last Updated:** 2026-02-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

Translate labels.

Now produce final markdown.

Be careful not to translate code placeholders.

Proceed to write final answer.# groupdocs viewer maven: Mengonversi File TXT ke HTML, JPG, PNG, dan PDF Menggunakan GroupDocs.Viewer untuk Java

Dalam aplikasi Java modern, **groupdocs viewer maven** memudahkan transformasi dokumen plain‑text (TXT) menjadi HTML siap web, gambar resolusi tinggi, atau file PDF yang portabel. Baik Anda membangun portal dokumen, layanan arsip, atau fitur pratinjau, mengonversi file TXT dengan GroupDocs.Viewer menghemat waktu Anda dan menghilangkan kebutuhan akan parser khusus. Dalam panduan ini kami akan menjelaskan pengaturan lengkap dan menunjukkan cara **convert txt files java** ke HTML (halaman tunggal‑ dan multi‑page), JPG, PNG, dan PDF.

![Mengonversi File TXT ke HTML, JPG, PNG, dan PDF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-txt-files-to-html-jpg-png-and-pdf-java.png)

## Quick Answers
- **Artifact Maven mana yang saya perlukan?** `com.groupdocs:groupdocs-viewer` (lihat snippet Maven di bawah).  
- **Apakah saya dapat merender HTML multi‑page?** Ya – gunakan `HtmlViewOptions.forEmbeddedResources` tanpa flag halaman tunggal.  
- **Apakah lisensi diperlukan untuk produksi?** Percobaan dapat digunakan untuk evaluasi; lisensi permanen diperlukan untuk penggunaan komersial.  
- **Versi Java apa yang didukung?** Java 8 atau yang lebih baru (Java 11+ disarankan).  
- **Apakah saya memerlukan pustaka tambahan untuk output gambar?** Tidak, pustaka Viewer sudah menyertakan dukungan JPG dan PNG secara bawaan.

## What is groupdocs viewer maven?
**groupdocs viewer maven** adalah distribusi berbasis Maven dari pustaka GroupDocs.Viewer untuk Java. Ia menyediakan API sederhana untuk merender lebih dari 100 format dokumen—termasuk plain‑text—ke dalam HTML, gambar, atau PDF tanpa memerlukan Microsoft Office atau alat pihak ketiga lainnya.

## Why convert txt files java?
- **Pratinjau lintas‑platform** – HTML dan gambar dapat ditampilkan di browser atau aplikasi seluler.  
- **Arsip standar** – PDF mempertahankan format dan dapat dibaca secara universal.  
- **Ramahan otomatisasi** – Integrasikan konversi ke dalam pekerjaan batch, layanan cloud, atau pipeline CI.  

## Prerequisites

- **GroupDocs.Viewer for Java** versi 25.2 atau lebih baru (disediakan melalui Maven).  
- JDK 8 + (Java 11 + disarankan).  
- IDE seperti IntelliJ IDEA, Eclipse, atau NetBeans.  
- Pengetahuan dasar Java dan Maven.  

## Setting Up GroupDocs.Viewer for Java

Tambahkan repositori dan dependensi ke `pom.xml` Anda:

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
- Mulailah dengan **percobaan gratis** atau dapatkan **lisensi sementara** untuk menjelajahi semua kemampuan.  
- Untuk produksi, beli lisensi melalui halaman resmi [purchase page](https://purchase.groupdocs.com/buy).  

### Basic Initialization and Setup
1. Tambahkan dependensi Maven yang ditampilkan di atas.  
2. Pastikan JDK dan IDE Anda dikonfigurasi dengan benar.  

Sekarang mari kita selami skenario konversi yang konkret.

## Implementation Guide

### Feature 1: Render TXT to Multi‑page HTML *(multi page html java)*

#### Overview
Contoh ini mengonversi dokumen TXT menjadi file **HTML multi‑page**, mempertahankan pemisahan baris pada halaman web terpisah.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Render the document to HTML using these options
    viewer.view(options);
}
```

*Explanation:* `HtmlViewOptions.forEmbeddedResources` menggabungkan CSS, font, dan gambar langsung ke dalam output HTML, sehingga menjadi portabel.

### Feature 2: Render TXT to Single‑page HTML *(convert txt to html java)*

#### Overview
Kondensasi seluruh file teks ke dalam satu halaman HTML—sempurna untuk pratinjau cepat.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Set the option to render as a single page HTML
    options.setRenderToSinglePage(true);
    
    // Render the document using these options
    viewer.view(options);
}
```

*Explanation:* `setRenderToSinglePage(true)` menggabungkan semua halaman menjadi satu file HTML.

### Feature 3: Render TXT to JPG

#### Overview
Konversi file TXT menjadi gambar JPEG berkualitas tinggi, berguna untuk berbagi di platform yang hanya menerima gambar.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a JPEG image
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // Render the document as a JPG using these options
    viewer.view(options);
}
```

*Explanation:* `JpgViewOptions` memungkinkan Anda mengontrol kualitas gambar, DPI, dan jalur output.

### Feature 4: Render TXT to PNG

#### Overview
Hasilkan gambar PNG lossless dari file teks—ideal ketika Anda memerlukan grafik yang tajam dan dapat diskalakan.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PNG image
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // Render the document as a PNG using these options
    viewer.view(options);
}
```

*Explanation:* PNG menyediakan kompresi lossless, mempertahankan tampilan asli teks secara tepat.

### Feature 5: Render TXT to PDF *(txt to pdf java / convert txt to pdf java)*

#### Overview
Buat file PDF dari dokumen TXT—bagus untuk arsip, pencetakan, atau pengiriman ke klien.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PDF
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // Render the document as a PDF using these options
    viewer.view(options);
}
```

*Explanation:* `PdfViewOptions` menangani tata letak halaman, font, dan penyematan sumber daya secara otomatis.

## Practical Applications

1. **Sistem Manajemen Dokumen:** Otomatisasi konversi dokumen TXT lama menjadi HTML untuk portal intranet.  
2. **Platform Penerbitan:** Ubah manuskrip TXT yang diajukan penulis menjadi HTML untuk integrasi CMS yang mulus.  
3. **Solusi Arsip:** Simpan file teks lama sebagai PDF atau PNG untuk penyimpanan jangka panjang.  
4. **Integrasi Penyimpanan Cloud:** Konversi secara langsung dan simpan file yang dirender di AWS S3, Azure Blob, atau Google Cloud.  

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Output is blank** | Jalur file tidak tepat atau izin baca tidak ada. | Verifikasi `YOUR_DOCUMENT_DIRECTORY` mengarah ke file TXT yang sebenarnya dan proses memiliki hak baca. |
| **Images are low quality** | DPI default rendah. | Gunakan `JpgViewOptions.setResolution(int dpi)` atau `PngViewOptions.setResolution(int dpi)` untuk meningkatkan DPI (misalnya, 300). |
| **HTML contains broken links** | Sumber daya tidak disematkan. | Gunakan `HtmlViewOptions.forEmbeddedResources` atau sediakan folder sumber daya khusus. |
| **License exception** | Lisensi yang valid belum diatur. | Muat file lisensi Anda dengan `License license = new License(); license.setLicense("path/to/license.file");` sebelum membuat `Viewer`. |

## Frequently Asked Questions

**Q: Can I convert large TXT files (hundreds of MB) with GroupDocs.Viewer?**  
A: Ya. Pustaka ini melakukan streaming pada file sumber, tetapi Anda mungkin perlu meningkatkan ukuran heap JVM untuk dokumen yang sangat besar.

**Q: Do I need additional dependencies to generate JPG or PNG?**  
A: Tidak. Paket Viewer sudah menyertakan semua pustaka pemrosesan gambar yang diperlukan.

**Q: Is it possible to customize the PDF page size?**  
A: Tentu saja. Gunakan `PdfViewOptions.setPageSize(PageSize.A4)` atau `PageSize` lain sebelum merender.

**Q: How do I handle password‑protected TXT files?**  
A: File TXT tidak mendukung kata sandi. Jika file terenkripsi, dekripsi terlebih dahulu sebelum memberikannya ke Viewer.

**Q: Can I run this conversion in a Docker container?**  
A: Ya. Cukup sertakan JDK, salin `pom.xml` Anda dengan dependensi GroupDocs, dan jalankan aplikasi Java di dalam kontainer.

---

**Last Updated:** 2026-02-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs