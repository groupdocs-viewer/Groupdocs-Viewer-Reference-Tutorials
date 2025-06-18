---
"description": "Pelajari cara merender gambar EMZ dan EMF ke berbagai format menggunakan GroupDocs.Viewer untuk .NET. Tutorial yang mudah diikuti bagi para pengembang."
"linktitle": "Render Gambar EMZ dan EMF"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Gambar EMZ dan EMF"
"url": "/id/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# Render Gambar EMZ dan EMF

## Perkenalan

GroupDocs.Viewer untuk .NET adalah API rendering dokumen canggih yang memungkinkan pengembang untuk menampilkan berbagai jenis dokumen, termasuk gambar EMZ (Enhanced Windows Metafile) dan EMF (Enhanced Metafile), dalam aplikasi .NET mereka. Dalam tutorial ini, kita akan membahas cara merender gambar EMZ dan EMF ke berbagai format seperti HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET.

![Render Gambar EMZ dan EMF dengan GroupDocs.Viewer untuk .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. GroupDocs.Viewer untuk .NET: Anda dapat mengunduh pustaka dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang kompatibel untuk pengembangan .NET.
3. Contoh Gambar EMZ/EMF: Sediakan contoh gambar EMZ dan EMF untuk dirender.

## Mengimpor Ruang Nama

Sebelum menyelami kodenya, mari impor namespace yang diperlukan:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Sekarang, mari kita uraikan setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah:

## Merender Gambar EMZ/EMF ke HTML

### Langkah 1: Tetapkan Direktori Output:
```csharp
string outputDirectory = "Your Document Directory";
```
Mengganti `"Your Document Directory"` dengan jalur tempat Anda ingin menyimpan berkas HTML yang telah dirender.

### Langkah 2: Tentukan Format Jalur File Halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Ini akan menentukan format jalur berkas untuk berkas HTML yang dirender.

### Langkah 3: Render ke HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Kode ini menginisialisasi `Viewer` objek dengan contoh gambar EMZ dan merendernya ke format HTML menggunakan opsi yang ditentukan.

## Merender Gambar EMZ/EMF ke JPG, PNG, dan PDF

Ulangi langkah-langkah berikut untuk merender ke format JPG, PNG, dan PDF:

### Langkah 1: Tentukan Format Jalur File Halaman:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Sesuaikan nama file dan ekstensi sesuai dengan format keluaran yang diinginkan (`jpg`Bahasa Indonesia: `png`, atau `pdf`).

### Langkah 2: Render ke Format Masing-masing:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Sesuaikan opsi sesuai dengan format keluaran (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Mengganti `JpgViewOptions` dengan `PngViewOptions` atau `PdfViewOptions` berdasarkan format keluaran yang diinginkan.

## Kesimpulan

Sebagai kesimpulan, GroupDocs.Viewer untuk .NET menyediakan solusi yang lancar untuk merender gambar EMZ dan EMF ke berbagai format dalam aplikasi .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, pengembang dapat dengan mudah mengintegrasikan kemampuan merender dokumen ke dalam aplikasi mereka.

## Pertanyaan yang Sering Diajukan

### T: Bisakah GroupDocs.Viewer menyajikan format dokumen lain selain gambar EMZ dan EMF?
A: Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk PDF, DOCX, PPTX, XLSX, dan banyak lagi.

### T: Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?
A: Ya, Anda dapat mengakses uji coba gratis [Di Sini](https://releases.groupdocs.com/).

### T: Apakah GroupDocs.Viewer menawarkan dukungan untuk pengembang?
A: Ya, GroupDocs menyediakan dukungan melalui [forum](https://forum.groupdocs.com/c/viewer/9) tempat pengembang dapat mengajukan pertanyaan dan mencari bantuan.

### T: Dapatkah saya membeli lisensi sementara untuk GroupDocs.Viewer untuk .NET?
A: Ya, lisensi sementara tersedia untuk dibeli [Di Sini](https://purchase.groupdocs.com/temporary-license/).

### T: Di mana saya dapat menemukan dokumentasi terperinci untuk GroupDocs.Viewer for .NET?
A: Anda dapat merujuk ke dokumentasi [Di Sini](https://tutorials.groupdocs.com/viewer/net/) untuk panduan lengkap tentang penggunaan API.