---
date: '2025-12-21'
description: Pelajari cara menonaktifkan pengelompokan dalam PDF dengan GroupDocs.Viewer
  untuk Java, menggunakan java html dari opsi rendering PDF untuk memastikan representasi
  teks yang tepat.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Cara Menonaktifkan Pengelompokan pada PDF dengan GroupDocs.Viewer untuk Java
type: docs
url: /id/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Cara Menonaktifkan Pengelompokan dalam PDF dengan GroupDocs.Viewer untuk Java

Ketika Anda membutuhkan **cara menonaktifkan pengelompokan** saat merender PDF, terutama untuk skrip kompleks atau bahasa kuno, penempatan karakter yang tepat menjadi penting. Fitur *Character Grouping* default dapat menggabungkan karakter secara tidak benar, menyebabkan salah tafsir konten. Dalam panduan ini kami akan menunjukkan langkah demi langkah cara menonaktifkan pengelompokan menggunakan GroupDocs.Viewer untuk Java, sehingga setiap glyph tetap tepat di tempatnya.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Jawaban Cepat
- **Apa yang dilakukan “disable grouping”?** Itu memaksa renderer memperlakukan setiap karakter sebagai elemen independen, mempertahankan tata letak yang tepat.  
- **Opsi API mana yang mengontrol ini?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengujian, tetapi lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya menghasilkan Java HTML dari PDF secara bersamaan?** Ya—gunakan `HtmlViewOptions` untuk membuat output HTML sambil menonaktifkan pengelompokan.  
- **Apakah fitur ini terbatas pada PDF?** Ini terutama untuk PDF, tetapi viewer mendukung banyak format lain.

## Pendahuluan

Saat bekerja dengan dokumen PDF, ketelitian dalam rendering sangat penting—terutama ketika menangani struktur teks kompleks seperti hieroglif atau bahasa yang memerlukan representasi karakter yang tepat. Fitur "Character Grouping" sering menyebabkan masalah dengan mengelompokkan karakter secara tidak benar, yang mengarah pada salah tafsir konten dokumen. Hal ini dapat menjadi sangat problematis bagi pengguna yang membutuhkan replikasi tepat tata letak teks dokumen mereka.

### Prasyarat

- **Libraries & Dependencies**: Anda memerlukan GroupDocs.Viewer untuk Java versi 25.2 atau lebih baru.  
- **Environment Setup**: Pastikan Anda memiliki Java Development Kit (JDK) terinstal dan IDE Anda disiapkan untuk bekerja dengan proyek Maven.  
- **Knowledge Prerequisites**: Pemahaman dasar tentang pemrograman Java, terutama penanganan jalur file dan penggunaan pustaka eksternal.

## Cara Menonaktifkan Pengelompokan dalam Rendering PDF

### Menyiapkan GroupDocs.Viewer untuk Java

#### Instalasi via Maven

Pertama, integrasikan pustaka yang diperlukan ke dalam proyek Anda. Tambahkan konfigurasi berikut di `pom.xml` Anda:

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

#### Akuisisi Lisensi

Untuk memanfaatkan GroupDocs.Viewer secara penuh, pertimbangkan untuk memperoleh lisensi:
- **Free Trial**: Mulai dengan versi percobaan gratis untuk menguji fitur.  
- **Temporary License**: Ajukan lisensi sementara jika Anda membutuhkan lebih banyak waktu.  
- **Purchase**: Untuk proyek jangka panjang, disarankan membeli lisensi.

#### Inisialisasi dan Penyiapan Dasar

Mulailah dengan menyiapkan lingkungan proyek Anda:

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

#### Fitur: Menonaktifkan Pengelompokan Karakter

##### Langkah 1: Tentukan Direktori Output

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Mengapa?** Ini memastikan output Anda terorganisir dan mudah diakses.

##### Langkah 2: Konfigurasikan Format Jalur File

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Mengapa?** Ini membantu dalam mengorganisir halaman dokumen PDF secara sistematis.

##### Langkah 3: Inisialisasi Opsi Tampilan HTML

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Mengapa?** Sumber daya tersemat memastikan semua aset yang diperlukan termasuk dalam file HTML setiap halaman.

##### Langkah 4: Nonaktifkan Pengelompokan Karakter

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Mengapa?** Ini memastikan karakter dirender secara individual, mempertahankan tata letak dan makna yang dimaksud.

##### Langkah 5: Render Dokumen

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Mengapa?** Ini memastikan semua sumber daya ditutup dengan tepat, mencegah kebocoran memori.

### Menghasilkan Java HTML dari PDF tanpa Pengelompokan

Kelas `HtmlViewOptions` memungkinkan Anda menghasilkan **java html from pdf** sambil menjaga setiap karakter terpisah. Ini sangat berguna ketika Anda perlu menyematkan halaman yang dirender ke dalam portal web atau platform e‑learning di mana penempatan glyph yang tepat penting.

### Tips Pemecahan Masalah

- Pastikan jalur dokumen Anda benar untuk menghindari `FileNotFoundException`.  
- Verifikasi bahwa direktori output memiliki izin menulis.  
- Periksa kembali bahwa Anda menggunakan versi GroupDocs.Viewer untuk Java yang kompatibel.

## Aplikasi Praktis

1. **Language Preservation**: Ideal untuk merender dokumen dalam bahasa seperti Mandarin, Jepang, atau skrip kuno di mana presisi karakter penting.  
2. **Legal and Financial Documents**: Menjamin akurasi dalam dokumen yang memerlukan representasi teks yang tepat untuk kepatuhan.  
3. **Educational Resources**: Sempurna untuk buku teks dan makalah akademik yang mencakup diagram atau anotasi kompleks.

## Pertimbangan Kinerja

- **Optimize Resource Usage**: Pastikan server Anda memiliki sumber daya yang memadai untuk menangani file PDF besar.  
- **Java Memory Management**: Gunakan struktur data yang efisien dan praktik garbage‑collection untuk mengelola memori secara efektif.  
- **Batch Processing**: Saat merender banyak dokumen, proses secara batch untuk meningkatkan throughput.

## Kesimpulan

Anda kini telah menguasai **cara menonaktifkan pengelompokan** selama rendering PDF dengan GroupDocs.Viewer untuk Java. Kemampuan ini penting untuk aplikasi yang menuntut representasi teks yang tepat. Untuk eksplorasi lebih lanjut, coba integrasikan fitur ini dengan sistem manajemen dokumen lain atau bereksperimen dengan opsi rendering tambahan.

Langkah selanjutnya meliputi menjelajahi fitur lebih lanjut dari GroupDocs.Viewer dan menyempurnakan kinerja untuk penyebaran skala besar.

## Pertanyaan yang Sering Diajukan

**Q:** *Mengapa saya perlu menonaktifkan pengelompokan karakter?*  
**A:** Menonaktifkan pengelompokan mencegah renderer menggabungkan karakter yang termasuk dalam glyph yang berbeda, yang penting untuk skrip di mana spasi dan urutan menyampaikan makna.

**Q:** *Apakah pengaturan `setDisableCharsGrouping` hanya berlaku untuk output HTML?*  
**A:** Tidak, ini memengaruhi mesin rendering PDF di bawahnya, sehingga semua format output (HTML, PNG, dll.) akan mencerminkan perubahan tersebut.

**Q:** *Bisakah saya menggabungkan pengaturan ini dengan font khusus?*  
**A:** Ya—cukup muat font khusus Anda sebelum menginisialisasi `Viewer`, dan aturan pengelompokan tetap berlaku.

**Q:** *Apakah menonaktifkan pengelompokan memengaruhi kinerja?*  
**A:** Sedikit, karena mesin memproses setiap karakter secara individual, tetapi dampaknya minimal untuk kebanyakan dokumen.

**Q:** *Apakah ada cara untuk mengaktifkan/menonaktifkan pengelompokan per halaman?*  
**A:** Saat ini opsi bersifat global per instance `PdfOptions`; Anda harus membuat instance `Viewer` terpisah untuk halaman yang berbeda.

## Sumber Daya

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2025-12-21  
**Diuji Dengan:** GroupDocs.Viewer 25.2 for Java  
**Penulis:** GroupDocs