---
date: '2026-07-19'
description: Pelajari cara mengonversi WMZ ke PDF, HTML, JPG, dan PNG dengan GroupDocs
  Viewer untuk Java. Panduan langkah demi langkah untuk konversi vektor grafis java.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Konversi WMZ ke PDF, HTML, JPG, dan PNG menggunakan GroupDocs Viewer
  untuk Java. Tutorial ini menunjukkan langkah demi langkah konversi vektor grafis
  java dengan fidelitas tinggi.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Konversi WMZ ke PDF dengan GroupDocs Viewer untuk Java – Panduan Cepat
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Konversi WMZ ke PDF dan Format Lain Menggunakan GroupDocs Viewer untuk Java
type: docs
url: /id/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Mengonversi WMZ ke PDF dan Format Lain Menggunakan GroupDocs Viewer untuk Java

Mengonversi file WMZ (Web Metafile) dan WMF (Windows Metafile) ke format yang lebih mudah diakses—terutama **convert WMZ to PDF**—bisa menjadi tantangan karena format grafik vektor ini menyimpan instruksi gambar bukan data piksel. Dengan **GroupDocs Viewer for Java**, Anda dapat merender dokumen WMZ/WMF ke HTML, JPG, PNG, **PDF**, dan format populer lainnya hanya dalam beberapa baris kode, sambil mempertahankan kesetiaan visual asli.

![Konversi Dokumen WMZ/WMF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Konversi Dokumen WMZ/WMF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Jawaban Cepat
- **Format apa yang dapat dikonversi dari WMZ/WMF?** HTML, JPG, PNG, dan PDF didukung sepenuhnya.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial menghapus batas evaluasi.  
- **Versi Java apa yang diperlukan?** Java 8 atau yang lebih baru disarankan.  
- **Bisakah saya merender hanya halaman tertentu?** Ya, Anda dapat menentukan rentang halaman dalam opsi tampilan.  
- **Apakah penggunaan memori menjadi masalah untuk file besar?** Gunakan try‑with‑resources dan render hanya halaman yang diperlukan untuk menjaga memori tetap rendah.

## Apa itu “convert WMZ to PDF”?
**Convert WMZ to PDF** berarti mengambil file vektor WMZ dan menyematkan instruksi gambarnya ke dalam wadah PDF, menghasilkan dokumen yang dapat dilihat secara universal, dapat dicari, dan dapat dicetak. Konversi ini mempertahankan kualitas garis dan bentuk, sehingga PDF yang dihasilkan terlihat identik dengan grafik asli pada perangkat apa pun.

## Mengapa menggunakan GroupDocs Viewer untuk Java untuk mengonversi grafik vektor?
GroupDocs Viewer untuk Java menangani rendering WMZ dan WMF dengan **high fidelity**, mempertahankan detail vektor baik Anda mengekspor ke PDF, PNG, atau HTML. Perpustakaan ini berjalan di platform apa pun dengan JDK, tidak memerlukan komponen Windows native, dan menyediakan API satu‑panggilan yang dapat diskalakan dari file satu‑ikon hingga gambar teknis multi‑halaman. Dalam pengujian benchmark, ia memproses **file WMZ lebih dari 200 halaman dalam waktu kurang dari 12 detik** pada server standar 4‑core.

## Prasyarat

- **GroupDocs.Viewer for Java** – mesin rendering inti.  
- Java Development Kit (JDK) 8 atau yang lebih baru.  
- IDE seperti IntelliJ IDEA atau Eclipse (opsional tetapi disarankan).  
- Maven (atau Gradle) untuk manajemen dependensi.  

Pemahaman tentang Java NIO (`java.nio.file.Path`) dan I/O file dasar akan membantu Anda mengikuti contoh dengan lancar.

## Menyiapkan GroupDocs.Viewer untuk Java

Kelas `Viewer` adalah titik masuk untuk semua operasi rendering. Ini mewakili mesin yang thread‑safe yang dapat digunakan kembali di beberapa konversi.

Tambahkan repositori dan dependensi ke `pom.xml` Anda (atau setara Gradle). Setelah Maven menyelesaikan artefak, Anda dapat membuat instance `Viewer` yang akan digunakan kembali untuk setiap langkah konversi.

> **Tips Lisensi:** Gunakan percobaan gratis untuk evaluasi, lalu terapkan lisensi sementara atau yang dibeli untuk membuka semua fungsi.

## Panduan Implementasi

Di bawah ini kami membahas empat skenario konversi—HTML, JPG, PNG, dan PDF. Setiap skenario mengikuti pola tiga langkah yang sama:

1. **Tentukan direktori output** tempat file yang dirender akan disimpan.  
2. **Buat instance `Viewer`** yang menunjuk ke file sumber WMZ/WMF.  
3. **Konfigurasikan opsi tampilan spesifik format** dan panggil metode `view`.  

Metode `view` melakukan rendering berdasarkan opsi yang diberikan.

### Rendering WMZ/WMF ke HTML

#### Ikhtisar
Output HTML memungkinkan Anda menyematkan grafik langsung ke halaman web, dengan semua sumber daya (gambar, CSS) terkandung dalam satu file.

**Langkah 1: Tentukan Jalur Direktori Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Langkah 2: Inisialisasi Viewer dan Render ke HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendering WMZ/WMF ke JPG

#### Ikhtisar
JPG adalah format raster yang didukung luas, sempurna untuk pratinjau cepat atau lampiran email.

**Langkah 1: Tentukan Jalur Direktori Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Langkah 2: Inisialisasi Viewer dan Render ke JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF ke PNG

#### Ikhtisar
PNG mendukung transparansi, menjadikannya ideal untuk grafik yang perlu berpadu dengan latar belakang yang berbeda.

**Langkah 1: Tentukan Jalur Direktori Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Langkah 2: Inisialisasi Viewer dan Render ke PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF ke PDF

#### Ikhtisar
PDF menyediakan dokumen yang platform‑independen, dapat dicari, yang mempertahankan tata letak asli.

**Langkah 1: Tentukan Jalur Direktori Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Langkah 2: Inisialisasi Viewer dan Render ke PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Masalah Umum dan Solusinya

`PageStreamViewOptions` memungkinkan rendering halaman tertentu sebagai stream.  
`PdfViewOptions` mengonfigurasi pengaturan output PDF seperti rentang halaman dan DPI.  
`FontSettings` memungkinkan Anda menyediakan font khusus ketika dokumen sumber merujuk font yang hilang.

| Issue | Cause | Solution |
|-------|-------|----------|
| **OutOfMemoryError** pada file WMZ besar | Viewer memuat seluruh dokumen ke dalam memori | Render satu halaman pada satu waktu menggunakan `PageStreamViewOptions` atau tingkatkan heap JVM (`-Xmx`). |
| **Font hilang** dalam PDF | Font tidak disematkan dalam WMZ sumber | Instal font yang diperlukan pada mesin host atau gunakan `FontSettings` untuk menyediakan font khusus. |
| **Output PNG kosong** | Jalur output tidak benar atau izin menulis tidak cukup | Pastikan `outputDirectory` ada dan aplikasi memiliki akses menulis. |
| **Sumber daya HTML tidak dimuat** | Menggunakan `forExternalResources` tanpa menyalin file | Gunakan `forEmbeddedResources` untuk file HTML yang berdiri sendiri. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengonversi WMF ke PNG menggunakan kode yang sama?**  
A: Ya. Contoh PNG bekerja untuk file WMZ dan WMF; cukup ganti `TestFiles.SAMPLE_WMZ` dengan sumber WMF Anda.

**Q: Apakah memungkinkan mengonversi hanya sebagian halaman?**  
A: Tentu saja. Gunakan `PdfViewOptions` (atau opsi yang sesuai untuk format lain) dan panggil `setPageNumbers(List<Integer>)` sebelum rendering.

**Q: Apakah saya memerlukan lisensi terpisah untuk setiap format output?**  
A: Tidak. Satu lisensi GroupDocs Viewer mencakup semua format yang didukung, termasuk HTML, JPG, PNG, dan PDF.

**Q: Bagaimana “java convert vector graphics” memengaruhi kinerja?**  
A: Konversi vektor‑ke‑raster intensif CPU. Untuk batch besar, pertimbangkan multi‑threading dan gunakan kembali satu instance `Viewer` di seluruh file.

**Q: Apakah PDF akan mempertahankan kualitas vektor, atau rasterisasi?**  
A: Saat mengonversi WMZ/WMF ke PDF, GroupDocs Viewer mempertahankan instruksi vektor bila memungkinkan, menghasilkan PDF yang dapat diskalakan.

## Kesimpulan

Anda kini memiliki panduan lengkap yang siap produksi untuk **convert WMZ to PDF** dan format umum lainnya menggunakan **GroupDocs Viewer untuk Java**. Baik Anda membangun layanan web yang menyajikan grafik secara langsung atau alat arsip yang menyimpan dokumen sebagai PDF, langkah-langkah di atas akan membantu Anda mencapainya dengan cepat dan andal. Jelajahi API lebih lanjut untuk menyesuaikan rentang halaman, pengaturan DPI, atau watermark sesuai kebutuhan proyek Anda.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

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

## Tutorial Terkait

- [Cara Mengonversi OBJ ke HTML, JPG, PNG, dan PDF dalam Java Menggunakan GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Konversi IGS ke PDF, HTML, JPG & PNG menggunakan GroupDocs.Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Mengonversi Dokumen ke PDF – Panduan Lengkap](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)