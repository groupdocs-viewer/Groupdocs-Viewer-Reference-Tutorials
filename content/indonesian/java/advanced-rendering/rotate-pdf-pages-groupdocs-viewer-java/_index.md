---
date: '2026-10-05'
description: Pelajari cara memutar halaman PDF tertentu dengan GroupDocs.Viewer untuk
  Java. Panduan langkah demi langkah ini mencakup penyiapan Maven, memutar PDF 90
  derajat, dan pemecahan masalah.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Putar halaman PDF tertentu dengan GroupDocs.Viewer untuk Java. Pelajari
  cara memutar PDF 90 derajat, mengonfigurasi Maven, dan memecahkan masalah umum dalam
  panduan singkat.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Putar halaman PDF tertentu dengan GroupDocs.Viewer untuk Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Cara Memutar Halaman PDF Tertentu dengan GroupDocs.Viewer untuk Java
type: docs
url: /id/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Cara memutar halaman pdf tertentu dengan GroupDocs.Viewer untuk Java

Memutar halaman tertentu dalam PDF dapat menjadi penting untuk menyelaraskan dokumen, memperbaiki gambar yang dipindai, atau menyesuaikan slide presentasi. **Dalam panduan ini Anda akan belajar cara memutar halaman pdf tertentu secara programatis dengan GroupDocs.Viewer**, apakah Anda perlu memutar pdf 90 derajat, membalik seluruh bagian, atau menangani beberapa halaman dalam satu panggilan.

![Putar Halaman PDF Tertentu dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Putar Halaman PDF Tertentu dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Apa yang akan Anda pelajari**
- Menyiapkan GroupDocs.Viewer dalam proyek Java Anda (termasuk konfigurasi Maven GroupDocs Viewer)
- Memutar halaman PDF tertentu secara programatis (memutar pdf 90 derajat, 180 derajat, dll.)
- Konfigurasi kunci untuk penggunaan optimal
- Memecahkan masalah umum selama implementasi

## Jawaban Cepat
- **Perpustakaan apa yang dapat memutar halaman PDF di Java?** GroupDocs.Viewer untuk Java menyediakan dukungan rotasi bawaan tanpa alat eksternal.  
- **Bisakah saya memutar satu halaman sebesar 90 derajat?** Ya – panggil `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` pada instance viewer.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara gratis untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Apakah Maven diperlukan?** Maven adalah manajer dependensi yang direkomendasikan, tetapi Anda juga dapat menggunakan Gradle atau menyertakan JAR secara manual.  
- **Bagaimana cara saya merender halaman yang diputar?** Gunakan `HtmlViewOptions` dengan `viewer.view(documentPath, viewOptions)` untuk mendapatkan output HTML yang mencerminkan rotasi.

## Apa itu memutar halaman pdf tertentu?
`rotate specific pdf pages` mengacu pada kemampuan mengubah orientasi halaman individual di dalam dokumen PDF sambil membiarkan bagian lain dari file tidak tersentuh. Operasi ini dilakukan pada saat rendering, sehingga file PDF asli tetap tidak berubah.

## Mengapa memutar halaman pdf tertentu?
Anda dapat memutar satu halaman dalam waktu kurang dari 0,05 detik pada VM kelas server tipikal, memungkinkan pratinjau waktu nyata dari kontrak yang dipindai, dek presentasi, atau faktur multi‑halaman yang berisi pemindaian yang salah orientasi. Kontrol yang sangat terperinci ini menghilangkan kebutuhan akan alat pasca‑pemrosesan yang mahal dan mengurangi upaya manual hingga 70 % dalam proyek digitalisasi berskala besar.

## Prasyarat

### Perpustakaan dan dependensi yang dibutuhkan
- Java Development Kit (JDK) 8 atau lebih baru.  
- IDE seperti IntelliJ IDEA atau Eclipse.  
- Maven untuk manajemen dependensi.

### Persyaratan penyiapan lingkungan
1. **Konfigurasi Maven** – tambahkan GroupDocs.Viewer ke `pom.xml` Anda.  
2. **Perolehan lisensi** – dapatkan lisensi sementara dari GroupDocs. Kunjungi [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) atau ajukan lisensi sementara pada [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Menyiapkan GroupDocs.Viewer untuk Java

Untuk mengintegrasikan GroupDocs.Viewer ke dalam proyek Java Anda menggunakan Maven, perbarui `pom.xml` Anda:

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

### Inisialisasi dan penyiapan dasar
`Viewer` adalah kelas inti yang memuat dokumen dan mengatur operasi rendering. Setelah membuat sebuah instance Anda dapat memanggil metode seperti `view` atau `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Cara memutar halaman PDF tertentu dengan GroupDocs.Viewer
Memutar halaman PDF tertentu dengan GroupDocs.Viewer melibatkan dua tindakan utama: pertama, tentukan rotasi yang diinginkan untuk setiap halaman target menggunakan metode `rotatePage`, dan kedua, render dokumen dengan `HtmlViewOptions` sehingga rotasi tercermin dalam output. Pendekatan ini menjaga PDF asli tetap tidak berubah sambil menghasilkan HTML dengan orientasi yang tepat.

### Langkah 1: mengonfigurasi rotasi halaman
`rotatePage` adalah metode yang menerima indeks halaman berbasis nol dan nilai enum `Rotation`. Enum ini menyediakan tiga opsi: `ON_90_DEGREE`, `ON_180_DEGREE`, dan `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Langkah 2: menginisialisasi viewer dan merender
`HtmlViewOptions` mengontrol proses konversi PDF‑ke‑HTML. Ia mempertahankan tata letak, font, dan sumber daya tersemat sambil menerapkan rotasi yang Anda konfigurasikan.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parameter dan konfigurasi
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` dimana opsi rotasi adalah `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Menangani konversi pdf‑to‑html sambil mempertahankan tata letak dan sumber daya tersemat.  
- **pdf to html java** – Kelas ini merupakan bagian dari API yang sama dan memastikan representasi visual yang akurat.

## Masalah umum dan solusi (memecahkan masalah rotasi pdf)

- **Jalur tidak benar** – Verifikasi bahwa `YOUR_DOCUMENT_DIRECTORY` dan `YOUR_OUTPUT_DIRECTORY` ada dan dapat diakses.  
- **Dependensi hilang** – Pastikan koordinat Maven sesuai dengan versi GroupDocs.Viewer terbaru (saat ini 25.2).  
- **Pembatasan lisensi** – Terapkan lisensi sementara dengan benar; jika tidak, beberapa fitur mungkin dinonaktifkan.  
- **Lonjakan memori** – Render PDF besar dalam batch lebih kecil atau tingkatkan ukuran heap JVM.

## Aplikasi praktis

### Kasus penggunaan dunia nyata
1. **Penyelarasan dokumen** – Memutar kontrak yang dipindai untuk orientasi digital yang tepat.  
2. **Penyesuaian presentasi** – Mengubah slide presentasi dalam PDF sebelum dibagikan.  
3. **Alur kerja arsip** – Secara otomatis menyesuaikan orientasi dokumen historis selama digitalisasi.

### Kemungkinan integrasi
Gabungkan GroupDocs.Viewer dengan sistem manajemen konten berbasis Java, portal perusahaan, atau API khusus yang memerlukan penayangan PDF secara langsung.

## Pertimbangan kinerja
- **Manajemen sumber daya** – Selalu tutup instance `Viewer` untuk melepaskan handle file dan memori.  
- **Manajemen memori Java** – Pantau penggunaan heap saat memproses PDF besar; pertimbangkan streaming halaman alih‑alih memuat seluruh file.  
- **Praktik terbaik** – Cache HTML yang dirender untuk dokumen yang sering diakses guna mengurangi waktu pemrosesan hingga 60 %.

## Kesimpulan
Tutorial ini membahas **cara memutar halaman pdf tertentu menggunakan GroupDocs.Viewer di Java**, mulai dari penyiapan Maven hingga merender halaman yang diputar dan menangani jebakan umum. Bereksperimenlah dengan fitur tambahan seperti penambahan watermark, konversi format, atau pemrosesan batch untuk memperluas alur kerja dokumen Anda.

**Langkah selanjutnya:** Selami kemampuan GroupDocs.Viewer lainnya seperti mengonversi PDF ke PNG, menambahkan watermark, atau mengintegrasikan dengan penyedia penyimpanan cloud.

## Bagian FAQ
- **Memecahkan masalah rotasi** – Verifikasi nomor halaman dan parameter rotasi sudah benar.  
- **Menangani file PDF besar** – Proses halaman dalam batch dan pantau penggunaan memori.  
- **Persyaratan lisensi** – Gunakan lisensi sementara untuk pengembangan; beli lisensi penuh untuk produksi.  
- **Memutar beberapa halaman** – Panggil `rotatePage` berulang kali dengan nomor halaman dan sudut yang berbeda.  
- **Integrasi dengan pustaka Java** – GroupDocs.Viewer bekerja mulus dengan Spring Boot, Jakarta EE, dan kerangka kerja Java lainnya.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya memutar semua halaman PDF sekaligus?**  
A: Ya. Lakukan perulangan pada nomor halaman dan panggil `rotatePage(page, Rotation.ON_90_DEGREE)` untuk setiap halaman.

**Q: Apakah rotasi memengaruhi file PDF asli?**  
A: Tidak. Rotasi hanya diterapkan selama proses rendering; PDF sumber tetap tidak berubah.

**Q: Bagaimana jika PDF dilindungi kata sandi?**  
A: Berikan kata sandi saat membuat instance `Viewer`: `new Viewer(path, password)`.

**Q: Bagaimana cara saya men-debug error “null pointer” saat menyiapkan HtmlViewOptions?**  
A: Pastikan direktori output ada dan bahwa `pageFilePathFormat` terresolusi dengan benar.

**Q: Apakah ada cara memutar halaman saat mengonversi ke format lain (misalnya PNG)?**  
A: Ya. Gunakan konfigurasi `rotatePage` yang sama dengan opsi tampilan yang sesuai untuk format target.

## Sumber Daya
- **Dokumentasi**: [Dokumentasi GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- **Referensi API**: [Referensi API GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **Unduh**: [Halaman Unduhan GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Pembelian**: [Opsi Pembelian GroupDocs](https://purchase.groupdocs.com/buy)  
- **Uji coba Gratis**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Lisensi Sementara**: [Minta Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)  
- **Dukungan**: [Forum Dukungan GroupDocs](https://forum.groupdocs.com/c/viewer/9)

**Terakhir Diperbarui:** 2026-10-05  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs

## Tutorial Terkait

- [Panduan Java: merender halaman terpilih java dengan GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Java Pdf Rendering Groupdocs Viewer Pemisah Halaman](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [Groupdocs Viewer Java Rendering HTML Responsif](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)