---
date: '2026-02-23'
description: Pelajari cara mengatur jumlah item per halaman, menyematkan sumber daya
  HTML, dan mengonversi arsip secara batch menjadi HTML satu halaman atau multi‑halaman
  menggunakan GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Atur Item per Halaman: Konversi Arsip ke HTML dengan GroupDocs.Viewer Java'
type: docs
url: /id/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Atur Item per Halaman: Konversi Arsip ke HTML dengan GroupDocs.Viewer Java

Mengonversi file arsip seperti ZIP atau RAR menjadi HTML yang ramah web adalah kebutuhan yang sering muncul ketika Anda ingin berbagi atau meninjau dokumen langsung di peramban. Dalam panduan ini Anda akan mempelajari **cara mengatur item per halaman** saat merender arsip, cara menyematkan sumber daya HTML untuk output yang berdiri sendiri, dan cara mengonversi arsip secara batch dengan efisien menggunakan GroupDocs.Viewer Java.

![Konversi Arsip ke HTML dengan GroupDocs.Viewer untuk Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Jawaban Cepat
- **Apa yang dikontrol oleh “set items per page”?** Ini menentukan berapa banyak file atau folder dari arsip yang muncul pada setiap halaman HTML yang dihasilkan.  
- **Apakah saya dapat menyematkan gambar dan CSS langsung di HTML?** Ya – gunakan opsi `forEmbeddedResources` untuk menyematkan sumber daya HTML.  
- **Apakah konversi batch memungkinkan?** Tentu saja; Anda dapat melakukan loop pada kumpulan arsip dan merender masing‑masing dengan pengaturan yang sama.  
- **Apakah saya memerlukan Maven untuk menggunakan GroupDocs.Viewer?** Ya, tambahkan dependensi `maven groupdocs viewer` seperti yang ditunjukkan di bawah.  
- **Format output apa yang didukung?** HTML Java satu‑halaman dan HTML Java multi‑halaman keduanya tersedia.

## Apa itu “set items per page” di GroupDocs.Viewer?
Pengaturan **set items per page** termasuk dalam opsi rendering arsip. Pengaturan ini memberi tahu viewer berapa banyak entri arsip (file atau folder) yang harus ditampilkan pada setiap halaman HTML ketika Anda menghasilkan dokumen HTML multi‑halaman. Menyesuaikan nilai ini membantu Anda menyeimbangkan ukuran halaman dan kecepatan navigasi, terutama untuk arsip yang besar.

## Mengapa menyematkan sumber daya HTML?
Menyematkan sumber daya (gambar, CSS, font) langsung di dalam file HTML menghasilkan satu dokumen portabel yang dapat dibuka tanpa file eksternal. Ini ideal untuk lampiran email, peninjauan offline, atau menyematkan output ke halaman web lain.

## Prasyarat

- **Perpustakaan yang Diperlukan:** Sertakan GroupDocs.Viewer versi 25.2 atau yang lebih baru.  
- **Lingkungan:** Java Development Kit (JDK) terpasang dan terkonfigurasi.  
- **Pengetahuan:** Dasar Java dan manajemen dependensi Maven.  

## Pengaturan Maven GroupDocs Viewer

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

### Akuisisi Lisensi
GroupDocs.Viewer menawarkan **tautan percobaan gratis**, lisensi sementara, atau opsi pembelian penuh. Pilih yang sesuai dengan jadwal proyek Anda.

### Inisialisasi Dasar
Setelah pengaturan Maven, panggil viewer ke dalam kode Anda:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cara Merender Arsip ke HTML Satu‑Halaman

### Langkah 1: Tentukan Direktori Output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Langkah 2: Atur Nama File untuk Output Satu‑Halaman
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Langkah 3: Inisialisasi Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Langkah 4: Konfigurasikan Opsi Rendering (sematkan sumber daya HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Langkah 5: Render sebagai Satu Halaman
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cara Merender Arsip ke HTML Multi‑Halaman dan Atur Item per Halaman

### Langkah 1: Gunakan Kembali Direktori Output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Langkah 2: Tentukan Format Nama File untuk Beberapa Halaman
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Langkah 3: Inisialisasi Viewer Lagi
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Langkah 4: Konfigurasikan Opsi Multi‑Halaman (sematkan sumber daya HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Langkah 5: Atur Item per Halaman (kata kunci utama dalam aksi)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Aplikasi Praktis

- **Sistem Manajemen Dokumen:** Tambahkan fungsi pratinjau arsip tanpa menginstal viewer tambahan.  
- **Portal Web:** Tawarkan pengguna cara cepat tanpa unduhan untuk menjelajahi dokumen yang dikemas.  
- **Alat Kolaborasi:** Biarkan tim memeriksa arsip yang dibagikan langsung di peramban.  

## Pertimbangan Kinerja

- **Manajemen Sumber Daya:** Pantau penggunaan memori; pertimbangkan penyesuaian garbage‑collector JVM untuk batch besar.  
- **Konversi Batch Arsip:** Loop melalui daftar file arsip dan panggil logika rendering yang sama untuk memaksimalkan throughput.  
- **Strategi Caching:** Simpan HTML yang dirender dalam cache jika arsip yang sama sering diakses.  

## Pertanyaan yang Sering Diajukan

**Q: Apa itu GroupDocs.Viewer Java?**  
A: Sebuah perpustakaan serbaguna untuk merender dokumen—termasuk arsip—ke dalam format seperti HTML, PDF, dan gambar.

**Q: Bagaimana saya dapat memperoleh percobaan gratis GroupDocs.Viewer?**  
A: Kunjungi [tautan percobaan gratis](https://releases.groupdocs.com/viewer/java/) untuk mengunduh dan menguji.

**Q: Bisakah saya mengonversi tipe dokumen lain selain arsip?**  
A: Ya, viewer mendukung PDF, Word, Excel, dan banyak format lainnya.

**Q: Apa yang harus saya lakukan jika rendering lambat?**  
A: Kurangi jumlah item per halaman, aktifkan streaming, atau proses arsip dalam batch yang lebih kecil.

**Q: Di mana saya dapat mendapatkan bantuan atau dukungan?**  
A: Hubungi melalui [forum dukungan](https://forum.groupdocs.com/c/viewer/9).

**Q: Apakah memungkinkan menyematkan CSS dan gambar langsung di HTML?**  
A: Tentu saja—gunakan `HtmlViewOptions.forEmbeddedResources` seperti yang ditunjukkan dalam contoh.

**Q: Bagaimana cara mengonversi batch folder arsip?**  
A: Iterasi setiap file dengan loop `for`, menerapkan konfigurasi `Viewer` dan `HtmlViewOptions` yang sama untuk setiap iterasi.

## Sumber Daya

- **Dokumentasi:** Selami lebih dalam fungsionalitas dengan [dokumentasi GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Referensi API:** Jelajahi API lengkap di [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Unduhan:** Dapatkan binary terbaru dari [halaman unduhan](https://releases.groupdocs.com/viewer/java/).  
- **Pembelian dan Lisensi:** Tinjau opsi pada [halaman pembelian](https://purchase.groupdocs.com/buy).  
- **Dukungan dan Komunitas:** Bergabung dalam diskusi di [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Terakhir Diperbarui:** 2026-02-23  
**Diuji Dengan:** GroupDocs.Viewer 25.2  
**Penulis:** GroupDocs