---
date: '2026-08-03'
description: Pelajari cara mengonversi zip ke html menggunakan GroupDocs.Viewer Java,
  mengatur item per halaman, menyematkan sumber daya html, dan mengonversi arsip secara
  batch dengan efisien.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Pelajari cara mengonversi zip ke html menggunakan GroupDocs.Viewer
  Java, mengatur item per halaman, menyematkan sumber daya html, dan mengonversi arsip
  secara batch dengan efisien. Ikuti step‑by‑step code dan performance tips.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Konversi zip ke html dan atur item per halaman dengan GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
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

# Mengonversi zip ke html dan mengatur item per halaman dengan GroupDocs.Viewer Java

Dalam banyak aplikasi web Anda perlu menampilkan isi arsip ZIP atau RAR langsung di peramban. Dengan GroupDocs.Viewer untuk Java Anda dapat **mengonversi zip ke html** dalam satu langkah, mengontrol berapa banyak entri arsip yang muncul di setiap halaman, menyematkan semua gambar dan CSS pendukung, dan bahkan memproses batch puluhan arsip. Tutorial ini memandu Anda melalui alur kerja lengkap, mulai dari penyiapan Maven hingga rendering multi‑halaman, dan menjelaskan mengapa setiap pengaturan penting untuk kinerja dan kegunaan.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Jawaban Cepat
- **Apa yang dikontrol oleh “set items per page”?** Itu menentukan berapa banyak file atau folder dari sebuah arsip yang muncul pada setiap halaman HTML yang dihasilkan.  
- **Apakah saya dapat menyematkan gambar dan CSS langsung di HTML?** Ya – gunakan opsi `forEmbeddedResources` untuk menyematkan sumber daya HTML.  
- **Apakah konversi batch memungkinkan?** Tentu saja; Anda dapat melakukan loop pada koleksi arsip dan merender masing‑masing dengan pengaturan yang sama.  
- **Apakah saya memerlukan Maven untuk menggunakan GroupDocs.Viewer?** Ya, tambahkan dependensi Maven `groupdocs-viewer` seperti yang ditunjukkan di bawah.  
- **Format output apa yang didukung?** HTML satu‑halaman dan HTML multi‑halaman keduanya tersedia, dan perpustakaan mendukung lebih dari 50 tipe arsip input.

## Apa itu “set items per page” di GroupDocs.Viewer?
Pengaturan **set items per page** termasuk dalam opsi rendering arsip. Ini memberi tahu viewer berapa banyak entri arsip (file atau folder) yang harus ditampilkan pada setiap halaman HTML ketika Anda menghasilkan dokumen HTML multi‑halaman. Menyesuaikan nilai ini membantu Anda menyeimbangkan ukuran halaman dan kecepatan navigasi, terutama untuk arsip besar.

## Mengapa menyematkan sumber daya html?
Menyematkan sumber daya (gambar, CSS, font) langsung di dalam file HTML menghasilkan satu dokumen portabel yang dapat dibuka tanpa file eksternal. Ini ideal untuk lampiran email, tampilan offline, atau menyematkan output ke halaman web lain. Pendekatan ini juga menyederhanakan penyebaran karena tidak ada jalur aset eksternal yang perlu dikelola.

## Prasyarat

- **Perpustakaan yang diperlukan:** Sertakan GroupDocs.Viewer versi 25.2 atau lebih baru.  
- **Lingkungan:** Java Development Kit (JDK) terpasang dan dikonfigurasi.  
- **Pengetahuan:** Java dasar dan manajemen dependensi Maven.  

## Penyiapan Maven GroupDocs Viewer

Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer menawarkan **tautan percobaan gratis**, lisensi sementara, atau opsi pembelian penuh. Pilih yang sesuai dengan jadwal proyek Anda.

### Inisialisasi Dasar
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cara merender arsip ke html satu‑halaman
Viewer adalah kelas inti yang memuat dokumen atau arsip untuk dirender.

Untuk menghasilkan satu file HTML yang berisi seluruh arsip, buat instance `Viewer` untuk file ZIP dan gunakan `HtmlViewOptions.forEmbeddedResources()` untuk menyematkan semua gambar, CSS, dan font. Merender arsip dengan opsi ini menghasilkan satu halaman mandiri yang cocok untuk email atau penggunaan offline.

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
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Langkah 5: Render sebagai satu halaman
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cara merender arsip ke html multi‑halaman dan mengatur item per halaman
`HtmlViewOptions` mengonfigurasi cara viewer merender output HTML, termasuk paginasi dan penyematan sumber daya.

Untuk membagi arsip menjadi beberapa halaman, buat `HtmlViewOptions.forEmbeddedResources()` dan atur ukuran halaman yang diinginkan dengan `options.setItemsPerPage(20)`. Viewer akan menghasilkan file HTML terpisah, masing‑masing menampilkan hingga jumlah entri yang ditentukan, yang meningkatkan navigasi untuk arsip besar dan memastikan pemuatan lebih cepat.

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
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Aplikasi Praktis

- **Sistem manajemen dokumen:** Tambahkan fungsi pratinjau arsip tanpa menginstal viewer tambahan.  
- **Portal web:** Tawarkan pengguna cara cepat tanpa unduhan untuk menjelajahi dokumen yang digabungkan.  
- **Alat kolaborasi:** Biarkan tim memeriksa arsip bersama langsung di peramban.

## Pertimbangan Kinerja

- **Manajemen sumber daya:** Jaga penggunaan memori tetap rendah dengan memproses arsip dalam aliran; viewer dapat menangani arsip hingga 500 MB tanpa memuat seluruh file ke memori.  
- **Konversi batch arsip:** Loop melalui daftar file arsip dan panggil logika rendering yang sama untuk memaksimalkan throughput.  
- **Strategi caching:** Simpan HTML yang dirender dalam cache jika arsip yang sama sering diakses, mengurangi waktu pemrosesan ulang hingga 70 %.

## Pertanyaan yang Sering Diajukan

**Q: Apa itu GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java adalah perpustakaan sisi‑server yang merender lebih dari 50 format dokumen dan arsip—termasuk ZIP dan RAR—ke dalam file HTML, PDF, atau gambar tanpa memerlukan aplikasi eksternal.

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

## Sumber Daya

- **Dokumentasi:** Selami lebih dalam fungsionalitas dengan [dokumentasi GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Referensi API:** Jelajahi API lengkap di [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Unduh:** Dapatkan binari terbaru dari [halaman unduhan](https://releases.groupdocs.com/viewer/java/).  
- **Pembelian dan lisensi:** Tinjau opsi pada [halaman pembelian](https://purchase.groupdocs.com/buy).  
- **Dukungan dan komunitas:** Bergabung dalam diskusi di [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Terakhir Diperbarui:** 2026-08-03  
**Diuji Dengan:** GroupDocs.Viewer 25.2  
**Penulis:** GroupDocs

## Tutorial Terkait

- [Cara mengonversi zip ke HTML dan merender folder zip di Java dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [mengonversi zip ke pdf dengan GroupDocs.Viewer Java - Nama File Kustom](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Cara Mengonversi DOCX ke HTML Menggunakan GroupDocs.Viewer untuk Java: Panduan Langkah‑per‑Langkah](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)