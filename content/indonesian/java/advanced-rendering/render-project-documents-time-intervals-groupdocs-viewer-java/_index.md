---
date: '2026-03-29'
description: Pelajari cara membuat tampilan HTML MPP menggunakan GroupDocs Viewer
  di Java, menampilkan dokumen proyek berdasarkan interval waktu dengan kode langkah
  demi langkah.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Buat tampilan HTML MPP dengan GroupDocs Viewer (Java)
type: docs
url: /id/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cara Menggunakan GroupDocs Viewer untuk Merender Dokumen Proyek berdasarkan Interval Waktu di Java

Dalam tutorial ini Anda akan belajar cara **membuat tampilan html mpp** dengan GroupDocs Viewer untuk Java, memungkinkan Anda merender hanya bagian-bagian file Microsoft Project yang berada dalam interval waktu tertentu. Kami akan membahas pengaturan Maven, konfigurasi kode, dan skenario dunia nyata sehingga Anda dapat menyematkan tampilan garis waktu yang tepat langsung ke dalam aplikasi Anda.

![Render Dokumen Proyek berdasarkan Interval Waktu dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Jawaban Cepat
- **Apa yang dilakukan fitur ini?** Ia merender hanya bagian dari file Microsoft Project yang berada antara tanggal mulai dan tanggal akhir.  
- **Format output apa yang digunakan?** HTML dengan sumber daya tersemat, sempurna untuk integrasi web.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya mengubah rentang tanggal saat runtime?** Ya—sesuaikan nilai `setStartDate` dan `setEndDate` dalam opsi rendering.  
- **Apakah ini didukung pada semua versi Java?** Berfungsi dengan Java 8+ selama Anda menggunakan GroupDocs.Viewer 25.2 atau yang lebih baru.

## Cara membuat tampilan html mpp untuk Dokumen Proyek
GroupDocs Viewer dapat mengonversi file Microsoft Project (`.mpp`, `.mpt`) menjadi halaman HTML. Dengan mengonfigurasi tanggal mulai dan akhir dalam opsi rendering, Anda membatasi output ke potongan waktu yang Anda butuhkan, yang mengurangi ukuran file dan mempercepat pemuatan halaman.

## Apa Itu “Cara Menggunakan GroupDocs” dalam Konteks Ini?
GroupDocs Viewer adalah pustaka Java yang mengonversi lebih dari 100 format file menjadi representasi yang ramah web. Ketika Anda **cara menggunakan GroupDocs** untuk file proyek, Anda memperoleh kemampuan untuk mengekstrak, memvisualisasikan, dan membagikan data jadwal tanpa memerlukan Microsoft Project di sisi klien.

## Mengapa Merender Dokumen Proyek dengan Interval Waktu?
- **Analisis terfokus:** Tampilkan hanya fase yang Anda butuhkan (mis., Q3 2024).  
- **Kinerja:** Output HTML yang lebih kecil berarti pemuatan halaman yang lebih cepat.  
- **Integrasi:** Sematkan tampilan garis waktu ke dalam dasbor, portal pelaporan, atau alat PM khusus.  

## Prasyarat

- **GroupDocs.Viewer untuk Java** versi 25.2 atau lebih tinggi.  
- Java Development Kit (JDK) 8 atau yang lebih baru.  
- IDE seperti IntelliJ IDEA atau Eclipse.  
- Pengetahuan dasar tentang Maven.  

## Menyiapkan GroupDocs.Viewer untuk Java

### Dependensi Maven

Tambahkan repositori dan dependensi ke `pom.xml` Anda:

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

1. **Percobaan Gratis** – Unduh versi percobaan dari [halaman unduhan GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Lisensi Sementara** – Dapatkan lisensi sementara untuk pengujian lanjutan melalui [tautan ini](https://purchase.groupdocs.com/temporary-license/).  
3. **Pembelian** – Untuk penggunaan produksi tanpa batas, beli lisensi di [Halaman Pembelian GroupDocs](https://purchase.groupdocs.com/buy).

### Inisialisasi Viewer Dasar

Potongan kode berikut menunjukkan cara membuat instance `Viewer` yang menunjuk ke file Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Panduan Implementasi Langkah‑per‑Langkah

### 1. Tentukan Direktori Output

Buat folder tempat halaman HTML yang dihasilkan akan disimpan:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Mengapa?* Menjaga file yang dirender terorganisir memudahkan penyajian dari server web atau penyematan ke dalam UI.

### 2. Inisialisasi Viewer dengan File Proyek Anda

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Mengapa?* Memuat dokumen menyiapkan parser internal dan membuat metadata spesifik proyek dapat diakses.

### 3. Dapatkan Informasi Tampilan untuk File Proyek

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Mengapa?* `ProjectManagementViewInfo` memberikan tanggal mulai dan akhir jadwal, yang nantinya akan Anda gunakan untuk membatasi ruang lingkup rendering.

### 4. Konfigurasikan Opsi Rendering HTML (Hasilkan HTML dari Proyek)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Mengapa?* Menetapkan `StartDate` dan `EndDate` memberi tahu GroupDocs untuk **menghasilkan data tampilan html mpp** hanya dalam jendela waktu tersebut.

### 5. Jalankan Proses Rendering

```java
viewer.view(viewOptions);
```

*Mengapa?* Panggilan ini menghasilkan serangkaian halaman HTML mandiri yang mewakili potongan waktu yang dipilih dari jadwal proyek Anda.

## Kesalahan Umum & Pemecahan Masalah

- **Path file tidak tepat** – Periksa kembali bahwa file sumber `.mpp` dan direktori output ada.  
- **Tipe file tidak didukung** – Pastikan dokumen merupakan format Proyek yang didukung (mis., `.mpp`, `.mpt`).  
- **Kesalahan lisensi** – Lisensi percobaan mungkin memberlakukan batasan rendering; beralih ke lisensi penuh untuk penggunaan tanpa batas.  

## Aplikasi Praktis

1. **Analisis Garis Waktu Proyek** – Tampilkan hanya fase saat ini kepada pemangku kepentingan.  
2. **Pelaporan Otomatis** – Hasilkan laporan HTML berbatas waktu untuk pembaruan status mingguan.  
3. **Integrasi dengan Dasbor** – Sematkan halaman yang dirender ke dalam alat BI atau portal khusus.  
4. **Arsip** – Simpan snapshot yang ramah web dari jadwal proyek untuk referensi di masa mendatang.  

## Tips Kinerja

- Gunakan opsi *embedded resources* untuk menjaga setiap halaman HTML mandiri, mengurangi permintaan HTTP.  
- Untuk proyek yang sangat besar, pertimbangkan merender dalam potongan tanggal yang lebih kecil untuk menjaga penggunaan memori tetap rendah.  
- Bersihkan file sementara setelah disajikan untuk menghindari pembengkakan disk.  

## Kesimpulan

Anda kini tahu **cara menggunakan GroupDocs** Viewer untuk merender dokumen proyek dalam interval waktu tertentu dan **menghasilkan HTML dari data proyek** di Java. Kemampuan ini mempermudah visualisasi garis waktu, meningkatkan efisiensi pelaporan, dan terintegrasi dengan mulus ke aplikasi web modern.

### Langkah Selanjutnya
- Jelajahi fitur Viewer tambahan seperti watermark, perlindungan kata sandi, atau penataan CSS khusus.  
- Gabungkan pipeline rendering ini dengan REST API untuk menyajikan tampilan garis waktu sesuai permintaan.  

## Pertanyaan yang Sering Diajukan

**Q: Format file apa yang didukung oleh GroupDocs.Viewer?**  
A: GroupDocs.Viewer mendukung berbagai format termasuk Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, dan banyak lagi.

**Q: Bagaimana cara memulai dengan percobaan gratis GroupDocs.Viewer?**  
A: Anda dapat mengunduh versi percobaan dari [sini](https://releases.groupdocs.com/viewer/java/).

**Q: Bisakah saya merender dokumen tanpa menyematkan sumber daya?**  
A: Ya, Anda dapat memilih opsi tampilan HTML lain yang merujuk ke sumber daya eksternal alih-alih menyematkannya.

**Q: Bagaimana jika dokumen saya terlalu besar untuk dirender?**  
A: Pertimbangkan membagi dokumen menjadi bagian yang lebih kecil atau merender hanya rentang tanggal yang diperlukan, seperti yang ditunjukkan di atas.

**Q: Bagaimana cara menangani kesalahan rendering?**  
A: Verifikasi semua pengaturan konfigurasi, pastikan Anda memiliki lisensi yang valid, dan konsultasikan dokumentasi GroupDocs untuk kode kesalahan yang detail.

## Sumber Daya
- **Dokumentasi**: [Dokumentasi GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Referensi API**: [Referensi API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Unduhan**: [Unduhan GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Pembelian**: [Beli Lisensi GroupDocs](https://purchase.groupdocs.com/buy)
- **Percobaan Gratis**: [Coba Versi Gratis](https://releases.groupdocs.com/viewer/java/)
- **Lisensi Sementara**: [Dapatkan Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)
- **Dukungan**: [Forum GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs