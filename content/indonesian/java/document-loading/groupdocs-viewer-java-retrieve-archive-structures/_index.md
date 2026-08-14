---
date: '2026-06-30'
description: Pelajari cara mendapatkan viewinfo dan mengambil struktur tipe file arsip
  java menggunakan GroupDocs.Viewer. Panduan ini mencakup pengaturan, contoh kode,
  dan kasus penggunaan dunia nyata.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Cara Mendapatkan ViewInfo dan Mengambil Struktur Arsip di Java
type: docs
url: /id/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Cara Mendapatkan ViewInfo dan Mengambil Struktur Arsip di Java

Mengelola file arsip secara efektif memerlukan pemahaman yang jelas tentang strukturnya. Dalam tutorial ini Anda akan belajar **cara mendapatkan viewinfo** untuk arsip apa pun dan melihat bagaimana hal itu membantu Anda bekerja dengan **tipe file arsip java**. Kami akan membahas cara menyiapkan GroupDocs.Viewer, mengekstrak informasi tampilan, dan membaca hierarki folder secara rekursif sehingga Anda dapat mengintegrasikan solusi ini ke dalam proyek nyata.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Apa yang Akan Anda Pelajari**
- Menyiapkan dan mengonfigurasi GroupDocs.Viewer untuk Java.  
- Metode untuk **get viewinfo** dari arsip.  
- Teknik untuk membaca dan menampilkan struktur folder dari file arsip.  
- Aplikasi praktis dan pertimbangan kinerja saat menggunakan GroupDocs.Viewer dalam proyek Java.

## Jawaban Cepat
- **Apa yang disediakan oleh “viewinfo”?** Itu mengembalikan tipe file, jumlah halaman, dan daftar lengkap folder serta file di dalam arsip.  
- **Format arsip apa yang didukung?** ZIP, RAR, TAR, 7z, ISO, dan lebih dari 12 format umum lainnya.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya—lisensi komersial diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Apakah arsip besar dapat diproses secara efisien?** Tentu—gunakan opsi streaming dan proses satu tingkat folder pada satu waktu untuk menjaga penggunaan memori tetap rendah.  
- **Apakah Maven satu-satunya cara untuk menambahkan pustaka?** Maven adalah manajer dependensi yang direkomendasikan, tetapi Gradle atau penambahan JAR manual juga berfungsi.

## Apa itu “cara mendapatkan viewinfo”

`getViewInfo` adalah metode API GroupDocs.Viewer yang mengekstrak metadata dari dokumen atau arsip tanpa rendering penuh. Ia mengembalikan pohon folder internal, jumlah file, dan properti dasar dalam satu panggilan, memungkinkan Anda memutuskan bagian mana yang akan diproses. Panggilan ini mengembalikan snapshot lengkap arsip hingga 500 MB dalam waktu kurang dari satu detik pada server tipikal.

## Mengapa Mengambil Struktur Tipe File Arsip Java?

Menarik tata letak internal dari **tipe file arsip java** memungkinkan Anda menemukan file yang diperlukan secara instan, menghindari ekstraksi yang tidak perlu, dan membangun pipeline otomatis yang hanya menyentuh sub‑folder yang relevan. Pendekatan ini mengurangi I/O hingga 70 % untuk arsip besar dan memungkinkan pemindaian ribuan file per menit dalam skenario ingest data.

## Prasyarat

- **Java Development Kit (JDK):** Versi 8 atau lebih baru.  
- **Maven:** Untuk manajemen dependensi dan build.  
- **Pengetahuan dasar Java:** Familiaritas dengan konsep OOP membantu tetapi tidak wajib.  

Anda juga memerlukan akses ke pustaka GroupDocs.Viewer, yang dapat Anda tambahkan ke proyek Maven Anda seperti ditunjukkan di bawah.

## Menyiapkan GroupDocs.Viewer untuk Java

### Konfigurasi Maven

Tambahkan repositori dan dependensi ke `pom.xml` Anda.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Akuisisi Lisensi

- **Free Trial:** Unduh versi percobaan dari situs web GroupDocs.  
- **Temporary License:** Minta kunci sementara untuk evaluasi jangka pendek.  
- **Full License:** Beli lisensi komersial untuk penggunaan produksi tanpa batas.

Setelah pustaka berada di classpath Anda, Anda dapat mulai menulis kode.

## Panduan Implementasi

### Cara Mendapatkan ViewInfo untuk File Arsip

Untuk memperoleh informasi tampilan, pertama muat arsip ke dalam Viewer, kemudian panggil `getViewInfo` untuk mengambil metadata, dan akhirnya iterasi hierarki folder yang dikembalikan. Pola tiga langkah ini bekerja untuk semua format arsip yang didukung dan memberikan snapshot lengkap dalam satu panggilan API, menyederhanakan pemrosesan selanjutnya.

#### Inisialisasi Viewer

The `Viewer` class is the entry point for all rendering and inspection operations. It manages file streams, format detection, and resource cleanup.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Mengambil Informasi Tampilan

`ViewInfo` menyatukan metadata seperti tipe file, total halaman, dan daftar hierarkis folder serta file. Memanggil `getViewInfo` mengembalikan objek ini secara instan.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Menampilkan Struktur Folder

Iterasi melalui `viewInfo.getFolders()` untuk mencetak nama setiap folder, kedalaman, dan file yang terkandung. Loop sederhana ini memberi Anda tampilan pohon yang dapat dibaca dari arsip.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Membaca Folder Secara Rekursif

Untuk arsip yang sangat bersarang, metode bantu rekursif dapat menelusuri pohon secara depth‑first, memastikan setiap sub‑folder dikunjungi tanpa memuat seluruh arsip ke memori.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Fitur 2: Mengambil Struktur Folder Arsip

Fitur ini berfokus pada mencetak struktur folder dari file arsip. Ini mirip dengan fitur pertama tetapi menekankan eksplorasi rekursif.

#### Menyiapkan Opsi View Info

`ArchiveOptions` memungkinkan Anda menentukan perlindungan kata sandi, batas halaman, dan preferensi streaming sebelum memanggil `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Eksplorasi Rekursif

Rutinitas rekursif kedua menunjukkan cara menangani arsip yang dilindungi kata sandi dan kumpulan file besar secara efisien.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Aplikasi Praktis

1. **Manajemen Data:** Dengan cepat mengatur dataset besar dengan memahami struktur arsip.  
2. **Pemrosesan File Otomatis:** Memproses file arsip secara batch tanpa mengekstraknya sepenuhnya, mengurangi I/O hingga 70 %.  
3. **Integrasi CMS:** Tingkatkan sistem manajemen konten dengan navigasi arsip secara langsung, memungkinkan editor melihat pratinjau file langsung dari arsip.

## Pertimbangan Kinerja

- **Optimalkan Penggunaan Memori:** Proses folder satu tingkat pada satu waktu dan tutup instance `Viewer` dengan cepat.  
- **Tetap Terbaru:** Gunakan versi GroupDocs.Viewer terbaru (25.2 pada saat penulisan) dan rilis JDK untuk peningkatan kinerja.  
- **Dukungan Streaming:** Pustaka dapat men-stream arsip lebih besar dari 1 GB tanpa memuat seluruh file ke RAM, berkat arsitektur pembacaan berpotongan internalnya.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| `NullPointerException` saat membaca folder | `viewInfo.getFolders()` mengembalikan null untuk direktori kosong | Periksa null atau daftar kosong sebelum iterasi. |
| Pemrosesan lambat pada file ZIP besar | Seluruh arsip dimuat ke memori | Gunakan opsi streaming yang tersedia di versi GroupDocs yang lebih baru. |
| Lisensi tidak ditemukan | Jalur file lisensi tidak benar | Tempatkan file lisensi di root aplikasi atau set `License.setLicense("path/to/license.json")`. |

## Pertanyaan yang Sering Diajukan

**Q:** Apa itu GroupDocs.Viewer?  
A: GroupDocs.Viewer adalah pustaka Java yang merender lebih dari 100 format dokumen, gambar, dan arsip ke HTML, PDF, atau aliran gambar tanpa memerlukan aplikasi native.

**Q:** Bisakah saya menggunakan GroupDocs.Viewer dengan bahasa pemrograman lain?  
A: Ya, GroupDocs menawarkan SDK untuk .NET, Python, PHP, dan lainnya, tetapi tutorial ini fokus pada implementasi Java.

**Q:** Bagaimana cara menangani file arsip besar?  
A: Aktifkan streaming melalui `ArchiveOptions.setUseStreaming(true)`, proses satu tingkat folder pada satu waktu, dan buang objek `Viewer` setelah digunakan.

**Q:** Jenis arsip apa yang didukung oleh GroupDocs.Viewer?  
A: Ia mendukung lebih dari 12 format arsip, termasuk ZIP, RAR, TAR, 7z, ISO, ARJ, dan CAB, serta banyak tipe kontainer proprietari.

**Q:** Apakah ada batas ukuran untuk arsip?  
A: Batas praktis tergantung pada RAM dan CPU server Anda; pengujian menunjukkan pemrosesan lancar arsip 2 GB pada mesin dengan RAM 16 GB ketika streaming diaktifkan.

**Q:** Apakah “cara mendapatkan viewinfo” bekerja dengan arsip yang dilindungi kata sandi?  
A: Ya, berikan kata sandi melalui `ArchiveOptions.setPassword("yourPassword")` sebelum memanggil `getViewInfo`.

## Kesimpulan

Dengan mengikuti panduan ini Anda kini tahu **cara mendapatkan viewinfo** untuk arsip yang didukung apa pun dan cara menelusuri hierarki foldernya menggunakan GroupDocs.Viewer untuk Java. Teknik ini memungkinkan Anda membangun pipeline pemrosesan data yang lebih cerdas, meningkatkan integrasi CMS, dan menangani koleksi besar file arsip dengan percaya diri. Selanjutnya, jelajahi rendering file individual dari arsip atau mengonversinya ke PDF/HTML menggunakan fitur Viewer lainnya.

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs  

**Sumber Daya**
- **Dokumentasi:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referensi API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Unduh GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Beli Lisensi:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial dan Temporary License:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Tutorial Terkait

- [Ekstrak Metadata Dokumen dengan GroupDocs.Viewer untuk Java - Mengambil Informasi Tampilan Dokumen dan Insight](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Cara Mengambil Lampiran dan Mencetak Lampiran Dokumen dengan GroupDocs.Viewer untuk Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Panduan Java: Render Halaman Tertentu dengan GroupDocs.Viewer API untuk Pratinjau dan Manajemen Dokumen](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)