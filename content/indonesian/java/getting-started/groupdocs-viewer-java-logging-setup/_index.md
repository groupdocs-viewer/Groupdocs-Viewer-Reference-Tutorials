---
date: '2026-04-10'
description: Pelajari cara mengkonfigurasi logging di GroupDocs.Viewer untuk Java,
  termasuk cara menambahkan logger konsol dan logger file untuk meningkatkan rendering
  dokumen.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: Cara Mengonfigurasi Logging di GroupDocs.Viewer untuk Java
type: docs
url: /id/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# Cara Mengonfigurasi Logging di GroupDocs.Viewer untuk Java

Dalam tutorial ini, Anda akan belajar **cara mengonfigurasi logging** di GroupDocs.Viewer untuk Java, yang memberikan wawasan waktu‑nyata ke dalam pipeline rendering dokumen dan membantu Anda memecahkan masalah dengan cepat.

## Jawaban Cepat
- **Apa yang diberikan logging?** Umpan balik waktu‑nyata pada operasi rendering dan detail kesalahan.  
- **Logger mana yang mencetak ke konsol?** `ConsoleLogger` (tambahkan logger konsol).  
- **Logger mana yang menulis ke file?** `FileLogger` (tambahkan logger file).  
- **Apakah saya memerlukan lisensi untuk mengaktifkan logging?** Tidak, logging berfungsi dengan versi percobaan maupun berlisensi.  
- **Bisakah saya menyesuaikan format log?** Ya, dengan memperluas kelas logger.

## Pendahuluan
Tingkatkan proses rendering dokumen Anda dalam aplikasi Java menggunakan **GroupDocs.Viewer for Java**. Panduan ini memandu Anda melalui konfigurasi logging baik ke konsol maupun ke file, memberikan wawasan penting tentang cara kerja rendering dokumen Anda.

![Logging Konsol dan File dengan GroupDocs.Viewer untuk Java](/viewer/getting-started/console-and-file-logging-java.png)

**Poin Pembelajaran Utama:**
- Konfigurasikan logging di GroupDocs.Viewer untuk Java.  
- Implementasikan sistem logging berbasis konsol dan file.  
- Render dokumen ke HTML dengan sumber daya tersemat menggunakan GroupDocs.Viewer.

## Prasyarat
Pastikan Anda memiliki:
1. **Perpustakaan yang Diperlukan:**  
   - GroupDocs.Viewer untuk Java library (versi 25.2 atau lebih baru).  

2. **Persyaratan Penyiapan Lingkungan:**  
   - Java Development Kit (JDK) terpasang di sistem Anda.  
   - Integrated Development Environment (IDE) seperti IntelliJ IDEA atau Eclipse.  

3. **Prasyarat Pengetahuan:**  
   - Pemahaman dasar tentang pemrograman Java.  
   - Familiaritas dengan Maven untuk manajemen dependensi.  

Dengan prasyarat ini terpenuhi, Anda siap menyiapkan GroupDocs.Viewer untuk Java!

## Menyiapkan GroupDocs.Viewer untuk Java
Untuk menggunakan GroupDocs.Viewer, tambahkan sebagai dependensi dalam proyek Anda menggunakan Maven. Berikut caranya:

### Penyiapan Maven
Tambahkan konfigurasi berikut dalam file `pom.xml` Anda:
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
- **Uji Coba Gratis:** Unduh uji coba gratis dari [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Lisensi Sementara:** Dapatkan lisensi sementara untuk menghapus batasan evaluasi di [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Pembelian:** Untuk akses penuh, pertimbangkan membeli lisensi di [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inisialisasi Dasar
Inisialisasi GroupDocs.Viewer dengan pola berikut:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

Penyiapan ini menjadi dasar untuk konfigurasi logging yang lebih kompleks.

## Cara Mengonfigurasi Logging
Jelajahi cara **menambahkan logger konsol** dan **menambahkan logger file** dengan GroupDocs.Viewer.

### Fitur 1: Logging ke Konsol
#### Ikhtisar
Logging ke konsol memberikan umpan balik langsung di terminal Anda, berguna selama fase pengembangan atau debugging.

#### Langkah-langkah
##### Langkah 1: Impor Kelas yang Diperlukan
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Langkah 2: Siapkan Konfigurasi Logging
Gunakan `ConsoleLogger` untuk mengarahkan log ke konsol.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Penjelasan**  
- **ConsoleLogger:** Kelas ini mengarahkan log ke konsol, memberikan tampilan waktu‑nyata dari operasi.  
- **HtmlViewOptions.forEmbeddedResources:** Menghasilkan HTML dengan sumber daya tersemat untuk setiap halaman, contoh penggunaan **html view options** secara efektif.

#### Tips Pemecahan Masalah
Pastikan jalur dokumen Anda benar dan dapat diakses. Verifikasi bahwa pernyataan logging telah dikonfigurasi dengan tepat dalam pengaturan konsol Anda.

### Fitur 2: Logging ke File
#### Ikhtisar
Logging ke file membantu mempertahankan catatan operasi yang persisten, berguna untuk audit atau analisis pasca‑mortem.

#### Langkah-langkah
##### Langkah 1: Impor Kelas yang Diperlukan
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Langkah 2: Siapkan Konfigurasi Logging Berbasis File
Gunakan `FileLogger` untuk menulis log ke file yang ditentukan.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Penjelasan**  
- **FileLogger:** Kelas ini mengarahkan log ke file bernama `output.log`.  
- **ViewerSettings with FileLogger:** Mengonfigurasi GroupDocs.Viewer untuk **menangkap log viewer** dalam file log yang ditentukan.

#### Tips Pemecahan Masalah
Pastikan direktori untuk file output dapat ditulisi. Periksa izin file jika logging gagal.

## Aplikasi Praktis
GroupDocs.Viewer dapat meningkatkan kemampuan manajemen dokumen dan rendering:
1. **Portal Web:** Render dokumen secara langsung untuk pengguna web tanpa unduhan langsung.  
2. **Sistem Perusahaan:** Integrasikan dengan alat CRM untuk menampilkan kontrak atau perjanjian.  
3. **Dashboard Internal:** Menyediakan tampilan yang dapat diakses dari laporan dan presentasi dalam intranet.

## Pertimbangan Kinerja & Praktik Terbaik Logging Java
Saat menggunakan GroupDocs.Viewer di Java, perhatikan poin-poin berikut:
- **Optimalkan Penggunaan Sumber Daya:** Pantau konsumsi memori saat merender dokumen besar.  
- **Manajemen Memori Java:** Manfaatkan try‑with‑resources untuk pembersihan sumber daya otomatis.  
- **Verbosity Logging:** Sesuaikan level logger (mis., INFO, DEBUG) untuk menyeimbangkan detail dengan dampak kinerja—bagian penting dari **praktik terbaik logging java**.  

## Kesimpulan
Anda telah mempelajari **cara mengonfigurasi logging** di GroupDocs.Viewer untuk Java, baik Anda memerlukan tampilan konsol cepat atau catatan file yang persisten. Kemampuan ini sangat berharga untuk debugging, pemantauan, dan audit aplikasi Anda. Jelajahi konfigurasi lebih lanjut, bereksperimen dengan logger khusus, dan integrasikan GroupDocs.Viewer dengan sistem lain untuk meningkatkan ketahanan.

Siap meningkatkan keterampilan implementasi Anda ke tingkat berikutnya? Cobalah menyiapkan logging di berbagai lingkungan dan amati bagaimana hal itu meningkatkan keandalan aplikasi Anda!

## Sumber Daya
- [Dokumentasi](https://docs.groupdocs.com/viewer/java/)
- [Referensi API](https://reference.groupdocs.com/viewer/java/)
- [Unduhan](https://downloads.groupdocs.com/viewer/java/)

---

**Terakhir Diperbarui:** 2026-04-10  
**Diuji Dengan:** GroupDocs.Viewer 25.2 for Java  
**Penulis:** GroupDocs