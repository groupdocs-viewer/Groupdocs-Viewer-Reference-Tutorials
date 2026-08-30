---
date: '2026-08-30'
description: Pelajari cara mengonversi DWG ke PNG, mengatur warna latar belakang di
  Java, dan menyesuaikan ukuran gambar dengan GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Konversi DWG ke PNG menggunakan GroupDocs.Viewer for Java sambil mengatur
  lebar gambar khusus dan warna latar belakang. Panduan ini menyediakan langkah‑demi‑langkah,
  potongan kode, dan tips pemecahan masalah.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Konversi DWG ke PNG dengan ukuran khusus, warna latar belakang di Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Cara mengonversi DWG ke PNG dengan ukuran khusus & warna latar belakang menggunakan
  GroupDocs.Viewer for Java
type: docs
url: /id/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Cara mengonversi DWG ke PNG dengan ukuran khusus & warna latar belakang menggunakan GroupDocs.Viewer untuk Java

Dalam tutorial ini Anda akan belajar **cara mengonversi DWG ke PNG** sambil mengontrol dimensi output dan warna latar belakang, menggunakan GroupDocs.Viewer untuk Java. Baik Anda perlu menyematkan gambar CAD dalam laporan, menghasilkan thumbnail untuk portal web, atau mengotomatiskan rendering batch, langkah-langkah di bawah ini memberi Anda kontrol penuh atas tampilan visual setiap file PNG.

## Jawaban Cepat
- **Apa arti “convert DWG to PNG”?** Ini adalah proses mengubah file CAD DWG menjadi gambar PNG melalui kode, mempertahankan detail vektor sebagai piksel raster.  
- **Apakah saya dapat mengatur lebar khusus?** Ya – panggil `CadOptions.forRenderingByWidth(int width)` untuk menentukan lebar piksel yang tepat yang Anda butuhkan.  
- **Bagaimana cara mengubah warna latar belakang?** Gunakan `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` sebelum rendering.  
- **Perpustakaan apa yang diperlukan?** GroupDocs.Viewer untuk Java (versi 25.2 atau lebih baru).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh menghapus batas evaluasi dan memungkinkan rendering tak terbatas.

![Render Gambar CAD sebagai PNG dengan Ukuran Kustom & Warna Latar Belakang menggunakan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Apa itu GroupDocs.Viewer untuk Java?
GroupDocs.Viewer untuk Java adalah API sisi‑server yang merender lebih dari 150 format file—termasuk file CAD—menjadi gambar, PDF, atau HTML. Ia berfungsi tanpa memerlukan perangkat lunak pihak ketiga seperti AutoCAD, menjadikannya ideal untuk alur kerja otomatis.

## Cara mengonversi DWG ke PNG dengan ukuran khusus dan warna latar belakang?
Muat file DWG dengan instance `Viewer`, konfigurasikan `CadOptions` untuk lebar dan latar belakang yang diinginkan, dan akhirnya panggil `viewer.view` dengan `PngViewOptions`. Alur tiga langkah ini menangani I/O file, rendering, dan penamaan output dalam satu operasi yang efisien memori.

Viewer adalah kelas utama yang memuat dokumen dan melakukan rendering.  
CadOptions mengonfigurasi pengaturan khusus CAD seperti lebar gambar dan warna latar belakang.  
PngViewOptions mendefinisikan format output PNG dan pola penamaan untuk halaman yang dirender.

Sekarang Anda dapat merender gambar DWG apa pun menjadi PNG dengan lebar tepat yang Anda tentukan, dan Anda dapat memilih warna latar belakang padat apa pun (atau transparan) untuk menyesuaikan merek atau tema UI Anda.

## Mengapa mengatur warna latar belakang khusus?
Mengatur warna latar belakang memastikan PNG yang dirender menyatu mulus dengan elemen UI di sekitarnya, menghindari margin putih yang tidak diinginkan, dan dapat menyoroti detail gambar yang sebaliknya akan hilang pada kanvas putih default. GroupDocs.Viewer mendukung setiap `java.awt.Color`, termasuk nilai RGB khusus, memberi Anda kontrol pixel‑perfect.

java.awt.Color mewakili nilai warna yang digunakan untuk merender latar belakang.

## Prasyarat
- **Java Development Kit (JDK) 8+** – API menargetkan Java 8 dan yang lebih baru.  
- **Maven** – untuk manajemen dependensi.  
- **IDE** – IntelliJ IDEA, Eclipse, atau editor apa pun yang Anda sukai.  
- **Pengetahuan dasar penanganan file Java** – untuk membaca file DWG sumber dan menulis output PNG.

## Menyiapkan GroupDocs.Viewer untuk Java
Tambahkan repositori GroupDocs dan dependensi Viewer ke `pom.xml` Maven Anda:

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
Dapatkan kunci lisensi sementara atau penuh dari portal GroupDocs dan letakkan file `license.lic` di folder sumber daya proyek Anda. Ini menghapus batas evaluasi 20‑halaman dan membuka rendering resolusi penuh.

### Inisialisasi dan Pengaturan Dasar
Buat instance `Viewer` yang menunjuk ke folder yang berisi file DWG Anda:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Fitur 1: merender gambar CAD dengan ukuran gambar khusus dan warna latar belakang

### Cara mengubah warna latar belakang CAD
Untuk mengubah warna latar belakang CAD, konfigurasikan objek CadOptions sebelum rendering. Tetapkan lebar yang diinginkan dengan `forRenderingByWidth` dan terapkan latar belakang baru menggunakan `setBackgroundColor`. Viewer kemudian menghasilkan gambar PNG yang mencerminkan warna yang ditentukan, memastikan gaya visual yang konsisten di semua file output.

#### Implementasi Langkah‑demi‑Langkah

##### Impor paket yang diperlukan
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Siapkan direktori output dan format jalur file
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inisialisasi viewer dengan opsi rendering khusus
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Penjelasan parameter**  
- `PngViewOptions` – mendefinisikan format output PNG dan pola penamaan.  
- `forRenderingByWidth(int width)` – memaksa renderer menghasilkan gambar yang lebarnya sesuai dengan nilai piksel yang diberikan; tinggi diskalakan secara proporsional.  
- `setBackgroundColor(Color color)` – menimpa kanvas putih default dengan warna yang Anda pilih, meningkatkan konsistensi visual di seluruh aset yang dihasilkan.

#### Tips Pemecahan Masalah
- Pastikan folder output ada; gunakan `Files.createDirectories(outputDir)` jika tidak.  
- Verifikasi jalur file input benar dan aplikasi memiliki izin membaca.  

## Fitur 2: mengatur warna latar belakang dalam opsi rendering

### Cara mengatur warna latar belakang PNG
Mengatur warna latar belakang PNG melibatkan pembuatan instance Color dan menetapkannya ke CadOptions sebelum rendering. Ini memastikan setiap PNG yang dihasilkan menggunakan latar belakang yang ditentukan, sesuai dengan pedoman merek atau tema UI Anda. Anda dapat menggunakan konstanta yang telah ditentukan atau mendefinisikan nilai RGB khusus untuk kontrol yang tepat.

java.awt.Color mewakili nilai warna yang digunakan untuk merender latar belakang.

#### Implementasi Langkah‑demi‑Langkah

##### Impor paket yang diperlukan
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Konfigurasikan opsi rendering dengan warna latar belakang
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Opsi konfigurasi utama**  
- Sesuaikan `forRenderingByWidth(int width)` untuk dimensi berbeda, seperti 800 px untuk thumbnail web atau 1920 px untuk cetakan resolusi tinggi.  
- Gunakan konstanta `Color` yang telah ditentukan (mis., `Color.LIGHT_GRAY`) atau buat instance khusus dengan `new Color(r, g, b)` untuk branding yang tepat.

## Aplikasi Praktis

### 1. Dokumentasi teknik
Rendering khusus memastikan setiap gambar mematuhi panduan gaya perusahaan, menghilangkan kebutuhan penyuntingan gambar manual setelah ekspor.

### 2. Visualisasi arsitektur
Tampilkan blueprint dengan latar belakang yang cocok dengan slide deck atau portal yang dihadapi klien, meningkatkan kohesi visual.

### 3. Prototipe manufaktur
Hasilkan PNG untuk alur kerja prototipe cepat di mana alat hilir mengharapkan ukuran gambar dan latar belakang tertentu.

### Kemungkinan Integrasi
Pasangkan pipeline rendering ini dengan sistem manajemen dokumen (mis., SharePoint) untuk secara otomatis menghasilkan gambar pratinjau setiap kali file DWG diunggah.

## Pertimbangan Kinerja

### Mengoptimalkan kinerja
- **Pemrosesan batch:** Loop melalui direktori file DWG dan render masing‑masing secara berurutan untuk mengurangi biaya pemanasan JVM.  
- **Manajemen sumber daya:** Untuk gambar besar (500+ halaman), tingkatkan heap JVM (`-Xmx2g`) atau proses file dalam batch lebih kecil untuk menghindari kesalahan out‑of‑memory.

### Pedoman penggunaan sumber daya
Pantau penggunaan CPU dan memori dengan alat seperti VisualVM; lepaskan instance `Viewer` dengan cepat menggunakan try‑with‑resources.

### Praktik terbaik untuk manajemen memori Java
- Gunakan try‑with‑resources (seperti yang ditunjukkan) untuk menutup otomatis `Viewer`.  
- Hindari mempertahankan objek `Path` besar di luar penggunaan langsungnya.  

## Masalah umum dan solusi

| Masalah | Solusi |
|-------|----------|
| Folder output tidak ditemukan | Buat direktori terlebih dahulu atau tambahkan `Files.createDirectories(outputDirectory);` |
| Gambar kosong | Pastikan `cadOptions.setBackgroundColor` dipanggil setelah `forRenderingByWidth`. |
| Kesalahan out‑of‑memory | Tingkatkan opsi JVM `-Xmx` atau proses file dalam batch lebih kecil. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya merender format CAD lain selain DWG?**  
A: Ya, GroupDocs.Viewer mendukung DXF, DWF, dan beberapa format CAD tambahan.

**Q: Bagaimana cara menggunakan warna RGB khusus alih-alih konstanta yang telah ditentukan?**  
A: Buat instance `Color` baru dengan `new Color(123, 45, 67)` dan berikan ke `setBackgroundColor`.

**Q: Apakah memungkinkan merender hanya tata letak atau lapisan tertentu?**  
A: Anda dapat menentukan opsi tata letak atau lapisan melalui `CadOptions` sebelum memanggil `viewer.view`.

**Q: Apakah perpustakaan mendukung latar belakang transparan?**  
A: Atur warna latar belakang menjadi `new Color(0,0,0,0)` untuk transparansi penuh jika format output mendukungnya.

**Q: Versi GroupDocs.Viewer apa yang diperlukan?**  
A: Tutorial ini menggunakan versi 25.2, tetapi rilis yang lebih baru mempertahankan antarmuka API yang sama.

---

**Terakhir Diperbarui:** 2026-08-30  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs

## Tutorial Terkait

- [groupdocs viewer dwg – Cara Merender Gambar CAD Spesifik di Java Menggunakan GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render Lapisan CAD Java dengan GroupDocs.Viewer – Panduan Lengkap](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Cara mengonversi pdf ke html dan mengoptimalkan kualitas gambar di Java dengan GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)