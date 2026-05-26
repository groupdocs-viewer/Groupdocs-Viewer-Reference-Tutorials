---
date: '2026-02-23'
description: Pelajari cara mengonversi IGS ke PDF, HTML, JPG, dan PNG dengan GroupDocs.Viewer
  untuk Java. Ikuti panduan langkah demi langkah ini dengan contoh kode siap dijalankan.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Konversi IGS ke PDF, HTML, JPG & PNG menggunakan GroupDocs.Viewer Java
type: docs
url: /id/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convert IGS ke PDF, HTML, JPG & PNG menggunakan GroupDocs.Viewer Java

Jika Anda perlu **mengonversi IGS ke PDF** (atau ke HTML, JPG, PNG) langsung dari aplikasi Java, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas semua yang Anda perlukan—dari menyiapkan pustaka hingga merender model 3‑D dalam format yang sesuai dengan proyek Anda. Anda akan melihat mengapa GroupDocs.Viewer adalah pilihan yang solid untuk konversi cepat dan andal serta mendapatkan contoh kode yang dapat langsung Anda gunakan dalam solusi Anda.

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Jawaban Cepat
- **Apakah saya dapat mengonversi IGS ke PDF dengan Java?** Ya, menggunakan `PdfViewOptions` milik GroupDocs.Viewer.  
- **Format output apa yang didukung?** HTML, JPG, PNG, dan PDF.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan; versi percobaan gratis tersedia untuk pengujian.  
- **Versi Java apa yang dibutuhkan?** JDK 8 atau lebih tinggi.  
- **Apakah Maven satu‑satunya cara menambahkan pustaka?** Tidak, Anda juga dapat menggunakan Gradle atau menambahkan JAR secara manual.

## Apa itu “convert IGS to PDF”?
Mengonversi IGS (format file netral untuk data CAD 3‑D) ke PDF berarti mengubah model 3‑D yang kompleks menjadi dokumen statis yang dapat dilihat secara luas. Ini berguna untuk berbagi desain dengan pemangku kepentingan yang tidak memiliki alat CAD.

## Mengapa menggunakan GroupDocs.Viewer untuk konversi IGS?
- **Rendering CAD tanpa kode** – pustaka menangani parsing format IGS secara otomatis.  
- **Berbagai pilihan output** – satu panggilan API dapat menghasilkan HTML, JPG, PNG, atau PDF.  
- **Cross‑platform** – bekerja pada sistem operasi apa pun yang mendukung Java.  
- **Berfokus pada performa** – rendering cepat bahkan untuk assembly besar.

## Prasyarat
- **GroupDocs.Viewer untuk Java** ≥ 25.2  
- **JDK 8+** terpasang dan terkonfigurasi di IDE Anda (IntelliJ IDEA, Eclipse, NetBeans, dll.)  
- Pengetahuan dasar Maven (opsional tetapi disarankan)

## Menyiapkan GroupDocs.Viewer untuk Java

### Dependensi Maven
Tambahkan repositori GroupDocs dan dependensi Viewer ke file `pom.xml` Anda:

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
GroupDocs.Viewer menawarkan:
- **Percobaan gratis** – penggunaan terbatas, cocok untuk pengujian cepat.  
- **Lisensi sementara** – semua fitur tersedia untuk periode evaluasi singkat.  
- **Lisensi komersial** – penggunaan produksi tanpa batas.

### Inisialisasi Viewer Dasar
Potongan kode di bawah ini menunjukkan cara membuat instance `Viewer` yang menunjuk ke file IGS Anda:

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

### Bagaimana cara mengonversi IGS ke HTML?
Output HTML memberi Anda tampilan interaktif yang ramah browser untuk model 3‑D.

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

**Poin penting:** `HtmlViewOptions.forEmbeddedResources()` menyematkan semua aset yang diperlukan (CSS, gambar) langsung ke dalam file HTML, sehingga file menjadi portabel.

## Merender IGS ke JPG

### Bagaimana cara mengonversi IGS ke JPG?
Gambar JPG sempurna untuk thumbnail atau pratinjau cepat.

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

Anda dapat menyesuaikan `JpgViewOptions` untuk mengontrol resolusi dan kualitas kompresi.

## Merender IGS ke PNG

### Bagaimana cara mengonversi IGS ke PNG?
PNG mendukung transparansi, yang berguna untuk menumpangkan model pada latar belakang yang berbeda.

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

Bereksperimenlah dengan `PngViewOptions` untuk mendapatkan keseimbangan terbaik antara ukuran file dan fidelitas visual.

## Merender IGS ke PDF

### Bagaimana cara mengonversi IGS ke PDF?
PDF adalah format utama untuk berbagi dokumentasi desain detail. Bagian ini secara langsung menjawab kata kunci utama **convert IGS to PDF**.

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

`PdfViewOptions` memungkinkan Anda mengontrol tata letak halaman, kualitas gambar, dan apakah akan menyematkan font.

## Aplikasi Praktis

- **Portal web** – sematkan model yang dirender dalam HTML langsung ke konfigurator produk.  
- **Aset pemasaran** – hasilkan gambar JPG/PNG resolusi tinggi untuk brosur.  
- **Dokumentasi teknis** – sertakan render PDF model CAD dalam manual pengguna.  
- **Jaminan kualitas** – otomatisasi pembuatan thumbnail untuk batch besar file IGS.

## Masalah Umum & Solusinya

| Masalah | Solusi |
|-------|----------|
| **Folder output tidak ditemukan** | Verifikasi jalur yang diberikan ke `Path outputDirectory` dan pastikan proses Java memiliki izin menulis. |
| **Halaman kosong di PDF** | Pastikan file IGS tidak rusak; coba buka terlebih dahulu di viewer CAD. |
| **Rendering lambat untuk assembly besar** | Tingkatkan heap JVM (`-Xmx2g` atau lebih) dan pertimbangkan rendering per halaman menggunakan `viewer.getPageCount()` bila diperlukan. |
| **Font hilang di PDF** | Gunakan `PdfViewOptions` untuk menyematkan font yang diperlukan atau instal font yang hilang di server. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya mengonversi beberapa file IGS dalam satu kali proses?**  
J: Ya. Lakukan iterasi pada daftar jalur file dan panggil metode `view` yang sesuai untuk masing‑masing.

**T: Apakah memungkinkan menyesuaikan ukuran halaman PDF?**  
J: Tentu. `PdfViewOptions` menyediakan `setPageSize(PageSize.A4)` dan metode serupa lainnya.

**T: Apakah saya memerlukan lisensi terpisah untuk setiap format output?**  
J: Tidak. Satu lisensi GroupDocs.Viewer mencakup semua format yang didukung.

**T: Seberapa besar file IGS sebelum performa menurun?**  
J: Pustaka dapat menangani file hingga ratusan megabyte, namun Anda mungkin perlu menambah memori JVM untuk model yang sangat besar.

**T: Bisakah saya merender hanya tampilan atau orientasi tertentu?**  
J: GroupDocs.Viewer merender tampilan default. Untuk orientasi khusus, pra‑proses file IGS dengan alat CAD sebelum konversi.

---

**Terakhir Diperbarui:** 2026-02-23  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs