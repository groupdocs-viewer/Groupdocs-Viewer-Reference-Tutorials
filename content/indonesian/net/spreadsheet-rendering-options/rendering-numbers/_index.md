---
title: Merender Nomor
linktitle: Merender Nomor
second_title: GroupDocs.Viewer .NET API
description: Jelajahi kecanggihan Groupdocs.Viewer untuk .NET dalam merender file Numbers dengan lancar. Konversikan ke HTML, JPG, PNG, dan PDF dengan mudah.
type: docs
weight: 15
url: /id/net/spreadsheet-rendering-options/rendering-numbers/
---
## Perkenalan
Selamat datang di tutorial langkah demi langkah tentang merender file Numbers menggunakan Groupdocs.Viewer untuk .NET. Baik Anda seorang pengembang berpengalaman atau pemula, panduan ini akan memandu Anda melalui proses mengonversi dokumen Numbers ke dalam berbagai format. Groupdocs.Viewer untuk .NET adalah alat canggih yang memungkinkan Anda mengintegrasikan kemampuan melihat dokumen dengan lancar ke dalam aplikasi .NET Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan tentang pengembangan C# dan .NET.
-  Groupdocs.Viewer untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.groupdocs.com/viewer/net/).
- Jalur direktori dokumen Anda tempat file keluaran akan disimpan.
## Impor Namespace
Dalam proyek C# Anda, pastikan Anda mengimpor namespace yang diperlukan untuk menggunakan perpustakaan Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Siapkan Direktori Output
Sebelum Anda mulai merender, tentukan direktori keluaran tempat file yang dikonversi akan disimpan. Ganti "Direktori Dokumen Anda" dengan jalur sebenarnya:
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Render ke HTML Multi-Halaman
Gunakan kode berikut untuk mengonversi file Numbers menjadi HTML multi-halaman:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Langkah 3: Render ke JPG
Konversikan file Numbers ke format JPG dengan kode berikut:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Langkah 4: Render ke PNG
Ubah file Numbers menjadi format PNG menggunakan kode berikut:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Langkah 5: Render ke PDF
Terakhir, konversikan file Numbers ke format PDF menggunakan kode berikut:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Selamat! Anda telah berhasil merender file Numbers ke dalam berbagai format menggunakan Groupdocs.Viewer untuk .NET.
## Kesimpulan
Dalam tutorial ini, kita membahas dasar-dasar rendering file Numbers menggunakan Groupdocs.Viewer untuk .NET. Pustaka yang kuat ini menyediakan integrasi yang lancar untuk melihat dan mengonversi dokumen di aplikasi .NET Anda.
## FAQ
### Bisakah saya menggunakan Groupdocs.Viewer untuk .NET dengan tipe dokumen lain?
Ya, Groupdocs.Viewer mendukung berbagai format dokumen, termasuk Word, Excel, PDF, dan banyak lagi.
### Apakah lisensi sementara tersedia untuk tujuan pengujian?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.groupdocs.com/temporary-license/) untuk pengujian.
### Di mana saya dapat menemukan dukungan untuk Groupdocs.Viewer untuk .NET?
 Mengunjungi[Groupdocs.Forum Penampil](https://forum.groupdocs.com/c/viewer/9) untuk bantuan dan diskusi.
### Bagaimana cara membeli versi lengkap Groupdocs.Viewer untuk .NET?
 Anda dapat membeli versi lengkap[Di Sini](https://purchase.groupdocs.com/buy).
### Apakah ada versi uji coba gratis yang tersedia?
 Ya, Anda dapat menjelajahi versi uji coba gratis[Di Sini](https://releases.groupdocs.com/).