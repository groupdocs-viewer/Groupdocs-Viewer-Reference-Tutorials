---
date: '2026-09-30'
description: Pelajari cara memutar halaman 90 derajat di Java menggunakan GroupDocs
  Viewer, termasuk pengaturan, kode, dan tips kinerja.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Putar halaman 90 derajat di Java menggunakan GroupDocs Viewer. Panduan
  langkah demi langkah, tips kinerja, dan contoh penggunaan dunia nyata untuk pengembang.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Putar halaman 90 derajat dengan GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Putar halaman 90 derajat dengan GroupDocs Viewer for Java
type: docs
url: /id/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Putar halaman 90 derajat dengan GroupDocs Viewer untuk Java

Jika Anda perlu **memutar halaman 90 derajat** dalam sebuah dokumen—apakah itu PDF, file Word, atau spreadsheet—melakukannya secara programatis di Java menghemat waktu, menghilangkan kesalahan manual, dan memungkinkan Anda menyematkan operasi tersebut ke dalam pipeline otomatis. Dalam panduan lanjutan ini Anda akan belajar cara memutar halaman pertama dari dokumen apa pun yang didukung menggunakan **GroupDocs Viewer for Java**, mengapa kemampuan ini penting dalam proyek dunia nyata, dan bagaimana menjaga proses tetap ringan dan efisien memori.

![Putar Halaman Pertama Dokumen dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Jawaban Cepat
- **Apa arti “rotate page 90 degrees”?** Itu memutar halaman yang dipilih searah jarum jam sebesar seperempat putaran.  
- **Library mana yang menangani rotasi?** GroupDocs Viewer for Java menyediakan metode `rotatePage`.  
- **Bisakah saya memutar halaman PDF dengan Java?** Ya—gunakan panggilan `rotatePage` yang sama; metode ini bekerja untuk PDF, DOCX, XLSX, dan lainnya.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi berbayar diperlukan untuk produksi.  
- **Apakah operasi ini intensif memori?** Tidak, asalkan Anda menutup instance `Viewer` dengan cepat; lihat tips kinerja di bawah.

## Apa itu “rotate page 90 degrees”?
Memutar halaman 90 derajat mengubah orientasi halaman dari potret ke lanskap (atau sebaliknya) tanpa mengubah konten dasarnya. Ini berguna untuk presentasi, mencetak grafik yang hanya dalam mode lanskap, atau memperbaiki dokumen yang dipindai yang diambil secara miring. Rotasi diterapkan pada saat render, sehingga file asli tetap tidak berubah.

## Mengapa memutar halaman secara programatis dengan GroupDocs Viewer untuk Java?
GroupDocs Viewer mendukung **lebih dari 50 format input dan output**—termasuk PDF, DOCX, PPTX, XLSX, dan banyak jenis gambar—sehingga Anda dapat merender dokumen apa pun tanpa konverter eksternal. API-nya bersifat fluent, thread‑safe, dan berjalan pada runtime Java 8+ apa pun, menjadikannya pilihan andal untuk otomasi tingkat perusahaan yang harus menangani puluhan jenis file secara konsisten.

## Prasyarat
- GroupDocs Viewer for Java (versi terbaru)
- JDK 8 atau lebih baru
- Maven (atau Gradle) untuk manajemen dependensi
- IDE seperti IntelliJ IDEA atau Eclipse
- Familiaritas dasar dengan Java I/O

## Menyiapkan GroupDocs.Viewer untuk Java
Tambahkan repositori GroupDocs dan dependensi ke `pom.xml` Anda. Potongan kode ini tidak berubah dari tutorial asli:

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
- **Free trial** – unduh dari situs GroupDocs.  
- **Temporary license** – minta jika Anda memerlukan periode evaluasi yang diperpanjang.  
- **Full license** – beli untuk penerapan produksi.

### Inisialisasi Viewer Dasar
Kelas `Viewer` adalah titik masuk yang memuat dokumen dan menyediakan metode rendering serta transformasi. Pertahankan kode persis seperti yang ditampilkan:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Cara memutar halaman PDF Java dengan GroupDocs Viewer
Muat file target dengan `Viewer`, tentukan nomor halaman, dan panggil `rotatePage`. Metode ini bekerja untuk PDF, DOCX, PPTX, XLSX, dan format lain yang didukung oleh pustaka. Setelah rotasi, Anda dapat merender dokumen ke PDF baru atau mengalirkannya langsung ke klien, memastikan file asli tetap tidak tersentuh.

## Implementasi langkah demi langkah: putar halaman pertama 90 derajat

### 1. Impor paket yang diperlukan
`PdfViewOptions` memberi tahu Viewer untuk menghasilkan file PDF, sementara enum `Rotation` menentukan sudutnya. Kedua kelas berada dalam paket `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Tentukan lokasi output dan buat Viewer
Ganti jalur placeholder dengan direktori Anda yang sebenarnya. Konstruktor `Viewer` menerima objek `File` yang menunjuk ke dokumen sumber.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Konfigurasikan opsi tampilan PDF dan terapkan rotasi
Metode `rotatePage(int, Rotation)` menerima indeks halaman **berbasis 1** dan nilai enum `Rotation`. Pada contoh ini kami menggunakan `Rotation.ON_90_DEGREE` untuk memutar halaman pertama searah jarum jam.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Render dokumen
Memanggil `view` dengan opsi yang dikonfigurasi menulis PDF yang telah diputar ke folder output.

```java
viewer.view(viewOptions);
```

#### Cara kerjanya
- **PdfViewOptions** mengarahkan Viewer untuk menghasilkan file output PDF.  
- **rotatePage(int, Rotation)** memutar hanya halaman yang ditentukan, meninggalkan semua halaman lain tidak berubah.  
- Metode ini mendukung tiga konstanta rotasi: `ON_90_DEGREE`, `ON_180_DEGREE`, dan `ON_270_DEGREE`.

## Masalah umum dan solusi
| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| **FileNotFoundException** | Jalur tidak tepat atau folder tidak ada | Verifikasi `YOUR_OUTPUT_DIRECTORY` dan `YOUR_DOCUMENT_DIRECTORY` ada dan dapat dibaca. |
| **Unsupported file format** | Mencoba memutar format yang tidak didukung oleh Viewer | Periksa halaman [format yang didukung GroupDocs Viewer]. |
| **No rotation visible** | Menggunakan nomor halaman yang salah (berbasis 0) | Ingat bahwa `rotatePage` menggunakan indeks **berbasis 1**. |
| **Out‑of‑memory errors on large docs** | Merender banyak file besar dalam satu thread | Proses dokumen secara berurutan atau gunakan thread pool dengan concurrency terbatas. |

## Aplikasi praktis
1. **Penyesuaian presentasi** – Mengonversi slide potret ke lanskap secara langsung untuk dampak visual yang lebih baik.  
2. **Koreksi dokumen massal** – Mengotomatiskan perbaikan PDF yang dipindai yang diambil secara miring, menghemat jam kerja manual.  
3. **Output siap cetak** – Memastikan grafik lanskap tercetak dengan benar pada kertas berorientasi potret tanpa rotasi manual di driver printer.

## Tips kinerja
- **Tutup sumber daya dengan cepat** – Blok `try‑with‑resources` secara otomatis membuang `Viewer`, membebaskan memori.  
- **Pemrosesan batch** – Gunakan kembali satu instance `Viewer` per thread untuk mengurangi overhead inisialisasi.  
- **Pantau memori** – Untuk dokumen lebih besar dari 100 MB, alirkan output ke disk alih-alih menyimpan seluruh file di memori; GroupDocs Viewer dapat memproses file 200 MB dengan penggunaan RAM di bawah 250 MB.

## Pertanyaan yang sering diajukan
**Q: Bisakah saya memutar beberapa halaman sekaligus?**  
A: Ya—panggil `rotatePage()` untuk setiap nomor halaman yang ingin Anda putar, baik dalam loop maupun dengan chaining panggilan.

**Q: Apakah ada cara untuk membatalkan rotasi setelah rendering?**  
A: Tidak secara langsung. Anda harus merender dokumen lagi tanpa opsi rotasi.

**Q: Format file apa yang mendukung rotasi halaman di GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, dan banyak format lain yang tercantum dalam dokumentasi resmi.

**Q: Bagaimana saya dapat memutar halaman dalam sekumpulan dokumen secara otomatis?**  
A: Bungkus logika rotasi dalam loop yang mengiterasi koleksi jalur file, menerapkan konfigurasi `rotatePage` yang sama ke setiap file.

**Q: Apa praktik terbaik untuk menangani kesalahan selama rotasi?**  
A: Bungkus penggunaan Viewer dalam blok `try‑catch`, catat detail pengecualian, dan secara opsional lanjutkan memproses file berikutnya untuk menghindari satu kegagalan menghentikan seluruh batch.

## Sumber daya
- **Dokumentasi**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referensi API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Unduh**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Pembelian**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Percobaan gratis**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Lisensi sementara**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Dukungan**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-09-30  
**Diuji Dengan:** GroupDocs Viewer 25.2 untuk Java  
**Penulis:** GroupDocs

## Tutorial Terkait
- [Cara Memutar Halaman PDF Tertentu dengan GroupDocs.Viewer untuk Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Muat Dokumen dari URL di Java – Tutorial GroupDocs.Viewer](/viewer/java/document-loading/)
- [Tampilan Dokumen Groupdocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}