---
title: Render Area Cetak dengan GroupDocs.Viewer untuk .NET
linktitle: Render Area Cetak
second_title: GroupDocs.Viewer .NET API
description: Jelajahi GroupDocs.Viewer untuk .NET dan render area pencetakan dengan mudah dalam berbagai format dokumen. Coba uji coba gratis sekarang! #GroupDocs.Viewer
weight: 17
url: /id/net/spreadsheet-rendering-options/render-print-areas/
---
## Perkenalan
Selamat datang di panduan komprehensif tentang memanfaatkan GroupDocs.Viewer untuk .NET untuk merender area cetak di dokumen Anda. Jika Anda seorang pengembang .NET yang mencari solusi tangguh untuk rendering dokumen, Anda berada di tempat yang tepat. Dalam tutorial ini, kami akan memandu Anda melalui proses rendering area cetak menggunakan GroupDocs.Viewer, memastikan pengalaman yang lancar dalam aplikasi Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan tentang pengembangan C# dan .NET.
-  GroupDocs.Viewer untuk .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.groupdocs.com/viewer/net/).
- Contoh dokumen (misalnya, "SAMPLE.XLSX") di direktori dokumen yang Anda tentukan.
## Impor Namespace
Pastikan untuk mengimpor namespace yang diperlukan dalam kode C# Anda untuk implementasi yang tepat:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Siapkan Direktori Dokumen
Mulailah dengan menentukan direktori keluaran untuk halaman HTML yang dirender:
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Buat format untuk jalur file halaman, gabungkan direktori output dan placeholder untuk nomor halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Inisialisasi GroupDocs.Viewer
Buat instance kelas Viewer dengan jalur ke dokumen sampel Anda:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi tampilan HTML, tentukan format jalur file halaman dan aktifkan opsi untuk merender area pencetakan:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Langkah 5: Render Dokumen
 Panggil`View` metode untuk merender dokumen dengan opsi yang ditentukan:
```csharp
viewer.View(options);
```
## Langkah 6: Tampilkan Pesan Sukses
Cetak pesan sukses, yang menunjukkan bahwa dokumen sumber telah berhasil dirender:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara memanfaatkan GroupDocs.Viewer untuk .NET untuk merender area cetak di dokumen Anda. Alat canggih ini membuka kemungkinan baru untuk rendering dokumen di aplikasi .NET Anda.
## FAQ
### Apakah GroupDocs.Viewer kompatibel dengan berbagai format dokumen?
 Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, DOCX, XLSX, dan banyak lagi. Mengacu kepada[dokumentasi](https://tutorials.groupdocs.com/viewer/net/) untuk daftar lengkap.
### Bisakah saya mencoba GroupDocs.Viewer sebelum melakukan pembelian?
 Sangat! Anda dapat menjelajahi alat ini dengan uji coba gratis yang tersedia[Di Sini](https://releases.groupdocs.com/).
### Di mana saya dapat memperoleh dukungan atau mencari bantuan untuk masalah apa pun?
 Mengunjungi[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)untuk berhubungan dengan masyarakat dan mendapatkan bantuan.
### Apakah ada opsi lisensi sementara yang tersedia?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.groupdocs.com/temporary-license/).
### Di mana saya dapat membeli GroupDocs.Viewer untuk .NET?
 Anda dapat melakukan pembelian[Di Sini](https://purchase.groupdocs.com/buy).