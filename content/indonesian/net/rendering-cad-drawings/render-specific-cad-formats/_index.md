---
title: Render Format CAD Tertentu (CF2)
linktitle: Render Format CAD Tertentu (CF2)
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender format CAD tertentu seperti CF2 ke HTML, JPG, PNG, dan PDF menggunakan Groupdocs.Viewer untuk .NET.
weight: 12
url: /id/net/rendering-cad-drawings/render-specific-cad-formats/
---

# Render Format CAD Tertentu (CF2)

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara merender format CAD tertentu menggunakan Groupdocs.Viewer untuk .NET. Groupdocs.Viewer adalah API penampil dokumen canggih yang memungkinkan pengembang menampilkan lebih dari 170 jenis dokumen dalam aplikasi mereka tanpa memerlukan instalasi perangkat lunak eksternal apa pun. Secara khusus, kami akan fokus pada rendering format CAD seperti CF2 ke berbagai format output seperti HTML, JPG, PNG, dan PDF.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Visual Studio diinstal pada sistem Anda.
-  Groupdocs.Viewer untuk .NET SDK. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
- Pengetahuan dasar bahasa pemrograman C#.
## Impor Namespace
Pertama, mari impor namespace yang diperlukan untuk merender format CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah:
## Render CF2 ke HTML
### Langkah 1: Tentukan direktori keluaran tempat HTML yang dirender akan disimpan.
```csharp
string outputDirectory = "Your Document Directory";
```
### Langkah 2: Tentukan format jalur file untuk keluaran HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Langkah 3: Inisialisasi objek Viewer dan tentukan file input CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Tetapkan opsi rendering tambahan jika diperlukan
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 ke JPG
### Langkah 1: Tentukan format jalur file untuk keluaran JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Langkah 2: Inisialisasi objek Viewer dan tentukan file input CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Tetapkan opsi rendering tambahan jika diperlukan
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 ke PNG

### Langkah 1: Tentukan format jalur file untuk keluaran PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Langkah 2: Inisialisasi objek Viewer dan tentukan file input CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Tetapkan opsi rendering tambahan jika diperlukan
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 ke PDF
### Langkah 1: Tentukan format jalur file untuk keluaran PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Langkah 2: Inisialisasi objek Viewer dan tentukan file input CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Tetapkan opsi rendering tambahan jika diperlukan
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara merender format CAD tertentu seperti CF2 menggunakan Groupdocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah mengintegrasikan kemampuan rendering dokumen ke dalam aplikasi .NET Anda.
## FAQ
### Bisakah Groupdocs.Viewer merender format CAD lain selain CF2?
Ya, Groupdocs.Viewer mendukung berbagai format CAD, termasuk DWG, DXF, DGN, dan banyak lagi.
### Apakah Groupdocs.Viewer cocok untuk merender dokumen dalam aplikasi web?
Tentu saja, Groupdocs.Viewer dapat diintegrasikan dengan mulus ke dalam aplikasi web untuk merender dokumen langsung di browser.
### Apakah Groupdocs.Viewer memerlukan ketergantungan eksternal untuk rendering?
Tidak, Groupdocs.Viewer adalah API mandiri dan tidak memerlukan ketergantungan eksternal atau instalasi perangkat lunak apa pun.
### Bisakah saya menyesuaikan opsi rendering sesuai dengan kebutuhan saya?
Ya, Groupdocs.Viewer menyediakan berbagai opsi rendering yang dapat disesuaikan untuk memenuhi kebutuhan spesifik Anda.
### Apakah ada versi uji coba yang tersedia untuk Groupdocs.Viewer?
 Ya, Anda bisa mendapatkan Groupdocs.Viewer versi uji coba gratis dari[Di Sini](https://releases.groupdocs.com/).