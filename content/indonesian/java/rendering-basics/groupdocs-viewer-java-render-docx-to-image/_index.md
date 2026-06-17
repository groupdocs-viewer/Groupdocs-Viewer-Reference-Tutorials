---
date: '2026-06-05'
description: Pelajari cara mengonversi docx ke jpeg menggunakan GroupDocs Viewer for
  Java, mencakup pengaturan, konfigurasi, dan rendering gambar secara praktis.
keywords:
- convert docx to jpeg
- convert word to image
- GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  headline: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  name: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  steps:
  - name: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
    text: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
  - name: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
    text: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
  - name: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
    text: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
  type: HowTo
- questions:
  - answer: '`DocumentSplitter` allows you to divide a large document into separate
      parts for easier processing. Split the source file into smaller sections using
      `DocumentSplitter` before rendering, or process pages in sequential batches
      to keep memory usage low.'
    question: How do I handle documents larger than 500 pages?
  - answer: Yes, replace `JpgViewOptions` with `PngViewOptions` and adjust the file‑path
      pattern accordingly.
    question: Can I output PNG instead of JPEG?
  - answer: A free trial license works for evaluation and development, but a commercial
      license is required for production deployments.
    question: Is a license mandatory for development builds?
  - answer: Absolutely. Pass the password to the `Viewer` constructor to unlock the
      document before rendering.
    question: Does the library support password‑protected DOCX files?
  - answer: GroupDocs.Viewer for Java is compatible with Java 8, 11, and 17.
    question: What Java versions are supported?
  type: FAQPage
title: Cara Mengonversi DOCX ke JPEG dengan GroupDocs Viewer for Java
type: docs
url: /id/java/rendering-basics/groupdocs-viewer-java-render-docx-to-image/
weight: 1
---

# Mengonversi DOCX ke JPEG dengan GroupDocs Viewer untuk Java

Mengonversi **DOCX ke JPEG** memungkinkan Anda membagikan halaman dokumen sebagai gambar ringan yang ditampilkan secara konsisten di seluruh browser dan klien email. Dalam panduan ini Anda akan melihat cara menggunakan **GroupDocs.Viewer for Java** untuk mengubah file Word menjadi gambar JPEG berkualitas tinggi, menyesuaikan dimensi, dan mengelola sumber daya secara efisien.

![Render DOCX ke Gambar dengan GroupDocs.Viewer untuk Java](/viewer/rendering-basics/render-docx-to-image.png)

[Render DOCX ke Gambar dengan GroupDocs.Viewer untuk Java](/viewer/rendering-basics/render-docx-to-image.png)

## Jawaban Cepat
- **Library apa yang menangani konversi DOCX → JPEG?** GroupDocs.Viewer for Java.  
- **Berapa baris kode yang diperlukan?** Hanya dua baris untuk memuat dan merender file.  
- **Bisakah saya mengatur ukuran gambar khusus?** Ya, melalui `JpgViewOptions` Anda dapat menentukan lebar dan tinggi.  
- **Apakah lisensi diperlukan untuk produksi?** Lisensi komersial diperlukan; percobaan gratis tersedia.  
- **Apakah ini bekerja dengan dokumen besar?** Ya, ia memproses file hingga 500 halaman sambil menjaga penggunaan memori di bawah 200 MB.

## Apa itu “convert docx to jpeg”?
Mengonversi file DOCX ke JPEG membuat satu gambar per halaman, mempertahankan tata letak, font, dan grafik asli. Setiap JPEG dapat ditampilkan di browser, disematkan dalam email, atau digunakan sebagai thumbnail. Format ini ringan, didukung secara luas, dan ideal untuk pratinjau dokumen tanpa memerlukan Microsoft Word atau plugin tambahan.

## Mengapa menggunakan GroupDocs Viewer untuk Java untuk konversi ini?
GroupDocs.Viewer mendukung **lebih dari 50 format input dan output** dan dapat merender dokumen hingga **500 halaman** dalam waktu kurang dari **2 detik per halaman** pada perangkat keras server standar. API berfungsi tanpa Microsoft Office terpasang, menjamin konsistensi pelestarian tata letak dan jejak memori yang rendah.

## Prasyarat
- **Java Development Kit** 8 atau lebih baru.  
- **Maven** untuk manajemen dependensi (atau penyertaan JAR manual).  
- **GroupDocs.Viewer for Java** library (dapat diunduh dari situs resmi).  
- Familiaritas dasar dengan struktur proyek Java.

## Menyiapkan GroupDocs Viewer untuk Java

Untuk menambahkan library ke proyek Maven, sisipkan dependensi berikut ke dalam `pom.xml` Anda:

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
GroupDocs menawarkan percobaan gratis untuk menjelajahi fitur. Untuk penggunaan yang lebih lama, dapatkan lisensi sementara atau berbayar melalui situs resmi mereka.

## Cara Mengonversi DOCX ke JPEG?

Kelas `Viewer` membaca dokumen dan menyediakan kemampuan rendering.  
`JpgViewOptions` mengonfigurasi pengaturan output JPEG seperti ukuran, kualitas, dan penamaan file.

Untuk mengonversi, buat instance `Viewer` dengan path DOCX, buat `JpgViewOptions` yang menunjuk ke folder output, opsional atur dimensi dan kualitas, lalu panggil `viewer.view(options)`. Library memproses setiap halaman dan menyimpan file JPEG sesuai pola penamaan yang ditentukan.

## Panduan Implementasi

### Merender DOCX ke JPEG

Ubah dokumen Word menjadi gambar JPEG untuk tujuan pratinjau atau berbagi.

#### Implementasi Langkah‑per‑Langkah

**1. Siapkan Direktori Output**  
Tentukan folder tempat JPEG yang dirender akan disimpan:

```java
import com.groupdocs.viewer.Viewer;

public class DocumentRenderer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Configuration and rendering logic goes here
        }
    }
}
```

**2. Tentukan Format Jalur File**  
Buat pola penamaan yang mencakup nomor halaman, misalnya `page_{0}.jpg`:

```java
import java.nio.file.Path;

// Define output directory using Path API
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("rendered_document");
```

**3. Konfigurasikan Opsi Gambar**  
`JpgViewOptions` memungkinkan Anda mengatur lebar, tinggi, dan kualitas. Misalnya, 1024 × 768 piksel dengan kualitas 90 %:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**4. Render Dokumen**  
Gunakan blok try‑with‑resources untuk memastikan instance `Viewer` ditutup secara otomatis, yang membebaskan sumber daya native dan mencegah kebocoran memori:

```java
import com.groupdocs.viewer.options.JpgViewOptions;

// Create JpgViewOptions with specified path format
JpgViewOptions viewOptions = new JpgViewOptions(pageFilePathFormat);

// Set custom width and height for each image
viewOptions.setWidth(600);  // Image width in pixels
viewOptions.setHeight(800); // Image height in pixels
```

### Masalah Umum dan Solusinya
- **Masalah Jalur File** – Pastikan direktori output ada dan aplikasi memiliki izin menulis.  
- **Manajemen Memori** – Untuk dokumen lebih dari 300 halaman, pertimbangkan memproses halaman secara batch dan memanggil `System.gc()` setelah setiap batch.  
- **Elemen Tidak Didukung** – Beberapa fitur Word lanjutan (mis., makro tersemat) diabaikan selama rendering; mereka tidak memengaruhi output visual.

## Aplikasi Praktis

1. **Pembuatan Pratinjau** – Tampilkan thumbnail dokumen dalam sistem manajemen konten tanpa memerlukan penampil layar penuh.  
2. **Lampiran Email** – Sematkan JPEG per halaman dalam email untuk menghindari batas ukuran lampiran.  
3. **Tampilan Web** – Render halaman sebagai gambar untuk pemuatan cepat pada koneksi berbandwidth rendah.

## Pertimbangan Kinerja

- **Manajemen Sumber Daya** – Selalu gunakan try‑with‑resources untuk menutup `Viewer`.  
- **Dimensi Gambar** – Dimensi lebih kecil mengurangi penggunaan RAM; pilih ukuran terkecil yang memenuhi persyaratan kualitas visual.  
- **Pemrosesan Asinkron** – Untuk konversi massal, jalankan tugas rendering pada pool thread terpisah untuk menjaga UI tetap responsif.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana saya menangani dokumen lebih dari 500 halaman?**  
A: `DocumentSplitter` memungkinkan Anda membagi dokumen besar menjadi bagian terpisah untuk pemrosesan yang lebih mudah. Bagi file sumber menjadi bagian yang lebih kecil menggunakan `DocumentSplitter` sebelum rendering, atau proses halaman dalam batch berurutan untuk menjaga penggunaan memori tetap rendah.

**Q: Bisakah saya menghasilkan PNG alih-alih JPEG?**  
A: Ya, ganti `JpgViewOptions` dengan `PngViewOptions` dan sesuaikan pola jalur file sesuai.

**Q: Apakah lisensi wajib untuk build pengembangan?**  
A: Lisensi percobaan gratis berfungsi untuk evaluasi dan pengembangan, tetapi lisensi komersial diperlukan untuk penyebaran produksi.

**Q: Apakah library mendukung file DOCX yang dilindungi kata sandi?**  
A: Tentu saja. Berikan kata sandi ke konstruktor `Viewer` untuk membuka dokumen sebelum rendering.

**Q: Versi Java apa yang didukung?**  
A: GroupDocs.Viewer untuk Java kompatibel dengan Java 8, 11, dan 17.

## Sumber Daya

- **Dokumentasi**: [Dokumentasi GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Referensi API**: [Referensi API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Unduh GroupDocs.Viewer**: [Halaman Unduhan](https://releases.groupdocs.com/viewer/java/)
- **Beli Lisensi**: [Beli GroupDocs](https://purchase.groupdocs.com/buy)
- **Percobaan Gratis**: [Coba GroupDocs Gratis](https://releases.groupdocs.com/viewer/java/)
- **Lisensi Sementara**: [Dapatkan Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)
- **Forum Dukungan**: [Forum Dukungan GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-06-05  
**Diuji Dengan:** GroupDocs.Viewer 23.12 for Java  
**Penulis:** GroupDocs

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

## Tutorial Terkait

- [Cara Mengonversi File DOCX ke PNG Menggunakan GroupDocs.Viewer untuk Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)
- [Cara Mengonversi DOCX ke HTML Menggunakan GroupDocs.Viewer untuk Java: Panduan Langkah‑per‑Langkah](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Render File DOCX dari InputStream di Java menggunakan GroupDocs.Viewer](/viewer/java/rendering-basics/render-docx-from-inputstream-groupdocs-viewer-java/)