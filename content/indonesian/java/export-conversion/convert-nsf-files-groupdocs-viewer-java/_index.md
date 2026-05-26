---
date: '2026-05-26'
description: Pelajari cara mengonversi nsf ke pdf dan format lain (HTML, JPG, PNG)
  menggunakan GroupDocs.Viewer for Java. Panduan langkah demi langkah dengan tip praktik
  terbaik.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: Konversi nsf ke pdf dengan GroupDocs.Viewer for Java
type: docs
url: /id/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# Konversi File NSF ke Berbagai Format Menggunakan GroupDocs.Viewer untuk Java

Dalam panduan komprehensif ini Anda akan belajar **cara mengonversi nsf ke pdf** dan juga merender file NSF ke HTML, JPG, dan PNG dengan GroupDocs.Viewer untuk Java. Apakah Anda perlu mengarsipkan basis data Lotus Notes, menampilkannya di browser, atau menghasilkan pratinjau gambar, tutorial ini memandu Anda melalui semuanya—dari penyiapan lingkungan hingga detail tingkat kode—sehingga Anda dapat menerapkan konversi dalam hitungan menit.

![Konversi File NSF ke HTML, JPG, PNG, dan PDF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[Konversi File NSF ke HTML, JPG, PNG, dan PDF dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## Jawaban Cepat
- **Apa kasus penggunaan utama?** Merender file NSF ke PDF, HTML, JPG, atau PNG untuk web, pengarsipan, atau berbagi.  
- **Perpustakaan mana yang menangani konversi?** GroupDocs.Viewer untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi penuh diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** JDK 8 atau lebih baru.  
- **Bisakah saya memproses batch banyak file NSF?** Ya – bungkus logika rendering dalam loop dan kelola sumber daya dengan try‑with‑resources.

## Apa itu “convert nsf to pdf”?

Mengonversi file NSF (basis data Lotus Notes) ke PDF menghasilkan dokumen statis yang dapat dibaca secara universal dan mempertahankan tata letak, font, serta grafik asli tanpa memerlukan klien Notes. Format ini ideal untuk pengarsipan hukum, distribusi aman, dan penyimpanan jangka panjang karena file PDF dapat dibuka di sistem operasi atau perangkat apa pun.

## Mengapa Mengonversi NSF ke PDF dan Format Lain?

Mengubah file NSF menjadi PDF, HTML, JPG, atau PNG membuka aksesibilitas universal, mempertahankan kesetiaan visual, dan memungkinkan integrasi mulus dengan aplikasi web dan seluler modern. PDF mempertahankan tata letak halaman yang tepat, HTML menyediakan tampilan instan di browser, dan JPG/PNG memberikan snapshot gambar resolusi tinggi untuk thumbnail atau penyematan.

## Prasyarat

- **Java Development Kit (JDK) 8+** – JDK 11 atau lebih baru direkomendasikan untuk kinerja garbage‑collection yang lebih baik.
- **Maven** – untuk manajemen dependensi.
- **GroupDocs.Viewer untuk Java** – versi percobaan atau berlisensi.
- Familiaritas dasar dengan I/O file Java dan struktur proyek Maven.

## Menyiapkan GroupDocs.Viewer untuk Java

### Konfigurasi Maven

Tambahkan dependensi GroupDocs.Viewer ke `pom.xml` Anda. Ini akan mengambil semua binary yang diperlukan serta library transitive.

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

Untuk membuka semua fungsi Anda dapat:
- **Free Trial:** Evaluasi fitur inti tanpa kunci lisensi.
- **Temporary License:** Minta kunci berjangka waktu terbatas untuk pengujian.
- **Full Purchase:** Dapatkan lisensi produksi untuk penggunaan tak terbatas.

### Inisialisasi Dasar

`Viewer` adalah kelas inti yang merender dokumen ke format output yang diinginkan. Inisialisasi dengan lisensi dan jalur file Anda di dalam blok try‑with‑resources untuk memastikan pembuangan yang tepat.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## Cara Mengonversi NSF ke PDF

Untuk mengonversi dokumen NSF ke PDF, pertama buat instance `Viewer` yang menunjuk ke file sumber. Kemudian konfigurasikan `PdfViewOptions` untuk menentukan karakteristik output seperti ukuran halaman, tingkat kompresi, dan apakah menyertakan font. Akhirnya, panggil `viewer.view(pdfOptions)` yang merender seluruh dokumen menjadi satu file PDF siap untuk distribusi.

`PdfViewOptions` menentukan pengaturan khusus PDF seperti ukuran halaman dan kompresi.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## Merender NSF ke HTML

### Ikhtisar

Konversi dokumen NSF menjadi halaman HTML mandiri, menyematkan gambar dan CSS untuk representasi layar yang akurat.

### Panduan Langkah‑per‑Langkah

#### 1. Siapkan Direktori Output dan Jalur File

Tentukan folder tempat file HTML akan disimpan.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. Konfigurasikan Load Options

`LoadOptions` memungkinkan Anda menyesuaikan pemuatan sumber daya, seperti mengatur batas waktu untuk aset eksternal.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. Inisialisasi Viewer dan Render

`Viewer` memproses NSF dan menulis file HTML ke direktori target.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## Merender NSF ke JPG

### Ikhtisar

Hasilkan gambar JPG berkualitas tinggi dari setiap halaman dokumen NSF, berguna untuk pratinjau atau penyematan dalam alur kerja berfokus gambar.

#### 1. Tentukan Jalur Output

Tentukan pola penamaan seperti `output_page_{0}.jpg` dimana `{0}` adalah nomor halaman.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. Konfigurasikan dan Render

`JpgViewOptions` menentukan pengaturan output gambar JPEG, termasuk resolusi dan kualitas. Buat `JpgViewOptions`, atur DPI yang diinginkan, dan panggil `viewer.view(options)`.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## Merender NSF ke PNG

### Ikhtisar

Hasilkan gambar PNG lossless yang mempertahankan setiap detail halaman NSF asli.

#### 1. Atur Jalur Output

Gunakan templat seperti `nsf_page_{0}.png` untuk paginasi otomatis.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. Render Dokumen

`PngViewOptions` mengonfigurasi parameter output PNG seperti resolusi dan kedalaman warna. Konfigurasikan `PngViewOptions` (mis., set `setResolution(300)`) dan render.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## Aplikasi Praktis

1. **Berbagi Dokumen Berbasis Web:** Konversi NSF ke HTML untuk tampilan instan di browser tanpa menginstal Notes.  
2. **Pengarsipan Gambar:** Simpan snapshot JPG/PNG per halaman untuk galeri thumbnail atau pipeline OCR.  
3. **Akses Universal:** Gunakan konversi PDF untuk menyediakan satu file aman yang dapat dibuka di perangkat apa pun, memenuhi persyaratan kepatuhan.

## Pertimbangan Kinerja

- **Pemuat Sumber Daya:** Sesuaikan `setResourceLoadingTimeout` berdasarkan latensi jaringan untuk menghindari kegagalan.  
- **Manajemen Memori:** Gunakan try‑with‑resources untuk instance `Viewer`; ini secara otomatis membebaskan sumber daya native.  
- **Pemrosesan Batch:** Untuk batch besar, proses file secara berurutan atau dalam aliran paralel, memantau penggunaan heap agar tetap di bawah batas memori JVM.

## Bagian FAQ

**Apa format terbaik untuk mengonversi dokumen NSF?**  
- Tergantung pada penggunaan downstream: HTML untuk portal web, PDF untuk distribusi universal, JPG/PNG untuk alur kerja berbasis gambar.

**Bagaimana cara menangani file NSF besar secara efisien?**  
- Sesuaikan `LoadOptions` (mis., tingkatkan `setResourceLoadingTimeout`), proses file dalam batch lebih kecil, dan gunakan kembali satu instance `Viewer` bila memungkinkan.

**Bisakah saya menyesuaikan kualitas output pada format gambar?**  
- Ya. Atur DPI, tingkat kompresi, dan kedalaman warna melalui `JpgViewOptions` atau `PngViewOptions` sebelum merender.

**Apa yang harus saya lakukan jika konversi gagal?**  
- Verifikasi jalur file, pastikan file NSF tidak rusak, dan periksa log GroupDocs.Viewer untuk kode error terperinci. Memperbarui ke versi library terbaru sering menyelesaikan masalah kompatibilitas.

**Apakah konversi batch didukung?**  
- Tentu saja. Bungkus logika rendering dalam loop `for` atau Java Stream untuk memproses banyak file NSF secara otomatis.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara mengonversi file NSF ke PDF tanpa kehilangan anotasi?**  
A: `PdfViewOptions` secara otomatis mempertahankan sebagian besar anotasi; cukup render dokumen dengan opsi ini dan PDF yang dihasilkan mencerminkan tata letak asli.

**Q: Bisakah saya mengonversi file NSF yang dilindungi kata sandi?**  
A: Ya. Berikan kredensial melalui `LoadOptions` sebelum membuat instance `Viewer`.

**Q: Versi Java apa yang memberikan kinerja terbaik?**  
A: JDK 11 atau lebih baru menawarkan garbage collection dan concurrency yang lebih baik, yang mempercepat konversi batch.

**Q: Apakah memungkinkan mengatur DPI khusus untuk output JPG/PNG?**  
A: Konfigurasikan `JpgViewOptions.setResolution(int dpi)` atau `PngViewOptions.setResolution(int dpi)` sebelum memanggil `viewer.view(options)`.

**Q: Apakah GroupDocs.Viewer mendukung streaming output langsung ke respons HTTP?**  
A: Ya. Gunakan overload `Stream` dari view options untuk menulis hasil langsung ke `HttpServletResponse.getOutputStream()`.

## Kesimpulan

Anda kini memiliki peta jalan lengkap untuk **convert nsf to pdf** dan merender file NSF ke HTML, JPG, dan PNG menggunakan GroupDocs.Viewer untuk Java. Dengan mengikuti langkah-langkah di atas Anda dapat mengintegrasikan konversi dokumen yang kuat ke dalam aplikasi Java apa pun, mengotomatisasi pekerjaan batch, dan menyajikan konten dalam format yang paling sesuai dengan kebutuhan pengguna Anda. Jelajahi fitur Viewer tambahan seperti watermark, font khusus, dan penanganan multi‑halaman untuk lebih memperkaya solusi Anda.

---

**Terakhir Diperbarui:** 2026-05-26  
**Diuji Dengan:** GroupDocs.Viewer 25.2  
**Penulis:** GroupDocs

## Tutorial Terkait

- [groupdocs viewer java: Konversi Dokumen ke PDF – Panduan Lengkap](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – Konversi ODF ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer untuk Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Konversi PST ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer untuk Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)