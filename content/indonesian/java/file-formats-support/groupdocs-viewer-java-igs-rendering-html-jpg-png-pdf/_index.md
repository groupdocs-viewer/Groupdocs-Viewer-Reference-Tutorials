---
date: '2026-08-08'
description: Pelajari cara mengonversi IGS ke PDF, HTML, JPG, dan PNG menggunakan
  GroupDocs.Viewer untuk Java. Panduan langkah demi langkah, prasyarat, dan pemecahan
  masalah untuk pengembang Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Konversi IGS ke PDF, HTML, JPG, dan PNG menggunakan GroupDocs.Viewer
  untuk Java. Penyiapan terperinci, contoh kode, dan pemecahan masalah untuk pengembang
  Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Konversi IGS ke PDF, HTML, JPG & PNG dengan GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Konversi IGS ke PDF, HTML, JPG & PNG dengan GroupDocs.Viewer Java
type: docs
url: /id/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Konversi IGS ke PDF, HTML, JPG & PNG dengan GroupDocs.Viewer Java

Jika Anda perlu **mengkonversi IGS ke PDF** (atau ke HTML, JPG, PNG) langsung dari aplikasi Java, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas semua yang Anda butuhkan—mulai dari menginstal pustaka hingga merender model 3‑D dalam format yang sesuai dengan proyek Anda. Anda akan memahami mengapa GroupDocs.Viewer adalah pilihan yang solid untuk konversi cepat dan andal serta Anda akan mendapatkan cuplikan kode siap‑jalankan yang dapat Anda sisipkan ke dalam solusi Anda.

![Konversi File IGS ke HTML, JPG, PNG, dan PDF dengan GroupDocs.Viewer untuk Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Jawaban Cepat
- **Bisakah saya mengkonversi IGS ke PDF dengan Java?** Ya, gunakan `PdfViewOptions` bersama dengan API `Viewer`.  
- **Format output apa yang didukung?** HTML, JPG, PNG, dan PDF semuanya ditangani secara native.  
- **Apakah saya memerlukan lisensi untuk produksi?** Diperlukan lisensi komersial; percobaan gratis memungkinkan Anda menguji fitur inti.  
- **Versi Java apa yang diperlukan?** JDK 8 atau lebih tinggi; pustaka juga berjalan pada Java 11, 17, dan versi selanjutnya.  
- **Apakah Maven satu‑satunya cara untuk menambahkan pustaka?** Tidak, Anda juga dapat menggunakan Gradle atau menambahkan file JAR secara manual ke classpath Anda.

## Apa itu konversi IGS ke PDF?
Mengkonversi IGS ke PDF berarti mengubah file CAD 3‑D netral menjadi dokumen statis yang dapat dilihat secara universal. Ini memungkinkan Anda berbagi visual desain dengan pemangku kepentingan yang tidak memiliki alat CAD, menyematkan rendering dalam laporan, atau mengarsipkan model untuk keperluan kepatuhan.

## Mengapa menggunakan GroupDocs.Viewer untuk konversi IGS?
GroupDocs.Viewer memproses file IGS tanpa memerlukan perangkat lunak CAD eksternal. Ia mendukung **lebih dari 50 format input dan output**, dapat merender rakitan yang berisi **ratusan bagian** sambil menjaga penggunaan memori di bawah **200 MB**, dan memberikan hasil dalam waktu kurang dari **2 detik** untuk model tipikal pada server standar. Manfaat terukur ini menjadikannya pilihan berperforma tinggi dan biaya‑efektif untuk alur kerja perusahaan.

## Prasyarat
- **GroupDocs.Viewer for Java** ≥ 25.2 (rilisan stabil terbaru).  
- **JDK 8+** terinstal dan dikonfigurasi di IDE Anda (IntelliJ IDEA, Eclipse, NetBeans, dll.).  
- Pengetahuan dasar Maven (opsional tetapi disarankan untuk manajemen dependensi).  

## Menyiapkan GroupDocs.Viewer untuk Java

### Dependensi Maven
Tambahkan repositori GroupDocs dan dependensi Viewer ke `pom.xml` Anda:

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
GroupDocs.Viewer menawarkan tiga opsi lisensi:
- **Free trial** – penggunaan terbatas, sempurna untuk pengujian proof‑of‑concept cepat.  
- **Temporary license** – set fitur lengkap untuk periode evaluasi singkat, ideal untuk proyek pilot.  
- **Commercial license** – penggunaan produksi tanpa batas, termasuk dukungan prioritas dan pembaruan.

### Inisialisasi viewer dasar
Kelas `Viewer` adalah titik masuk untuk semua operasi rendering. Ia memuat file sumber, mengurai format, dan menyediakan metode untuk menghasilkan output yang diinginkan.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Merender IGS ke HTML

### Cara mengkonversi IGS ke HTML?
Muat file IGS dengan instance `Viewer` dan berikan objek `HtmlViewOptions` yang menyematkan semua aset yang diperlukan. Panggilan tersebut mengembalikan satu file HTML yang berisi tampilan 3‑D lengkap, memudahkan penyematan ke halaman web. Anda juga dapat menyesuaikan rendering dengan mengatur opsi seperti ukuran halaman, warna latar belakang, dan apakah menyertakan kontrol interaktif.  
HtmlViewOptions mengonfigurasi cara output HTML dihasilkan, termasuk penyematan sumber daya dan tata letak halaman.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Merender IGS ke JPG

### Cara mengkonversi IGS ke JPG?
Buat objek `JpgViewOptions`, konfigurasikan resolusi dan kualitas kompresi yang diinginkan, dan biarkan `Viewer` menghasilkan gambar raster untuk setiap halaman model. File JPG yang dihasilkan dapat disimpan ke direktori yang ditentukan, dan Anda dapat menyesuaikan parameter kualitas untuk menyeimbangkan ukuran file dengan fidelitas visual, yang berguna untuk thumbnail atau cetakan resolusi tinggi.  
JpgViewOptions menentukan pengaturan untuk pembuatan gambar JPG seperti resolusi, kualitas, dan direktori output.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Merender IGS ke PNG

### Cara mengkonversi IGS ke PNG?
Kelas `PngViewOptions` memungkinkan Anda menghasilkan gambar lossless dengan transparansi opsional. Format ini ideal untuk menumpangkan model pada latar belakang berwarna dalam materi pemasaran. Anda juga dapat menentukan resolusi dan warna latar belakang agar sesuai dengan pedoman merek Anda, memastikan tampilan konsisten di semua aset yang dihasilkan.  
PngViewOptions mendefinisikan parameter untuk rendering PNG, termasuk resolusi, transparansi, dan warna latar belakang.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Merender IGS ke PDF

### Cara mengkonversi IGS ke PDF?
Gunakan `PdfViewOptions` untuk menghasilkan PDF berhalaman yang mempertahankan tata letak visual model 3‑D. Anda juga dapat menyematkan font dan mengontrol ukuran halaman untuk memenuhi pedoman merek perusahaan. Pengaturan tambahan memungkinkan Anda menentukan kualitas gambar, tingkat kompresi, dan apakah menyertakan daftar isi untuk rakitan multi‑halaman.  
PdfViewOptions mengontrol pembuatan PDF, memungkinkan konfigurasi ukuran halaman, kualitas gambar, dan penyematan font.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Aplikasi Praktis
- **Web portals** – sematkan model yang dirender HTML langsung ke dalam konfigurator produk, memungkinkan pelanggan memutar dan memperbesar tanpa menginstal plugin.  
- **Marketing assets** – hasilkan gambar JPG/PNG resolusi tinggi untuk brosur, presentasi slide, dan posting media sosial.  
- **Technical documentation** – sertakan rendering PDF model CAD dalam manual pengguna, memastikan insinyur dapat melihat desain secara offline.  
- **Quality assurance** – otomatisasi pembuatan thumbnail untuk ribuan file IGS, mempercepat alur kerja inspeksi visual.

## Masalah umum & solusi

| Issue | Solution |
|-------|----------|
| **Folder output tidak ditemukan** | Verifikasi jalur yang diberikan ke `Path outputDirectory` dan pastikan proses Java memiliki izin menulis pada direktori target. |
| **Halaman kosong dalam PDF** | Pastikan file IGS sumber tidak rusak; buka terlebih dahulu di viewer CAD native. |
| **Rendering lambat untuk rakitan besar** | Tingkatkan heap JVM (`-Xmx2g` atau lebih) dan pertimbangkan rendering halaman per halaman menggunakan `viewer.getPageCount()` untuk memproses dalam potongan. |
| **Font hilang dalam PDF** | Gunakan `PdfViewOptions` untuk menyematkan font yang diperlukan atau instal font yang hilang pada server yang menyelenggarakan layanan konversi. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya mengkonversi beberapa file IGS dalam satu kali jalankan?**  
A: Ya. Iterasi koleksi jalur file dan panggil metode `view` yang sesuai untuk setiap file dalam instance `Viewer` yang sama.

**Q: Apakah memungkinkan untuk menyesuaikan ukuran halaman PDF?**  
A: Tentu saja. `PdfViewOptions` menawarkan `setPageSize(PageSize.A4)`, `PageSize.Letter`, dan dimensi khusus melalui `setCustomSize(width, height)`.

**Q: Apakah saya memerlukan lisensi terpisah untuk setiap format output?**  
A: Tidak. Satu lisensi GroupDocs.Viewer mencakup semua format yang didukung, termasuk HTML, JPG, PNG, dan PDF.

**Q: Seberapa besar file IGS dapat sebelum kinerja menurun?**  
A: Pustaka ini dapat memproses file hingga **500 MB** secara andal; untuk model lebih besar dari 200 MB, alokasikan memori JVM tambahan dan pertimbangkan rendering dalam batch.

**Q: Bisakah saya merender hanya tampilan atau orientasi tertentu?**  
A: GroupDocs.Viewer merender orientasi default yang didefinasikan dalam file IGS. Untuk tampilan khusus, pra‑proses file dengan alat CAD atau sesuaikan model sebelum konversi.

---

**Terakhir diperbarui:** 2026-08-08  
**Diuji dengan:** GroupDocs.Viewer 25.2 for Java  
**Penulis:** GroupDocs

## Tutorial Terkait

- [konversi cdr ke html, jpg, png, pdf dengan GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Cara mengkonversi pdf ke html dan mengoptimalkan kualitas gambar di Java dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)