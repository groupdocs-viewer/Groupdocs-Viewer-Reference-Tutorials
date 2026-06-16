---
date: '2026-03-29'
description: Pelajari cara memutar halaman 90 derajat di Java menggunakan GroupDocs
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

# Putar halaman 90 derajat dengan GroupDocs Viewer untuk Java

Ketika Anda perlu **memutar halaman 90 derajat** dalam sebuah dokumen—baik itu PDF, file Word, atau spreadsheet—melakukannya secara programatik menghemat waktu dan menghilangkan kesalahan manual. Dalam panduan lanjutan ini kami akan menjelaskan langkah‑langkah tepat untuk memutar halaman pertama dari dokumen apa pun yang didukung menggunakan **GroupDocs Viewer for Java**. Pada akhir panduan, Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat Anda sisipkan ke dalam proyek Anda.  
Kami juga akan membahas mengapa memutar halaman di Java penting, skenario umum di mana teknik ini bersinar, dan cara menjaga operasi tetap ringan.

![Putar Halaman Pertama Dokumen dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Jawaban Cepat
- **Apa arti “rotate page 90 degrees”?** Ini memutar halaman yang dipilih searah jarum jam sebesar seperempat putaran.  
- **Perpustakaan mana yang menangani rotasi?** GroupDocs Viewer for Java menyediakan metode `rotatePage`.  
- **Bisakah saya memutar halaman PDF dengan Java?** Ya—gunakan panggilan `rotatePage` yang sama; ini bekerja untuk PDF, DOCX, XLSX, dan lainnya.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi berbayar diperlukan untuk produksi.  
- **Apakah operasi ini memakan banyak memori?** Tidak ketika Anda menutup instance `Viewer` dengan cepat; lihat tips kinerja di bawah.

## Apa itu “rotate page 90 degrees”?
Memutar halaman 90 derajat mengubah orientasi halaman dari potret ke lanskap (atau sebaliknya) tanpa mengubah konten dasarnya. Ini sangat berguna untuk presentasi, mencetak grafik yang hanya dalam mode lanskap, atau memperbaiki dokumen yang dipindai yang diambil secara miring.

## Mengapa memutar halaman secara programatik dengan GroupDocs Viewer untuk Java?
GroupDocs Viewer menyederhanakan kompleksitas penanganan puluhan format file. Ini memungkinkan Anda menerapkan transformasi tingkat halaman—seperti rotasi—sementara file asli tetap tidak berubah. API-nya bersifat fluent, thread‑safe, dan bekerja pada runtime Java 8+ apa pun, menjadikannya pilihan andal untuk otomatisasi tingkat perusahaan.

## Prasyarat

- **GroupDocs.Viewer for Java** (versi terbaru)
- **JDK 8** atau lebih baru
- **Maven** (atau Gradle) untuk manajemen dependensi
- Sebuah IDE seperti IntelliJ IDEA atau Eclipse
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
Kode berikut menunjukkan cara minimal untuk membuat instance `Viewer`. Pertahankan persis seperti yang ditampilkan:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Cara memutar halaman PDF di Java dengan GroupDocs Viewer
Meskipun API berfungsi pada banyak format, PDF adalah kasus penggunaan paling umum untuk rotasi halaman. Metode `rotatePage` yang sama digunakan, jadi Anda hanya perlu mengarahkan viewer ke file PDF dan menentukan nomor halaman.

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

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| **FileNotFoundException** | Jalur tidak tepat atau folder tidak ada | Verifikasi bahwa `YOUR_OUTPUT_DIRECTORY` dan `YOUR_DOCUMENT_DIRECTORY` ada dan dapat dibaca. |
| **Unsupported file format** | Mencoba memutar format yang tidak didukung oleh Viewer | Periksa halaman [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Menggunakan nomor halaman yang salah (berbasis 0) | Ingat bahwa `rotatePage` menggunakan indeks **berbasis 1**. |
| **Out‑of‑memory errors on large docs** | Merender banyak file besar dalam satu thread | Proses dokumen secara berurutan atau gunakan thread pool dengan concurrency terbatas. |

## Aplikasi Praktis

1. **Presentation adjustments** – Mengonversi slide potret ke lanskap secara langsung.  
2. **Bulk document correction** – Mengotomatiskan perbaikan PDF yang dipindai yang diambil secara miring.  
3. **Print‑ready output** – Memastikan grafik lanskap tercetak dengan benar pada kertas berorientasi potret.

## Tips Kinerja

- **Close resources promptly** – Blok `try‑with‑resources` secara otomatis menutup `Viewer`.  
- **Batch processing** – Saat menangani banyak file, gunakan kembali satu instance `Viewer` per thread untuk mengurangi overhead.  
- **Monitor memory** – Untuk dokumen lebih besar dari 100 MB, pertimbangkan untuk men‑stream output ke disk alih‑alih menyimpannya di memori.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya memutar beberapa halaman sekaligus?**  
A: Ya—panggil `rotatePage()` untuk setiap nomor halaman yang ingin Anda putar.

**Q: Apakah ada cara untuk membatalkan rotasi setelah rendering?**  
A: Tidak secara langsung. Anda perlu merender dokumen lagi tanpa opsi rotasi.

**Q: Format file apa yang mendukung rotasi halaman di GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, dan banyak format lain yang tercantum dalam dokumentasi resmi.

**Q: Bagaimana saya dapat memutar halaman dalam sekumpulan dokumen secara otomatis?**  
A: Bungkus kode dalam loop yang mengiterasi koleksi jalur file, menerapkan logika `rotatePage` yang sama pada masing‑masing.

**Q: Apa praktik terbaik untuk menangani kesalahan selama rotasi?**  
A: Bungkus penggunaan Viewer dalam blok `try‑catch`, catat pengecualian, dan opsional melanjutkan pemrosesan file berikutnya.

## Sumber Daya

- **Dokumentasi**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referensi API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Unduh**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Beli**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Coba Gratis**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Lisensi Sementara**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Dukungan**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** GroupDocs Viewer 25.2 for Java  
**Penulis:** GroupDocs