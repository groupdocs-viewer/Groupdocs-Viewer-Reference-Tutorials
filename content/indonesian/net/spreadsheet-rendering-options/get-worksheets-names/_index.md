---
title: Dapatkan Nama Lembar Kerja
linktitle: Dapatkan Nama Lembar Kerja
second_title: GroupDocs.Viewer .NET API
description: Jelajahi keajaiban GroupDocs.Viewer untuk .NET – integrasikan tampilan dokumen dengan mulus ke dalam aplikasi Anda. Coba uji coba gratis sekarang!
weight: 11
url: /id/net/spreadsheet-rendering-options/get-worksheets-names/
---

# Dapatkan Nama Lembar Kerja

## Perkenalan
Selamat datang di dunia GroupDocs.Viewer untuk .NET yang menakjubkan! Jika Anda seorang pengembang atau penggila yang ingin menjelajahi kemampuan melihat dokumen yang canggih dalam aplikasi .NET, Anda siap menikmatinya. Dalam panduan komprehensif ini, kita akan mempelajari seluk-beluk mengambil nama lembar kerja menggunakan GroupDocs.Viewer. Jadi, kencangkan sabuk pengaman Anda dan mari memulai perjalanan mengasyikkan ini!
## Prasyarat
Sebelum kita mendalami keajaiban coding, pastikan Anda sudah menyiapkan semuanya:
1.  Instal GroupDocs.Viewer untuk .NET: Buka[tautan unduhan](https://releases.groupdocs.com/viewer/net/)untuk mengambil versi terbaru GroupDocs.Viewer untuk .NET. Ikuti petunjuk instalasi untuk mengintegrasikannya dengan lancar ke dalam lingkungan pengembangan Anda.
2. Siapkan Dokumen Anda: Pastikan Anda memiliki dokumen target, misalnya file Excel bernama "file.xlsx," di direktori dokumen yang Anda tentukan.
## Impor Namespace
Sekarang setelah Anda memiliki prasyaratnya, mari kita mulai dengan mengimpor namespace yang diperlukan. Hal ini memastikan aplikasi Anda mengenali dan dapat memanfaatkan fungsi yang disediakan oleh GroupDocs.Viewer untuk .NET.
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
## 2. Menginisialisasi Penampil
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
Pada langkah ini, kami membuat instance kelas Viewer, yang menyediakan jalur ke file Excel Anda.
## 3. Mengonfigurasi Opsi Tampilan Informasi
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Di sini, kami mengonfigurasi ViewInfoOptions untuk menghasilkan tampilan HTML dan menetapkan opsi tambahan untuk rendering spreadsheet.
## 4. Mengambil Lihat Informasi
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Manfaatkan instance Viewer untuk mengambil informasi tampilan berdasarkan opsi yang dikonfigurasi.
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
Selamat! Anda telah berhasil menavigasi proses pengambilan nama lembar kerja menggunakan GroupDocs.Viewer untuk .NET. Ini membuka segudang kemungkinan untuk meningkatkan fungsi tampilan dokumen dalam aplikasi Anda.
## FAQ
### Bisakah saya menggunakan GroupDocs.Viewer untuk .NET dengan format dokumen lain?
Sangat! GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, Microsoft Office, dan banyak lagi.
### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat menjelajahi GroupDocs.Viewer untuk .NET dengan kami[uji coba gratis](https://releases.groupdocs.com/).
### Di mana saya bisa mendapatkan dukungan tambahan?
 Pergilah ke[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) untuk dukungan dan diskusi komunitas.
### Bisakah saya mendapatkan lisensi sementara?
 Tentu! Mengunjungi[Link ini](https://purchase.groupdocs.com/temporary-license/) untuk mendapatkan lisensi sementara Anda.
### Apakah tersedia sumber dokumentasi terperinci?
 Sangat! Lihat[dokumentasi resmi](https://tutorials.groupdocs.com/viewer/net/) untuk informasi dan panduan mendalam.