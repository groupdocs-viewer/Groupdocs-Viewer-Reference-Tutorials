---
title: Tambahkan Tanda Air di Dokumen
linktitle: Tambahkan Tanda Air di Dokumen
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara menambahkan tanda air ke dokumen dengan lancar menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan keamanan dan pencitraan merek dokumen dengan tutorial yang mudah diikuti ini.
type: docs
weight: 10
url: /id/net/rendering-options/add-watermark/
---
## Perkenalan
Di era digital saat ini, mengelola dan melihat berbagai format dokumen dengan lancar merupakan kebutuhan bagi banyak bisnis dan individu. Untungnya, dengan alat seperti GroupDocs.Viewer untuk .NET, penanganan dokumen menjadi mudah. Pustaka .NET yang kuat ini memungkinkan pengembang dengan mudah mengintegrasikan fungsionalitas tampilan dokumen ke dalam aplikasi mereka, memungkinkan pengguna untuk melihat dokumen tanpa memerlukan perangkat lunak asli yang membuatnya.
## Prasyarat
Sebelum mulai menggunakan GroupDocs.Viewer untuk .NET guna menambahkan tanda air ke dokumen, pastikan Anda memiliki hal berikut:
1. Pengaturan Lingkungan: Siapkan lingkungan pengembangan dengan .NET Framework atau .NET Core yang terinstal.
2.  GroupDocs.Viewer untuk .NET: Unduh dan instal pustaka GroupDocs.Viewer untuk .NET dari[Unduh Halaman](https://releases.groupdocs.com/viewer/net/).
3. File Dokumen: Siapkan file dokumen yang ingin Anda kerjakan, seperti DOCX, PDF, atau lainnya.
4. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# diperlukan untuk mengimplementasikan contoh kode.

## Impor Namespace
Sebelum mulai menambahkan tanda air ke dokumen menggunakan GroupDocs.Viewer untuk .NET, pastikan untuk mengimpor namespace yang diperlukan dalam kode C# Anda. Langkah ini memungkinkan Anda mengakses kelas dan metode yang disediakan oleh perpustakaan dengan lancar.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang, mari kita telusuri proses menambahkan tanda air ke dokumen menggunakan GroupDocs.Viewer untuk .NET. Ikuti langkah-langkah berikut untuk mengintegrasikan fungsi watermarking ke dalam aplikasi Anda dengan lancar.
## Langkah 1: Tetapkan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Tentukan direktori tempat Anda ingin menyimpan file keluaran setelah menerapkan tanda air.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Atur format jalur file dari halaman yang dirender. Dalam contoh ini, file HTML dengan nomor halaman akan dibuat.
## Langkah 3: Buat Instansiasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kode berlanjut ke langkah berikutnya...
}
```
Buat instance kelas Viewer, meneruskan jalur ke file dokumen sebagai parameter. Dalam contoh ini, kami menggunakan contoh file DOCX.
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
Panggil metode View dari objek Viewer, dengan meneruskan opsi yang dikonfigurasi. Ini akan merender dokumen dengan tanda air yang ditentukan.
## Langkah 6: Tampilkan Jalur Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Beri tahu pengguna tentang keberhasilan rendering dokumen dan tunjukkan direktori tempat file keluaran disimpan.

## Kesimpulan
GroupDocs.Viewer untuk .NET menyediakan cara mudah untuk menambahkan tanda air ke dokumen secara terprogram. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan fungsi watermarking ke dalam aplikasi .NET Anda, sehingga meningkatkan keamanan dan pencitraan merek dokumen.
## FAQ
### Bisakah saya menyesuaikan tampilan tanda air?
Ya, Anda dapat menyesuaikan berbagai properti tanda air, seperti teks, font, warna, ukuran, dan posisi.
### Apakah GroupDocs.Viewer mendukung melihat dokumen dari sumber jarak jauh?
Ya, GroupDocs.Viewer mendukung melihat dokumen dari penyimpanan lokal serta URL jarak jauh.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.groupdocs.com/).
### Bisakah saya menambahkan tanda air ke beberapa halaman dokumen?
Tentu saja, GroupDocs.Viewer memungkinkan penambahan tanda air ke halaman individual atau semua halaman dokumen.
### Bagaimana saya bisa mendapatkan dukungan atau bantuan jika saya mengalami masalah?
 Anda dapat mencari bantuan dan dukungan dari forum komunitas GroupDocs[Di Sini](https://forum.groupdocs.com/c/viewer/9).