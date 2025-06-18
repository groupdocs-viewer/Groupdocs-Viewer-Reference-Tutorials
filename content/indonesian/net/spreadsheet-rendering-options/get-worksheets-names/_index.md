---
"description": "Jelajahi keajaiban GroupDocs.Viewer untuk .NET – integrasikan tampilan dokumen dengan lancar ke dalam aplikasi Anda. Coba uji coba gratis sekarang!"
"linktitle": "Dapatkan Nama Lembar Kerja"
"second_title": "API Penampil GroupDocs.NET"
"title": "Dapatkan Nama Lembar Kerja"
"url": "/id/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Dapatkan Nama Lembar Kerja

## Perkenalan
Selamat datang di dunia GroupDocs.Viewer yang menarik untuk .NET! Jika Anda seorang pengembang atau penggemar yang ingin menjelajahi kemampuan tampilan dokumen yang canggih dalam aplikasi .NET Anda, Anda akan dimanjakan. Dalam panduan lengkap ini, kita akan membahas seluk-beluk pengambilan nama lembar kerja menggunakan GroupDocs.Viewer. Jadi, kencangkan sabuk pengaman Anda dan mari kita mulai perjalanan yang mengasyikkan ini!
## Prasyarat
Sebelum kita menyelami keajaiban pengkodean, mari pastikan Anda telah menyiapkan semuanya:
1. Instal GroupDocs.Viewer untuk .NET: Buka [tautan unduhan](https://releases.groupdocs.com/viewer/net/) untuk mendapatkan versi terbaru GroupDocs.Viewer untuk .NET. Ikuti petunjuk penginstalan untuk mengintegrasikannya dengan lancar ke dalam lingkungan pengembangan Anda.
2. Siapkan Dokumen Anda: Pastikan Anda memiliki dokumen target, katakanlah file Excel bernama "file.xlsx," di direktori dokumen yang Anda tentukan.
## Mengimpor Ruang Nama
Setelah Anda memiliki prasyarat yang diperlukan, mari kita mulai dengan mengimpor namespace yang diperlukan. Ini memastikan aplikasi Anda mengenali dan dapat memanfaatkan fungsionalitas yang disediakan oleh GroupDocs.Viewer untuk .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Menyiapkan Direktori Dokumen
```csharp
string outputDirectory = "Your Document Directory";
```
Ganti "Direktori Dokumen Anda" dengan jalur ke direktori tempat dokumen target Anda berada.
## 2. Inisialisasi Viewer
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Pada langkah ini, kita membuat contoh kelas Viewer, yang menyediakan jalur ke berkas Excel Anda.
## 3. Mengonfigurasi Opsi Tampilan Informasi
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Di sini, kami mengonfigurasi ViewInfoOptions untuk menghasilkan tampilan HTML dan menetapkan opsi tambahan untuk rendering spreadsheet.
## 4. Mengambil Informasi Tampilan
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Manfaatkan instans Viewer untuk mengambil informasi tampilan berdasarkan opsi yang dikonfigurasi.
## 5. Menampilkan Nama Lembar Kerja
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Ulangi halaman yang diambil dan cetak nama setiap lembar kerja ke konsol.
## Kesimpulan
Selamat! Anda telah berhasil menavigasi proses pengambilan nama lembar kerja menggunakan GroupDocs.Viewer untuk .NET. Ini membuka banyak kemungkinan untuk meningkatkan fungsionalitas tampilan dokumen dalam aplikasi Anda.
## Tanya Jawab Umum
### Dapatkah saya menggunakan GroupDocs.Viewer untuk .NET dengan format dokumen lain?
Tentu saja! GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, Microsoft Office, dan banyak lagi.
### Apakah ada uji coba gratis yang tersedia?
Ya, Anda dapat menjelajahi GroupDocs.Viewer untuk .NET dengan [uji coba gratis](https://releases.groupdocs.com/).
### Di mana saya dapat menemukan dukungan tambahan?
Menuju ke [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk dukungan dan diskusi komunitas.
### Bisakah saya memperoleh lisensi sementara?
Tentu saja! Kunjungi [tautan ini](https://purchase.groupdocs.com/temporary-license/) untuk mendapatkan lisensi sementara Anda.
### Apakah ada sumber dokumentasi terperinci yang tersedia?
Tentu saja! Lihat [dokumentasi resmi](https://tutorials.groupdocs.com/viewer/net/) untuk informasi dan panduan mendalam.