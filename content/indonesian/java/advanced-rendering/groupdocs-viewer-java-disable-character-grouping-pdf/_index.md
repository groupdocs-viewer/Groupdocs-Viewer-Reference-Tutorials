---
date: '2026-03-22'
description: Pelajari cara menghasilkan HTML dari PDF dan menonaktifkan pengelompokan
  karakter menggunakan GroupDocs Viewer untuk Java untuk representasi teks yang tepat.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Buat HTML dari PDF & Nonaktifkan Pengelompokan – GroupDocs Java
type: docs
url: /id/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Hasilkan HTML dari PDF dan Nonaktifkan Pengelompokan dengan GroupDocs Viewer untuk Java

Dalam banyak proyek Anda perlu **menghasilkan HTML dari PDF** sambil menjaga setiap glif tepat pada tempatnya. Hal ini terutama berlaku untuk skrip kompleks, bahasa kuno, atau dokumen hukum di mana satu karakter yang salah tempat dapat mengubah makna. Dalam tutorial ini kami akan memandu Anda melalui proses lengkap merender PDF ke HTML dengan GroupDocs Viewer untuk Java dan menunjukkan **cara menonaktifkan pengelompokan** sehingga setiap karakter diperlakukan sebagai elemen independen.

![Teknik Rendering Presisi dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Jawaban Cepat
- **Apa yang dilakukan “menonaktifkan pengelompokan”?** Itu memaksa renderer memperlakukan setiap karakter sebagai elemen independen, mempertahankan tata letak yang tepat.  
- **Opsi API mana yang mengontrol ini?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengujian, tetapi lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya menghasilkan HTML dari PDF secara bersamaan?** Ya—gunakan `HtmlViewOptions` untuk membuat output HTML sambil menonaktifkan pengelompokan.  
- **Apakah fitur ini terbatas pada PDF?** Ini terutama untuk PDF, tetapi viewer mendukung banyak format lain.

## Pendahuluan

Saat bekerja dengan dokumen PDF, ketelitian dalam rendering sangat penting—terutama ketika menangani struktur teks kompleks seperti hieroglif atau bahasa yang memerlukan representasi karakter yang tepat. Fitur “Character Grouping” sering menyebabkan masalah dengan mengelompokkan karakter secara tidak tepat, yang mengakibatkan salah tafsir isi dokumen. Hal ini dapat menjadi sangat problematis bagi pengguna yang membutuhkan replikasi tepat tata letak teks dokumen mereka.

### Prasyarat

Sebelum menyelam ke implementasi kode, pastikan Anda memenuhi persyaratan berikut:
- **Libraries & Dependencies**: Anda memerlukan GroupDocs.Viewer untuk Java versi 25.2 atau lebih baru.  
- **Environment Setup**: Pastikan Anda memiliki Java Development Kit (JDK) terpasang dan IDE Anda sudah disiapkan untuk bekerja dengan proyek Maven.  
- **Knowledge Prerequisites**: Pemahaman dasar pemrograman Java, terutama dalam menangani jalur file dan menggunakan pustaka eksternal.

## Cara menghasilkan HTML dari PDF dengan GroupDocs Viewer

Menghasilkan HTML dari PDF adalah proses dua langkah: mengkonfigurasi viewer, kemudian merender dokumen. Kuncinya adalah mematikan pengelompokan karakter sebelum rendering sehingga output HTML mencerminkan tata letak PDF asli karakter demi karakter.

### Menyiapkan GroupDocs.Viewer untuk Java

#### Instalasi via Maven

Pertama, integrasikan pustaka yang diperlukan ke dalam proyek Anda. Tambahkan konfigurasi berikut ke dalam `pom.xml` Anda:

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

#### Perolehan Lisensi

Untuk memanfaatkan GroupDocs.Viewer secara penuh, pertimbangkan untuk memperoleh lisensi:
- **Free Trial**: Mulailah dengan versi percobaan gratis untuk menguji fitur.  
- **Temporary License**: Ajukan lisensi sementara jika Anda membutuhkan lebih banyak waktu.  
- **Purchase**: Untuk proyek jangka panjang, disarankan membeli lisensi.

#### Inisialisasi dan Pengaturan Dasar

Berikut adalah cuplikan kode siap‑jalankan yang menunjukkan alur kerja lengkap—dari mengatur folder output hingga merender PDF sebagai HTML sambil menonaktifkan pengelompokan karakter:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Panduan Implementasi

#### Fitur: Nonaktifkan Pengelompokan Karakter

Di bawah ini kami menjabarkan setiap baris contoh sehingga Anda dapat memahami **mengapa** kami melakukannya dan **bagaimana** hal itu berkontribusi pada menghasilkan HTML dari PDF tanpa penggabungan karakter yang tidak diinginkan.

##### Langkah 1: Tentukan Direktori Output  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Mengapa?** Ini memastikan file HTML yang dirender disimpan dalam folder khusus, memudahkan pencarian dan pengelolaan nanti.

##### Langkah 2: Konfigurasikan Format Jalur File  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Mengapa?** Menggunakan placeholder (`{0}`) memungkinkan viewer membuat file HTML terpisah untuk setiap halaman PDF, menjaga output tetap terorganisir.

##### Langkah 3: Inisialisasi Opsi Tampilan HTML  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Mengapa?** Sumber daya tersemat menggabungkan gambar, font, dan CSS langsung dengan setiap halaman HTML, yang ideal untuk viewer berbasis web atau platform e‑learning.

##### Langkah 4: Nonaktifkan Pengelompokan Karakter  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Mengapa?** Ini adalah baris penting yang memberi tahu mesin rendering **untuk tidak** menggabungkan karakter berdekatan, menjamin bahwa HTML yang dihasilkan mencerminkan penempatan glif yang tepat dari PDF sumber.

##### Langkah 5: Render Dokumen  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Mengapa?** Membungkus `Viewer` dalam blok try‑with‑resources memastikan semua sumber daya native dilepaskan secara otomatis, mencegah kebocoran memori pada aplikasi yang berjalan lama.

### Menghasilkan HTML Java dari PDF tanpa Pengelompokan

Kelas `HtmlViewOptions` memungkinkan Anda menghasilkan **generate html from pdf** sambil menjaga setiap karakter terpisah. Ini sangat berguna ketika Anda perlu menyematkan halaman yang dirender ke dalam portal web atau platform e‑learning di mana penempatan glif yang tepat penting.

### Masalah Umum dan Solusinya

- **FileNotFoundException** – Periksa kembali jalur yang Anda berikan ke `new Viewer(...)`. Gunakan jalur absolut atau `Path.of(...)` untuk kejelasan.  
- **Write Permissions** – Pastikan direktori output dapat ditulisi oleh proses Java; di Linux Anda mungkin perlu menyesuaikan izin folder (`chmod 775`).  
- **Version Mismatch** – Opsi `setDisableCharsGrouping` tersedia mulai versi 25.2. Pastikan `pom.xml` Anda mencerminkan versi yang tepat.  

### Aplikasi Praktis

1. **Language Preservation** – Ideal untuk merender dokumen dalam bahasa Mandarin, Jepang, Arab, atau skrip kuno di mana spasi karakter membawa makna.  
2. **Legal & Financial Documents** – Menjamin replikasi teks yang tepat untuk dokumen dengan kepatuhan tinggi.  
3. **Educational Resources** – Sempurna untuk buku teks yang mencakup diagram kompleks, anotasi, atau konten multibahasa.  

### Pertimbangan Kinerja

- **Optimize Resource Usage** – PDF besar dapat mengonsumsi memori signifikan. Pertimbangkan memproses halaman dalam batch dan membuang instance `Viewer` dengan cepat.  
- **Java Memory Management** – Sesuaikan heap JVM (`-Xmx2g` atau lebih tinggi) jika Anda memperkirakan memproses PDF ratusan halaman.  
- **Parallel Rendering** – Untuk konversi massal, buat thread terpisah masing‑masing dengan instance `Viewer` sendiri untuk memanfaatkan CPU multi‑core.  

## Pertanyaan yang Sering Diajukan

**Q:** *Mengapa saya perlu menonaktifkan pengelompokan karakter?*  
**A:** Menonaktifkan pengelompokan mencegah renderer menggabungkan karakter yang merupakan glyph terpisah, yang penting untuk skrip di mana spasi dan urutan menyampaikan makna.

**Q:** *Apakah pengaturan `setDisableCharsGrouping` hanya berlaku untuk output HTML?*  
**A:** Tidak, pengaturan ini memengaruhi mesin rendering PDF di bawahnya, sehingga semua format output (HTML, PNG, JPEG, dll.) akan mencerminkan perubahan tersebut.

**Q:** *Bisakah saya menggabungkan pengaturan ini dengan font khusus?*  
**A:** Ya—muat font khusus Anda sebelum menginisialisasi `Viewer`, dan aturan pengelompokan tetap berlaku.

**Q:** *Apakah menonaktifkan pengelompokan memengaruhi kinerja?*  
**A:** Sedikit, karena mesin memproses setiap karakter secara individual, namun dampaknya minimal untuk kebanyakan dokumen.

**Q:** *Apakah ada cara untuk mengaktifkan/menonaktifkan pengelompokan per halaman?*  
**A:** Saat ini opsi bersifat global per instance `PdfOptions`; Anda memerlukan instance `Viewer` terpisah untuk halaman yang berbeda jika memerlukan perilaku campuran.

## Sumber Daya

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-03-22  
**Diuji Dengan:** GroupDocs.Viewer 25.2 for Java  
**Penulis:** GroupDocs