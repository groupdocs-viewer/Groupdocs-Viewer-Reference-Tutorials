---
title: Render Kolom dan Baris Tersembunyi
linktitle: Render Kolom dan Baris Tersembunyi
second_title: GroupDocs.Viewer .NET API
description: Buka kunci data tersembunyi di spreadsheet dengan mudah menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah kami untuk menampilkan kolom dan baris yang tersembunyi.
weight: 13
url: /id/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## Perkenalan
Dalam bidang visualisasi dokumen, GroupDocs.Viewer untuk .NET berdiri sebagai alat tangguh yang memfasilitasi rendering berbagai format dokumen dengan lancar. Salah satu kemampuan yang menarik adalah kemampuan untuk menampilkan kolom dan baris tersembunyi di dalam spreadsheet. Dalam tutorial ini, kami akan mempelajari langkah-langkah untuk membuka fitur ini dan mengeluarkan potensi data Anda.
## Prasyarat
Sebelum memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
- GroupDocs.Viewer untuk .NET: Pastikan Anda menginstal versi terbaru. Jika belum, Anda dapat mendownloadnya dari[situs web resmi](https://releases.groupdocs.com/viewer/net/).
- File Dokumen: Siapkan contoh dokumen dalam format spreadsheet (misalnya, SAMPLE.XLSX) untuk bereksperimen dengan kolom dan baris tersembunyi.
- Lingkungan Pengembangan: Siapkan lingkungan kerja, sebaiknya menggunakan Visual Studio atau IDE lain yang sesuai untuk pengembangan .NET.
## Impor Namespace
Dalam proyek .NET Anda, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas GroupDocs.Viewer secara efektif:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Siapkan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tentukan direktori keluaran tempat halaman HTML yang dirender akan disimpan. Sesuaikan format jalur file.
## Langkah 2: Inisialisasi Penampil dan Konfigurasikan Opsi
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Buat instance Viewer dengan memberikan jalur ke dokumen spreadsheet Anda. Konfigurasikan opsi tampilan HTML untuk menyematkan sumber daya dan mengaktifkan rendering kolom dan baris tersembunyi.
## Langkah 3: Jalankan Proses Rendering
```csharp
    viewer.View(options);
}
```
Panggil metode View pada objek penampil, dengan meneruskan opsi yang dikonfigurasi. Ini memulai proses rendering.
## Langkah 4: Periksa Outputnya
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verifikasi keberhasilan rendering dokumen sumber dan temukan hasilnya di direktori yang ditentukan.
## Kesimpulan
Membuka kunci kolom dan baris tersembunyi di spreadsheet Anda menjadi mudah dengan GroupDocs.Viewer untuk .NET. Tutorial ini telah membekali Anda dengan langkah-langkah penting untuk mengungkap data tersembunyi, memberikan tampilan dokumen Anda yang lebih komprehensif.
## Pertanyaan yang Sering Diajukan
### Bisakah saya merender kolom dan baris tersembunyi dalam format dokumen lain selain spreadsheet?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk Word, PDF, dan PowerPoint, selain spreadsheet.
### Apakah ada batasan jumlah kolom dan baris tersembunyi yang dapat dirender?
GroupDocs.Viewer secara efisien menangani rendering untuk berbagai kolom dan baris tersembunyi. Namun, kasus ekstrem dengan sejumlah besar data tersembunyi dapat memengaruhi performa.
### Bisakah saya menyesuaikan format keluaran data yang dirender?
Sangat! GroupDocs.Viewer memberikan opsi fleksibel untuk menyesuaikan keluaran, memungkinkan Anda menyesuaikan data yang diberikan dengan kebutuhan spesifik Anda.
### Apakah ada pertimbangan lisensi untuk menggunakan GroupDocs.Viewer?
 Ya, pastikan Anda memiliki lisensi yang sesuai untuk penggunaan Anda. Jelajahi opsi lisensi di[Pembelian GroupDocs](https://purchase.groupdocs.com/buy) atau memperoleh a[izin sementara](https://purchase.groupdocs.com/temporary-license/) untuk pengujian.
### Di mana saya dapat mencari bantuan atau terhubung dengan komunitas GroupDocs untuk mendapatkan dukungan?
 Mengunjungi[GroupDocs.Forum Penampil](https://forum.groupdocs.com/c/viewer/9) untuk dukungan, diskusi, dan interaksi komunitas.