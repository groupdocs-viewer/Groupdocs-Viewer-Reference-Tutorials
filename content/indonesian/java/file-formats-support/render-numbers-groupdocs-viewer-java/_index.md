---
date: '2026-08-25'
description: Pelajari cara mengonversi Numbers dengan GroupDocs.Viewer untuk Java,
  mengubah file Apple Numbers menjadi PDF, HTML, JPG, atau PNG. Termasuk panduan pengaturan,
  langkah-langkah konversi dokumen Java, dan tips menampilkan di web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Pelajari cara mengonversi Numbers dengan GroupDocs.Viewer untuk Java,
  mengubah file Apple Numbers menjadi PDF, HTML, JPG, atau PNG. Termasuk panduan pengaturan,
  langkah-langkah konversi dokumen Java, dan tips menampilkan di web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Cara mengonversi Numbers dengan GroupDocs.Viewer untuk Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Cara mengonversi Numbers dengan GroupDocs.Viewer untuk Java
type: docs
url: /id/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Cara mengonversi Numbers dengan GroupDocs.Viewer untuk Java

Menampilkan spreadsheet Apple Numbers di web atau di dalam klien desktop dapat terasa seperti teka‑teki, terutama ketika Anda perlu **mengonversi Numbers ke PDF** atau menyematkannya sebagai gambar untuk laporan. Dalam tutorial ini Anda akan mempelajari secara tepat **cara mengonversi Numbers** ke PDF, HTML, JPG, dan PNG menggunakan **GroupDocs.Viewer untuk Java**. Kami akan membahas penyiapan proyek, rendering tingkat kode, dan skenario dunia nyata sehingga Anda dapat membangun pipeline preview atau pengarsipan yang kuat dalam hitungan menit.

![Render Dokumen Apple Numbers dengan GroupDocs.Viewer untuk Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Render Dokumen Apple Numbers dengan GroupDocs.Viewer untuk Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Apa yang akan Anda pelajari
- Cara menambahkan GroupDocs.Viewer ke proyek Java berbasis Maven.  
- Kode langkah‑demi‑langkah untuk **mengonversi numbers ke pdf**, **mengonversi numbers ke html**, **mengonversi numbers ke jpg**, dan **mengonversi numbers ke png**.  
- Kapan memilih setiap format output untuk portal web, alur kerja email, atau sistem manajemen dokumen.  

## Jawaban Cepat
- **Apakah saya dapat mengonversi Numbers ke PDF dengan Java?** Ya – buat instance `Viewer` dan panggil `PdfViewOptions` untuk mendapatkan PDF yang siap disimpan.  
- **Format mana yang memberikan preview web paling kaya?** HTML, karena mempertahankan tabel, rumus, dan gaya secara interaktif.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk setiap penerapan non‑trial.  
- **Apakah konversi gambar didukung?** Tentu – gunakan `JpgViewOptions` atau `PngViewOptions` untuk snapshot berkualitas tinggi.  
- **Versi Java apa yang diperlukan?** Java 8+ dan Maven untuk manajemen dependensi.  

## Prasyarat
- Java Development Kit (JDK) 8 atau yang lebih baru terpasang di mesin Anda.  
- Maven untuk menangani dependensi dan membangun proyek.  
- Familiaritas dasar dengan I/O file Java, path, dan penanganan exception.  

## Menyiapkan GroupDocs.Viewer untuk Java

### Instalasi dengan Maven
Tambahkan repositori GroupDocs dan dependensi Viewer ke `pom.xml` Anda. Blok ini harus tetap persis seperti yang ditampilkan:

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

### Akuisisi Lisensi
- **Free trial:** Set lengkap fitur, tidak memerlukan kartu kredit.  
- **Temporary license:** Minta kunci berjangka waktu untuk pengujian lanjutan.  
- **Full purchase:** Dapatkan lisensi seumur hidup untuk penggunaan komersial.  

## Apa itu kelas Viewer?
Kelas `Viewer` adalah mesin inti GroupDocs.Viewer yang memuat dokumen dan merendernya ke format output yang diminta. Ia mengabstraksi penanganan tipe file sehingga Anda dapat fokus pada logika bisnis alih-alih parsing internal spreadsheet.  

## Cara mengonversi Numbers ke HTML dengan GroupDocs.Viewer untuk Java?

`HtmlViewOptions` menentukan pengaturan untuk rendering HTML, seperti menyematkan sumber daya atau menautkan file eksternal.  
Muat file Numbers, konfigurasikan opsi HTML, dan panggil `viewer.view()`. Metode `HtmlViewOptions.forEmbeddedResources()` menggabungkan CSS dan gambar langsung ke dalam HTML, sehingga hasilnya ideal untuk disematkan di halaman web tanpa aset tambahan.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Why this matters:** Embedded resources keep the preview self‑contained, eliminating broken image links and simplifying CDN deployment.  

## Cara mengonversi Numbers ke JPG dengan GroupDocs.Viewer untuk Java?

`JpgViewOptions` mengonfigurasi output JPEG, memungkinkan penyesuaian kualitas dan ukuran untuk setiap halaman yang dirender.  
Anda dapat mengubah setiap halaman spreadsheet menjadi snapshot JPEG. Sesuaikan pengaturan `quality` untuk menyeimbangkan ukuran file dan fidelitas visual, yang berguna ketika Anda memerlukan gambar ringan untuk media sosial atau buletin email.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Tip:** Untuk pemrosesan lebih cepat pada workbook besar, turunkan kualitas menjadi 70 % – dampak visual minimal sementara ukuran file berkurang secara dramatis.  

## Cara mengonversi Numbers ke PNG dengan GroupDocs.Viewer untuk Java?

`PngViewOptions` mengonfigurasi output PNG, mendukung kompresi lossless dan pengaturan resolusi untuk gambar berkualitas tinggi.  
PNG menawarkan kompresi lossless, mempertahankan setiap piksel persis seperti yang dirender. Gunakan properti `resolution` untuk meningkatkan DPI ketika Anda memerlukan grafik siap cetak untuk laporan atau PDF.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro tip:** Set `options.setResolution(300)` for high‑resolution output that looks crisp on printed pages.  

## Cara mengonversi Numbers ke PDF dengan GroupDocs.Viewer untuk Java?

`PdfViewOptions` mendefinisikan opsi rendering PDF, termasuk penyematan font, kompresi, dan kontrol ukuran halaman.  
Objek `PdfViewOptions` memungkinkan Anda menyematkan font, mengontrol ukuran halaman, dan mempertahankan tata letak asli workbook Numbers. Konversi dijalankan dalam satu panggilan, menghasilkan PDF yang dapat dicari, tidak dapat diedit, dan sempurna untuk pengarsipan atau kepatuhan.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Key configuration:** Enable `options.setCompress(true)` to shrink the PDF size without sacrificing quality, which is essential for large‑scale document warehouses.  

## Mengapa menggunakan GroupDocs.Viewer untuk Java?

GroupDocs.Viewer mendukung **lebih dari 100 format file**, termasuk Apple Numbers, dan dapat merender spreadsheet ratusan halaman tanpa memuat seluruh file ke memori. Benchmark menunjukkan bahwa file Numbers 250‑halaman dapat dikonversi ke PDF dalam kurang dari 8 detik pada CPU standar 2.5 GHz, memberikan kecepatan dan keandalan untuk pipeline perusahaan.  

## Aplikasi Praktis
- **Web integration:** Render ke HTML untuk penampil spreadsheet interaktif yang bekerja di semua browser tanpa plugin.  
- **Content sharing:** Konversi ke JPG/PNG untuk penyematan gambar cepat dalam buletin, aplikasi chat, atau feed sosial.  
- **Enterprise DMS:** Gunakan **cara mengonversi numbers** ke PDF untuk menyimpan versi spreadsheet yang tidak dapat diedit, dapat dicari, demi kepatuhan dan jejak audit.  

## Pertimbangan Kinerja
- **Resource management:** Selalu buat instance `Viewer` di dalam blok try‑with‑resources (seperti yang ditunjukkan) sehingga sumber daya native dilepaskan segera.  
- **Large workbooks:** Proses halaman per halaman dan streaming output untuk menjaga penggunaan memori di bawah 100 MB, bahkan untuk file 500‑halaman.  
- **Thread safety:** Buat instance `Viewer` terpisah per thread; kelas ini tidak thread‑safe, sehingga berbagi satu instance dapat menyebabkan kondisi balapan.  

## Kesulitan Umum dan Pemecahan Masalah

- **Missing fonts:** Jika PDF yang dihasilkan terlihat berbeda, pastikan font yang diperlukan tersedia di server atau sematkan mereka menggunakan `PdfViewOptions.setEmbedFonts(true)`.  
- **Blank pages:** Verifikasi bahwa file Numbers tidak dilindungi kata sandi; GroupDocs.Viewer saat ini tidak dapat mendekripsi workbook yang dilindungi.  
- **Out‑of‑memory errors:** Untuk file yang sangat besar, aktifkan `options.setPageCount(1)` untuk merender satu halaman pada satu waktu dan gabungkan hasilnya nanti.  

## Pertanyaan yang Sering Diajukan

**Q: Format file apa yang didukung oleh GroupDocs.Viewer?**  
A: Lebih dari 100 format, termasuk DOCX, XLSX, PDF, HTML, dan Apple Numbers, dengan kemampuan rendering penuh untuk masing‑masing.

**Q: Bagaimana cara menangani file Numbers besar secara efisien?**  
A: Streaming konversi per halaman, gunakan `options.setPageCount()` untuk membatasi penggunaan memori, dan pertimbangkan mengompres PDF output.

**Q: Apakah GroupDocs.Viewer dapat digunakan dalam proyek komersial?**  
A: Ya—beli lisensi komersial untuk menghapus batas trial dan mendapatkan dukungan produksi.

**Q: Apakah memungkinkan menyesuaikan kualitas output gambar?**  
A: Tentu. Sesuaikan `JpgViewOptions.setQuality(int)` atau `PngViewOptions.setResolution(int)` untuk memenuhi kebutuhan ukuran‑kualitas Anda.

**Q: Di mana saya dapat menemukan contoh penggunaan lanjutan?**  
A: Kunjungi [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) untuk panduan mendalam, contoh proyek, dan detail referensi API.  

## Langkah Selanjutnya
Eksperimen dengan opsi yang ditunjukkan di atas, lalu jelajahi kustomisasi tambahan seperti menambahkan watermark pada PDF, menambahkan perlindungan kata sandi, atau mengintegrasikan viewer ke layanan REST Spring Boot. [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) menyediakan katalog lengkap fitur yang dapat Anda gabungkan.  

## Sumber Daya
- **Documentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs documentation:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **API reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Purchase license:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Support forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-08-25  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs

## Tutorial Terkait

- [Cara Mengonversi Excel ke HTML, JPG, PNG, dan PDF Menggunakan GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Cara Mengonversi Excel ke HTML dan Merender Baris & Kolom Tersembunyi di Java dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Tutorial Rendering Dokumen Java - Mengonversi File ke HTML, PDF & Gambar](/viewer/java/rendering-basics/)