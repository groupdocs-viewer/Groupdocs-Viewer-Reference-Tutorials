---
"description": "Jelajahi GroupDocs.Viewer untuk .NET dan tampilkan area cetak dalam berbagai format dokumen dengan mudah. Coba uji coba gratis sekarang!"
"linktitle": "Render Area Cetak"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Area Cetak dengan GroupDocs.Viewer untuk .NET"
"url": "/id/net/spreadsheet-rendering-options/render-print-areas/"
"weight": 17
type: docs
---
# Render Area Cetak dengan GroupDocs.Viewer untuk .NET

## Perkenalan
Selamat datang di panduan lengkap tentang cara memanfaatkan GroupDocs.Viewer untuk .NET guna merender area cetak di dokumen Anda. Jika Anda seorang pengembang .NET yang mencari solusi tangguh untuk merender dokumen, Anda berada di tempat yang tepat. Dalam tutorial ini, kami akan memandu Anda melalui proses merender area cetak menggunakan GroupDocs.Viewer, untuk memastikan pengalaman yang lancar di aplikasi Anda.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan praktis tentang pengembangan C# dan .NET.
- GroupDocs.Viewer untuk .NET telah terinstal. Anda dapat mengunduhnya [Di Sini](https://releases.groupdocs.com/viewer/net/).
- Dokumen contoh (misalnya, "SAMPLE.XLSX") di direktori dokumen yang Anda tentukan.
## Mengimpor Ruang Nama
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
Buat format untuk jalur berkas halaman, gabungkan direktori keluaran dan tempat penampung untuk nomor halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Inisialisasi GroupDocs.Viewer
Buat instance kelas Viewer dengan jalur ke dokumen contoh Anda:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi tampilan HTML, tentukan format jalur file halaman dan aktifkan opsi untuk merender area cetak:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Langkah 5: Render Dokumen
Memanggil `View` metode untuk merender dokumen dengan opsi yang ditentukan:
```csharp
viewer.View(options);
```
## Langkah 6: Menampilkan Pesan Sukses
Cetak pesan sukses, yang menunjukkan bahwa dokumen sumber telah berhasil dirender:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menggunakan GroupDocs.Viewer for .NET untuk merender area cetak di dokumen Anda. Alat canggih ini membuka kemungkinan baru untuk merender dokumen di aplikasi .NET Anda.
## Tanya Jawab Umum
### Apakah GroupDocs.Viewer kompatibel dengan berbagai format dokumen?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, DOCX, XLSX, dan lainnya. Lihat [dokumentasi](https://tutorials.groupdocs.com/viewer/net/) untuk daftar lengkap.
### Dapatkah saya mencoba GroupDocs.Viewer sebelum melakukan pembelian?
Tentu saja! Anda dapat mencoba alat ini dengan uji coba gratis yang tersedia [Di Sini](https://releases.groupdocs.com/).
### Di mana saya dapat menemukan dukungan atau mencari bantuan untuk masalah apa pun?
Kunjungi [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk terhubung dengan masyarakat dan mendapatkan bantuan.
### Apakah ada pilihan lisensi sementara yang tersedia?
Ya, Anda bisa mendapatkan lisensi sementara [Di Sini](https://purchase.groupdocs.com/temporary-license/).
### Di mana saya dapat membeli GroupDocs.Viewer untuk .NET?
Anda dapat melakukan pembelian Anda [Di Sini](https://purchase.groupdocs.com/buy).