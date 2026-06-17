---
date: '2026-06-05'
description: Pelajari cara mengonversi Excel ke HTML, JPG, PNG, dan PDF menggunakan
  GroupDocs.Viewer Java. Panduan step‑by‑step ini mencakup setup, rendering options,
  dan real‑world use cases.
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: Cara Mengonversi Excel ke HTML, JPG, PNG, dan PDF Menggunakan GroupDocs.Viewer
  Java
type: docs
url: /id/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# Cara Mengonversi Excel ke HTML, JPG, PNG, dan PDF Menggunakan GroupDocs.Viewer Java

Mengonversi Excel ke HTML adalah kebutuhan umum ketika Anda perlu menampilkan data spreadsheet di web sambil mempertahankan judul baris dan kolom. Dalam tutorial ini Anda akan mempelajari bagaimana GroupDocs.Viewer untuk Java menyederhanakan **convert excel to html** serta cara merender workbook yang sama ke format JPG, PNG, dan PDF. Kami akan membahas prasyarat, penyiapan pustaka, dan setiap skenario rendering dengan potongan kode yang jelas dan siap produksi.

## Jawaban Cepat
- **Apakah GroupDocs.Viewer dapat merender Excel ke berbagai format?** Ya – HTML, JPG, PNG, dan PDF didukung secara langsung.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi permanen diperlukan untuk produksi.  
- **Apakah judul baris dan kolom akan dipertahankan?** Atur `setRenderHeadings(true)` pada opsi tampilan untuk menyertakannya.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih tinggi; pustaka kompatibel dengan Java 11, 17, dan versi selanjutnya.  
- **Apakah konversi cepat untuk workbook besar?** GroupDocs.Viewer dapat memproses spreadsheet 200‑halaman dalam kurang dari satu detik pada perangkat keras server standar.

## Apa itu “convert excel to html”?
**Convert excel to html** berarti mengubah workbook Excel menjadi dokumen HTML siap web sambil mempertahankan tata letak asli, formula, dan header. Ini memungkinkan penyematan spreadsheet secara mulus ke halaman web atau portal tanpa memerlukan pengguna akhir menginstal Excel.

## Mengapa Menggunakan GroupDocs.Viewer Java untuk Rendering Excel?
GroupDocs.Viewer Java mendukung **lebih dari 50 format input dan output**, termasuk DOCX, XLSX, PPTX, HTML, JPG, PNG, dan PDF. Ia memproses workbook ratusan halaman tanpa memuat seluruh file ke memori, memberikan kecepatan konversi hingga **10 × lebih cepat** dibandingkan banyak alternatif sumber terbuka. Pustaka ini juga menyediakan kontrol terperinci atas opsi rendering seperti visibilitas heading, ukuran halaman, dan kualitas gambar.

## Prasyarat

- **Java Development Kit (JDK) 8+** terpasang dan dikonfigurasi di IDE Anda (IntelliJ IDEA, Eclipse, dll.).
- **Maven** untuk manajemen dependensi.
- Pemahaman dasar tentang sintaks Java dan `pom.xml` Maven.
- Lisensi **GroupDocs.Viewer Java** yang aktif (percobaan atau permanen).

### Perpustakaan dan Dependensi yang Diperlukan
Add the GroupDocs.Viewer Java dependency to your `pom.xml`:

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

### Penyiapan Lingkungan
- Verifikasi `java -version` mengembalikan 1.8 atau lebih baru.
- Buka IDE favorit Anda dan buat proyek Maven.

Mari kita mulai dengan prasyarat yang diperlukan sebelum kita menyelami implementasi.

![convert Excel files into HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## Menyiapkan GroupDocs.Viewer Java

### Informasi Instalasi
Sertakan dependensi Maven yang ditunjukkan di atas dalam `pom.xml` proyek Anda. Setelah menjalankan `mvn clean install`, pustaka akan tersedia di classpath Anda.

### Langkah-langkah Akuisisi Lisensi
1. **Free Trial:** Unduh versi percobaan dari [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License:** Dapatkan lisensi sementara untuk pengujian lanjutan dari [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase:** Dapatkan lisensi penuh untuk penggunaan produksi di [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inisialisasi Dasar
Kelas `Viewer` adalah titik masuk untuk semua operasi rendering. Menginisialisasinya sangat sederhana:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

## Panduan Implementasi

Di bawah ini kami membahas setiap target rendering. Untuk setiap format kami pertama **mengimpor kelas yang diperlukan**, kemudian **menetapkan direktori output**, dan akhirnya **mengonfigurasi opsi tampilan** dengan `setRenderHeadings(true)` untuk mempertahankan header baris/kolom.

### Render Spreadsheet ke HTML
**Bagaimana cara mengonversi workbook Excel ke HTML menggunakan GroupDocs.Viewer Java?**  
Untuk mengonversi workbook Excel ke HTML, muat file dengan Viewer, buat instance HtmlViewOptions, aktifkan rendering heading, dan panggil metode view. Proses ini menulis setiap lembar kerja ke file HTML terpisah, mempertahankan format sel, formula, dan tata letak asli untuk tampilan web yang akurat.

#### Implementasi Langkah‑per‑Langkah
**1. Impor Perpustakaan yang Diperlukan**  
HtmlViewOptions mengonfigurasi cara workbook dirender ke HTML, memungkinkan penyesuaian heading, gaya, dan tata letak halaman.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Tetapkan Direktori Output**  
Tentukan folder tempat halaman HTML yang dihasilkan akan ditulis.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Inisialisasi Viewer dan Konfigurasi Opsi**  
Buat instance `Viewer`, atur `setRenderHeadings(true)`, dan panggil `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Penjelasan:** `HtmlViewOptions` mengontrol output HTML. Mengaktifkan `setRenderHeadings(true)` memastikan bahwa baris dan kolom pertama (biasanya header) muncul dalam HTML yang dihasilkan, sehingga data langsung dapat dipahami.

### Render Spreadsheet ke JPG
**Bagaimana saya dapat merender lembar Excel sebagai gambar JPG dengan header termasuk?**  
Merender lembar Excel sebagai JPG melibatkan inisialisasi Viewer dengan workbook, membuat objek JpgViewOptions, mengatur renderHeadings menjadi true, dan memanggil view. Pustaka ini meraster setiap halaman pada DPI yang ditentukan, menghasilkan file JPG resolusi tinggi yang mempertahankan struktur visual spreadsheet dan header.

#### Implementasi Langkah‑per‑Langkah
**1. Impor Perpustakaan yang Diperlukan**  
JpgViewOptions mendefinisikan pengaturan untuk merender lembar kerja sebagai gambar JPG, termasuk DPI, kualitas, dan visibilitas heading.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Tetapkan Direktori Output**  
Tentukan tempat penyimpanan file JPG.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Inisialisasi Viewer dan Konfigurasi Opsi**  
Buat viewer, atur rendering heading, dan jalankan konversi.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Penjelasan:** `JpgViewOptions` memungkinkan Anda mengontrol DPI dan kualitas. Dengan `setRenderHeadings(true)`, gambar yang dihasilkan mempertahankan baris dan kolom header spreadsheet, yang penting untuk laporan dan presentasi.

### Render Spreadsheet ke PNG
**Apa proses mengonversi Excel ke PNG sambil mempertahankan heading kolom?**  
Untuk menghasilkan gambar PNG dari file Excel, gunakan Viewer untuk membuka workbook, buat instance PngViewOptions, aktifkan rendering heading, dan jalankan view. Output PNG memberikan kualitas lossless, mempertahankan semua gaya sel dan baris header, menjadikannya ideal untuk arsip atau pemrosesan gambar lanjutan.

#### Implementasi Langkah‑per‑Langkah
**1. Impor Perpustakaan yang Diperlukan**  
PngViewOptions mengontrol rendering lembar kerja ke gambar PNG, menawarkan kompresi lossless dan opsi heading.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Tetapkan Direktori Output**  
Pilih folder untuk output PNG.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Inisialisasi Viewer dan Konfigurasi Opsi**  
Buat viewer, aktifkan rendering heading, dan panggil `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Penjelasan:** Dengan memanggil `setRenderHeadings(true)`, file PNG menyertakan baris dan kolom header spreadsheet asli, mempertahankan konteks bagi konsumen selanjutnya.

### Render Spreadsheet ke PDF
**Bagaimana cara mengonversi file Excel ke PDF dengan header baris dan kolom terlihat?**  
Mengonversi Excel ke PDF sangat mudah: buat instance Viewer dengan file sumber, konfigurasikan objek PdfViewOptions untuk merender heading, dan panggil view. PDF yang dihasilkan mencerminkan tata letak workbook, termasuk header baris dan kolom, serta mendukung grafik vektor untuk pencetakan dan distribusi yang tajam.

#### Implementasi Langkah‑per‑Langkah
**1. Impor Perpustakaan yang Diperlukan**  
PdfViewOptions menentukan parameter pembuatan PDF seperti ukuran halaman, margin, dan rendering heading.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Tetapkan Direktori Output**  
Tentukan folder tujuan untuk dokumen PDF.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Inisialisasi Viewer dan Konfigurasi Opsi**  
Buat `Viewer`, aktifkan rendering heading, dan jalankan konversi.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Penjelasan:** Mengatur `setRenderHeadings(true)` pada `PdfViewOptions` menjamin bahwa baris/kolom pertama muncul di PDF akhir, sehingga dokumen siap untuk pencetakan atau arsip.

## Aplikasi Praktis
Skenario dunia nyata di mana **convert excel to html**, **excel to pdf java**, atau **convert spreadsheet to image** sangat berharga:

1. **Laporan Bisnis:** Hasilkan dasbor HTML atau laporan PDF dari model keuangan tanpa menyalin‑tempel manual.  
2. **Visualisasi Data:** Sematkan snapshot JPG/PNG spreadsheet dalam presentasi slide, memastikan header memberikan konteks langsung kepada penonton.  
3. **Arsip Dokumen:** Simpan workbook Excel sebagai PDF untuk kepatuhan, sambil mempertahankan tata letak dan header asli.  
4. **Portal Web:** Sajikan versi HTML spreadsheet langsung di browser, memungkinkan penyaringan interaktif dengan JavaScript.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengonversi file Excel yang dilindungi kata sandi?**  
A: Ya. Berikan kata sandi ke konstruktor `Viewer`, dan pustaka akan mendekripsi workbook sebelum merender.

**Q: Apakah GroupDocs.Viewer mendukung workbook yang mengaktifkan macro (.xlsm)?**  
A: Tentu saja. Viewer memperlakukan macro sebagai data; mereka diabaikan selama rendering, memastikan konversi yang aman.

**Q: Berapa ukuran file maksimum yang didukung?**  
A: Pustaka dapat memproses file hingga **2 GB** tanpa memuat seluruh dokumen ke memori, berkat arsitektur streamingnya.

**Q: Apakah memungkinkan merender hanya worksheet tertentu?**  
A: Ya. Gunakan `ViewOptions.setPageNumber(pageIndex)` untuk menargetkan satu sheet saat menghasilkan HTML, JPG, PNG, atau PDF.

**Q: Bagaimana cara mengontrol kualitas gambar untuk output JPG?**  
A: Atur `JpgViewOptions.setQuality(90)` (nilai 0‑100) untuk menyeimbangkan ukuran file dan kesetiaan visual.

## Kesimpulan
Anda kini memiliki panduan lengkap dan siap produksi untuk **convert excel to html**, **excel to pdf java**, dan **convert spreadsheet to image** menggunakan GroupDocs.Viewer Java. Dengan mengikuti langkah-langkah di atas, Anda dapat mengintegrasikan rendering spreadsheet ke dalam backend Java apa pun, menyajikan laporan HTML, gambar resolusi tinggi, atau PDF arsip dengan header yang secara otomatis dipertahankan.

---

**Terakhir Diperbarui:** 2026-06-05  
**Diuji Dengan:** GroupDocs.Viewer Java 23.12  
**Penulis:** GroupDocs

## Tutorial Terkait

- [Cara Mengonversi DOCX ke HTML Menggunakan GroupDocs.Viewer untuk Java: Panduan Langkah‑per‑Langkah](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Rendering HTML Responsif dengan GroupDocs.Viewer untuk Java: Panduan Komprehensif](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – Mengonversi ODF ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer untuk Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)