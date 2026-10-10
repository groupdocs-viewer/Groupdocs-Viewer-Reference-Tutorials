---
date: '2026-10-10'
description: Pelajari cara mengonversi zip ke html menggunakan GroupDocs.Viewer Java,
  mengatur item per halaman, menyematkan sumber daya html, dan mengonversi arsip secara
  batch dengan efisien.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: Pelajari cara mengonversi zip ke html dengan GroupDocs.Viewer Java,
  menyematkan sumber daya, mengatur item per halaman, dan memproses arsip secara batch
  untuk pratinjau web yang cepat dan portabel.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: Konversi zip ke HTML dengan pagination GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Konversi zip ke html dan atur item per halaman dengan GroupDocs.Viewer Java
type: docs
url: /id/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi zip ke html dan mengatur item per halaman dengan GroupDocs.Viewer Java

Dalam banyak aplikasi web Anda perlu menampilkan isi arsip ZIP atau RAR langsung di peramban. **Cara mengonversi zip** menjadi HTML menggunakan GroupDocs.Viewer untuk Java adalah kebutuhan umum, dan perpustakaan ini memungkinkan Anda menyematkan gambar, CSS, dan font sehingga hasilnya menjadi satu halaman yang dapat dipindahkan. Tutorial ini memandu Anda melalui semuanya—dari penyiapan Maven hingga rendering multi‑halaman—sementara menjelaskan mengapa setiap opsi penting untuk kinerja dan kegunaan.

![Mengonversi Arsip ke HTML dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Jawaban Cepat
- **Apa yang dikontrol oleh “set items per page”?** Ini menentukan berapa banyak file atau folder dari arsip yang muncul pada setiap halaman HTML yang dihasilkan.  
- **Bisakah saya menyematkan gambar dan CSS langsung di HTML?** Ya – gunakan opsi `forEmbeddedResources` untuk menyematkan sumber daya HTML.  
- **Apakah konversi batch memungkinkan?** Tentu saja; Anda dapat melakukan loop pada kumpulan arsip dan merender masing‑masing dengan pengaturan yang sama.  
- **Apakah saya memerlukan Maven untuk menggunakan GroupDocs.Viewer?** Ya, tambahkan dependensi Maven `groupdocs-viewer` seperti yang ditunjukkan di bawah.  
- **Format output apa yang didukung?** HTML satu‑halaman dan HTML multi‑halaman keduanya tersedia, dan perpustakaan mendukung lebih dari 50 tipe arsip input.

## Apa itu “set items per page” di GroupDocs.Viewer?
Ini memberi tahu viewer berapa banyak entri arsip (file atau folder) yang harus ditampilkan pada setiap halaman HTML ketika Anda menghasilkan dokumen multi‑halaman. Menyesuaikan nilai ini membantu Anda menyeimbangkan ukuran halaman dan kecepatan navigasi, terutama untuk arsip besar, dengan membatasi jumlah data yang dimuat per halaman dan mengurangi waktu rendering bagi pengguna akhir.

## Mengapa menyematkan sumber daya HTML?
Menyematkan sumber daya (gambar, CSS, font) langsung di dalam file HTML menciptakan dokumen tunggal yang dapat dipindahkan dan dapat dibuka tanpa file eksternal. Ini ideal untuk lampiran email, penampilan offline, atau menyematkan output ke halaman web lain. Hal ini juga menghilangkan kebutuhan mengelola jalur aset eksternal.

## Prasyarat

- **Perpustakaan yang diperlukan:** Sertakan GroupDocs.Viewer versi 25.2 atau lebih baru.  
- **Lingkungan:** Java Development Kit (JDK) terpasang dan dikonfigurasi.  
- **Pengetahuan:** Dasar Java dan manajemen dependensi Maven.  

## Penyiapan Maven GroupDocs Viewer

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

### Perolehan Lisensi
GroupDocs.Viewer menawarkan **tautan percobaan gratis**, lisensi sementara, atau opsi pembelian penuh. Pilih yang sesuai dengan jadwal proyek Anda.

## Inisialisasi Dasar
Kelas `Viewer` adalah titik masuk untuk merender dokumen dan arsip. Setelah penyiapan Maven, masukkan viewer ke dalam kode Anda:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cara merender arsip ke html satu‑halaman
Kelas `HtmlViewOptions` mendefinisikan pengaturan untuk output HTML, seperti penyematan sumber daya. Muat arsip, konfigurasikan opsi HTML untuk menyematkan sumber daya, dan render semuanya ke dalam satu halaman mandiri. Ini menghasilkan satu file HTML yang berisi semua file, gambar, CSS, dan font, siap untuk penggunaan offline atau lampiran email.

**Jawaban langsung:** Buat instance `Viewer` untuk file ZIP, panggil `HtmlViewOptions.forEmbeddedResources()`, dan panggil `viewer.view(documentPath, options)`. Ini menghasilkan satu file HTML yang berisi semua file, gambar, CSS, dan font, siap untuk penggunaan offline atau lampiran email.

### Langkah 1: Tentukan direktori output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Langkah 2: Tetapkan nama file untuk output satu‑halaman
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Langkah 3: Inisialisasi viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Langkah 4: Konfigurasikan opsi rendering (menyematkan sumber daya html)
Kelas `HtmlViewOptions` mendefinisikan pengaturan untuk output HTML, seperti penyematan sumber daya. Gunakan `forEmbeddedResources()` untuk menggabungkan semuanya menjadi satu file.

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Langkah 5: Render sebagai satu halaman
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cara merender arsip ke html multi‑halaman dan mengatur item per halaman
Kelas `HtmlViewOptions` juga mendukung paginasi. Dengan memanggil `options.setItemsPerPage(N)`, Anda memberi instruksi kepada viewer untuk membagi arsip menjadi beberapa file HTML, masing‑masing menampilkan hingga **N** entri. Pendekatan ini meningkatkan kecepatan navigasi untuk arsip besar sambil menjaga setiap halaman ringan.

**Jawaban langsung:** Gunakan `HtmlViewOptions.forEmbeddedResources()`, panggil `options.setItemsPerPage(N)`, dan render arsip. Viewer akan menghasilkan file HTML terpisah—satu per halaman—masing‑masing berisi hingga **N** entri, yang mempercepat navigasi untuk arsip besar.

### Langkah 1: Gunakan kembali direktori output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Langkah 2: Tentukan format nama file untuk beberapa halaman
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Langkah 3: Inisialisasi viewer lagi
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Langkah 4: Konfigurasikan opsi multi‑halaman (menyematkan sumber daya html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Langkah 5: Atur item per halaman (kata kunci utama dalam aksi)
`options.setItemsPerPage(20); // cara mengonversi arsip zip dengan 20 entri per halaman`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Aplikasi Praktis

- **Sistem manajemen dokumen:** Tambahkan fungsi pratinjau arsip tanpa menginstal viewer tambahan.  
- **Portal web:** Tawarkan pengguna cara cepat, tanpa unduhan untuk menjelajahi dokumen yang terbundel.  
- **Alat kolaborasi:** Biarkan tim memeriksa arsip bersama langsung di peramban.  

## Pertimbangan Kinerja

- **Manajemen sumber daya:** Jaga penggunaan memori tetap rendah dengan memproses arsip dalam aliran; viewer dapat menangani arsip hingga 500 MB tanpa memuat seluruh file ke memori.  
- **Konversi batch arsip:** Lakukan loop melalui daftar file arsip dan panggil logika rendering yang sama untuk memaksimalkan throughput.  
- **Strategi caching:** Simpan HTML yang dirender dalam cache jika arsip yang sama sering diakses, mengurangi waktu pemrosesan ulang hingga 70 %.  

## Pertanyaan yang Sering Diajukan

**Q: Apa itu GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java adalah perpustakaan sisi‑server yang merender lebih dari 50 format dokumen dan arsip—termasuk ZIP dan RAR—ke dalam HTML, PDF, atau file gambar tanpa memerlukan aplikasi eksternal.

**Q: Bagaimana saya dapat memperoleh percobaan gratis GroupDocs.Viewer?**  
A: Kunjungi [tautan percobaan gratis](https://releases.groupdocs.com/viewer/java/) untuk mengunduh dan menguji.

**Q: Bisakah saya mengonversi tipe dokumen lain selain arsip?**  
A: Ya, viewer mendukung PDF, Word, Excel, PowerPoint, dan lebih dari 35 format tambahan.

**Q: Apa yang harus saya lakukan jika rendering lambat?**  
A: Kurangi jumlah item per halaman, aktifkan streaming, atau proses arsip dalam batch yang lebih kecil untuk meningkatkan kecepatan.

**Q: Di mana saya dapat mendapatkan bantuan atau dukungan?**  
A: Hubungi melalui [forum dukungan](https://forum.groupdocs.com/c/viewer/9).

**Q: Apakah memungkinkan menyematkan CSS dan gambar langsung di HTML?**  
A: Tentu saja—gunakan `HtmlViewOptions.forEmbeddedResources` seperti yang ditunjukkan dalam contoh.

**Q: Bagaimana cara saya mengonversi batch folder arsip?**  
A: Iterasi setiap file dengan loop `for`, menerapkan konfigurasi `Viewer` dan `HtmlViewOptions` yang sama untuk setiap iterasi.

**Q: Di mana saya dapat mendiskusikan masalah dengan pengguna lain?**  
A: Kunjungi [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk diskusi komunitas.

## Sumber Daya

- **Dokumentasi:** Selami lebih dalam fungsionalitas dengan [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referensi API:** Jelajahi API lengkap di [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Unduh:** Dapatkan binary terbaru dari [download page](https://releases.groupdocs.com/viewer/java/).  
- **Pembelian dan lisensi:** Tinjau opsi pada [purchase page](https://purchase.groupdocs.com/buy).  
- **Dukungan dan komunitas:** Bergabung dalam diskusi di [support forum](https://forum.groupdocs.com/c/viewer/9).  
- **Forum GroupDocs:** Akses bantuan komunitas di [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Terakhir Diperbarui:** 2026-10-10  
**Diuji Dengan:** GroupDocs.Viewer 25.2  
**Penulis:** GroupDocs

## Tutorial Terkait

- [Cara mengonversi zip ke HTML dan merender folder zip di Java dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [mengonversi zip ke pdf dengan GroupDocs.Viewer Java - Nama File Kustom](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Cara Mengonversi DOCX ke HTML Menggunakan GroupDocs.Viewer untuk Java: Panduan Langkah‑per‑Langkah](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}