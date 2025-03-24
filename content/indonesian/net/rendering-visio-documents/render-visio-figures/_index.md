---
title: Render Gambar Visio
linktitle: Render Gambar Visio
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender gambar Visio menggunakan GroupDocs.Viewer untuk .NET dengan komprehensif ini. Tingkatkan kemampuan melihat dokumen di aplikasi .NET Anda.
weight: 10
url: /id/net/rendering-visio-documents/render-visio-figures/
---

# Render Gambar Visio

## Perkenalan
Di era digital saat ini, rendering dokumen memainkan peran penting dalam berbagai aplikasi. Baik itu menampilkan dokumen di situs web atau mengonversinya ke format lain, rendering yang efisien sangatlah penting. GroupDocs.Viewer untuk .NET memberikan solusi tangguh untuk melihat dan memanipulasi dokumen dalam aplikasi .NET. Dalam tutorial ini, kita akan mempelajari rendering gambar Visio menggunakan GroupDocs.Viewer untuk .NET, dan membagi prosesnya menjadi beberapa langkah sederhana.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Pengaturan Lingkungan: Pastikan Anda memiliki lingkungan kerja untuk pengembangan .NET.
2.  GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari[tautan unduhan](https://releases.groupdocs.com/viewer/net/).
3. Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.
4. Contoh Dokumen Visio: Siapkan contoh dokumen Visio untuk dirender.

## Impor Namespace
Di proyek C# Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Merender ke HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Direktori Output: Tentukan direktori tempat HTML yang dirender akan disimpan.
- Format Jalur File Halaman: Tentukan format jalur untuk halaman HTML.
- Inisialisasi Penampil: Inisialisasi objek Penampil dengan jalur ke dokumen Visio.
- Opsi Tampilan HTML: Konfigurasikan opsi untuk merender HTML.
- Opsi Rendering Visio: Mengatur opsi khusus untuk rendering Visio, seperti hanya merender gambar dan lebar gambar.
## 2. Merender ke JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Mirip dengan rendering ke HTML, konfigurasikan opsi untuk rendering ke format JPG.
## 3. Merender ke PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Konfigurasi untuk rendering ke format PNG mengikuti pola yang sama seperti rendering JPG.
## 4. Merender ke PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Untuk merender ke PDF, konfigurasikan opsi khusus untuk format PDF.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara merender gambar Visio menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah mengintegrasikan kemampuan rendering dokumen ke dalam aplikasi .NET Anda, sehingga meningkatkan pengalaman pengguna dan produktivitas.
## FAQ
### Bisakah saya menyesuaikan opsi rendering untuk gambar Visio?
Ya, GroupDocs.Viewer untuk .NET menyediakan opsi ekstensif untuk menyesuaikan rendering, termasuk lebar gambar, hanya merender gambar, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET cocok untuk rendering dokumen skala besar?
Tentu saja, GroupDocs.Viewer untuk .NET dioptimalkan untuk menangani rendering dokumen skala besar secara efisien.
### Apakah GroupDocs.Viewer mendukung format dokumen lain selain Visio?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, Microsoft Office, AutoCAD, dan banyak lagi.
### Bisakah saya mengintegrasikan GroupDocs.Viewer ke dalam aplikasi web?
Ya, GroupDocs.Viewer dapat diintegrasikan dengan mulus ke dalam aplikasi web untuk melihat dan memanipulasi dokumen.
### Apakah ada versi uji coba yang tersedia untuk pengujian sebelum membeli?
Ya, Anda dapat memanfaatkan uji coba gratis dari[situs web](https://releases.groupdocs.com/) untuk menguji kemampuan GroupDocs.Viewer untuk .NET.