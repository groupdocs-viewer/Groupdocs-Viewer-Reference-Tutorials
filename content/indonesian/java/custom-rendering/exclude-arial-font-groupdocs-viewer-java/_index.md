---
date: '2026-04-06'
description: Pelajari cara merender HTML, cara merender HTML sambil mengecualikan
  font Arial, dan mengoptimalkan rendering HTML menggunakan GroupDocs.Viewer untuk
  Java. Panduan langkah demi langkah untuk konversi DOCX ke HTML dengan Java.
keywords:
- how to render html
- convert docx to html
- embed resources html
- groupdocs viewer html
- optimize html rendering
title: Cara Merender HTML dan Mengecualikan Font Arial dengan GroupDocs.Viewer Java
type: docs
url: /id/java/custom-rendering/exclude-arial-font-groupdocs-viewer-java/
weight: 1
---

# Cara Merender HTML dan Mengecualikan Font Arial dengan GroupDocs.Viewer Java

Merender dokumen ke HTML adalah kebutuhan umum untuk aplikasi berbasis web, tetapi font yang tidak diinginkan dapat merusak konsistensi visual. Dalam tutorial ini, Anda akan belajar **cara merender html** sambil mengecualikan font Arial, memastikan output Anda sesuai dengan pedoman desain. Kami juga akan membahas cara **mengonversi docx ke html**, menyematkan sumber daya dalam halaman yang dihasilkan, dan **mengoptimalkan rendering html** untuk kinerja yang lebih baik.

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

## Cara Merender HTML dengan GroupDocs.Viewer Java
Sebelum menyelam ke kode, mari pahami mengapa merender HTML itu berharga. Output HTML memungkinkan Anda menampilkan dokumen langsung di peramban tanpa memerlukan penampil eksternal, menjadikannya ideal untuk portal web, integrasi CMS, dan pratinjau yang ramah seluler.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memiliki:
- **Libraries & Versions**: Anda memerlukan GroupDocs.Viewer untuk Java versi 25.2.
- **Environment Setup**: Lingkungan pengembangan Java (IDE seperti IntelliJ IDEA atau Eclipse) dan Maven terpasang di mesin Anda.
- **Knowledge Prerequisites**: Pemahaman dasar tentang pemrograman Java dan familiaritas dengan penyiapan proyek Maven.

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
- **Free Trial**: Unduh percobaan gratis dari [GroupDocs Free Trials](https://releases.groupdocs.com/viewer/java/).
- **Temporary License**: Ajukan lisensi sementara melalui [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) untuk pengujian yang lebih lama.
- **Purchase**: Beli lisensi penuh di [Purchase Page](https://purchase.groupdocs.com/buy) setelah puas dengan kemampuan GroupDocs.Viewer.

### Inisialisasi dan Penyiapan Dasar

Setelah menyiapkan proyek Maven Anda, buat kelas Java baru dan impor paket GroupDocs yang diperlukan. Penyiapan ini penting untuk menginisialisasi viewer agar dapat merender dokumen.

## Cara Mengecualikan Font Arial Saat Merender HTML

### Gambaran Umum
Mengecualikan font tertentu memberi Anda kontrol lebih ketat atas output visual konversi HTML Anda, membantu Anda **mengoptimalkan rendering html** untuk kecepatan dan konsistensi merek.

### Implementasi Langkah‑per‑Langkah

#### 1. Tentukan Direktori Output
Mulailah dengan menentukan di mana file HTML akan disimpan:

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
```

Jalur ini menentukan lokasi dokumen HTML yang dirender akan berada.

#### 2. Atur Jalur File Halaman HTML
Tentukan bagaimana nama file setiap halaman harus disusun:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

Placeholder `{0}` memungkinkan penamaan dinamis file berdasarkan nomor halaman, memastikan penyimpanan yang teratur.

#### 3. Konfigurasikan Opsi Tampilan dengan Sumber Daya Tersemat
Buat objek `HtmlViewOptions` yang menentukan cara rendering HTML harus ditangani:

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

Pengaturan ini memastikan semua sumber daya tersemat dalam file HTML, menjadikannya **self‑contained** dan ideal untuk skenario **embed resources html**.

#### 4. Mengecualikan Font Tertentu
Tambahkan font yang ingin Anda kecualikan (dalam hal ini, Arial) dari rendering dalam output:

```java
viewOptions.getFontsToExclude().add("Arial");
```

Mengecualikan font dapat menjadi penting untuk menjaga konsistensi desain dan mengurangi ukuran file.

#### 5. Render Dokumen Menggunakan Viewer
Akhirnya, gunakan kelas `Viewer` untuk merender dokumen Anda ke format HTML:

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

Pernyataan try‑with‑resources memastikan bahwa `viewer` ditutup dengan benar setelah proses rendering selesai.

### Tips Pemecahan Masalah
- **Common Issue**: Pastikan jalur sudah benar dan dapat diakses; jalur yang salah dapat menyebabkan error file‑not‑found.
- **Performance Tip**: Saat merender dokumen besar, pantau penggunaan memori karena sumber daya tersemat dapat meningkatkan waktu pemuatan.

## Cara Mengonversi DOCX ke HTML Menggunakan GroupDocs.Viewer
Konfigurasi `HtmlViewOptions` yang sama bekerja untuk format apa pun yang didukung, termasuk DOCX. Cukup arahkan konstruktor `Viewer` ke file `.docx`, dan perpustakaan akan menangani konversi sambil menghormati pengaturan pengecualian font.

## Mengapa Ini Penting: Kasus Penggunaan Dunia Nyata

1. **Corporate Reporting** – Mengecualikan font default untuk menjaga laporan tetap selaras dengan pedoman merek.  
2. **Educational Materials** – Menyesuaikan rendering font untuk keterbacaan yang lebih baik di berbagai perangkat.  
3. **Legal Documents** – Mempertahankan tampilan seragam untuk presentasi HTML yang siap dipakai di pengadilan.  
4. **E‑commerce Listings** – Memastikan deskripsi produk mengikuti standar branding.  
5. **CMS Integration** – Menyediakan pratinjau bersih dengan kontrol font di dalam sistem manajemen konten.

## Optimalkan Kinerja Rendering HTML

### Tips untuk Konversi Lebih Cepat
- **Use Efficient File Paths**: Jaga struktur direktori tetap dangkal untuk mengurangi beban I/O.  
- **Limit Embedded Resources**: Hanya sematkan CSS/JS penting agar HTML tetap ringan.  

### Praktik Terbaik untuk Manajemen Memori Java
- **Close Viewer Promptly**: Pola `try‑with‑resources` membebaskan memori segera setelah rendering selesai.  
- **Monitor Application Load**: Profil JVM Anda saat menangani banyak atau dokumen besar untuk menghindari error out‑of‑memory.

## Pertanyaan yang Sering Diajukan

**Q1: Apa kegunaan GroupDocs.Viewer?**  
A1: Ini adalah perpustakaan kuat yang memungkinkan pengembang merender dokumen dalam berbagai format seperti HTML, gambar, atau PDF.

**Q2: Bagaimana cara mengecualikan font lain selain Arial?**  
A2: Gunakan metode `getFontsToExclude().add("FONT_NAME")` dengan nama font yang diinginkan.

**Q3: Bisakah GroupDocs.Viewer menangani konversi dokumen besar secara efisien?**  
A3: Ya, dengan mengoptimalkan penanganan sumber daya dan praktik manajemen memori seperti yang dijelaskan dalam panduan ini.

**Q4: Apa saja masalah umum saat menyiapkan GroupDocs.Viewer?**  
A4: Masalah umum meliputi konfigurasi jalur yang salah atau ketergantungan Maven yang hilang. Verifikasi semua jalur dan pastikan koordinat Maven sudah tepat.

**Q5: Di mana saya dapat menemukan lebih banyak sumber daya tentang penggunaan GroupDocs.Viewer dengan Java?**  
A5: Kunjungi [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) untuk panduan detail dan referensi API.

**Q6: Apakah pendekatan ini bekerja untuk mengonversi DOCX ke HTML di Java?**  
A6: Tentu saja—cukup arahkan konstruktor `Viewer` ke file `.docx`, dan logika pengecualian font yang sama akan diterapkan.

**Q7: Bagaimana saya dapat lebih lanjut **mengoptimalkan rendering html** untuk perangkat seluler?**  
A7: Pertimbangkan meminifikasi HTML yang dihasilkan dan menyajikan CSS responsif bersama sumber daya tersemat.

**Q8: Apakah lisensi wajib untuk build pengembangan?**  
A8: Versi percobaan gratis cukup untuk pengembangan dan pengujian; lisensi komersial diperlukan untuk penerapan produksi.

## Sumber Daya
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs Viewer Java API](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase License**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License**: [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/) | [Request a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: Jika Anda memerlukan bantuan lebih lanjut, kunjungi [GroupDocs Support Page](https://support.groupdocs.com/hc/en-us/).

---

**Last Updated:** 2026-04-06  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs