---
"description": "Pelajari cara merender format CAD tertentu seperti CF2 ke HTML, JPG, PNG, dan PDF menggunakan Groupdocs.Viewer untuk .NET."
"linktitle": "Format CAD Spesifik Render (CF2)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Format CAD Spesifik Render (CF2)"
"url": "/id/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Format CAD Spesifik Render (CF2)

## Perkenalan
Dalam tutorial ini, kita akan menjelajahi cara merender format CAD tertentu menggunakan Groupdocs.Viewer untuk .NET. Groupdocs.Viewer adalah API penampil dokumen canggih yang memungkinkan pengembang untuk menampilkan lebih dari 170 jenis dokumen dalam aplikasi mereka tanpa memerlukan instalasi perangkat lunak eksternal apa pun. Secara khusus, kita akan fokus pada merender format CAD seperti CF2 ke berbagai format keluaran seperti HTML, JPG, PNG, dan PDF.
## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Visual Studio terinstal di sistem Anda.
- Groupdocs.Viewer untuk .NET SDK. Anda dapat mengunduhnya dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
- Pengetahuan dasar tentang bahasa pemrograman C#.
## Mengimpor Ruang Nama
Pertama, mari impor namespace yang diperlukan untuk merender format CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Sekarang, mari kita uraikan setiap contoh menjadi beberapa langkah:
## Render CF2 ke HTML
### Langkah 1: Tentukan direktori keluaran di mana hasil HTML akan disimpan.
```csharp
string outputDirectory = "Your Document Directory";
```
### Langkah 2: Tentukan format jalur file untuk keluaran HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Langkah 3: Inisialisasi objek Viewer dan tentukan file CF2 input.
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
### Langkah 2: Inisialisasi objek Viewer dan tentukan file CF2 input.
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

### Langkah 1: Tentukan format jalur berkas untuk keluaran PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Langkah 2: Inisialisasi objek Viewer dan tentukan file CF2 input.
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
### Langkah 2: Inisialisasi objek Viewer dan tentukan file CF2 input.
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
Dalam tutorial ini, kita telah mempelajari cara merender format CAD tertentu seperti CF2 menggunakan Groupdocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah mengintegrasikan kemampuan merender dokumen ke dalam aplikasi .NET Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah Groupdocs.Viewer menyajikan format CAD lain selain CF2?
Ya, Groupdocs.Viewer mendukung berbagai format CAD, termasuk DWG, DXF, DGN, dan banyak lagi.
### Apakah Groupdocs.Viewer cocok untuk merender dokumen di aplikasi web?
Tentu saja, Groupdocs.Viewer dapat diintegrasikan secara mulus ke dalam aplikasi web untuk menampilkan dokumen langsung di browser.
### Apakah Groupdocs.Viewer memerlukan dependensi eksternal untuk rendering?
Tidak, Groupdocs.Viewer adalah API mandiri dan tidak memerlukan dependensi eksternal atau instalasi perangkat lunak apa pun.
### Bisakah saya menyesuaikan pilihan rendering sesuai dengan kebutuhan saya?
Ya, Groupdocs.Viewer menyediakan berbagai opsi rendering yang dapat disesuaikan untuk memenuhi kebutuhan spesifik Anda.
### Apakah ada versi uji coba yang tersedia untuk Groupdocs.Viewer?
Ya, Anda bisa mendapatkan versi uji coba gratis Groupdocs.Viewer dari [Di Sini](https://releases.groupdocs.com/).