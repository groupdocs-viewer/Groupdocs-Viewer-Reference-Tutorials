---
title: Render Lapisan dalam Gambar CAD
linktitle: Render Lapisan dalam Gambar CAD
second_title: GroupDocs.Viewer .NET API
description: Render gambar CAD dengan mulus di aplikasi .NET dengan GroupDocs.Viewer untuk .NET. Jelajahi opsi rendering, sesuaikan lapisan, dan banyak lagi.
weight: 13
url: /id/net/rendering-cad-drawings/render-layers-cad/
---

# Render Lapisan dalam Gambar CAD

## Perkenalan
GroupDocs.Viewer untuk .NET adalah alat canggih yang memungkinkan pengembang mengintegrasikan kemampuan rendering dokumen dengan lancar ke dalam aplikasi .NET mereka. Baik Anda perlu merender gambar CAD, PDF, dokumen Microsoft Office, atau lainnya, GroupDocs.Viewer menyediakan solusi komprehensif.
## Prasyarat
Sebelum mulai menggunakan GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar bahasa pemrograman C#.
- Lingkungan pengembangan .NET disiapkan di mesin Anda.
-  GroupDocs.Viewer untuk .NET diinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
-  Akses ke dokumentasi GroupDocs.Viewer untuk .NET untuk referensi, yang dapat ditemukan[Di Sini](https://tutorials.groupdocs.com/viewer/net/).

## Impor Namespace
Untuk mulai menggunakan GroupDocs.Viewer untuk .NET, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Ikuti langkah ini:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Inisialisasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Blok kode berlanjut...
}
```
## Langkah 4: Atur Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Langkah 5: Tentukan Lapisan CAD
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Langkah 6: Render Dokumen
```csharp
viewer.View(options);
```
## Langkah 7: Keluaran Lokasi Dokumen yang Dirender
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Dengan GroupDocs.Viewer untuk .NET, merender gambar CAD di aplikasi .NET Anda menjadi proses yang lancar. Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat dengan mudah mengintegrasikan kemampuan rendering dokumen ke dalam proyek Anda.
## FAQ
### Apakah GroupDocs.Viewer kompatibel dengan semua jenis gambar CAD?
Ya, GroupDocs.Viewer mendukung rendering berbagai format gambar CAD, termasuk DWG dan DXF.
### Bisakah saya menyesuaikan opsi rendering untuk gambar CAD?
Tentu saja, GroupDocs.Viewer menawarkan berbagai opsi penyesuaian, seperti menentukan lapisan yang akan dirender atau mengatur format keluaran.
### Apakah GroupDocs.Viewer memerlukan koneksi internet untuk merender dokumen?
Tidak, GroupDocs.Viewer melakukan rendering secara lokal tanpa memerlukan koneksi internet.
### Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mengakses uji coba gratis GroupDocs.Viewer untuk .NET[Di Sini](https://releases.groupdocs.com/).
### Di mana saya bisa mendapatkan dukungan untuk GroupDocs.Viewer untuk .NET?
 Untuk bantuan teknis atau pertanyaan apa pun, Anda dapat mengunjungi forum GroupDocs.Viewer[Di Sini](https://forum.groupdocs.com/c/viewer/9).