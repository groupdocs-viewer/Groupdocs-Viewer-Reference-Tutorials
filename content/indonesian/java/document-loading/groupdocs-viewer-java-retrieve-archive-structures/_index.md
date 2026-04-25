---
date: '2026-02-05'
description: Pelajari cara mendapatkan viewinfo dan mengambil struktur tipe file arsip
  Java menggunakan GroupDocs.Viewer. Panduan ini mencakup pengaturan, contoh kode,
  dan kasus penggunaan dunia nyata.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Cara Mendapatkan ViewInfo dan Mengambil Struktur Arsip dalam Java
type: docs
url: /id/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Cara Mendapatkan ViewInfo dan Mengambil Struktur Arsip di Java

Mengelola file arsip secara efektif memerlukan pemahaman yang jelas tentang strukturnya. Dalam tutorial ini Anda akan mempelajari **cara mendapatkan viewinfo** untuk arsip apa pun dan melihat bagaimana hal itu membantu Anda bekerja dengan **tipe file arsip java**. Kami akan memandu Anda menyiapkan GroupDocs.Viewer, mengekstrak informasi tampilan, dan membaca hierarki folder secara rekursif sehingga Anda dapat mengintegrasikan solusi ini ke dalam proyek nyata.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Apa yang Akan Anda Pelajari**
- Menyiapkan dan mengonfigurasi GroupDocs.Viewer untuk Java.  
- Metode untuk **mendapatkan viewinfo** dari arsip.  
- Teknik untuk membaca dan menampilkan struktur folder dari file arsip.  
- Aplikasi praktis dan pertimbangan kinerja saat menggunakan GroupDocs.Viewer dalam proyek Java.

## Jawaban Cepat
- **Apa yang disediakan “viewinfo”?** Itu mengembalikan tipe file, jumlah halaman, dan daftar folder arsip.  
- **Arsip apa yang didukung?** ZIP, RAR, TAR, dan format umum lainnya.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya memproses arsip besar?** Ya – gunakan streaming dan penanganan memori yang tepat seperti yang ditunjukkan nanti.  
- **Apakah Maven diperlukan?** Maven adalah cara yang disarankan untuk mengelola dependensi GroupDocs.Viewer.

## Apa itu “cara mendapatkan viewinfo”?
`getViewInfo` adalah metode dalam API GroupDocs.Viewer yang mengekstrak metadata tentang dokumen atau arsip tanpa merender seluruh konten. Untuk arsip, metode ini mengungkapkan pohon folder internal, memungkinkan Anda memutuskan bagian mana yang akan dirender atau diproses lebih lanjut.

## Mengapa Mengambil Struktur Tipe File Arsip Java?
Memahami tata letak internal **tipe file arsip java** (misalnya, ZIP, RAR) memungkinkan Anda:
- Dengan cepat menemukan file yang dibutuhkan tanpa mengekstrak semuanya.  
- Membangun pipeline otomatis yang memproses hanya sub‑folder yang relevan.  
- Mengintegrasikan navigasi arsip ke dalam sistem manajemen konten atau ingest data.

## Prasyarat

- **Java Development Kit (JDK):** Versi 8 atau lebih baru.  
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

Bagian ini menunjukkan langkah-langkah tepat untuk memanggil `getViewInfo` dan membaca hierarki folder.

#### Inisialisasi Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Mengambil Informasi Tampilan

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Menampilkan Struktur Folder

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Membaca Folder Secara Rekursif

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

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Eksplorasi Rekursif

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Aplikasi Praktis

1. **Manajemen Data:** Dengan cepat mengatur dataset besar dengan memahami struktur arsip.  
2. **Pemrosesan File Otomatis:** Memproses batch file arsip tanpa mengekstrak sepenuhnya.  
3. **Integrasi CMS:** Meningkatkan sistem manajemen konten dengan navigasi arsip secara langsung.

## Pertimbangan Kinerja

- **Optimalkan Penggunaan Memori:** Proses folder satu tingkat pada satu waktu dan tutup instance `Viewer` dengan cepat.  
- **Tetap Terbaru:** Gunakan versi GroupDocs.Viewer terbaru dan rilis JDK untuk peningkatan kinerja.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| `NullPointerException` saat membaca folder | `viewInfo.getFolders()` mengembalikan null untuk direktori kosong | Periksa null atau daftar kosong sebelum iterasi. |
| Pemrosesan lambat pada file ZIP besar | Seluruh arsip dimuat ke dalam memori | Gunakan opsi streaming yang tersedia di versi GroupDocs yang lebih baru. |
| Lisensi tidak ditemukan | Path file lisensi tidak benar | Tempatkan file lisensi di root aplikasi atau atur `License.setLicense("path/to/license.json")`. |

## Pertanyaan yang Sering Diajukan

**Q: Apa itu GroupDocs.Viewer?**  
A: Itu adalah pustaka Java yang kuat untuk merender dokumen, termasuk arsip, ke dalam format seperti HTML, gambar, dan PDF.

**Q: Bisakah saya menggunakan GroupDocs.Viewer dengan bahasa pemrograman lain?**  
A: Ya, GroupDocs menawarkan SDK untuk berbagai platform, tetapi tutorial ini berfokus pada implementasi Java.

**Q: Bagaimana cara menangani file arsip besar?**  
A: Gunakan praktik manajemen memori yang efisien, dan pertimbangkan untuk memecah arsip jika diperlukan.

**Q: Jenis arsip apa yang didukung oleh GroupDocs.Viewer?**  
A: Itu mendukung berbagai format termasuk ZIP, RAR, TAR, dan lain-lain.

**Q: Apakah ada batas ukuran arsip yang dapat saya proses?**  
A: Batas tergantung pada sumber daya sistem Anda. Uji dengan lingkungan target Anda untuk menentukan batas praktis.

**Q: Apakah “cara mendapatkan viewinfo” bekerja dengan arsip yang dilindungi kata sandi?**  
A: Ya, Anda dapat menyediakan kata sandi melalui `ArchiveOptions.setPassword("yourPassword")` sebelum memanggil `getViewInfo`.

## Kesimpulan

Dengan mengikuti panduan ini Anda kini mengetahui **cara mendapatkan viewinfo** untuk arsip yang didukung apa pun dan cara menelusuri hierarki foldernya menggunakan GroupDocs.Viewer untuk Java. Teknik ini memungkinkan Anda membangun pipeline pemrosesan data yang lebih cerdas, meningkatkan integrasi CMS, dan menangani koleksi besar file arsip dengan percaya diri. Selanjutnya, jelajahi merender file individual dari arsip atau mengonversinya ke PDF/HTML menggunakan fitur Viewer lainnya.

---

**Terakhir Diperbarui:** 2026-02-05  
**Diuji Dengan:** GroupDocs.Viewer 25.2 for Java  
**Penulis:** GroupDocs  

**Sumber Daya**
- **Dokumentasi:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referensi API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Unduh GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Beli Lisensi:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial dan Lisensi Sementara:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)