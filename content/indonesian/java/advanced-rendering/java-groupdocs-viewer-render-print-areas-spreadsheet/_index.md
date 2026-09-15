---
date: '2026-09-15'
description: Pelajari cara menghasilkan HTML dari Excel di Java menggunakan GroupDocs.Viewer,
  hanya merender area cetak yang telah ditentukan untuk pratinjau yang lebih cepat
  dan efisien dalam penggunaan bandwidth.
keywords:
- generate html from excel
- display excel print area
- render excel print area
lastmod: '2026-09-15'
og_description: Pelajari cara menghasilkan HTML dari Excel di Java menggunakan GroupDocs.Viewer,
  hanya merender area cetak yang telah ditentukan untuk pratinjau yang lebih cepat
  dan efisien dalam penggunaan bandwidth.
og_image_alt: 'GroupDocs.Viewer preview: generate HTML from Excel with print‑area
  rendering'
og_title: Cara menghasilkan HTML dari Excel di Java dengan GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to generate HTML from Excel in Java using GroupDocs.Viewer,
    rendering only defined print areas for faster, bandwidth‑efficient previews.
  headline: How to generate HTML from Excel in Java with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to generate HTML from Excel in Java using GroupDocs.Viewer,
    rendering only defined print areas for faster, bandwidth‑efficient previews.
  name: How to generate HTML from Excel in Java with GroupDocs.Viewer
  steps:
  - name: Define output directory and file path format
    text: First, tell the viewer where to write the generated HTML pages. *Explanation:*
      `outputDirectory` is the folder that will hold all preview files. `pageFilePathFormat`
      uses a placeholder (`{0}`) that the viewer replaces with the page number.
  - name: Configure HTML view options for print‑area rendering
    text: '`HtmlViewOptions` controls how the HTML is generated. `forEmbeddedResources`
      creates a single HTML file per page that contains all CSS/JS inline, simplifying
      deployment. `forRenderingPrintArea()` tells the engine to **render the Excel
      print area** only. *Explanation:* `HtmlViewOptions.forEmbeddedRes'
  - name: Load the spreadsheet and render it
    text: Finally, point the viewer at your workbook and invoke the rendering process.
      *Explanation:* The `view()` method processes the workbook according to the options
      we set, outputting HTML files that display only the print‑area sections.
  type: HowTo
- questions:
  - answer: It reduces clutter and speeds up rendering, delivering a focused preview
      that highlights the most important data.
    question: What is the primary benefit of rendering only the Excel print area?
  - answer: Yes—omit `SpreadsheetOptions.forRenderingPrintArea()` and use the default
      options to render the entire workbook.
    question: Can I render non‑printable worksheets as well?
  - answer: It handles XLS, XLSX, CSV, ODS, and several other formats. Check the official
      docs for the full list.
    question: Does GroupDocs.Viewer support other spreadsheet formats?
  - answer: Increase JVM heap size, render only needed pages, and consider multi‑threaded
      processing.
    question: How can I improve rendering speed for very large files?
  - answer: Ensure the print area is defined in the source file (Excel → Page Layout
      → Print Area) and that you are using the latest GroupDocs.Viewer version.
    question: My print areas are not showing up—what should I check?
  type: FAQPage
tags:
- convert xlsx
- GroupDocs.Viewer
- Java document preview
title: Cara menghasilkan HTML dari Excel di Java dengan GroupDocs.Viewer
type: docs
url: /id/java/advanced-rendering/java-groupdocs-viewer-render-print-areas-spreadsheet/
weight: 1
---

# Cara menghasilkan HTML dari Excel di Java dengan GroupDocs.Viewer

Jika Anda perlu **menghasilkan HTML dari Excel** dengan cepat sambil menampilkan hanya bagian workbook yang penting, merender bagian area cetak yang telah ditentukan adalah cara yang tepat. Tutorial ini memandu Anda membangun solusi pratinjau Java yang mengekstrak hanya area cetak dari file Excel dan menghasilkan halaman HTML bersih serta mandiri menggunakan **GroupDocs.Viewer for Java**. Anda akan melihat mengapa pendekatan ini mempercepat pemuatan, mengurangi bandwidth, dan menjaga UI tetap rapi—sempurna untuk portal, dasbor, dan penampil dokumen berbasis web mana pun.

![Rendering Area Cetak Spreadsheet dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/spreadsheet-print-areas-rendering-java.png)

## Jawaban Cepat
- **Apa arti “generate HTML from Excel”?** Itu berarti secara program mengubah workbook Excel menjadi halaman HTML siap web yang dapat ditampilkan browser tanpa Excel.  
- **Mengapa hanya merender area cetak Excel?** Ini mengisolasi data yang paling relevan, mengurangi waktu render dan bandwidth.  
- **Apakah saya memerlukan lisensi untuk mencoba ini?** Tersedia trial gratis atau lisensi sementara; lisensi penuh diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 atau lebih baru (Java 11 direkomendasikan).  
- **Bisakah saya menyematkan preview di halaman web?** Ya—gunakan opsi embedded‑resources untuk menghasilkan halaman HTML yang mandiri.

## Apa itu “generate HTML from Excel”?
**Generate HTML from Excel** berarti mengonversi tata letak visual dari workbook XLSX menjadi markup HTML standar yang dirender secara native oleh browser. Teknik ini memungkinkan Anda melihat pratinjau data spreadsheet secara instan dalam aplikasi web tanpa memerlukan Microsoft Office di sisi klien.

## Mengapa hanya merender area cetak Excel?
Merender hanya area cetak menghasilkan payload HTML yang lebih kecil, yang dapat memuat hingga 60 % lebih cepat untuk laporan tipikal. Ini juga menyembunyikan worksheet internal yang mungkin berisi formula sensitif, meningkatkan keamanan. Dengan fokus pada area cetak yang ditentukan pengguna, Anda memberikan tampilan yang lebih bersih dan lebih bermakna yang selaras dengan maksud penulis.

## Prasyarat
- **GroupDocs.Viewer for Java** v25.2 atau lebih baru (mendukung lebih dari 70 format dokumen dan dapat memproses spreadsheet hingga 10.000 baris tanpa memuat seluruh file ke memori).  
- Maven terpasang di mesin pengembangan Anda.  
- JDK 8 atau lebih baru (Java 11 direkomendasikan).  
- IDE (IntelliJ IDEA, Eclipse, atau VS Code).  

## Menyiapkan GroupDocs.Viewer untuk Java
Tambahkan repositori GroupDocs dan dependensi ke `pom.xml` Anda:

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
Mulailah dengan **trial gratis** atau minta **lisensi sementara** untuk evaluasi. Saat Anda siap untuk produksi, beli lisensi penuh untuk membuka semua fitur dan menghapus batasan trial.

### Inisialisasi Dasar
`Viewer` adalah kelas inti yang memuat dokumen dan mengendalikan pipeline rendering. Di bawah ini adalah kode minimal yang diperlukan untuk membuka spreadsheet dengan GroupDocs.Viewer:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer object with the path to your spreadsheet
try (Viewer viewer = new Viewer("path/to/your/spreadsheet.xlsx")) {
    // Further configurations will be discussed in upcoming sections.
}
```

## Cara mengonversi XLSX ke HTML dengan GroupDocs.Viewer
Bagian ini menunjukkan cara menggunakan GroupDocs.Viewer untuk mengubah workbook XLSX menjadi file HTML mandiri yang menampilkan hanya bagian area cetak yang ditentukan. Dengan mengonfigurasi opsi tampilan dan memanggil viewer, Anda dapat menghasilkan pratinjau ringan yang cocok untuk disematkan di halaman web atau portal.

Berikut adalah panduan langkah demi langkah yang **hanya merender area cetak Excel**, menghasilkan file HTML mandiri.

### Langkah 1: Tentukan direktori output dan format jalur file
Pertama, beri tahu viewer ke mana menulis halaman HTML yang dihasilkan.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Set the output directory path
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");

// Define a file path format for the rendered pages
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Penjelasan:* `outputDirectory` adalah folder yang akan menyimpan semua file pratinjau. `pageFilePathFormat` menggunakan placeholder (`{0}`) yang digantikan viewer dengan nomor halaman.

### Langkah 2: Konfigurasikan opsi tampilan HTML untuk rendering area cetak
`HtmlViewOptions` mengontrol cara HTML dihasilkan. `forEmbeddedResources` membuat satu file HTML per halaman yang berisi semua CSS/JS secara inline, menyederhanakan deployment. `forRenderingPrintArea()` memberi tahu engine untuk **hanya merender area cetak Excel**.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
import com.groupdocs.viewer.options.SpreadsheetOptions;

// Configure HTML view options with embedded resources and print area rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forRenderingPrintArea());
```

*Penjelasan:* `HtmlViewOptions.forEmbeddedResources` membuat satu file HTML per halaman yang berisi semua CSS/JS secara inline, menyederhanakan deployment. `forRenderingPrintArea()` memberi tahu engine untuk **hanya merender area cetak Excel**.

### Langkah 3: Muat spreadsheet dan render
Akhirnya, arahkan viewer ke workbook Anda dan panggil proses rendering.

```java
// Replace with your actual document path
Path documentPath = Paths.get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_PRINT_AREAS.xlsx");

try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Render to HTML using the configured view options
    viewer.view(viewOptions);
}
```

*Penjelasan:* Metode `view()` memproses workbook sesuai dengan opsi yang kami tetapkan, menghasilkan file HTML yang menampilkan hanya bagian area cetak.

## Masalah umum dan solusi
- **Kesalahan jalur file:** Periksa kembali bahwa jalur bersifat absolut atau relatif dengan benar terhadap direktori kerja proyek Anda.  
- **Masalah izin:** Pastikan proses Java memiliki akses baca ke file sumber dan akses tulis ke folder output.  
- **Area cetak tidak ada:** Pastikan spreadsheet memang mendefinisikan area cetak (Page Layout → Print Area di Excel).  

## Aplikasi praktis
1. **Sistem manajemen dokumen:** Tampilkan pratinjau bersih laporan kepada pengguna akhir tanpa memuat seluruh workbook.  
2. **Dashboard keuangan:** Secara otomatis menghasilkan snapshot HTML dari tabel keuangan utama yang ditandai sebagai area cetak.  
3. **Platform pembelajaran:** Berikan siswa tampilan terfokus data tugas.  
4. **Portal CRM:** Sorot metrik pelanggan sambil menyembunyikan worksheet internal.  
5. **Notebook data‑science:** Sematkan pratinjau spreadsheet ringkas dalam dokumentasi.  

## Tips kinerja
- **Penyesuaian memori:** Untuk workbook sangat besar, tingkatkan heap JVM (`-Xmx2g` atau lebih tinggi).  
- **Pemuatan malas:** Jika hanya membutuhkan beberapa halaman pertama, hentikan rendering setelah jumlah halaman yang diperlukan.  
- **Pemrosesan paralel:** Render beberapa workbook secara bersamaan menggunakan instance `Viewer` terpisah (masing‑masing dalam threadnya).  

## Cara menampilkan pratinjau spreadsheet tanpa area cetak
`SpreadsheetOptions` mengonfigurasi perilaku rendering spreadsheet, termasuk apakah membatasi output ke area cetak yang ditentukan. Jika kemudian Anda memutuskan menampilkan seluruh workbook, cukup hapus pemanggilan `SpreadsheetOptions.forRenderingPrintArea()` dan gunakan `SpreadsheetOptions` default. Ini akan merender setiap worksheet dan sel, memberikan pratinjau **convert XLSX to HTML** yang lengkap yang mencakup semua data, formula, dan format yang ada di file asli.

## Kesimpulan
Anda kini telah mempelajari cara **menghasilkan HTML dari Excel** di Java sambil merender hanya area cetak yang ditentukan dari sebuah spreadsheet. Teknik ini membuat pratinjau lebih cepat, lebih bersih, dan lebih aman—sempurna untuk aplikasi web modern dan perusahaan.

### Langkah selanjutnya
- Bereksperimen dengan format tampilan lain (PDF, PNG) menggunakan `PdfViewOptions` atau `PngViewOptions`.  
- Gabungkan pembuatan pratinjau dengan otentikasi untuk melindungi data sensitif.  
- Jelajahi API `SpreadsheetOptions` lengkap untuk penyesuaian ukuran halaman, garis kisi, dan lainnya.  

## Pertanyaan yang sering diajukan

**Q: Apa manfaat utama merender hanya area cetak Excel?**  
A: Ini mengurangi kekacauan dan mempercepat rendering, memberikan pratinjau terfokus yang menyoroti data terpenting.

**Q: Bisakah saya merender worksheet yang tidak dapat dicetak juga?**  
A: Ya—hilangkan `SpreadsheetOptions.forRenderingPrintArea()` dan gunakan opsi default untuk merender seluruh workbook.

**Q: Apakah GroupDocs.Viewer mendukung format spreadsheet lain?**  
A: Ia menangani XLS, XLSX, CSV, ODS, dan beberapa format lainnya. Periksa dokumentasi resmi untuk daftar lengkapnya.

**Q: Bagaimana saya dapat meningkatkan kecepatan rendering untuk file sangat besar?**  
A: Tingkatkan ukuran heap JVM, render hanya halaman yang diperlukan, dan pertimbangkan pemrosesan multi‑thread.

**Q: Area cetak saya tidak muncul—apa yang harus saya periksa?**  
A: Pastikan area cetak didefinisikan dalam file sumber (Excel → Page Layout → Print Area) dan Anda menggunakan versi GroupDocs.Viewer terbaru.

## Sumber daya
- **Dokumentasi:** [Dokumentasi GroupDocs.Viewer Java](https://docs.groupdocs.com/viewer/java/)  
- **Referensi API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Unduh:** [Unduh GroupDocs.Viewer untuk Java](https://releases.groupdocs.com/viewer/java/)  
- **Pembelian:** [Beli Lisensi](https://purchase.groupdocs.com/buy)  
- **Trial gratis:** [Mulai dengan Trial Gratis](https://releases.groupdocs.com/viewer/java/)  
- **Lisensi sementara:** [Minta Di Sini](https://purchase.groupdocs.com/temporary-license/)  
- **Dukungan:** [Forum GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-09-15  
**Diuji Dengan:** GroupDocs.Viewer for Java 25.2  
**Penulis:** GroupDocs

## Tutorial Terkait

- [Cara Mengonversi Excel ke HTML, JPG, PNG, dan PDF Menggunakan GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [excel to html java: Lewati Rendering Baris Kosong dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Cara Mengonversi Excel ke HTML dan Merender Baris & Kolom Tersembunyi di Java dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)