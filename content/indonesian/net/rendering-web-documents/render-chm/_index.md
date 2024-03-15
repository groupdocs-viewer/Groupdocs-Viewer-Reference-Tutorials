---
title: Render File CHM
linktitle: Render File CHM
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender file CHM di .NET menggunakan GroupDocs.Viewer. Konversikan format CHM ke HTML, JPG, PNG, dan PDF dengan mudah.
type: docs
weight: 10
url: /id/net/rendering-web-documents/render-chm/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara merender file CHM (Bantuan HTML Terkompilasi) menggunakan GroupDocs.Viewer untuk .NET. GroupDocs.Viewer untuk .NET adalah API rendering dokumen canggih yang memungkinkan pengembang menampilkan lebih dari 170 jenis dokumen dalam aplikasi .NET mereka tanpa memerlukan instalasi perangkat lunak eksternal apa pun.

## Prasyarat

Sebelum kita mendalami rendering file CHM, pastikan Anda memiliki prasyarat berikut:

### Menginstal GroupDocs.Viewer untuk .NET

 Untuk memulai, Anda perlu menginstal GroupDocs.Viewer untuk .NET. Anda dapat mengunduh perpustakaan dari[Situs web GroupDocs](https://releases.groupdocs.com/viewer/net/) atau menginstalnya melalui NuGet Package Manager dengan menjalankan perintah berikut di Package Manager Console:

```bash
Install-Package GroupDocs.Viewer
```

## Mengimpor Namespace

Pastikan untuk mengimpor namespace yang diperlukan ke dalam proyek Anda:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang mari kita bagi proses rendering menjadi beberapa langkah:

## Langkah 1: Tentukan Direktori Output

Tentukan direktori tempat Anda ingin menyimpan file yang dirender:

```csharp
string outputDirectory = "Your Document Directory";
```

## Langkah 2: Render ke HTML

Untuk merender file CHM ke HTML, gunakan cuplikan kode berikut:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Setel ke true untuk mengonversi semua konten CHM menjadi satu halaman

    viewer.View(options); //Konversi semua halaman
}
```

## Langkah 3: Render ke JPG

Untuk merender file CHM ke gambar JPG, gunakan cuplikan kode berikut:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konversi hanya halaman 1, 2, 3
}
```

## Langkah 4: Render ke PNG

Untuk merender file CHM ke gambar PNG, gunakan cuplikan kode berikut:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konversi hanya halaman 1, 2, 3
}
```

## Langkah 5: Render ke PDF

Untuk merender file CHM ke dokumen PDF, gunakan cuplikan kode berikut:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Konversi semua halaman
}
```

## Langkah 6: Periksa Keluaran

Setelah proses rendering selesai, periksa direktori keluaran yang ditentukan untuk file yang dirender:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan

Merender file CHM menggunakan GroupDocs.Viewer untuk .NET adalah proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efisien mengonversi dokumen CHM ke berbagai format seperti HTML, gambar (JPG, PNG), dan PDF dalam aplikasi .NET Anda.

## FAQ

### Q1: Bisakah GroupDocs.Viewer merender format dokumen lain selain CHM?

A1: Ya, GroupDocs.Viewer mendukung rendering lebih dari 170 format dokumen termasuk PDF, DOCX, XLSX, PPTX, dan banyak lagi.

### Q2: Apakah GroupDocs.Viewer kompatibel dengan .NET Core?

A2: Ya, GroupDocs.Viewer mendukung .NET Core selain .NET Framework tradisional.

### Q3: Dapatkah saya menyesuaikan opsi rendering untuk format output yang berbeda?

A3: Ya, GroupDocs.Viewer menyediakan berbagai opsi untuk menyesuaikan proses rendering, seperti menentukan nomor halaman, mengatur kualitas gambar, dan mengonfigurasi jalur keluaran.

### Q4: Apakah GroupDocs.Viewer memerlukan ketergantungan eksternal untuk merender dokumen?

A4: Tidak, GroupDocs.Viewer adalah perpustakaan mandiri dan tidak memerlukan ketergantungan eksternal atau instalasi perangkat lunak pihak ketiga.

### Q5: Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer?

 A5: Ya, Anda dapat memanfaatkan uji coba gratis GroupDocs.Viewer dengan mengunjungi[situs web](https://releases.groupdocs.com/).