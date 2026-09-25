---
date: '2026-09-25'
description: Pelajari cara membuat tampilan html mpp dengan GroupDocs Viewer untuk
  Java, menampilkan dokumen proyek berdasarkan interval waktu dengan kode langkah
  demi langkah.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Buat tampilan html mpp dengan GroupDocs Viewer untuk Java untuk menampilkan
  file Microsoft Project berdasarkan interval waktu tertentu. Ikuti pengaturan langkah
  demi langkah, lisensi, dan potongan kode untuk visualisasi timeline yang akurat.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Buat tampilan html mpp dengan GroupDocs Viewer untuk Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Buat tampilan html mpp dengan GroupDocs Viewer (Java)
type: docs
url: /id/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cara menggunakan GroupDocs Viewer untuk merender dokumen proyek berdasarkan interval waktu di Java

Dalam tutorial ini Anda akan belajar cara **create html view mpp** dengan GroupDocs Viewer untuk Java, memungkinkan Anda merender hanya bagian-bagian dari file Microsoft Project yang berada dalam rentang tanggal mulai dan tanggal akhir tertentu. Kami akan membahas pengaturan Maven, lisensi, dan panggilan API yang tepat yang Anda perlukan untuk menyematkan tampilan timeline yang akurat langsung ke dalam aplikasi Anda.

![Render Dokumen Proyek berdasarkan Interval Waktu dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Untuk pratinjau, lihat [Render Dokumen Proyek berdasarkan Interval Waktu dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Jawaban Cepat
- **Apa yang dilakukan fitur ini?** Itu merender hanya bagian dari file Microsoft Project yang berada di antara tanggal mulai dan tanggal akhir.  
- **Format output apa yang digunakan?** HTML dengan sumber daya tersemat, sempurna untuk integrasi web.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya mengubah rentang tanggal saat runtime?** Ya—sesuaikan nilai `setStartDate` dan `setEndDate` dalam opsi rendering.  
- **Apakah ini didukung pada semua versi Java?** Berfungsi dengan Java 8+ selama Anda menggunakan GroupDocs.Viewer 25.2 atau yang lebih baru.

## Apa itu create html view mpp?
`create html view mpp` adalah proses mengonversi file Microsoft Project (`.mpp` atau `.mpt`) menjadi sekumpulan halaman HTML yang mewakili jadwal. GroupDocs Viewer melakukan konversi di sisi server, sehingga Anda dapat menampilkan timeline di browser apa pun tanpa menginstal Microsoft Project.

## Mengapa merender dokumen proyek dengan interval waktu?
Merender hanya interval waktu yang diperlukan mengurangi ukuran HTML yang dihasilkan, mempercepat pemuatan halaman, dan memungkinkan Anda fokus pada fase proyek spesifik yang perlu dianalisis. Tampilan terarah ini ideal untuk dasbor, laporan status, atau penyematan ke dalam alat PM khusus di mana data seluruh proyek akan terlalu banyak.

## Prasyarat

- **GroupDocs.Viewer for Java** versi 25.2 atau lebih tinggi.  
- Java Development Kit (JDK) 8 atau lebih baru.  
- IDE seperti IntelliJ IDEA atau Eclipse.  
- Pengetahuan dasar tentang Maven.  

## Menyiapkan GroupDocs.Viewer untuk Java

### Dependensi Maven

Add the repository and dependency to your `pom.xml`:

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

### Langkah-langkah memperoleh lisensi

1. **Free trial** – Unduh versi percobaan dari [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary license** – Dapatkan lisensi sementara untuk pengujian lanjutan melalui [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Untuk penggunaan produksi tanpa batas, beli lisensi di [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Inisialisasi viewer dasar

`Viewer` adalah kelas utama di GroupDocs.Viewer untuk Java yang memuat dokumen dan menyediakan kemampuan rendering.

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

## Mengambil informasi tampilan untuk file proyek

`ProjectManagementViewInfo` menyediakan metadata tentang file Microsoft Project, termasuk tanggal mulai dan akhir jadwal keseluruhan.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Mengonfigurasi opsi rendering HTML (menghasilkan HTML dari proyek)

`HtmlViewOptions` mengonfigurasi cara GroupDocs merender HTML, memungkinkan Anda mengatur rentang tanggal, menyematkan sumber daya, dan menyesuaikan tampilan.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Menjalankan proses rendering

`viewer.render` mengeksekusi konversi berdasarkan opsi yang diberikan dan menulis file HTML hasil ke folder target.

```java
viewer.view(viewOptions);
```

## Kesulitan umum & pemecahan masalah

- **Incorrect file paths** – Periksa kembali bahwa file sumber `.mpp` dan direktori output ada.  
- **Unsupported file type** – Pastikan dokumen merupakan format Project yang didukung (mis., `.mpp`, `.mpt`).  
- **License errors** – Lisensi percobaan mungkin membatasi rendering; beralih ke lisensi penuh untuk penggunaan tanpa batas.  

## Aplikasi praktis

1. **Project timeline analysis** – Tampilkan hanya fase saat ini kepada pemangku kepentingan.  
2. **Automated reporting** – Hasilkan laporan HTML berbasis waktu untuk pembaruan status mingguan.  
3. **Integration with dashboards** – Sematkan halaman yang dirender ke dalam alat BI atau portal khusus.  
4. **Archival** – Simpan snapshot ramah web dari jadwal proyek untuk referensi di masa mendatang.  

## Tips kinerja

- Gunakan opsi *embedded resources* untuk menjaga setiap halaman HTML mandiri, mengurangi permintaan HTTP.  
- Untuk proyek yang sangat besar, pertimbangkan merender dalam potongan tanggal yang lebih kecil untuk menjaga penggunaan memori tetap rendah. Merender potongan satu tahun dapat mengurangi ukuran HTML hingga 80 % dibandingkan ekspor seluruh proyek, memotong waktu muat dari beberapa detik menjadi kurang dari satu detik pada server tipikal.  
- Bersihkan file sementara setelah disajikan untuk menghindari penumpukan disk.  

## Kesimpulan

Anda kini tahu **cara menggunakan GroupDocs** Viewer untuk merender dokumen proyek dalam interval waktu tertentu dan **menghasilkan HTML dari data proyek** di Java. Kemampuan ini menyederhanakan visualisasi timeline, meningkatkan efisiensi pelaporan, dan terintegrasi mulus dengan aplikasi web modern.

### Langkah selanjutnya
- Jelajahi fitur Viewer tambahan seperti watermark, perlindungan kata sandi, atau penataan CSS khusus.  
- Gabungkan pipeline rendering ini dengan REST API untuk menyajikan tampilan timeline sesuai permintaan.  

## Pertanyaan yang sering diajukan

**Q: Format file apa yang didukung oleh GroupDocs.Viewer?**  
A: GroupDocs.Viewer mendukung lebih dari 100 format input, termasuk PDF, DOCX, XLSX, PPTX, dan file Microsoft Project, memungkinkan visualisasi dokumen universal.

**Q: Bagaimana cara memulai dengan percobaan gratis GroupDocs.Viewer?**  
A: Anda dapat mengunduh versi percobaan dari [GroupDocs Viewer Java download page](https://releases.groupdocs.com/viewer/java/).

**Q: Bisakah saya merender dokumen tanpa menyematkan sumber daya?**  
A: Ya, Anda dapat memilih opsi tampilan HTML lain yang merujuk ke sumber daya eksternal alih-alih menyematkannya.

**Q: Bagaimana jika dokumen saya terlalu besar untuk dirender?**  
A: Pertimbangkan membagi dokumen menjadi bagian‑bagian lebih kecil atau merender hanya rentang tanggal yang diperlukan, seperti yang ditunjukkan di atas.

**Q: Bagaimana cara menangani kesalahan rendering?**  
A: Verifikasi semua pengaturan konfigurasi, pastikan Anda memiliki lisensi yang valid, dan konsultasikan dokumentasi GroupDocs untuk kode kesalahan terperinci.

## Sumber daya
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporary license**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

**Terakhir Diperbarui:** 2026-09-25  
**Diuji dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Tutorial Terkait

- [Cara Merender File MS Project sebagai HTML, JPG, PNG, dan PDF dengan Catatan Menggunakan GroupDocs.Viewer untuk Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Ekspor HTML MS Project: Sesuaikan Unit Waktu via GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Groupdocs Viewer Java Rendering HTML Responsif](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)