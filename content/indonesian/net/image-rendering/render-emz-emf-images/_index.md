---
title: Render Gambar EMZ dan EMF
linktitle: Render Gambar EMZ dan EMF
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender gambar EMZ dan EMF ke berbagai format menggunakan GroupDocs.Viewer untuk .NET. Tutorial yang mudah diikuti untuk pengembang.
type: docs
weight: 14
url: /id/net/image-rendering/render-emz-emf-images/
---
## Perkenalan

GroupDocs.Viewer untuk .NET adalah API rendering dokumen canggih yang memungkinkan pengembang menampilkan berbagai jenis dokumen, termasuk gambar EMZ (Enhanced Windows Metafile) dan EMF (Enhanced Metafile), dalam aplikasi .NET mereka. Dalam tutorial ini, kita akan mempelajari cara merender gambar EMZ dan EMF ke berbagai format seperti HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1.  GroupDocs.Viewer untuk .NET: Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang kompatibel untuk pengembangan .NET.
3. Contoh Gambar EMZ/EMF: Sediakan contoh gambar EMZ dan EMF untuk dirender.

## Impor Namespace

Sebelum mendalami kodenya, mari impor namespace yang diperlukan:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah:

## Merender Gambar EMZ/EMF ke HTML

### Langkah 1: Tetapkan Direktori Output:
```csharp
string outputDirectory = "Your Document Directory";
```
 Mengganti`"Your Document Directory"`dengan jalur tempat Anda ingin menyimpan file HTML yang dirender.

### Langkah 2: Tentukan Format Jalur File Halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Ini akan menentukan format jalur file untuk file HTML yang dirender.

### Langkah 3: Render ke HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Kode ini menginisialisasi`Viewer` objek dengan contoh gambar EMZ dan merendernya ke format HTML menggunakan opsi yang ditentukan.

## Merender Gambar EMZ/EMF ke JPG, PNG, dan PDF

Ulangi langkah berikut untuk merender ke format JPG, PNG, dan PDF:

### Langkah 1: Tentukan Format Jalur File Halaman:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Sesuaikan nama file dan ekstensinya sesuai dengan format output yang diinginkan (`jpg`, `png` , atau`pdf`).

### Langkah 2: Render ke Format Masing-Masing:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Sesuaikan opsi sesuai dengan format output (Jpg, PNG, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Mengganti`JpgViewOptions` dengan`PngViewOptions` atau`PdfViewOptions` berdasarkan format keluaran yang diinginkan.

## Kesimpulan

Kesimpulannya, GroupDocs.Viewer untuk .NET memberikan solusi yang mulus untuk merender gambar EMZ dan EMF ke berbagai format dalam aplikasi .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, pengembang dapat dengan mudah mengintegrasikan kemampuan rendering dokumen ke dalam aplikasi mereka.

## FAQ

### T: Dapatkah GroupDocs.Viewer merender format dokumen lain selain gambar EMZ dan EMF?
J: Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk PDF, DOCX, PPTX, XLSX, dan banyak lagi.

### T: Apakah tersedia uji coba gratis untuk GroupDocs.Viewer untuk .NET?
 A: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.groupdocs.com/).

### T: Apakah GroupDocs.Viewer menawarkan dukungan untuk pengembang?
 J: Ya, GroupDocs memberikan dukungan melaluinya[forum](https://forum.groupdocs.com/c/viewer/9) tempat pengembang dapat mengajukan pertanyaan dan mencari bantuan.

### T: Bisakah saya membeli lisensi sementara GroupDocs.Viewer untuk .NET?
 J: Ya, lisensi sementara tersedia untuk dibeli[Di Sini](https://purchase.groupdocs.com/temporary-license/).

### T: Di mana saya dapat menemukan dokumentasi terperinci untuk GroupDocs.Viewer untuk .NET?
 A: Anda dapat merujuk ke dokumentasinya[Di Sini](https://reference.groupdocs.com/viewer/net/)untuk panduan komprehensif tentang penggunaan API.