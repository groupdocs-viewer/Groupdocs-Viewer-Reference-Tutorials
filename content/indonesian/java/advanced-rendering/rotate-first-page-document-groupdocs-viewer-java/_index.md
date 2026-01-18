---
date: '2026-01-18'
description: Pelajari cara memutar halaman 90 derajat di Java menggunakan GroupDocs
  Viewer, termasuk pengaturan, kode, dan tips kinerja.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Putar halaman 90 derajat dengan GroupDocs Viewer untuk Java
type: docs
url: /id/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Memutar halaman 90 derajat dengan GroupDocs Viewer untuk Java

Ketika Anda perlu **memutar halaman 90 derajat** dalam sebuah dokumen—baik itu PDF, file Word, atau spreadsheet—melakukannya secara programatik menghemat waktu dan menghilangkan kesalahan manual. Dalam panduan lanjutan ini kami akan menelusuri langkah‑langkah tepat untuk memutar halaman pertama dari dokumen apa pun yang didukung menggunakan **GroupDocs Viewer untuk Java**. Pada akhir panduan, Anda akan memiliki cuplikan kode yang dapat dipakai ulang dan dapat disisipkan ke dalam proyek Anda sendiri.

![Putar Halaman Pertama Dokumen dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Jawaban Cepat
- **Apa arti “rotate page 90 degrees”?** Itu memutar halaman yang dipilih searah jarum jam sebesar seperempat putaran.  
- **Perpustakaan mana yang menangani rotasi?** GroupDocs Viewer untuk Java menyediakan metode `rotatePage`.  
- **Bisakah saya memutar halaman PDF dengan Java?** Ya—gunakan pemanggilan `rotatePage` yang sama; ia bekerja untuk PDF, DOCX, XLSX, dan lainnya.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi berbayar diperlukan untuk produksi.  
- **Apakah operasi ini memakan banyak memori?** Tidak, selama Anda menutup instance `Viewer` dengan cepat; lihat tips kinerja di bawah.

## Apa itu “rotate page 90 degrees”?
Memutar halaman 90 derajat mengubah orientasi halaman dari potret ke lanskap (atau sebaliknya) tanpa mengubah konten dasarnya. Ini sangat berguna untuk presentasi, mencetak grafik yang hanya cocok dalam mode lanskap, atau memperbaiki dokumen hasil pemindaian yang diambil miring.

## Mengapa memutar halaman dengan GroupDocs Viewer untuk Java?
GroupDocs Viewer menyederhanakan kompleksitas penanganan puluhan format file. Ia memungkinkan Anda menerapkan transformasi tingkat halaman—seperti rotasi—sementara menjaga file asli tetap tidak berubah. API‑nya bersifat fluent, thread‑safe, dan bekerja pada runtime Java 8+ apa pun.

## Prasyarat

- **GroupDocs.Viewer for Java** (versi terbaru)
- **JDK 8** atau yang lebih baru
- **Maven** (atau Gradle) untuk manajemen dependensi
- IDE seperti IntelliJ IDEA atau Eclipse
- Familiaritas dasar dengan Java I/O

## Menyiapkan GroupDocs.Viewer untuk Java

Tambahkan repositori GroupDocs dan dependensi ke `pom.xml` Anda. Cuplikan ini tidak berubah dari tutorial asli:

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
- **Free trial** – unduh dari situs GroupDocs.  
- **Temporary license** – minta jika Anda memerlukan periode evaluasi yang diperpanjang.  
- **Full license** – beli untuk penerapan produksi.

### Inisialisasi Viewer Dasar
Kode berikut menunjukkan cara minimal untuk membuat instance `Viewer`. Pertahankan persis seperti yang ditampilkan:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Implementasi Langkah‑per‑Langkah: Putar Halaman Pertama 90 Derajat

### 1. Impor paket yang diperlukan
Impor ini memberi Anda akses ke opsi rendering PDF dan enum rotasi.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Tentukan lokasi output dan buat Viewer
Ganti jalur placeholder dengan direktori Anda yang sebenarnya.

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
Metode `rotatePage` menerima nomor halaman (berbasis 1) dan nilai enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Render dokumen
Akhirnya, panggil `view` untuk menghasilkan PDF yang telah diputar.

```java
viewer.view(viewOptions);
```

#### Cara kerjanya
- **PdfViewOptions** memberi tahu Viewer untuk menghasilkan file PDF.  
- **rotatePage(int, Rotation)** memutar hanya halaman yang Anda tentukan, meninggalkan yang lain tidak berubah.  
- Metode ini mendukung `ON_90_DEGREE`, `ON_180_DEGREE`, dan `ON_270_DEGREE`.

## Masalah Umum dan Solusinya

| **Gejala** | **Penyebab Kemungkinan** | **Perbaikan** |
|------------|--------------------------|---------------|
| **FileNotFoundException** | Jalur tidak tepat atau folder tidak ada | Verifikasi bahwa `YOUR_OUTPUT_DIRECTORY` dan `YOUR_DOCUMENT_DIRECTORY` ada dan dapat dibaca. |
| **Unsupported file format** | Mencoba memutar format yang tidak didukung oleh Viewer | Periksa halaman [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Menggunakan nomor halaman yang salah (berbasis 0) | Ingat bahwa `rotatePage` menggunakan indeks **berbasis 1**. |
| **Out‑of‑memory errors on large docs** | Merender banyak file besar dalam satu thread | Proses dokumen secara berurutan atau gunakan thread pool dengan concurrency terbatas. |

## Aplikasi Praktis

1. **Penyesuaian presentasi** – Mengonversi slide potret menjadi lanskap secara langsung.  
2. **Koreksi dokumen massal** – Mengotomatiskan perbaikan PDF yang dipindai yang diambil secara miring.  
3. **Output siap cetak** – Memastikan grafik lanskap tercetak dengan benar pada kertas berorientasi potret.

## Tips Kinerja

- **Tutup sumber daya dengan cepat** – blok `try‑with‑resources` secara otomatis membuang `Viewer`.  
- **Pemrosesan batch** – Saat menangani banyak file, gunakan kembali satu instance `Viewer` per thread untuk mengurangi overhead.  
- **Pantau memori** – Untuk dokumen lebih besar dari 100 MB, pertimbangkan streaming output ke disk alih‑alih menyimpannya di memori.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya memutar beberapa halaman sekaligus?**  
J: Ya—panggil `rotatePage()` untuk setiap nomor halaman yang ingin Anda putar.

**T: Apakah ada cara untuk membatalkan rotasi setelah rendering?**  
J: Tidak secara langsung. Anda harus merender ulang dokumen tanpa opsi rotasi.

**T: Format file apa yang mendukung rotasi halaman di GroupDocs Viewer?**  
J: DOCX, PDF, PPTX, XLSX, dan banyak format lain yang tercantum dalam dokumentasi resmi.

**T: Bagaimana cara memutar halaman dalam batch dokumen secara otomatis?**  
J: Bungkus kode dalam loop yang mengiterasi koleksi jalur file, menerapkan logika `rotatePage` yang sama pada masing‑masing.

**T: Praktik terbaik apa untuk menangani error selama rotasi?**  
J: Bungkus penggunaan Viewer dalam blok `try‑catch`, catat pengecualian, dan opsional lanjutkan pemrosesan file berikutnya.

## Sumber Daya

- **Dokumentasi**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referensi API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Unduh**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Beli Lisensi**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Coba Gratis**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Minta Lisensi Sementara**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Forum GroupDocs**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-18  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs