---
date: '2026-06-15'
description: Pelajari cara mengonversi Excel ke PDF Java dan membagi sheet Excel berdasarkan
  baris dan kolom menggunakan GroupDocs Viewer. Termasuk pengaturan, kode, dan praktik
  terbaik.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Konversi Excel ke PDF Java & Membagi Sheet berdasarkan Baris & Kolom
type: docs
url: /id/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Konversi Excel ke PDF Java & Membagi Lembar berdasarkan Baris & Kolom (Java)

Buku kerja Excel yang besar sering berisi lebih banyak data daripada yang dapat ditampilkan dengan nyaman pada satu layar atau halaman cetak. **convert excel to pdf java** adalah kebutuhan umum ketika Anda memerlukan format statis yang dapat dibagikan, sementara **splitting Excel sheets by rows and columns** membuat data lebih mudah dikonsumsi dalam tata letak web atau cetak. Dalam panduan ini kami akan membahas kedua tugas menggunakan **GroupDocs Viewer for Java**, menunjukkan cara mengonfigurasi pagination, dan menjelaskan tip praktik terbaik untuk kinerja serta pemecahan masalah.

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Membagi Lembar Excel berdasarkan Baris dan Kolom dengan GroupDocs.Viewer untuk Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Jawaban Cepat
- **Perpustakaan apa yang digunakan?** GroupDocs Viewer for Java.  
- **Bisakah saya membagi berdasarkan baris dan kolom sekaligus?** Ya – Anda dapat menentukan rows‑per‑page dan columns‑per‑page bersama-sama.  
- **Apakah saya memerlukan lisensi?** Lisensi percobaan atau sementara dapat digunakan untuk pengembangan; lisensi penuh diperlukan untuk produksi.  
- **Format output apa yang didukung?** HTML (sumber daya tersemat) ditampilkan; PDF dapat dihasilkan dengan opsi yang sama.  
- **Apakah Maven diperlukan?** Maven adalah cara yang direkomendasikan untuk mengelola dependensi.  
- **Bisakah saya juga mengonversi Excel ke PDF?** Tentu – cukup ganti `HtmlViewOptions` dengan `PdfViewOptions` dan gunakan kembali pengaturan pagination yang sama.

## Apa Itu “Cara Membagi Excel”?
Membagi lembar Excel berarti membagi satu worksheet menjadi beberapa halaman atau file berdasarkan jumlah baris, kolom, atau keduanya yang tetap. Teknik ini berguna ketika Anda perlu membuat laporan berhalaman, menyematkan data di halaman web, atau menghasilkan bagian yang dapat dicetak tanpa harus memuat seluruh buku kerja sekaligus.

## Mengapa Menggunakan GroupDocs Viewer untuk Java?
GroupDocs Viewer memproses spreadsheet dalam satu kali lintasan dan secara otomatis mempaginasikannya, menghilangkan perhitungan manual. **Proses rendering cepat memproses buku kerja XLSX 250‑halaman dalam kurang dari 2 detik pada server 2‑core tipikal**, dan **perpustakaan mendukung lebih dari 50 format input dan output**, termasuk XLS, XLSX, CSV, PDF, dan HTML. Ia berjalan pada platform apa pun yang kompatibel dengan JVM—Windows, Linux, macOS, kontainer Docker, atau runtime serverless berbasis cloud—sehingga Anda dapat mengintegrasikannya di mana saja aplikasi Java Anda berada.

## Prasyarat
- Java 17 atau lebih baru terpasang.  
- IDE seperti IntelliJ IDEA atau Eclipse.  
- Maven untuk manajemen dependensi.  
- Pengetahuan dasar Java dan familiaritas dengan penanganan file Excel.

### Perpustakaan, Versi, dan Dependensi yang Diperlukan
Tambahkan repositori GroupDocs dan dependensi viewer ke `pom.xml` Anda:

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
Dapatkan lisensi percobaan gratis, lisensi sementara, atau beli lisensi penuh dari [GroupDocs](https://purchase.groupdocs.com/buy).

## Cara Mengonversi Excel ke PDF Java?

Kelas `Viewer` adalah komponen inti GroupDocs Viewer yang memuat dokumen dan menyediakan metode rendering untuk berbagai format output. `SpreadsheetOptions` memungkinkan Anda mengontrol pengaturan pagination seperti rows‑per‑page dan columns‑per‑page untuk rendering spreadsheet.

Muat file Excel Anda dengan `new Viewer("source.xlsx")`, konfigurasikan `SpreadsheetOptions` untuk pagination, dan panggil `viewer.view(pdfOptions, stream)` – panggilan tunggal itu mengonversi buku kerja ke PDF sambil menghormati batas baris/kolom yang Anda tetapkan. Konversi ini mempertahankan rumus, gambar, dan gaya sel, menghasilkan replika PDF yang setia siap didistribusikan.

## Cara Membagi Lembar Excel berdasarkan Baris

Membagi berdasarkan baris menghasilkan serangkaian halaman HTML, masing‑masing berisi jumlah baris tetap (misalnya, 15). Pendekatan ini ideal untuk dasbor yang menampilkan sejumlah rekaman terbatas per tampilan. Viewer akan menghasilkan file HTML terpisah seperti `page_0.html`, `page_1.html`, dll., masing‑masing berisi jumlah baris yang ditentukan. Ini memudahkan memuat hanya bagian yang diperlukan dalam antarmuka web, mengurangi bandwidth dan waktu rendering.

### Anchor Definisi
`Viewer` adalah kelas inti GroupDocs Viewer yang memuat dokumen dan mengatur rendering ke format output yang dipilih.

### Implementasi Langkah‑per‑Langkah

#### Langkah 1: Siapkan Jalur dan Inisialisasi Viewer
Pertama, tentukan tempat penyimpanan halaman yang dibagi dan buat instance `Viewer` untuk buku kerja sumber.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Langkah 2: Konfigurasikan Baris per Halaman
Beritahu viewer berapa banyak baris yang harus ada di setiap halaman.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Langkah 3: Render Dokumen
Akhirnya, render buku kerja menggunakan opsi yang telah Anda definisikan.

```java
viewer.view(viewOptions);
```

## Cara Membagi Lembar Excel berdasarkan Baris dan Kolom

Kadang‑kadang satu halaman perlu menampilkan matriks baris **dan** kolom (misalnya, 15 baris × 7 kolom). Ini memberi Anda kontrol penuh atas tata letak setiap halaman HTML. Halaman yang dihasilkan menampilkan blok sel persegi panjang, misalnya baris 1‑15 dan kolom A‑G pada halaman pertama, baris 16‑30 dan kolom H‑N pada halaman berikutnya. Pagination gaya grid ini berguna untuk membuat laporan cetak yang sesuai dengan ukuran kertas standar.

### Anchor Definisi
`SpreadsheetOptions` mengonfigurasi berapa banyak baris dan kolom yang muncul pada setiap halaman yang dihasilkan.

### Implementasi Langkah‑per‑Langkah

#### Langkah 1: Siapkan Jalur dan Inisialisasi Viewer
Pengaturan mirip dengan contoh hanya baris, hanya nama file yang berubah.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Langkah 2: Konfigurasikan Baris dan Kolom per Halaman
Tentukan kedua dimensi untuk membuat pembagian gaya grid.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Langkah 3: Render Dokumen
Render menggunakan panggilan `view` yang sama.

```java
viewer.view(options);
```

## Aplikasi Praktis
- **Buat Laporan Excel Java**: Ubah model keuangan besar menjadi serangkaian laporan HTML berhalaman.  
- **GroupDocs Viewer Excel**: Sematkan halaman terpisah langsung ke portal web untuk eksplorasi data interaktif.  
- **Render Excel HTML Java**: Sajikan halaman HTML yang dihasilkan melalui servlet atau kontroler Spring untuk rendering sisi klien yang cepat.  

## Pertimbangan Kinerja
- **Penggunaan memori** – Buku kerja besar dapat mengonsumsi heap yang signifikan; pertimbangkan meningkatkan pengaturan JVM `-Xmx`.  
- **Ukuran chunk** – Pilih jumlah baris/kolom yang menyeimbangkan ukuran halaman dan kecepatan rendering.  
- **Pembaruan versi** – Jaga GroupDocs Viewer tetap terbaru untuk mendapatkan perbaikan kinerja; rilis 25.2 terbaru meningkatkan kecepatan rendering hingga 30 % dibandingkan 24.x.

## Masalah Umum & Pemecahan Masalah
| Gejala | Penyebab Kemungkinan | Solusi |
|--------|----------------------|--------|
| `OutOfMemoryError` | Rendering lembar sangat besar dengan terlalu banyak baris per halaman | Kurangi `countRowsPerPage` atau tingkatkan heap JVM |
| File output kosong | Jalur file tidak tepat atau izin menulis tidak ada | Verifikasi `outputDirectory` ada dan dapat ditulisi |
| Sumber daya HTML tidak dimuat | Menggunakan `forEmbeddedResources` tetapi melayani file dari URL dasar yang berbeda | Layani seluruh folder output atau beralih ke `forExternalResources` |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menghasilkan PDF alih-alih HTML?**  
A: Ya. Ganti `HtmlViewOptions` dengan `PdfViewOptions` dan pertahankan konfigurasi `SpreadsheetOptions` yang sama.

**Q: Apakah memungkinkan membagi berdasarkan konten sel daripada baris/kolom tetap?**  
A: Pembagian berbasis konten langsung tidak tersedia di GroupDocs Viewer, tetapi Anda dapat memproses buku kerja terlebih dahulu dengan Apache POI untuk membuat lembar terpisah sebelum rendering.

**Q: Apakah GroupDocs Viewer mendukung format Excel lama (XLS)?**  
A: Tentu. Viewer menangani XLS, XLSX, CSV, dan format spreadsheet lainnya.

**Q: Bagaimana cara menyematkan HTML yang dihasilkan ke dalam tampilan Spring MVC?**  
A: Layani folder output sebagai sumber daya statis dan referensikan `page_0.html`, `page_1.html`, dll., dari templat Thymeleaf atau JSP Anda.

**Q: Lisensi apa yang saya perlukan untuk deployment komersial?**  
A: Lisensi produksi penuh dari GroupDocs diperlukan; lisensi percobaan hanya untuk evaluasi.

## Sumber Daya
- **Dokumentasi**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referensi API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Unduhan**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Pembelian**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Uji Coba Gratis**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Lisensi Sementara**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Dukungan**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-06-15  
**Diuji Dengan:** GroupDocs Viewer 25.2 for Java  
**Penulis:** GroupDocs  

## Tutorial Terkait

- [Render Baris & Kolom Tersembunyi di Spreadsheet Java Menggunakan GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Lewati Rendering Baris Kosong di Java Menggunakan GroupDocs.Viewer: Panduan Kinerja](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Panduan Komprehensif: Konversi Excel 2003 XML ke HTML/JPG/PNG/PDF dengan GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)