---
title: Render Arsip RAR
linktitle: Render Arsip RAR
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender arsip RAR ke dalam format HTML, JPG, PNG, atau PDF menggunakan GroupDocs.Viewer untuk .NET. Lihat dan bagikan konten arsip RAR dengan mudah.
weight: 13
url: /id/net/rendering-archive-files/render-rar/
---

# Render Arsip RAR

## Perkenalan
Arsip RAR adalah format populer untuk mengompresi dan menyimpan banyak file dan folder ke dalam satu wadah. Merender arsip RAR ke dalam berbagai format seperti HTML, JPG, PNG, atau PDF penting untuk melihat atau berbagi konten arsip ini. Dalam tutorial ini, kita akan mempelajari cara merender arsip RAR menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Instal GroupDocs.Viewer untuk perpustakaan .NET dari[tautan unduhan](https://releases.groupdocs.com/viewer/net/).
2. Contoh Arsip RAR: Siapkan contoh arsip RAR untuk dirender.

## Impor Namespace
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
Merender arsip RAR ke dalam berbagai format menjadi sederhana dengan GroupDocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengonversi arsip RAR ke format HTML, JPG, PNG, atau PDF, sehingga memudahkan melihat dan berbagi kontennya.
## FAQ
### Bisakah GroupDocs.Viewer untuk .NET menangani arsip RAR terenkripsi?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering arsip RAR terenkripsi asalkan kata sandi yang diperlukan diberikan selama proses rendering.
### Apakah mungkin untuk menyesuaikan tampilan keluaran dokumen yang dirender?
Sangat! GroupDocs.Viewer untuk .NET menawarkan opsi penyesuaian ekstensif yang memungkinkan pengguna menyesuaikan tampilan dokumen yang dirender sesuai dengan preferensi mereka.
### Apakah GroupDocs.Viewer untuk .NET mendukung rendering format arsip lain selain RAR?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering berbagai format arsip termasuk ZIP, TAR, 7z, dan banyak lagi.
### Bisakah saya mengintegrasikan GroupDocs.Viewer untuk .NET ke dalam aplikasi web saya?
Tentu! GroupDocs.Viewer untuk .NET menyediakan API yang cocok untuk integrasi ke dalam aplikasi desktop dan web.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat memanfaatkan uji coba gratis GroupDocs.Viewer untuk .NET dari[situs web](https://releases.groupdocs.com/).