---
title: Render Gambar SVG dan SVGZ
linktitle: Render Gambar SVG dan SVGZ
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender gambar SVG dan SVGZ menggunakan GroupDocs.Viewer untuk .NET. Ubah grafik vektor menjadi HTML, JPG, PNG, dan PDF dengan mudah.
weight: 16
url: /id/net/image-rendering/render-svg-svgz-images/
---

# Render Gambar SVG dan SVGZ

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses rendering gambar SVG dan SVGZ menggunakan GroupDocs.Viewer untuk .NET. GroupDocs.Viewer untuk .NET adalah API rendering dokumen canggih yang memungkinkan pengembang merender berbagai format dokumen dalam aplikasi .NET mereka. SVG dan SVGZ adalah format gambar populer yang digunakan untuk grafik vektor, dan dengan GroupDocs.Viewer untuk .NET, Anda dapat dengan mudah merendernya ke dalam format keluaran berbeda seperti HTML, JPG, PNG, dan PDF.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menginstal dan menyiapkan prasyarat berikut:
1.  GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang berfungsi untuk pengembangan .NET, seperti Visual Studio.
3. Contoh File SVGZ: Siapkan contoh file SVGZ untuk pengujian.

## Impor Namespace
Sebelum kita mendalami kodenya, mari impor namespace yang diperlukan:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Langkah 1: Render SVGZ ke HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Langkah 2: Render SVGZ ke JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Langkah 3: Render SVGZ ke PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Langkah 4: Render SVGZ ke PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara merender gambar SVG dan SVGZ menggunakan GroupDocs.Viewer untuk .NET. Hanya dengan beberapa langkah sederhana, Anda dapat mengonversi gambar SVGZ ke berbagai format keluaran seperti HTML, JPG, PNG, dan PDF, menjadikannya dapat diakses dan dilihat di lingkungan berbeda.
## FAQ
### Bisakah GroupDocs.Viewer merender format gambar lain?
Ya, GroupDocs.Viewer mendukung rendering berbagai format gambar termasuk PNG, JPEG, BMP, TIFF, GIF, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer kompatibel dengan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan opsi rendering?
Ya, GroupDocs.Viewer menyediakan opsi rendering ekstensif yang memungkinkan Anda menyesuaikan output sesuai kebutuhan Anda.
### Apakah GroupDocs.Viewer memerlukan ketergantungan pihak ketiga?
Tidak, GroupDocs.Viewer adalah API mandiri dan tidak memerlukan ketergantungan pihak ketiga untuk merender dokumen.
### Apakah ada versi uji coba yang tersedia untuk pengujian?
Ya, Anda dapat mengunduh GroupDocs.Viewer versi uji coba gratis dari[Di Sini](https://releases.groupdocs.com/) untuk mengevaluasi fitur-fiturnya sebelum melakukan pembelian.