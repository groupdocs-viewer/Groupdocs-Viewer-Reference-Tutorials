---
date: '2026-02-02'
description: Pelajari cara mengambil dan menyimpan lampiran dokumen secara efisien
  dalam aplikasi Java menggunakan Java file output stream dan API GroupDocs.Viewer
  yang kuat.
keywords:
- GroupDocs.Viewer Java
- retrieve document attachments Java
- save document attachments GroupDocs
title: Cara Mengambil dan Menyimpan Lampiran Dokumen Menggunakan Java File Output
  Stream dengan GroupDocs.Viewer untuk Java
type: docs
url: /id/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Cara Mengambil dan Menyimpan Lampiran Dokumen Menggunakan java file output stream dengan GroupDocs.Viewer untuk Java

## Pendahuluan

Apakah Anda ingin mengekstrak dan mengelola lampiran dokumen secara programatis dalam aplikasi Java Anda menggunakan **java file output stream**? Dengan meningkatnya manajemen dokumen digital, penting memiliki alat yang dapat memperlancar proses ini secara efisien. Perkenalkan GroupDocs.Viewer untuk Java—solusi utama Anda untuk dengan mudah mengambil dan menyimpan lampiran dokumen.

![Mengambil dan Menyimpan Lampiran Dokumen dengan GroupDocs.Viewer untuk Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

Dalam tutorial ini, kami akan menjelaskan cara memanfaatkan kekuatan GroupDocs.Viewer untuk mengambil lampiran dari dokumen dan menyimpannya ke direktori yang Anda inginkan. Dengan mengikuti langkah‑langkah ini, Anda akan memperoleh keterampilan praktis dalam mengelola data dokumen secara efektif di lingkungan Java.

## Jawaban Cepat
- **Apa yang dilakukan java file output stream?** Ia menulis aliran byte langsung ke file, memungkinkan data biner (seperti lampiran) disimpan di disk.  
- **API mana yang mengambil lampiran?** `Viewer.getAttachments()` mengembalikan daftar metadata lampiran.  
- **Bisakah saya menentukan folder output?** Ya—gunakan `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi berbayar diperlukan untuk produksi.  
- **Apakah pendekatan ini thread‑safe?** Buat instance `Viewer` terpisah per thread atau sinkronkan aksesnya.

## Apa itu java file output stream?
`java.io.FileOutputStream` adalah kelas inti Java yang menulis byte mentah ke sebuah file. Ini merupakan pilihan ideal ketika Anda perlu menyimpan konten biner seperti lampiran email, gambar, atau data non‑teks lain yang diekstrak dari dokumen.

## Mengapa menggunakan java file output stream dengan GroupDocs.Viewer?
- **Penanganan biner langsung** – Tidak perlu konversi perantara; byte lampiran ditulis persis seperti yang ada di file sumber.  
- **Kinerja** – Penulisan yang di‑stream mengurangi beban memori, terutama untuk lampiran berukuran besar.  
- **Kesederhanaan** – API terintegrasi mulus dengan I/O standar Java, sehingga kode mudah dibaca dan dipelihara.

## Prasyarat
- **Pustaka dan Dependensi yang Diperlukan**: Tambahkan pustaka GroupDocs.Viewer ke proyek Anda (lihat cuplikan Maven di bawah).  
- **Pengaturan Lingkungan**: IDE Java (IntelliJ IDEA, Eclipse, dll.) dengan JDK 8+ terpasang.  
- **Prasyarat Pengetahuan**: Familiaritas dengan Java I/O, khususnya `FileOutputStream`, serta penggunaan dasar Maven.

## Menyiapkan GroupDocs.Viewer untuk Java
Untuk memulai menggunakan API GroupDocs.Viewer dalam proyek Anda, Anda perlu menginstalnya melalui Maven. Tambahkan konfigurasi berikut ke file `pom.xml` Anda:

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

**Langkah-langkah Akuisisi Lisensi:**
- **Percobaan Gratis**: Mulai dengan percobaan gratis untuk menjelajahi fitur‑fiturnya.  
- **Lisensi Sementara**: Dapatkan lisensi sementara untuk periode evaluasi yang lebih lama.  
- **Pembelian**: Untuk penggunaan produksi, Anda memerlukan lisensi berbayar.

### Inisialisasi dan Penyiapan Dasar
Setelah GroupDocs.Viewer ditambahkan sebagai dependensi dalam proyek Anda, inisialisasikan di aplikasi Java Anda. Berikut caranya:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Penyiapan dasar ini menginisialisasi GroupDocs.Viewer dan mempersiapkannya untuk mengambil lampiran.

## Panduan Implementasi

### Mengambil Lampiran Menggunakan java file output stream
Mari kita uraikan cara mengambil lampiran menggunakan GroupDocs.Viewer. Fitur ini memungkinkan Anda mengekstrak metadata tentang setiap lampiran yang ada dalam dokumen Anda.

#### Ikhtisar
Mengambil lampiran melibatkan pemanggilan metode `getAttachments`, yang mengembalikan daftar objek `Attachment` berisi detail seperti nama file dan ukuran.

#### Langkah-langkah Implementasi
1. **Buat Instance Viewer**  
   Inisialisasikan kelas `Viewer` dengan path ke dokumen Anda:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Ambil Lampiran**  
   Gunakan metode `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Memahami Parameter dan Metode**  
   - `Viewer`: Menerima path file atau stream ke dokumen.  
   - `getAttachments()`: Mengambil daftar file yang dilampirkan, menyediakan detail seperti nama.

### Menyimpan Lampiran Dokumen ke Direktori
Sekarang Anda telah mempelajari cara mengambil lampiran, mari simpan ke direktori yang Anda inginkan menggunakan API GroupDocs.Viewer dan **java file output stream**.

#### Ikhtisar
Fitur ini melibatkan penyimpanan setiap file lampiran yang diambil ke direktori output yang telah ditentukan.

#### Langkah-langkah Implementasi
1. **Tentukan Direktori Output**  
   Siapkan path `outputDirectory` tempat file akan disimpan:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Simpan Lampiran**  
   Gunakan loop untuk menyimpan setiap lampiran dengan metode `saveAttachment`:

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Jelaskan Parameter dan Metode**  
   - `saveAttachment`: Menerima objek `Attachment` dan file output stream untuk menyimpan lampiran.  
   - `FileOutputStream`: Mengelola penulisan data ke file menggunakan semantik **java file output stream**.

### Tips Pemecahan Masalah
- **Dependensi Maven telahumen dan direktori outputis
Menggunakan GroupDocs.Viewer di Java dapat menjadi sangat berharga dalam berbagai skenario:

1. **Klien Email** – Secara otomatis mengekstrak lampiran dari arsip email untuk diproses atau diistem Manajemen Dokumen (DMS)** – Tingkatkan DMS dengan mengambil danungkinan integrasi dengan CRM, ERP, atau mesin alur kerja khusus dapat lebih mem## Pertimbangan Kinerja
Untuk mengoptimalkan kinerja saat menggunakan GroupDocs.Viewer:

- **Optimalkan Penanganan File** – Gunakan buffered stream untuk file besar dan tut (ari kebocoran memori.  

Menerapkan praktik terbaik Java akan secara signifikan meningkatkan efisiensi pipeline pemrosesan lampiran Anda.

## Kesimpulan
Anda kini telah mempelajari cara mengambil dan menyimpan lampiran dokumen menggunakan **java file output stream** dengan GroupDocs.Viewer untuk Java. API yang kuat ini menyederhanakan pengelolaan data dokumen, menjadikannya alat penting bagi pengembang yang bekerja dengan dokumen digital.

Untuk mengekspl merender mengekstrak teks. Jika Anda memiliki pertanyaan atau membutuhkan dukungan, silakan hubungi melalui sumber resmi.

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara menginstal GroupDocs.Viewer di proyek Java saya?**  
J: Tambahkan dependensi Maven yang ditunjukkan sebelumnya; URL repositori dan versi sudah cukup untuk memulai dengan cepat.

**T: Apakah GroupDocs.Viewer dapat menangani semua jenis dokumen?**  
J: Ia mendukung beragam format (PDF, DOCX error saat Anda lisensi Ya, lisensi GroupDocs.Viewer yang dengan file lampiran berukuran besar?**  
J: Menggunakan **java file output stream** dengan I/O ber‑buffer memastikan penanganan efisien untuk biner berukuran besar. Pantau penggunaan memori dan pertimbangkan streaming dalam potongan jika diperlukan.

---

**Terakhir Diperbarui:** 2026-02-02  
**Diuji Dengan:** GroupDocs.Viewer 25.2  
**Penulis:** GroupDocs