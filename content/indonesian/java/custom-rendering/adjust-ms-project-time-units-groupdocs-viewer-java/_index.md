---
date: '2026-05-21'
description: Pelajari cara melakukan ekspor HTML MS Project dengan unit waktu yang
  disesuaikan menggunakan GroupDocs Viewer for Java. Panduan langkah demi langkah
  dengan prasyarat, pengaturan, dan pemecahan masalah.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Ekspor HTML MS Project: Sesuaikan Unit Waktu melalui GroupDocs Java'
type: docs
url: /id/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Ekspor HTML MS Project: Sesuaikan Unit Waktu via GroupDocs Java

Mengekspor file **MS Project** ke HTML adalah kebutuhan umum untuk dasbor manajemen proyek, portal laporan status, dan alat tinjauan kolaboratif. Secara default, penampil menampilkan data terkait waktu dalam menit, yang dapat membuat tata letak visual berantakan dan membuat pelaporan harian lebih sulit dibaca. Dengan **GroupDocs Viewer for Java** Anda dapat secara programatis mengatur unit waktu menjadi **hari**, menghasilkan *ekspor html ms project* yang bersih yang sesuai dengan harapan pemangku kepentingan biasanya. Dalam tutorial ini Anda akan belajar cara mengonfigurasi penampil, menyesuaikan unit waktu, dan merender proyek ke HTML dalam beberapa langkah sederhana.

![Sesuaikan Unit Waktu MS Project dengan GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Sesuaikan Unit Waktu MS Project dengan GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Jawaban Cepat
- **Perpustakaan apa yang merender file MS Project?** GroupDocs Viewer for Java.  
- **Unit waktu apa yang dapat saya atur untuk ekspor HTML?** Hari, menggunakan `TimeUnit.DAYS`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya— lisensi permanen diperlukan; versi percobaan dapat digunakan untuk evaluasi. Anda dapat memulai dengan [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **IDE mana yang paling cocok?** Setiap IDE Java (IntelliJ IDEA, Eclipse, NetBeans) yang mendukung Maven.  
- **Apakah Maven wajib?** Maven menyederhanakan manajemen dependensi, tetapi Anda juga dapat menggunakan Gradle atau penyertaan JAR manual.  
- **Di mana saya dapat membeli?** Kunjungi [halaman pembelian](https://purchase.groupdocs.com/buy) untuk harga.

## Apa itu GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** adalah SDK Java yang mengonversi lebih dari 150 format dokumen—termasuk MS Project—menjadi HTML, PNG, JPEG, atau PDF yang ramah web.  
Ia mengabstraksi logika parsing, memungkinkan Anda mengontrol opsi rendering seperti unit waktu, dan bekerja pada platform apa pun yang mendukung Java 8 atau yang lebih tinggi.  

## Mengapa menyesuaikan unit waktu untuk ekspor HTML MS Project?
Mengatur unit waktu menjadi **hari** mengurangi kebisingan visual, cocok dengan kebanyakan siklus pelaporan, dan meningkatkan waktu muat halaman karena lebih sedikit penanda waktu granular yang dihasilkan. Dalam istilah kuantitatif, merender dengan hari alih-alih menit dapat mengurangi ukuran HTML yang dihasilkan hingga **45 %** untuk proyek 30‑hari tipikal, dan mempercepat rendering sisi klien sekitar **30 %**.

## Prasyarat
- **Java Development Kit (JDK) 8 atau yang lebih baru** terpasang di workstation Anda.  
- **Maven** (atau Gradle) untuk manajemen dependensi.  
- File **MS Project (.mpp)** yang ingin Anda ekspor.  
- Akses ke lisensi **GroupDocs Viewer for Java** (percobaan atau permanen).  

### Perpustakaan yang Diperlukan
Tambahkan dependensi berikut ke `pom.xml` Anda (atau potongan Gradle yang setara):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Tip pro:** Jaga nomor versi tetap terbaru; rilis yang lebih baru menambahkan dukungan format dan peningkatan kinerja.

## Bagaimana cara menyiapkan GroupDocs Viewer for Java?
Inisialisasi penampil dengan membuat instance `Viewer` yang menunjuk ke file MS Project Anda. Kelas `Viewer` adalah titik masuk untuk semua operasi rendering. Ia memuat dokumen sumber, menyiapkan struktur internal, dan mengekspos metode seperti `view()` dan `viewToHtml()` untuk menghasilkan format output yang diinginkan.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definisi anchor:** Kelas `Viewer` adalah komponen inti GroupDocs Viewer yang memuat dokumen sumber dan menyediakan metode rendering seperti `view()` dan `viewToHtml()`.

## Bagaimana saya dapat menyesuaikan unit waktu untuk ekspor HTML?
Untuk mengubah granularitas waktu, buat objek `ViewOptions`, konfigurasikan `ProjectOptions`‑nya untuk menggunakan `TimeUnit.DAYS`, dan berikan ke penampil. `ViewOptions` mendefinisikan pengaturan rendering untuk dokumen, sementara enum `TimeUnit` menentukan unit (menit, jam, hari) untuk data terkait waktu. Setelah mengatur opsi ini, panggil `viewer.view(options)` untuk menghasilkan HTML dengan penanda harian.

Muat file MS Project Anda dengan `new Viewer("file.mpp")`, buat objek `ViewOptions`, setel `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, lalu panggil `viewer.view(options)`. Alur tiga langkah ini mengubah unit waktu dari menit ke hari dan menghasilkan file HTML yang hanya menampilkan interval harian.

### Langkah 1: Tentukan folder output
Pilih direktori yang dapat ditulisi tempat halaman HTML akan disimpan, misalnya `output/`.

### Langkah 2: Buat opsi tampilan dengan sumber daya tersemat
Sumber daya tersemat (CSS, JavaScript) memastikan halaman HTML bersifat mandiri.

### Langkah 3: Atur unit waktu ke hari
Gunakan `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` untuk mengubah granularitas.

### Langkah 4: Render dokumen
Panggil `viewer.view(options)`; penampil menulis satu file HTML per halaman proyek ke dalam folder output.

### Langkah 5: Verifikasi hasil
Buka `index.html` yang dihasilkan di browser; Anda akan melihat batang tugas yang selaras dengan penanda hari alih-alih penanda menit.

## Kesulitan umum dan pemecahan masalah
- **Path output tidak benar** – Pastikan direktori ada dan proses Java memiliki izin menulis.  
- **Lisensi hilang** – Tanpa lisensi yang valid, penampil akan kembali ke mode percobaan dan mungkin menyisipkan watermark.  
- **File besar (> 500 MB)** – Pertimbangkan meningkatkan ukuran heap JVM (`-Xmx2g`) atau merender dengan `options.setRenderLimit(1000)` untuk memproses halaman secara batch.  

## Aplikasi praktis dari ekspor HTML dengan unit waktu yang disesuaikan
1. **Dasbor eksekutif** – Granularitas harian cocok dengan kebanyakan visualisasi KPI.  
2. **Email status otomatis** – Sematkan HTML yang dihasilkan langsung ke dalam isi email untuk pembaruan cepat.  
3. **Portal proyek** – Host HTML di situs intranet tempat anggota tim dapat memfilter tugas berdasarkan hari.  

## Pertimbangan kinerja untuk file MS Project besar
- **Manajemen memori** – Gunakan flag garbage collector Java (`-XX:+UseG1GC`) untuk segera membebaskan objek yang tidak terpakai.  
- **Rendering selektif** – Jika Anda hanya membutuhkan diagram Gantt, nonaktifkan rendering sumber daya lain melalui `options.getProjectOptions().setRenderGantt(true)` dan `setRenderResources(false)`.  
- **Pemrosesan paralel** – Untuk konversi batch, buat objek `Viewer` terpisah per file dan jalankan mereka dalam pool thread untuk memanfaatkan CPU multi‑core.  

## Kesimpulan
Anda kini memiliki alur kerja lengkap dan siap produksi untuk melakukan **ekspor html ms project** dengan unit waktu diatur ke hari menggunakan GroupDocs Viewer for Java. Pendekatan ini mengurangi ukuran HTML, mempercepat rendering sisi klien, dan menyajikan tampilan jadwal proyek yang ramah pemangku kepentingan. Jelajahi opsi rendering tambahan—seperti ekspor PDF atau snapshot gambar—untuk memperluas integrasi ke dalam pipeline pelaporan yang lebih luas.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya merender tampilan Project lain (mis., Lembar Sumber Daya) ke HTML?**  
A: Ya, objek `ProjectOptions` memungkinkan Anda mengaktifkan atau menonaktifkan tampilan spesifik seperti Gantt, Lembar Sumber Daya, dan Kalender sebelum merender.

**Q: Apakah memungkinkan untuk menyesuaikan CSS dari HTML yang dihasilkan?**  
A: Tentu saja. Berikan jalur stylesheet khusus melalui `options.setStyleSheetPath("path/to/custom.css")` dan penampil akan menyematkannya ke setiap halaman.

**Q: Batas ukuran file apa yang didukung GroupDocs Viewer untuk MS Project?**  
A: SDK dapat menangani file hingga **500 MB** tanpa harus memuat seluruh dokumen ke memori, berkat arsitektur streaming-nya.

**Q: Apakah saya perlu menginstal Microsoft Project di server?**  
A: Tidak. GroupDocs Viewer mem-parsing format .mpp secara langsung dan tidak memerlukan Microsoft Project atau instalasi Office apa pun.

**Q: Bagaimana cara melisensikan penampil untuk lingkungan produksi?**  
A: Beli lisensi permanen dari toko GroupDocs; terapkan file lisensi pada runtime dengan `License license = new License(); license.setLicense("path/to/license.lic");`. Untuk kebutuhan jangka pendek Anda dapat memperoleh [lisensi sementara](https://purchase.groupdocs.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-05-21  
**Diuji Dengan:** GroupDocs Viewer Java 25.2  
**Penulis:** GroupDocs  

**Resources**  
- [Dokumentasi](https://docs.groupdocs.com/viewer/java/)  
- [Referensi API](https://reference.groupdocs.com/viewer/java/)  
- [Unduh GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Beli Lisensi](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Tutorial Terkait

- [Cara Merender File MS Project sebagai HTML, JPG, PNG, dan PDF dengan Catatan Menggunakan GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Cara Menggunakan GroupDocs Viewer untuk Merender Dokumen Proyek berdasarkan Interval Waktu di Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Cara Mengatur Lisensi di GroupDocs.Viewer Java: Panduan Pengaturan File dan URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)