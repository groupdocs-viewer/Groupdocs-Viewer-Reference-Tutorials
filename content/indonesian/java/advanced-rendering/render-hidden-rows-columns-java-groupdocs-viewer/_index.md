---
date: '2026-03-27'
description: Pelajari cara mengonversi Excel ke HTML dan menampilkan baris serta kolom
  tersembunyi dalam spreadsheet Java menggunakan GroupDocs.Viewer untuk konversi HTML
  yang mulus. Pastikan visibilitas data lengkap dengan panduan rendering lanjutan
  ini.
keywords:
- convert excel to html
- xlsx to html java
- display hidden spreadsheet data
- GroupDocs Viewer Java
title: Cara Mengonversi Excel ke HTML dan Menampilkan Baris & Kolom Tersembunyi di
  Java dengan GroupDocs.Viewer
type: docs
url: /id/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/
weight: 1
---

# Mengonversi Excel ke HTML dan Menampilkan Baris & Kolom Tersembunyi dalam Spreadsheet Java Menggunakan GroupDocs.Viewer

Apakah Anda kesulitan **mengonversi Excel ke HTML** dan memvisualisasikan baris serta kolom tersembunyi dalam spreadsheet saat mengonversinya ke HTML menggunakan Java? Anda tidak sendirian! Banyak pengembang menghadapi tantangan ini saat mencoba menjaga integritas visualisasi data di berbagai format. Tutorial ini akan memandu Anda cara menampilkan baris dan kolom tersembunyi dalam spreadsheet menggunakan GroupDocs.Viewer untuk Java, memastikan tidak ada informasi penting yang hilang selama konversi.

![Render Hidden Rows & Columns with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-hidden-rows-and-columns-java.png)

## Jawaban Cepat
- **Apakah GroupDocs.Viewer dapat mengonversi Excel ke HTML?** Ya, ia menyediakan dukungan out‑of‑the‑box untuk mengonversi file XLSX ke HTML.
- **Apakah baris dan kolom tersembunyi akan terlihat dalam output HTML?** Ketika Anda mengaktifkan opsi yang tepat, data tersembunyi ditampilkan seperti sel yang terlihat.
- **Artifact Maven mana yang diperlukan?** `com.groupdocs:groupdocs-viewer` (versi terbaru disarankan).
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi permanen diperlukan untuk produksi; lisensi percobaan gratis atau lisensi sementara tersedia untuk evaluasi.
- **Apakah pendekatan ini kompatibel dengan Java 8 dan yang lebih baru?** Tentu – ia bekerja dengan JDK 8+.

## Apa itu “mengonversi Excel ke HTML”?
Mengonversi Excel ke HTML berarti mengubah workbook `.xlsx` menjadi sekumpulan halaman HTML siap web sambil mempertahankan tata letak, gaya, dan data asli. Hal ini memungkinkan Anda menampilkan spreadsheet langsung di peramban tanpa memerlukan Microsoft Office.

## Mengapa menampilkan data spreadsheet yang tersembunyi?
- **Pelaporan keuangan** membutuhkan jejak audit lengkap, termasuk baris/kolom yang disembunyikan untuk tujuan presentasi.
- **Alat analisis data** memerlukan dataset lengkap untuk perhitungan yang akurat.
- **Sumber daya pendidikan** memerlukan setiap sel terlihat untuk mengajarkan formula dan struktur data.

## Prasyarat

### Perpustakaan dan Dependensi yang Diperlukan
Untuk mengimplementasikan fitur ini, pastikan untuk menyertakan GroupDocs.Viewer untuk Java sebagai dependensi dalam proyek Anda. Perpustakaan ini penting untuk merender dokumen ke berbagai format seperti HTML, PDF, dan file gambar.

### Persyaratan Penyiapan Lingkungan
- **Java Development Kit (JDK)**: Versi 8 atau lebih baru  
- **Integrated Development Environment (IDE)**: Seperti IntelliJ IDEA atau Eclipse  
- **Maven**: Untuk mengelola dependensi proyek  

### Prasyarat Pengetahuan
Pemahaman dasar tentang pemrograman Java diperlukan. Selain itu, familiaritas dengan Maven akan bermanfaat untuk menyiapkan proyek Anda.

## Menyiapkan GroupDocs.Viewer untuk Java
Untuk mulai menggunakan GroupDocs.Viewer dalam aplikasi Java Anda, Anda perlu menyiapkannya melalui Maven. Berikut caranya:

**Maven**  
Tambahkan konfigurasi berikut ke file `pom.xml` Anda:
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

### Langkah-langkah Akuisisi Lisensi
- **Free Trial**: Unduh versi percobaan untuk mengevaluasi fitur.  
- **Temporary License**: Minta lisensi sementara untuk akses penuh fitur tanpa batasan evaluasi.  
- **Purchase**: Dapatkan lisensi permanen untuk penggunaan produksi.  

Setelah menyiapkan Maven dan memperoleh lisensi Anda, Anda dapat mulai menginisialisasi GroupDocs.Viewer. Berikut cara melakukannya:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        // Initialize the viewer with your license file if available.
        try (Viewer viewer = new Viewer("path/to/your/document.xlsx")) {
            // Your code here...
        }
    }
}
```

## Cara Mengonversi Excel ke HTML dengan Data Tersembunyi
Bagian ini memandu Anda melalui langkah-langkah tepat untuk **mengonversi Excel ke HTML** sambil memastikan baris dan kolom tersembunyi ditampilkan.

### Langkah 1: Tentukan Jalur Direktori Output
Mulailah dengan menentukan di mana file yang dirender akan disimpan:
```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderHiddenRowsAndColumns");
```

### Langkah 2: Konfigurasikan HTMLViewOptions
Selanjutnya, atur `HtmlViewOptions` untuk menyematkan sumber daya langsung dalam file HTML yang dihasilkan:
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

// Create a file path format for rendering each page.
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Langkah 3: Aktifkan Rendering Kolom dan Baris Tersembunyi
Konfigurasikan `SpreadsheetOptions` untuk merender elemen tersembunyi:
```java
// Enable rendering of hidden columns and rows.
viewOptions.getSpreadsheetOptions().setRenderHiddenColumns(true);
viewOptions.getSpreadsheetOptions().setRenderHiddenRows(true);
```

### Langkah 4: Inisialisasi Viewer dengan Dokumen dan Render
Akhirnya, inisialisasi GroupDocs.Viewer dengan jalur dokumen Anda dan render kontennya:
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_HIDDEN_ROW_AND_COLUMN")) {
    // Render the document to HTML using the specified view options.
    viewer.view(viewOptions);
} catch (Exception e) {
    System.out.println("Error rendering document: " + e.getMessage());
}
```

**Tips Pemecahan Masalah**: Pastikan jalur telah diatur dengan benar dan dependensi disertakan dengan tepat dalam `pom.xml` Anda.

## Aplikasi Praktis
Berikut beberapa aplikasi praktis dari fitur ini:
1. **Financial Reporting**: Pastikan semua data, termasuk metrik keuangan tersembunyi, terlihat selama konversi untuk kepatuhan.  
2. **Data Analysis**: Jaga integritas dataset dengan menampilkan semua baris dan kolom dalam laporan atau presentasi.  
3. **Educational Tools**: Gunakan konten spreadsheet lengkap untuk tujuan pembelajaran tanpa kehilangan informasi tersembunyi.  

## Pertimbangan Kinerja
Untuk mengoptimalkan kinerja saat menggunakan GroupDocs.Viewer:
- Pantau penggunaan memori, terutama dengan dokumen besar.  
- Optimalkan jalur file dan lokasi penyimpanan untuk mengurangi operasi I/O.  
- Secara rutin perbarui perpustakaan untuk memanfaatkan peningkatan kinerja dan perbaikan bug baru.  

## Kesimpulan
Dalam tutorial ini, Anda telah belajar cara **mengonversi Excel ke HTML** dan mengonfigurasi GroupDocs.Viewer untuk Java agar merender baris dan kolom tersembunyi dalam spreadsheet. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan visibilitas data yang komprehensif di berbagai format. Sebagai langkah selanjutnya, coba bereksperimen dengan berbagai jenis dokumen dan jelajahi fitur tambahan yang ditawarkan oleh GroupDocs.Viewer.

Siap menyelami lebih dalam? Cobalah mengimplementasikan fitur ini dalam proyek Anda dan lihat bagaimana hal itu meningkatkan fungsionalitas aplikasi Anda!

## Bagian FAQ

**Q1: Bisakah saya menggunakan GroupDocs.Viewer secara gratis?**  
A1: Ya, Anda dapat mengunduh versi percobaan dari situs resmi untuk menjelajahi fitur. Untuk akses penuh tanpa batasan, pertimbangkan memperoleh lisensi sementara atau permanen.

**Q2: Format file apa yang didukung oleh GroupDocs.Viewer?**  
A2: Ia mendukung lebih dari 50 format dokumen berbeda termasuk PDF, Word, Excel, dan gambar.

**Q3: Bagaimana cara menangani dokumen besar dengan GroupDocs.Viewer?**  
A3: Optimalkan manajemen memori dengan menyesuaikan pengaturan Java dan memecah file besar menjadi bagian yang lebih kecil jika diperlukan.

**Q4: Apakah memungkinkan untuk menyesuaikan format output HTML?**  
A4: Ya, Anda dapat mengonfigurasi berbagai opsi menggunakan `HtmlViewOptions` untuk menyesuaikan tampilan dokumen yang dirender.

**Q5: Apa cara terbaik untuk memecahkan masalah dengan GroupDocs.Viewer?**  
A5: Periksa dokumentasi resmi dan forum untuk solusi. Pastikan semua dependensi dikonfigurasi dengan benar dalam penyiapan proyek Anda.

## Pertanyaan yang Sering Diajukan

**Q: Apakah mengaktifkan `setRenderHiddenColumns(true)` memengaruhi kinerja?**  
A: Merender kolom tersembunyi menambah overhead kecil, tetapi dampaknya minimal untuk workbook tipikal. Untuk lembar yang sangat besar, pantau penggunaan memori.

**Q: Bisakah saya mengonversi file XLSX menjadi satu halaman HTML alih-alih beberapa halaman?**  
A: Ya, Anda dapat mengatur nama file `HtmlViewOptions` khusus tanpa placeholder `{0}` untuk menghasilkan satu file HTML.

**Q: Bagaimana cara menampilkan data spreadsheet tersembunyi hanya untuk lembar kerja tertentu?**  
A: Gunakan `viewOptions.getSpreadsheetOptions().setWorksheetIndexes(...)` untuk menargetkan lembar tertentu sebelum mengaktifkan rendering tersembunyi.

**Q: Apakah ada cara untuk menyembunyikan toolbar atau navigasi setelah konversi?**  
A: Output HTML yang dihasilkan oleh GroupDocs.Viewer bersifat statis; Anda dapat secara manual menghapus elemen navigasi apa pun jika menyesuaikan templat.

**Q: Versi GroupDocs.Viewer mana yang diperlukan untuk rendering baris/kolom tersembunyi?**  
A: Fitur ini tersedia mulai versi 22.0; kami menyarankan menggunakan rilis stabil terbaru.

## Sumber Daya
- **Dokumentasi**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referensi API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Unduh**: [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Beli**: [Buy a License](https://purchase.groupdocs.com/buy)
- **Versi Gratis**: [Try Free Version](https://releases.groupdocs.com/viewer/java/)
- **Lisensi Sementara**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Dukungan**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-03-27  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs