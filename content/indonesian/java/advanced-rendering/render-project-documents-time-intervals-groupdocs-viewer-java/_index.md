---
date: '2026-01-15'
description: Pelajari cara menggunakan GroupDocs Viewer untuk menghasilkan HTML dari
  dokumen proyek dalam interval waktu tertentu. Panduan ini mencakup pengaturan, kode,
  dan contoh penggunaan dunia nyata.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Cara Menggunakan GroupDocs Viewer untuk Menampilkan Dokumen Proyek Berdasarkan
  Interval Waktu di Java
type: docs
url: /id/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cara Menggunakan GroupDocs Viewer untuk Merender Dokumen Proyek berdasarkan Interval Waktu di Java

Jika Anda mencari **how to use GroupDocs** untuk merender jadwal proyek dalam jendela waktu yang terfokus, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas seluruh proses—dari penyiapan Maven hingga menghasilkan HTML dari dokumen proyek—sehingga Anda dapat menyematkan tampilan timeline yang tepat langsung ke dalam aplikasi Anda.

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Jawaban Cepat
- **Apa yang dilakukan fitur ini?** Itu merender hanya bagian dari file Microsoft Project yang berada di antara tanggal mulai dan akhir.  
- **Format output apa yang digunakan?** HTML dengan sumber daya tersemat, sempurna untuk integrasi web.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya mengubah rentang tanggal saat runtime?** Ya—sesuaikan nilai `setStartDate` dan `setEndDate` dalam opsi rendering.  
- **Apakah ini didukung pada semua versi Java?** Berfungsi dengan Java 8+ selama Anda menggunakan GroupDocs.Viewer 25.2 atau yang lebih baru.

## Apa Itu “how to use GroupDocs” dalam Konteks Ini?
GroupDocs Viewer adalah pustaka Java yang mengonversi lebih dari 100 format file menjadi representasi yang ramah web. Ketika Anda **how to use GroupDocs** untuk file proyek, Anda memperoleh kemampuan untuk mengekstrak, memvisualisasikan, dan membagikan data jadwal tanpa memerlukan Microsoft Project di sisi klien.

## Mengapa Merender Dokumen Proyek dengan Interval Waktu?
- **Analisis terfokus:** Tampilkan hanya fase yang Anda pedulikan (mis., Q3 2024).  
- **Kinerja:** Output HTML yang lebih kecil berarti pemuatan halaman lebih cepat.  
- **Integrasi:** Sematkan tampilan timeline ke dalam dasbor, portal pelaporan, atau alat PM khusus.  

## Prerequisites

- **GroupDocs.Viewer for Java** versi 25.2 atau lebih tinggi.  
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

1. **Free Trial** – Unduh versi percobaan dari [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Dapatkan lisensi sementara untuk pengujian lanjutan melalui [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Untuk penggunaan produksi tanpa batas, beli lisensi di [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

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

*Mengapa?* Menjaga file yang dirender terorganisir memudahkan penyajian dari server web atau penyematan dalam UI.

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

*Mengapa?* Menetapkan `StartDate` dan `EndDate` memberi tahu GroupDocs untuk **generate HTML from project** data hanya dalam jendela tersebut.

### 5. Jalankan Proses Rendering

```java
viewer.view(viewOptions);
```

*Mengapa?* Panggilan ini menghasilkan serangkaian halaman HTML mandiri yang mewakili potongan waktu yang dipilih dari jadwal proyek Anda.

## Kesalahan Umum & Pemecahan Masalah

- **Path file tidak tepat** – Periksa kembali bahwa file sumber `.mpp` dan direktori output ada.  
- **Tipe file tidak didukung** – Pastikan dokumen adalah format Project yang didukung (mis., `.mpp`, `.mpt`).  
- **Kesalahan lisensi** – Lisensi percobaan mungkin memberlakukan batasan rendering; beralih ke lisensi penuh untuk penggunaan tanpa batas.  

## Aplikasi Praktis

1. **Analisis Timeline Proyek** – Tampilkan hanya fase saat ini kepada pemangku kepentingan.  
2. **Pelaporan Otomatis** – Hasilkan laporan HTML berbatas waktu untuk pembaruan status mingguan.  
3. **Integrasi dengan Dasbor** – Sematkan halaman yang dirender ke dalam alat BI atau portal khusus.  
4. **Arsip** – Simpan snapshot yang ramah web dari jadwal proyek untuk referensi di masa mendatang.  

## Tips Kinerja

- Gunakan opsi *embedded resources* untuk menjaga setiap halaman HTML mandiri, mengurangi permintaan HTTP.  
- Untuk proyek yang sangat besar, pertimbangkan merender dalam potongan tanggal yang lebih kecil untuk menjaga penggunaan memori tetap rendah.  
- Bersihkan file sementara setelah disajikan untuk menghindari penumpukan disk.  

## Kesimpulan

Anda kini tahu **how to use GroupDocs** Viewer untuk merender dokumen proyek dalam interval waktu tertentu dan **generate HTML from project** data di Java. Kemampuan ini menyederhanakan visualisasi timeline, meningkatkan efisiensi pelaporan, dan terintegrasi dengan mulus ke aplikasi web modern.

### Langkah Selanjutnya
- Jelajahi fitur Viewer tambahan seperti watermarking, perlindungan password, atau styling CSS khusus.  
- Gabungkan pipeline rendering ini dengan REST API untuk menyajikan tampilan timeline sesuai permintaan.  

## Pertanyaan yang Sering Diajukan

**T: Format file apa yang didukung oleh GroupDocs.Viewer?**  
J: GroupDocs.Viewer mendukung berbagai format termasuk Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, dan banyak lagi.

**T: Bagaimana cara memulai dengan percobaan gratis GroupDocs.Viewer?**  
J: Anda dapat mengunduh versi percobaan dari [here](https://releases.groupdocs.com/viewer/java/).

**T: Bisakah saya merender dokumen tanpa menyematkan sumber daya?**  
J: Ya, Anda dapat memilih opsi tampilan HTML lain yang merujuk ke sumber daya eksternal alih-alih menyematkannya.

**T: Bagaimana jika dokumen saya terlalu besar untuk dirender?**  
J: Pertimbangkan membagi dokumen menjadi bagian yang lebih kecil atau merender hanya rentang tanggal yang diperlukan, seperti yang ditunjukkan di atas.

**T: Bagaimana cara menangani kesalahan rendering?**  
J: Verifikasi semua pengaturan konfigurasi, pastikan Anda memiliki lisensi yang valid, dan konsultasikan dokumentasi GroupDocs untuk kode kesalahan terperinci.

## Sumber Daya
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

**Last Updated:** 2026-01-15  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs