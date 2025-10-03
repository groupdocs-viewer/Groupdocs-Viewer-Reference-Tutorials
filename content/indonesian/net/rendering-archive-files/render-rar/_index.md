---
"description": "Pelajari cara mengubah arsip RAR menjadi format HTML, JPG, PNG, atau PDF menggunakan GroupDocs.Viewer untuk .NET. Lihat dan bagikan konten arsip RAR dengan mudah."
"linktitle": "Render Arsip RAR"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Arsip RAR"
"url": "/id/net/rendering-archive-files/render-rar/"
"weight": 13
type: docs
---
# Render Arsip RAR

## Perkenalan
Arsip RAR merupakan format populer untuk mengompresi dan menyimpan beberapa file dan folder ke dalam satu wadah. Merender arsip RAR ke dalam berbagai format seperti HTML, JPG, PNG, atau PDF dapat menjadi hal penting untuk melihat atau membagikan konten arsip ini. Dalam tutorial ini, kita akan membahas cara merender arsip RAR menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum kita memulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Instal pustaka GroupDocs.Viewer untuk .NET dari [tautan unduhan](https://releases.groupdocs.com/viewer/net/).
2. Contoh Arsip RAR: Siapkan contoh arsip RAR yang siap dirender.

## Mengimpor Ruang Nama
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Render ke HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Langkah 3: Render ke JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Langkah 4: Render ke PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## Langkah 5: Render ke PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Kesimpulan
Mengubah arsip RAR ke berbagai format menjadi mudah dengan GroupDocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengubah arsip RAR ke format HTML, JPG, PNG, atau PDF, sehingga memudahkan untuk melihat dan berbagi kontennya.
## Pertanyaan yang Sering Diajukan
### Bisakah GroupDocs.Viewer untuk .NET menangani arsip RAR yang terenkripsi?
Ya, GroupDocs.Viewer untuk .NET mendukung penyajian arsip RAR terenkripsi asalkan kata sandi yang diperlukan diberikan selama proses penyajian.
### Dapatkah saya menyesuaikan tampilan keluaran dari dokumen yang dirender?
Tentu saja! GroupDocs.Viewer untuk .NET menawarkan opsi penyesuaian yang luas yang memungkinkan pengguna untuk menyesuaikan tampilan dokumen yang ditampilkan sesuai dengan tutorial mereka.
### Apakah GroupDocs.Viewer untuk .NET mendukung rendering format arsip lain selain RAR?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering berbagai format arsip termasuk ZIP, TAR, 7z, dan banyak lagi.
### Dapatkah saya mengintegrasikan GroupDocs.Viewer untuk .NET ke dalam aplikasi web saya?
Tentu saja! GroupDocs.Viewer untuk .NET menyediakan API yang cocok untuk diintegrasikan ke dalam aplikasi desktop dan web.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat memanfaatkan uji coba gratis GroupDocs.Viewer untuk .NET dari [situs web](https://releases.groupdocs.com/).