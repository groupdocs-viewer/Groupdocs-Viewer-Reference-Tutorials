---
date: '2026-01-28'
description: Pelajari cara merender HTML, mengecualikan font Arial, dan mengoptimalkan
  rendering HTML menggunakan GroupDocs.Viewer untuk Java. Panduan langkah demi langkah
  untuk konversi DOCX ke HTML dengan Java.
keywords:
- exclude Arial font GroupDocs.Viewer Java
- render documents to HTML with GroupDocs
- customize document rendering in Java
title: Cara Merender HTML dan Mengecualikan Font Arial dengan GroupDocs.Viewer Java
type: docs
url: /id/java/custom-rendering/exclude-arial-font-groupdocs-viewer-java/
weight: 1
---

# Cara Merender HTML dan Mengecualikan Font Arial dengan GroupDocs.Viewer Java

Rendering dokumen ke HTML adalah kebutuhan umum untuk aplikasi berbasis web, tetapi font yang tidak diinginkan dapat merusak konsistensi visual. Dalam tutorial ini, Anda akan belajar **cara merender html** sambil mengecualikan font Arial, memastikan output Anda sesuai dengan pedoman desain. Kami akan membahas pengaturan, perubahan kode yang tepat, dan praktik terbaik untuk konversi **docx to html java** yang mulus.

![Mengecualikan Font Arial dalam Rendering HTML dengan GroupDocs.Viewer untuk Java](/viewer/custom-rendering/exclude-arial-font-in-html-rendering-java.png)

**Apa yang Akan Anda Pelajari:**
- Cara mengkonfigurasi GroupDocs.Viewer untuk Java agar merender dokumen dalam HTML.
- Proses mengecualikan font tertentu seperti Arial selama konversi dokumen.
- Praktik terbaik dan pertimbangan kinerja saat menggunakan GroupDocs.Viewer Java.

## Jawaban Cepat
- **Bagaimana cara merender html?** Gunakan `HtmlViewOptions` dengan GroupDocs.Viewer Java untuk menghasilkan halaman HTML yang berdiri sendiri.  
- **Apakah saya dapat mengecualikan font Arial?** Ya—panggil `viewOptions.getFontsToExclude().add("Arial")`.  
- **Versi perpustakaan mana?** Panduan ini menggunakan GroupDocs.Viewer untuk Java 25.2 (atau rilis stabil terbaru).  
- **Format input apa yang didukung?** DOCX, PDF, PPTX, XLSX, dan banyak lagi.  
- **Apakah lisensi diperlukan?** Versi percobaan gratis cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memiliki:
- **Perpustakaan & Versi**: Anda memerlukan GroupDocs.Viewer untuk Java versi 25.2.
- **Pengaturan Lingkungan**: Lingkungan pengembangan Java (IDE seperti IntelliJ IDEA atau Eclipse) dan Maven terpasang di mesin Anda.
- **Prasyarat Pengetahuan**: Pemahaman dasar pemrograman Java dan familiaritas dengan pengaturan proyek Maven.

## Menyiapkan GroupDocs.Viewer untuk Java

Untuk memulai, tambahkan dependensi yang diperlukan untuk GroupDocs.Viewer di file `pom.xml` Anda menggunakan Maven:

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
- **Trial Gratis**: Unduh trial gratis dari [GroupDocs Free Trials](https://releases.groupdocs.com/viewer/java/).
- **Lisensi Sementara**: Ajukan lisensi sementara melalui [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) untuk pengujian lanjutan.
- **Pembelian**: Beli lisensi penuh di [Purchase Page](https://purchase.groupdocs.com/buy) setelah puas dengan kemampuan GroupDocs.Viewer.

### Inisialisasi dan Pengaturan Dasar

Setelah menyiapkan proyek Maven Anda, buat kelas Java baru dan impor paket GroupDocs yang diperlukan. Pengaturan ini penting untuk menginisialisasi viewer agar merender dokumen.

## Cara Mengecualikan Font Arial Saat Merender HTML

### Gambaran Umum
Mengecualikan font tertentu memberi Anda kontrol lebih ketat atas output visual konversi HTML Anda, membantu Anda **mengoptimalkan rendering html** untuk kecepatan dan konsistensi merek.

### Implementasi Langkah‑per‑Langkah

#### 1. Tentukan Direktori Output
Mulailah dengan menentukan di mana file HTML akan disimpan:

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
```

Jalur ini menentukan di mana dokumen HTML yang dirender akan berada.

#### 2. Atur Jalur File Halaman HTML
Definisikan bagaimana nama file setiap halaman harus disusun:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

Placeholder `{0}` memungkinkan penamaan dinamis file berdasarkan nomor halaman, memastikan penyimpanan yang teratur.

#### 3. Konfigurasikan Opsi Tampilan dengan Sumber Daya Tersemat
Buat objek `HtmlViewOptions` yang menentukan cara rendering HTML harus ditangani:

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

Pengaturan ini memastikan semua sumber daya tersemat dalam file HTML, menjadikannya **self‑contained**.

#### 4. Mengecualikan Font Tertentu
Tambahkan font yang ingin Anda kecualikan (dalam hal ini, Arial) dari rendering output:

```java
viewOptions.getFontsToExclude().add("Arial");
```

Mengecualikan font dapat menjadi kunci untuk mempertahankan konsistensi desain dan mengurangi ukuran file.

#### 5. Render Dokumen Menggunakan Viewer
Akhirnya, gunakan kelas `Viewer` untuk merender dokumen Anda ke format HTML:

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

Pernyataan `try‑with‑resources` memastikan bahwa `viewer` ditutup dengan benar setelah rendering selesai.

### Tips Pemecahan Masalah
- **Masalah Umum**: Pastikan jalur benar dan dapat diakses; jalur yang salah dapat menyebabkan kesalahan file‑not‑found.
- **Tips Kinerja**: Saat merender dokumen besar, pantau penggunaan memori karena sumber daya tersemat dapat meningkatkan waktu pemuatan.

## Mengapa Ini Penting: Kasus Penggunaan Dunia Nyata

1. **Pelaporan Korporat** – Mengecualikan font default untuk menjaga laporan tetap sesuai dengan pedoman merek.  
2. **Materi Pendidikan** – Menyesuaikan rendering font untuk keterbacaan yang lebih baik di berbagai perangkat.  
3. **Dokumen Hukum** – Mempertahankan tampilan seragam untuk presentasi HTML siap pengadilan.  
4. **Daftar E‑commerce** – Memastikan deskripsi produk mengikuti standar merek.  
5. **Integrasi CMS** – Menyediakan pratinjau bersih dengan kontrol font di dalam sistem manajemen konten.

## Optimalkan Kinerja Rendering HTML

### Tips untuk Konversi Lebih Cepat
- **Gunakan Jalur File Efisien**: Pertahankan struktur direktori dangkal untuk mengurangi overhead I/O.  
- **Batasi Sumber Daya Tersemat**: Hanya sematkan CSS/JS penting untuk menjaga HTML ringan.  

### Praktik Terbaik untuk Manajemen Memori Java
- **Tutup Viewer Segera**: Pola `try‑with‑resources` membebaskan memori segera setelah rendering selesai.  
- **Pantau Beban Aplikasi**: Profil JVM Anda saat menangani banyak atau dokumen besar untuk menghindari kesalahan out‑of‑memory.

## Pertanyaan yang Sering Diajukan

**Q1: Apa kegunaan GroupDocs.Viewer?**  
A1: Ini adalah perpustakaan kuat yang memungkinkan pengembang merender dokumen dalam berbagai format seperti HTML, gambar, atau PDF.

**Q2: Bagaimana cara mengecualikan font lain selain Arial?**  
A2: Gunakan metode `getFontsToExclude().add("FONT_NAME")` dengan nama font yang diinginkan.

**Q3: Bisakah GroupDocs.Viewer menangani konversi dokumen besar secara efisien?**  
A3: Ya, dengan mengoptimalkan penanganan sumber daya dan praktik manajemen memori seperti yang dijelaskan dalam panduan ini.

**Q4: Apa saja masalah umum saat menyiapkan GroupDocs.Viewer?**  
A4: Masalah umum meliputi konfigurasi jalur yang salah atau ketergantungan Maven yang hilang. Verifikasi semua jalur dan pastikan koordinat Maven benar.

**Q5: Di mana saya dapat menemukan lebih banyak sumber tentang penggunaan GroupDocs.Viewer dengan Java?**  
A5: Kunjungi [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) untuk panduan terperinci dan referensi API.

**Q6: Apakah pendekatan ini bekerja untuk mengonversi DOCX ke HTML di Java?**  
A6: Tentu—cukup arahkan konstruktor `Viewer` ke file `.docx`, dan logika pengecualian font yang sama berlaku.

**Q7: Bagaimana saya dapat lebih lanjut **mengoptimalkan rendering html** untuk perangkat seluler?**  
A7: Pertimbangkan meminifikasi HTML yang dihasilkan dan menyajikan CSS responsif bersama sumber daya tersemat.

**Q8: Apakah lisensi wajib untuk build pengembangan?**  
A8: Trial gratis cukup untuk pengembangan dan pengujian; lisensi komersial diperlukan untuk penerapan produksi.

## Sumber Daya
- **Dokumentasi**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referensi API**: [GroupDocs Viewer Java API](https://reference.groupdocs.com/viewer/java/)
- **Unduh GroupDocs.Viewer**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Beli Lisensi**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Trial Gratis dan Lisensi Sementara**: [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/) | [Request a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Dukungan**: Jika Anda memerlukan bantuan lebih lanjut, kunjungi [GroupDocs Support Page](https://support.groupdocs.com/hc/en-us/).

---

**Terakhir Diperbarui:** 2026-01-28  
**Diuji Dengan:** GroupDocs.Viewer for Java 25.2  
**Penulis:** GroupDocs