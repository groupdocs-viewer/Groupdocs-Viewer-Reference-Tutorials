---
title: Render Judul Baris dan Kolom
linktitle: Render Judul Baris dan Kolom
second_title: GroupDocs.Viewer .NET API
description: Tingkatkan tampilan dokumen di .NET! Pelajari cara merender judul baris dan kolom menggunakan GroupDocs.Viewer untuk .NET. Jelajahi keluaran HTML, JPG, PNG, dan PDF.
weight: 18
url: /id/net/spreadsheet-rendering-options/render-row-column-headings/
---

# Render Judul Baris dan Kolom

## Perkenalan
Apakah Anda ingin meningkatkan pengalaman melihat dokumen di aplikasi .NET? Dengan GroupDocs.Viewer untuk .NET, Anda dapat merender judul baris dan kolom dengan lancar dari file spreadsheet Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses rendering judul baris dan kolom menggunakan format output berbeda seperti HTML, JPG, PNG, dan PDF.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Menginstal GroupDocs.Viewer untuk perpustakaan .NET.
- Contoh file XLSX untuk tujuan pengujian.
- Pengetahuan tentang pengembangan C# dan .NET.
## Impor Namespace
Dalam kode C# Anda, pastikan Anda mengimpor namespace yang diperlukan untuk menggunakan GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Siapkan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. Render ke HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. Render ke JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. Render ke PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. Render ke PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## Kesimpulan
Selamat! Anda telah berhasil merender judul baris dan kolom dari spreadsheet Anda menggunakan GroupDocs.Viewer untuk .NET. Bereksperimenlah dengan berbagai format keluaran untuk memenuhi kebutuhan aplikasi Anda.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menyesuaikan direktori keluaran untuk dokumen yang dirender?
 A: Ya, Anda dapat mengatur direktori keluaran yang Anda inginkan dalam kode di mana`outputDirectory` variabel didefinisikan.
### T: Apakah GroupDocs.Viewer kompatibel dengan format spreadsheet lainnya?
J: Ya, GroupDocs.Viewer mendukung berbagai format spreadsheet, termasuk XLS, XLSX, CSV, dan banyak lagi.
### T: Bagaimana cara menangani pengecualian selama proses rendering?
J: Anda dapat menerapkan blok coba-tangkap untuk menangani pengecualian dan mencatat atau menampilkan pesan yang sesuai kepada pengguna.
### T: Apakah ada persyaratan lisensi untuk menggunakan GroupDocs.Viewer di aplikasi saya?
A: Ya, Anda memerlukan lisensi yang valid. Anda dapat memperoleh lisensi sementara untuk tujuan pengujian atau membeli lisensi penuh untuk produksi.
### T: Di mana saya bisa mendapatkan dukungan tambahan atau diskusi komunitas?
 J: Kunjungi[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) untuk dukungan dan diskusi.