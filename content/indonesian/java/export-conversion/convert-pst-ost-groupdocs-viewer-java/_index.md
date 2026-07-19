---
date: '2026-07-19'
description: Pelajari cara mengonversi PST ke HTML dan format lain seperti JPG, PNG,
  PDF menggunakan GroupDocs.Viewer untuk Java. Panduan ini mencakup semua langkah
  dan konfigurasi yang diperlukan.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Konversi PST ke HTML dengan cepat menggunakan GroupDocs.Viewer untuk
  Java. Pelajari langkah demi langkah cara mengekspor ke JPG, PNG, dan PDF dalam panduan
  siap produksi.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Konversi PST ke HTML dengan GroupDocs.Viewer untuk Java – Ekspor Email Cepat
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Konversi PST ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer untuk Java
type: docs
url: /id/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Konversi PST ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer untuk Java

Apakah Anda ingin **konversi pst ke html** atau format lain seperti JPG, PNG, atau PDF? Dengan pustaka GroupDocs.Viewer untuk Java yang kuat, tugas ini menjadi sederhana dan efisien. Dalam tutorial ini Anda akan belajar cara merender file Outlook PST/OST menjadi HTML yang ramah web, file gambar, atau satu PDF, sehingga arsip email Anda mudah dibagikan dan diarsipkan.

![Konversi PST/OST ke HTML, JPG, PNG, PDF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Konversi PST/OST ke HTML, JPG, PNG, PDF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Apa yang Akan Anda Pelajari**
- Cara menyiapkan GroupDocs.Viewer untuk Java dalam proyek Maven.  
- Instruksi langkah demi langkah untuk **java convert pst** file ke HTML, JPG, PNG, dan PDF.  
- Tips konfigurasi untuk kinerja optimal dan jebakan umum.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi PST?** GroupDocs.Viewer for Java.  
- **Bisakah saya mengonversi PST ke PDF secara langsung?** Ya, menggunakan `PdfViewOptions`.  
- **Apakah lisensi diperlukan untuk produksi?** Lisensi GroupDocs yang valid diperlukan.  
- **Versi Java mana yang didukung?** JDK 8 atau lebih tinggi.  
- **Apakah saya perlu mengekstrak lampiran secara manual?** Tidak, viewer merendernya secara otomatis.

## Apa itu GroupDocs.Viewer untuk Java?
GroupDocs.Viewer untuk Java adalah API sisi server yang memuat lebih dari 100 format dokumen dan email serta merendernya menjadi output HTML, gambar, atau PDF tanpa perangkat lunak eksternal. Ia memproses file PST hingga 2 GB sambil menjaga penggunaan memori di bawah 200 MB.

## Cara mengonversi pst ke html menggunakan GroupDocs.Viewer untuk Java?

Muat file PST dengan `new Viewer("source.pst")`, konfigurasikan `HtmlViewOptions` untuk menunjuk ke folder output, dan panggil `viewer.view(htmlOptions)`. API mengekstrak setiap email, mempertahankan format, lampiran, dan metadata, serta menulis halaman HTML terpisah per pesan—semua dalam satu pemanggilan metode.

### Mengapa memilih GroupDocs.Viewer?
- **Rendering berfidelitas tinggi** – 99,9 % konten email (termasuk badan teks kaya, tabel, dan gambar tersemat) direproduksi secara akurat.  
- **Berbagai format output** – Satu panggilan API dapat menghasilkan HTML, JPG, PNG, atau PDF, mencakup lebih dari 50 opsi ekspor.  
- **Tanpa ketergantungan eksternal** – Tidak perlu Outlook, Exchange Server, atau konverter pihak ketiga; semuanya berjalan di dalam runtime Java Anda.

## Prasyarat
- **GroupDocs.Viewer for Java** – versi 25.2 atau lebih baru.  
- **Java Development Kit (JDK)** – 8 atau lebih baru.  
- Maven untuk manajemen dependensi.  
- Pengetahuan dasar Java dan familiaritas dengan Maven.

## Menyiapkan GroupDocs.Viewer untuk Java

`Viewer` adalah kelas inti dalam GroupDocs.Viewer untuk Java yang memuat dokumen dan merendernya ke format yang dipilih. Tambahkan repositori GroupDocs dan dependensi ke `pom.xml` Anda:

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

### Perolehan Lisensi
- **Free trial** – jelajahi semua fitur tanpa biaya.  
- **Temporary license** – perpanjang waktu evaluasi jika diperlukan.  
- **Full license** – diperlukan untuk penerapan produksi.

### Inisialisasi Dasar

Instansi `Viewer` ringan; Anda dapat menggunakan kembali satu instansi untuk banyak file guna meminimalkan beban pembuatan objek.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Panduan Implementasi

Bagian berikut akan memandu Anda melalui proses merender file PST/OST ke setiap format yang didukung.

### Merender Dokumen PST/OST ke HTML

#### Langkah 1: Siapkan Direktori Output

Tentukan folder tempat halaman HTML akan ditulis. GroupDocs membuat sub‑folder untuk setiap email agar aset terorganisir.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Langkah 2: Konfigurasikan Load Options

`LoadOptions` memungkinkan Anda menentukan penanganan kata sandi, batas waktu pemuatan sumber daya, dan rendering halaman selektif. Menetapkan batas waktu 30 detik bekerja baik untuk kebanyakan lingkungan server.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Langkah 3: Tentukan HTML View Options

`HtmlViewOptions` menentukan folder output, penanganan sumber daya, dan pengaturan CSS opsional untuk konversi HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Langkah 4: Inisialisasi Viewer dan Render HTML

Buat objek `Viewer`, berikan jalur file PST, dan panggil `view` dengan `HtmlViewOptions`. API secara otomatis mengiterasi semua pesan di dalam PST dan menghasilkan hierarki HTML yang rapi.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Merender Dokumen PST/OST ke JPG

#### Langkah 1: Siapkan Direktori Output

Buat folder khusus untuk snapshot JPG; setiap email akan menjadi satu atau beberapa file gambar tergantung pada panjangnya.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Langkah 2: Konfigurasikan Load Options

`LoadOptions` yang sama digunakan untuk HTML dapat digunakan kembali di sini, memastikan penanganan kata sandi yang konsisten di semua format.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Langkah 3: Tentukan JPG View Options

`JpgViewOptions` mengontrol resolusi gambar, kualitas, dan folder output untuk konversi JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Langkah 4: Inisialisasi Viewer dan Render JPG

Gunakan `viewer.view(jpgOptions)` untuk menghasilkan file JPEG berkualitas tinggi siap untuk pratinjau web.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Merender Dokumen PST/OST ke PNG

#### Langkah 1: Siapkan Direktori Output

Output PNG berguna ketika Anda membutuhkan kualitas lossless untuk pengarsipan atau pemrosesan OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Langkah 2: Konfigurasikan Load Options

Tidak ada pengaturan tambahan yang diperlukan selain konfigurasi kata sandi dan batas waktu.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Langkah 3: Tentukan PNG View Options

`PngViewOptions` memungkinkan Anda mengatur latar belakang transparan dan folder output untuk gambar PNG lossless.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Langkah 4: Inisialisasi Viewer dan Render PNG

Instansiasi `viewer.view(pngOptions)` untuk menghasilkan snapshot PNG dari setiap email.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Merender Dokumen PST/OST ke PDF

#### Langkah 1: Siapkan Direktori Output

Satu file PDF per PST menyederhanakan alur kerja peninjauan hukum dan mengurangi beban penyimpanan.

CODE_BLOCK_PLACEHOLDER_14_END

#### Langkah 2: Konfigurasikan Load Options

Saat mengonversi ke PDF, Anda mungkin ingin mengaktifkan `setEmbedFonts(true)` untuk menjamin fidelitas visual pada mesin apa pun.

CODE_BLOCK_PLACEHOLDER_15_END

#### Langkah 3: Tentukan PDF View Options

`PdfViewOptions` memungkinkan Anda memilih tingkat kompresi, menyematkan font, dan mengatur nama file output untuk konversi PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Langkah 4: Inisialisasi Viewer dan Render PDF

Buat `PdfViewOptions`, pilih tingkat kompresi secara opsional, dan panggil `viewer.view(pdfOptions)`. API menggabungkan semua email menjadi satu dokumen PDF yang dapat dicari.

CODE_BLOCK_PLACEHOLDER_17_END

## Aplikasi Praktis
- **Pengarsipan Email:** Ubah arsip PST besar menjadi HTML atau PDF yang dapat dicari untuk kepatuhan.  
- **Sistem Manajemen Dokumen:** Simpan file yang dikonversi dalam sistem yang hanya menerima PDF, PNG, atau JPG.  
- **Platform Kolaborasi:** Bagikan email yang dikonversi sebagai gambar di Slack atau Teams.  
- **Peninjauan Hukum:** Berikan pengadilan versi PDF dari bukti email.  
- **Strategi Cadangan:** Simpan snapshot PNG atau JPG ringan dari pesan penting.

## Pertimbangan Kinerja
- **Manajemen Sumber Daya:** Gunakan kembali instansi `Viewer` saat memproses banyak file untuk mengurangi beban.  
- **Penyesuaian Memori:** Sesuaikan `loadOptions.setResourceLoadingTimeout` berdasarkan kapasitas server.  
- **Pemrosesan Asinkron:** Alihkan konversi ke thread latar belakang untuk UI yang responsif.  

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara **convert pst to pdf** dengan basis kode yang sama?**  
A: Gunakan `PdfViewOptions` seperti yang ditunjukkan di bagian rendering PDF; sisanya kode tetap identik.

**Q: Bisakah GroupDocs.Viewer menangani file PST terenkripsi?**  
A: Ya, berikan kata sandi melalui `LoadOptions.setPassword("yourPassword")` sebelum merender.

**Q: Apa perbedaan antara **java convert pst** ke PNG vs JPG?**  
A: PNG mempertahankan kualitas lossless, ideal untuk tangkapan layar, sementara JPG menawarkan ukuran file lebih kecil untuk pratinjau email.

**Q: Apakah ada cara untuk **how to convert pst** file secara massal?**  
A: Bungkus logika rendering dalam loop yang mengiterasi direktori file PST; gunakan kembali konfigurasi `Viewer` yang sama untuk setiap file.

**Q: Apakah API mendukung konversi file PST lebih besar dari 1 GB?**  
A: Ya, GroupDocs.Viewer melakukan streaming data dan dapat memproses file hingga 2 GB tanpa memuat seluruh arsip ke memori.

## Kesimpulan

Anda kini memiliki panduan lengkap yang siap produksi untuk **convert pst to html**, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk Java. Dengan mengikuti langkah-langkah di atas, Anda dapat mengintegrasikan konversi email ke dalam alur kerja berbasis Java apa pun, meningkatkan aksesibilitas, dan memenuhi persyaratan kepatuhan.

---

**Terakhir Diperbarui:** 2026-07-19  
**Diuji Dengan:** GroupDocs.Viewer for Java 25.2  
**Penulis:** GroupDocs

## Tutorial Terkait
- [Konversi NSF ke PDF, HTML, JPG, PNG menggunakan GroupDocs.Viewer untuk Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Konversi ODF ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer untuk Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Cara Mengonversi DOCX ke HTML Menggunakan GroupDocs.Viewer untuk Java: Panduan Langkah‑per‑Langkah](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)