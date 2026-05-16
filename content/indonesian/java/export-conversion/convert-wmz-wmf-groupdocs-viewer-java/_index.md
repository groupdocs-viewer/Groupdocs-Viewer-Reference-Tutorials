---
date: '2026-02-18'
description: Pelajari cara mengonversi file WMZ dan WMF ke PDF, HTML, JPG, dan PNG
  menggunakan GroupDocs Viewer untuk Java. Panduan ini mencakup GroupDocs Viewer Java
  dan konversi grafik vektor dengan Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Cara Mengonversi WMZ ke PDF dan Format Lain Menggunakan GroupDocs Viewer untuk
  Java
type: docs
url: /id/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Cara Mengonversi WMZ ke PDF dan Format Lain Menggunakan GroupDocs Viewer untuk Java

Mengonversi file WMZ (Web Metafile) dan WMF (Windows Metafile) ke format yang lebih mudah diakses—terutama **convert WMZ to PDF**—bisa jadi rumit karena format grafik vektor ini menyimpan instruksi gambar bukan data piksel. Dengan **GroupDocs Viewer for Java**, Anda dapat merender dokumen WMZ/WMF ke HTML, JPG, PNG, **PDF**, dan format populer lainnya hanya dalam beberapa baris kode.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

Dalam tutorial ini Anda akan belajar cara menyiapkan pustaka, merender file WMZ/WMF ke output yang diinginkan, dan menangani jebakan umum. Pada akhir tutorial, Anda akan dapat mengintegrasikan **groupdocs viewer java** ke dalam aplikasi Java Anda untuk **java convert vector graphics** dengan cepat dan andal.

## Jawaban Cepat
- **Format apa yang dapat dikonversi dari WMZ/WMF?** HTML, JPG, PNG, dan PDF didukung sepenuhnya.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial menghapus batas evaluasi.  
- **Versi Java apa yang diperlukan?** Java 8 atau yang lebih baru disarankan.  
- **Bisakah saya merender hanya halaman tertentu?** Ya, Anda dapat menentukan rentang halaman dalam opsi tampilan.  
- **Apakah penggunaan memori menjadi masalah untuk file besar?** Gunakan try‑with‑resources dan render hanya halaman yang diperlukan untuk menjaga memori tetap rendah.

## Apa itu “convert WMZ to PDF”?

Mengonversi WMZ ke PDF berarti mengambil file WMZ berbasis vektor dan merasternya (atau mempertahankan data vektornya) di dalam wadah PDF. PDF dapat dilihat, dicari, dan dicetak secara universal, menjadikannya ideal untuk mengarsipkan dan berbagi grafik WMZ.

## Mengapa menggunakan GroupDocs Viewer untuk Java untuk mengonversi grafik vektor?

- **High fidelity**: Perpustakaan mempertahankan kualitas gambar asli, baik Anda mengekspor ke PDF atau PNG.  
- **Zero external dependencies**: Tidak memerlukan pustaka Windows native; semuanya berjalan di platform apa pun dengan JDK.  
- **Simple API**: Satu instance `Viewer` dan satu panggilan `view` menangani seluruh konversi.  
- **Scalable**: Berfungsi sama baiknya untuk ikon satu halaman dan gambar teknis multi‑halaman.

## Prasyarat

### Perpustakaan yang Diperlukan
- **GroupDocs.Viewer for Java** – mesin rendering inti.  
- Java Development Kit (JDK) 8+.

### Penyiapan Lingkungan
- IDE seperti IntelliJ IDEA atau Eclipse.  
- Maven untuk manajemen dependensi (atau Gradle jika Anda lebih suka).

### Prasyarat Pengetahuan
- Familiaritas dengan Java file I/O (`java.nio.file.Path`).  
- Pemahaman dasar tentang cara viewer dokumen merender konten.

## Menyiapkan GroupDocs.Viewer untuk Java

Add the repository and dependency to your `pom.xml`:

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

> **License tip:** Gunakan percobaan gratis untuk evaluasi, lalu terapkan lisensi sementara atau yang dibeli untuk membuka semua fungsi.

Setelah dependensi teratasi, Anda dapat membuat instance `Viewer` yang akan digunakan kembali untuk setiap langkah konversi.

## Panduan Implementasi

Kami akan membahas empat skenario konversi: HTML, JPG, PNG, dan PDF. Setiap contoh mengikuti pola yang sama—menentukan jalur output, menginstansiasi `Viewer` dengan file WMZ sumber, mengonfigurasi opsi tampilan yang sesuai, dan memanggil `view`.

### Merender WMZ/WMF ke HTML

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

### Merender WMZ/WMF ke JPG

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

### Merender WMZ/WMF ke PNG

#### Ikhtisar
PNG mendukung transparansi, menjadikannya ideal untuk grafik yang perlu menyatu dengan latar belakang yang berbeda.

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

### Merender WMZ/WMF ke PDF

#### Ikhtisar
PDF menyediakan dokumen yang platform‑independen, dapat dicari, dan mempertahankan tata letak asli.

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

| Masalah | Penyebab | Solusi |
|-------|-------|----------|
| **OutOfMemoryError** pada file WMZ besar | Viewer memuat seluruh dokumen ke memori | Render satu halaman pada satu waktu menggunakan `PageStreamViewOptions` atau tingkatkan heap JVM (`-Xmx`). |
| **Missing fonts** di PDF | Font tidak tersemat dalam WMZ sumber | Instal font yang diperlukan pada mesin host atau gunakan `FontSettings` untuk menyediakan font khusus. |
| **Blank PNG output** | Jalur output tidak benar atau izin menulis tidak cukup | Verifikasi `outputDirectory` ada dan aplikasi memiliki akses menulis. |
| **HTML resources not loading** | Menggunakan `forExternalResources` tanpa menyalin file | Gunakan `forEmbeddedResources` untuk file HTML yang berdiri sendiri. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengonversi WMF ke PNG menggunakan kode yang sama?**  
A: Ya. Contoh PNG berfungsi untuk file WMZ dan WMF; cukup ganti `TestFiles.SAMPLE_WMZ` dengan sumber WMF Anda.

**Q: Apakah memungkinkan mengonversi hanya sebagian halaman?**  
A: Tentu saja. Gunakan `PdfViewOptions` (atau opsi yang sesuai untuk format lain) dan panggil `setPageNumbers(List<Integer>)` sebelum merender.

**Q: Apakah saya memerlukan lisensi terpisah untuk setiap format output?**  
A: Tidak. Satu lisensi GroupDocs Viewer mencakup semua format yang didukung, termasuk HTML, JPG, PNG, dan PDF.

**Q: Bagaimana “java convert vector graphics” memengaruhi kinerja?**  
A: Konversi vektor‑ke‑raster intensif CPU. Untuk batch besar, pertimbangkan multi‑threading dan menggunakan kembali satu instance `Viewer` untuk banyak file.

**Q: Apakah PDF akan mempertahankan kualitas vektor, atau rasterisasi?**  
A: Saat mengonversi WMZ/WMF ke PDF, GroupDocs Viewer mempertahankan instruksi vektor bila memungkinkan, menghasilkan PDF yang dapat diskalakan.

## Kesimpulan

Anda kini memiliki panduan lengkap yang siap produksi untuk **convert WMZ to PDF** dan format umum lainnya menggunakan **GroupDocs Viewer untuk Java**. Baik Anda membangun layanan web yang menyajikan grafik secara langsung atau alat arsip yang menyimpan dokumen sebagai PDF, langkah-langkah di atas akan membantu Anda mencapainya dengan cepat.

---

**Terakhir Diperbarui:** 2026-02-18  
**Diuji Dengan:** GroupDocs.Viewer 25.2 for Java  
**Penulis:** GroupDocs