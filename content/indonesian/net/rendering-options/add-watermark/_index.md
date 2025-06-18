---
"description": "Pelajari cara menambahkan tanda air ke dokumen dengan mudah menggunakan GroupDocs.Viewer for .NET. Tingkatkan keamanan dan pencitraan merek dokumen dengan tutorial yang mudah diikuti ini."
"linktitle": "Tambahkan Tanda Air di Dokumen"
"second_title": "API Penampil GroupDocs.NET"
"title": "Tambahkan Tanda Air di Dokumen"
"url": "/id/net/rendering-options/add-watermark/"
"weight": 10
---

# Tambahkan Tanda Air di Dokumen

## Perkenalan
Di era digital saat ini, mengelola dan melihat berbagai format dokumen dengan mudah merupakan suatu keharusan bagi banyak bisnis dan individu. Untungnya, dengan alat seperti GroupDocs.Viewer untuk .NET, penanganan dokumen menjadi mudah. Pustaka .NET yang canggih ini memungkinkan pengembang untuk dengan mudah mengintegrasikan fungsionalitas tampilan dokumen ke dalam aplikasi mereka, yang memungkinkan pengguna untuk melihat dokumen tanpa memerlukan perangkat lunak asli yang membuatnya.
## Prasyarat
Sebelum mulai menggunakan GroupDocs.Viewer untuk .NET untuk menambahkan tanda air ke dokumen, pastikan Anda memiliki hal berikut:
1. Pengaturan Lingkungan: Siapkan lingkungan pengembangan dengan .NET Framework atau .NET Core yang terpasang.
2. GroupDocs.Viewer untuk .NET: Unduh dan instal pustaka GroupDocs.Viewer untuk .NET dari [halaman unduhan](https://releases.groupdocs.com/viewer/net/).
3. File Dokumen: Siapkan file dokumen yang ingin Anda kerjakan, seperti DOCX, PDF, atau lainnya.
4. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# diperlukan untuk mengimplementasikan contoh kode.

## Mengimpor Ruang Nama
Sebelum mulai menambahkan tanda air ke dokumen menggunakan GroupDocs.Viewer for .NET, pastikan untuk mengimpor namespace yang diperlukan dalam kode C# Anda. Langkah ini memungkinkan Anda mengakses kelas dan metode yang disediakan oleh pustaka dengan mudah.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang, mari kita telusuri proses penambahan tanda air ke dokumen menggunakan GroupDocs.Viewer for .NET. Ikuti langkah-langkah berikut untuk mengintegrasikan fungsionalitas tanda air ke dalam aplikasi Anda dengan lancar.
## Langkah 1: Atur Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Tentukan direktori tempat Anda ingin menyimpan file keluaran setelah menerapkan tanda air.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Atur format untuk jalur file halaman yang dirender. Dalam contoh ini, file HTML dengan nomor halaman akan dibuat.
## Langkah 3: Buat Instansiasi Objek Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kode berlanjut pada langkah berikutnya...
}
```
Buat instance kelas Viewer, dengan meneruskan path ke file dokumen sebagai parameter. Dalam contoh ini, kami menggunakan contoh file DOCX.
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Konfigurasikan opsi tampilan HTML, termasuk teks tanda air yang ingin Anda tambahkan ke dokumen.
## Langkah 5: Lihat Dokumen dengan Tanda Air
```csharp
viewer.View(options);
```
Panggil metode View dari objek Viewer, dengan meneruskan opsi yang dikonfigurasi. Ini akan menampilkan dokumen dengan tanda air yang ditentukan.
## Langkah 6: Menampilkan Jalur Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Beritahukan pengguna tentang keberhasilan pemrosesan dokumen dan tunjukkan direktori tempat file keluaran disimpan.

## Kesimpulan
GroupDocs.Viewer untuk .NET menyediakan cara mudah untuk menambahkan tanda air ke dokumen secara terprogram. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengintegrasikan fungsionalitas tanda air ke dalam aplikasi .NET Anda dengan lancar, meningkatkan keamanan dan pencitraan merek dokumen.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menyesuaikan tampilan tanda air?
Ya, Anda dapat menyesuaikan berbagai properti tanda air, seperti teks, font, warna, ukuran, dan posisi.
### Apakah GroupDocs.Viewer mendukung tampilan dokumen dari sumber jarak jauh?
Ya, GroupDocs.Viewer mendukung tampilan dokumen dari penyimpanan lokal maupun URL jarak jauh.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengunduh versi uji coba gratis dari [Di Sini](https://releases.groupdocs.com/).
### Bisakah saya menambahkan tanda air ke beberapa halaman dokumen?
Tentu saja, GroupDocs.Viewer memungkinkan penambahan tanda air ke halaman individual atau semua halaman dokumen.
### Bagaimana saya bisa mendapatkan dukungan atau bantuan jika saya menghadapi masalah?
Anda dapat mencari bantuan dan dukungan dari forum komunitas GroupDocs [Di Sini](https://forum.groupdocs.com/c/viewer/9).