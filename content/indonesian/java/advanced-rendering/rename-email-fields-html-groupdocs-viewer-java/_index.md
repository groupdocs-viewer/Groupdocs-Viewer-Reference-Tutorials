---
date: '2026-01-05'
description: Pelajari cara mengganti nama bidang email, mengonversi email ke HTML,
  dan menyesuaikan header email menggunakan GroupDocs.Viewer untuk Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Cara Mengubah Nama Kolom Email Saat Merender Email ke HTML dengan GroupDocs.Viewer
  Java
type: docs
url: /id/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Cara Mengganti Nama Kolom Email Saat Merender Email ke HTML dengan GroupDocs.Viewer Java

Apakah Anda bertanya-tanya **bagaimana cara mengganti nama email** saat mengonversi email ke HTML? Dalam panduan ini kami akan menjelaskan langkah‑langkah tepat untuk mengganti nama kolom email, **mengonversi email ke HTML**, dan **menyesuaikan header email** menggunakan GroupDocs.Viewer untuk Java. Pada akhir panduan Anda akan memiliki representasi HTML yang bersih dengan nama header pilihan Anda, sehingga output lebih mudah dibaca dan diintegrasikan ke dalam aplikasi Anda.

![Ganti Nama Kolom Email Saat Mengonversi Email ke HTML dengan GroupDocs.Viewer untuk Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Apa yang Akan Anda Pelajari
- Cara menggunakan GroupDocs.Viewer untuk Java untuk **mengonversi email ke HTML**.  
- Teknik untuk **mengganti nama kolom email** seperti “From,” “To,” “Sent,” dan “Subject.”  
- Praktik terbaik untuk menyiapkan Maven dan lisensi.  
- Skenario dunia nyata di mana **menyesuaikan header email** menambah nilai.

## Jawaban Cepat
- **Apa arti “bagaimana cara mengganti nama email”?** Ini merujuk pada pemetaan nama header email default ke label khusus selama proses rendering.  
- **Perpustakaan mana yang menangani konversi?** GroupDocs.Viewer untuk Java (v25.2+).  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya mengubah nama header apa pun?** Ya, setiap header email standar dapat dipetakan ulang melalui `fieldTextMap`.  
- **Apakah output berupa HTML atau sumber daya tersemat?** Anda dapat memilih sumber daya tersemat untuk satu file mandiri.

## Apa Itu “Bagaimana Cara Mengganti Nama Email” dalam Konteks GroupDocs.Viewer?
Mengganti nama kolom email berarti mengganti label default (misalnya “From”) dengan teks khusus (misalnya “Sender”) saat email dirender ke HTML. Ini berguna untuk menyelaraskan output dengan terminologi perusahaan atau meningkatkan keterbacaan bagi pengguna akhir.

## Mengapa Mengonversi Email ke HTML dan Menyesuaikan Header Email?
- **Branding konsisten:** Sesuaikan bahasa organisasi Anda di semua komunikasi.  
- **Pencarian yang lebih baik:** Header khusus dapat diindeks lebih efektif dalam sistem arsip.  
- **Integrasi UI yang lebih baik:** Sesuaikan potongan HTML agar cocok secara mulus ke portal web atau dasbor dukungan.

## Prasyarat

### Perpustakaan, Versi, dan Dependensi yang Diperlukan
- **GroupDocs.Viewer untuk Java** – versi 25.2 atau lebih baru.  
- **Java Development Kit (JDK)** – versi 8+.

### Persyaratan Penyiapan Lingkungan
- **Maven** untuk manajemen dependensi.  
- IDE seperti IntelliJ IDEA, Eclipse, atau VS Code.

### Prasyarat Pengetahuan
Pemahaman dasar tentang Java dan Maven akan membantu Anda mengikuti dengan cepat.

## Menyiapkan GroupDocs.Viewer untuk Java

### Konfigurasi Maven
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
- **Versi Percobaan Gratis:** Unduh versi percobaan gratis dari [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Lisensi Sementara:** Dapatkan lisensi sementara untuk menjelajahi semua fitur tanpa batasan di [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Pembelian:** Untuk penggunaan berkelanjutan, pertimbangkan membeli lisensi melalui [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inisialisasi dan Penyiapan Dasar
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Sesuaikan jalur file untuk mengarah ke file `.msg` Anda.

## Panduan Implementasi

### Mengganti Nama Kolom Email – Langkah‑per‑Langkah

#### 1. Siapkan Jalur Direktori Output
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Ganti `"YOUR_OUTPUT_DIRECTORY"` dengan folder tempat Anda ingin menyimpan file HTML.*

#### 2. Tentukan Format Jalur File Halaman
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` akan diganti dengan nomor halaman selama proses rendering.*

#### 3. Buat Pemetaan Kolom Email ke Nama Baru
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Di sini kami mengubah label default menjadi label khusus.*

#### 4. Konfigurasikan Opsi Tampilan HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` menggabungkan CSS/JS di dalam HTML, sementara `setFieldTextMap` menerapkan nama header khusus.*

#### 5. Render Email ke HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ganti `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` dengan jalur sebenarnya ke file MSG Anda.*

#### Tips Pemecahan Masalah
- Pastikan direktori output dapat ditulisi.  
- Pastikan file MSG input ada dan jalurnya benar.  
- Gunakan versi GroupDocs.Viewer yang sama (25.2) seperti yang dideklarasikan di Maven.

## Aplikasi Praktis
1. **Laporan Email Kustom:** Sesuaikan header email dengan terminologi perusahaan untuk laporan yang lebih jelas.  
2. **Sistem Arsip Email:** Tingkatkan kemampuan pencarian dengan menggunakan nama header yang terstandarisasi.  
3. **Platform Dukungan Pelanggan:** Tampilkan tiket dengan label header yang dipersonalisasi untuk pengalaman agen yang lebih baik.

## Pertimbangan Kinerja
- Buang objek `Viewer` dengan try‑with‑resources untuk membebaskan memori secara cepat.  
- Profilkan batch besar dan pertimbangkan memproses email dalam aliran paralel jika diperlukan.

## Kesimpulan
Anda sekarang tahu **cara mengganti nama email** saat **mengonversi email ke HTML** dan **menyesuaikan header email** dengan GroupDocs.Viewer untuk Java. Teknik ini memberi Anda kontrol penuh atas penyajian metadata email dalam output HTML.

### Langkah Selanjutnya
- Bereksperimen dengan pemetaan kolom tambahan (mis., CC, BCC).  
- Jelajahi format rendering lain seperti PDF atau PNG.  
- Kunjungi [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) untuk wawasan API yang lebih mendalam.

## Bagian FAQ
1. **Bisakah saya mengganti semua header email menggunakan metode ini?**  
   - Ya, Anda dapat memetakan header email standar apa pun ke nama baru sesuai kebutuhan Anda.  
2. **Apakah memungkinkan menggunakan GroupDocs.Viewer tanpa lisensi?**  
   - Versi percobaan tersedia untuk pengujian, tetapi versi lengkap memerlukan lisensi yang valid.  
3. **Bagaimana cara menangani volume email yang besar secara efisien dengan GroupDocs.Viewer?**  
   - Pertimbangkan pemrosesan batch dan optimalkan sumber daya sistem untuk mengelola dataset yang lebih besar secara efektif.  
4. **Bisakah saya mengintegrasikan solusi ini ke dalam aplikasi Java yang ada?**  
   - Tentu saja, integrasi mudah dilakukan menggunakan dependensi Maven.  
5. **Di mana saya dapat menemukan dukungan jika mengalami masalah?**  
   - Kunjungi [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) untuk bantuan komunitas dan resmi.

## Pertanyaan yang Sering Diajukan

**T: Apakah pendekatan ini bekerja dengan format email lain seperti EML?**  
J: Ya, GroupDocs.Viewer mendukung file MSG dan EML; logika pemetaan kolom yang sama berlaku.

**T: Bisakah saya menghasilkan HTML tanpa sumber daya tersemat?**  
J: Anda dapat menggunakan `HtmlViewOptions.forExternalResources(...)` jika lebih suka file CSS/JS terpisah.

**T: Versi GroupDocs.Viewer apa yang diuji?**  
J: Kode tersebut diuji dengan GroupDocs.Viewer **25.2**.

**T: Apakah memungkinkan mengubah font atau gaya header khusus?**  
J: Styling dapat diterapkan melalui CSS setelah rendering, atau Anda dapat menyuntikkan CSS khusus menggunakan `HtmlViewOptions.getResourcesPath()`.

**T: Bagaimana cara mendapatkan jalur file HTML yang dihasilkan secara programatik?**  
J: Jalur file mengikuti pola yang didefinisikan dalam `pageFilePathFormat`; Anda dapat membangunnya menggunakan `String.format` dengan nomor halaman.

## Sumber Daya
- **Dokumentasi:** Panduan lengkap tersedia di [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referensi API:** Informasi API detail dapat ditemukan di [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Unduh GroupDocs.Viewer:** Akses versi terbaru melalui [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Terakhir Diperbarui:** 2026-01-05  
**Diuji Dengan:** GroupDocs.Viewer 25.2  
**Penulis:** GroupDocs